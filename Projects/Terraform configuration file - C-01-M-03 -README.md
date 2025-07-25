# Terraform Configuration: GCP VM with Custom VPC and Flask Setup

## Project Description

This project uses **Terraform** to provision a **Google Cloud Platform (GCP)** virtual machine with a custom VPC network, subnetwork, and firewall configuration. The VM is automatically configured to install **Flask** via a startup script, making it suitable for lightweight web application development or testing.

### Key Features:
- Custom **VPC network** with no auto-created subnetworks.
- **Subnetwork** in the `us-west1` region.
- **Compute Engine instance** (Debian-based) with Flask installed on startup.
- **External IP address** and **firewall rules** to allow SSH and Flask traffic.

This setup helps streamline infrastructure-as-code practices for developers deploying basic Python web apps in GCP environments.

---

## Terraform Configuration

```hcl
# Create a custom VPC network
resource "google_compute_network" "vpc_network" {
  name                    = "my-custom-mode-network"
  auto_create_subnetworks = false
  mtu                     = 1460
}

# Create a subnetwork within the VPC
resource "google_compute_subnetwork" "default" {
  name          = "my-custom-subnet"
  ip_cidr_range = "10.0.1.0/24"
  region        = "us-west1"
  network       = google_compute_network.vpc_network.id
}

# Create a Compute Engine instance with Flask installed
resource "google_compute_instance" "default" {
  name         = "flask-vm"
  machine_type = "f1-micro"
  zone         = "us-west1-a"
  tags         = ["ssh"]

  boot_disk {
    initialize_params {
      image = "debian-cloud/debian-11"
    }
  }

  metadata_startup_script = <<-EOT
    #!/bin/bash
    apt-get update
    apt-get install -yq build-essential python3-pip rsync
    pip3 install flask
  EOT

  network_interface {
    subnetwork = google_compute_subnetwork.default.id

    access_config {
      # Gives the VM an external IP
    }
  }
}

# Firewall rule to allow SSH and Flask (port 5000)
resource "google_compute_firewall" "allow_ssh_flask" {
  name    = "allow-ssh-flask"
  network = google_compute_network.vpc_network.name

  allow {
    protocol = "tcp"
    ports    = ["22", "5000"]
  }

  source_ranges = ["0.0.0.0/0"]
  target_tags   = ["ssh"]
}
```

## Conclusion

This Terraform configuration provides a foundational setup for deploying a lightweight, Flask-ready virtual machine in Google Cloud Platform using Infrastructure as Code. By provisioning a custom VPC, controlled subnetwork, and secure firewall rules, the setup emphasizes security and scalability from the start.

Whether you're a developer testing a new Flask app or a team creating sandbox environments, this template helps automate and standardize deployment workflows in the cloud.

For production environments, consider adding:
- Auto-start Flask as a service (via `systemd`)
- Load balancers and HTTPS with SSL certificates
- State management with remote backends (e.g., Cloud Storage)
- Role-based access control (RBAC) for sensitive resources

This configuration is flexible and extensible—ready to grow with your project needs.
