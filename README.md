# Terraform Slurm Cloud

## Local Setup

- Install [Terraform](https://www.terraform.io/downloads.html)

## OpenStack Cloud

1. Download the latest version of this project: (master)[https://git.computecanada.ca/fafor10/slurm_cloud/repository/master/archive.tar.gz]
2. Untar: `tar xvf archive.tar.gz`
3. Go in the openstack project folder : `cd slurm_cloud/openstack`
4. Download your project openrc file from the OpenStack _Access and security_ section into the `openstack` folder.
5. Source your project openrc file : `source _project_-openrsh.sh`.
6. Initiate the Terraform state : `terraform init`.
7. Adapt the cluster variables in the `variables.tf` file (i.e.: number of guest accounts, number of nodes).
8. Adapt the OpenStack variables in the `openstack.tf` file (i.e: compute node flavor, ssh key pair).
9. Verify the Terraform plan : `terraform plan`.
10. Apply the Terraform plan : `terraform apply`.

To tear down the cluster, from the `openstack` folder, call: `terraform destroy`.

## Amazon Web Services

1. Download the latest version of this project: (master)[https://git.computecanada.ca/fafor10/slurm_cloud/repository/master/archive.tar.gz]
2. Untar: `tar xvf archive.tar.gz`
3. Go in the aws project folder : `cd slurm_cloud/aws`
4. Export the following environment variables : `AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY`.
5. Initiate the Terraform state : `terraform init`.
6. Adapt the cluster variables in the `variables.tf` file (i.e.: number of guest accounts, number of nodes).
7. Adapt the AWS parameters in the `main.tf` file (i.e: compute node flavor, ssh key pair).
9. Verify the Terraform plan : `terraform plan`.
10. Apply the Terraform plan : `terraform apply`.

To tear down the cluster, from the `openstack` folder, call: `terraform destroy`.

## Using Cloudflare DNS Service

1. Create a symlink to the `dns.tf` file into your cloud project folder (i.e: `openstack`, `aws`, etc.).
2. Export the following environment variables `CLOUDFLARE_EMAIL` and `CLOUDFLARE_TOKEN`.
3. Run `terraform apply`.