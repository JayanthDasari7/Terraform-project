# Terraform AWS Infrastructure Project

This repository contains Terraform configurations to provision a highly available infrastructure on AWS. It automates the creation of a VPC, networking components, compute resources (EC2), storage (S3), and load balancing.

## 📋 Project Overview

The Terraform code in this project sets up the following resources:

* **VPC (Virtual Private Cloud)**: A custom network environment.
* **Subnets**: Network partitions across **2 Availability Zones** for high availability.
* **Route Tables**: Custom routing logic to control network traffic.
* **Security Groups**: Firewalls for the EC2 instances and the Load Balancer to control inbound/outbound traffic.
* **EC2 Instances**: Two virtual servers configured with custom user data scripts.
* **Application Load Balancer (ALB)**: Distributes incoming application traffic across the EC2 instances in multiple Availability Zones.
* **S3 Bucket**: Scalable object storage.

## 📂 File Structure

| File Name | Description |
| :--- | :--- |
| `main.tf` | The primary configuration file creating the VPC, EC2, ALB, and S3 resources. |
| `variables.tf` | Defines the input variables (e.g., CIDR blocks, Instance types, Region) for reusability. |
| `providers.tf` | Configures the Terraform provider (AWS). |
| `userdata1.sh` | Shell script to bootstrap the first EC2 instance (e.g., install web server). |
| `userdata2.sh` | Shell script to bootstrap the second EC2 instance. |

## 🚀 Getting Started

### Prerequisites

Ensure you have the following installed on your local machine:

1.  **Terraform**: [Download and Install Terraform](https://developer.hashicorp.com/terraform/downloads)
2.  **AWS CLI**: [Install AWS CLI](https://aws.amazon.com/cli/)
3.  **AWS Credentials**: Configure your AWS credentials using `aws configure` or by setting environment variables (`AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY`).

### Installation & Deployment

1.  **Clone the Repository**
    ```bash
    git clone [https://github.com/JayanthDasari7/Terraform-project.git](https://github.com/JayanthDasari7/Terraform-project.git)
    cd Terraform-project
    ```

2.  **Initialize Terraform**
    Initialize the directory to download the necessary providers.
    ```bash
    terraform init
    ```

3.  **Review the Plan**
    See what resources Terraform will create before making any changes.
    ```bash
    terraform plan
    ```

4.  **Apply the Configuration**
    Provision the resources on AWS. Type `yes` when prompted.
    ```bash
    terraform apply
    ```

### Clean Up

To destroy the infrastructure and avoid incurring costs, run:
```bash
terraform destroy
