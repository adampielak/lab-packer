# Lab - Packer Files
A repo to manage, track and maintain the different Packer files used to create
my home lab.

## Current Homelab
My current home lab currently runs on __ProxmoxVE 6.2-4__.

## Current Packer Builds
* CentOS 8
    * [CentOS 8.1.1911](./centos-8.1.1911-x86_64)
        * Builders: Proxmox

## Using Packer with ProxmoxVE
The Packer ProxmoxVE builder creates a template VM on the ProxmoxVE Datacenter.
My current lab is a single-node ProxmoxVE deployment so certain options are set
up to reflect this throughout the Packer template.

In order to build the Packer template you will need to supply the following
variables to the `packer build` command:
* `proxmox_host` - IP address or URL for the ProxmoxVE instance
* `proxmox_api_user` - Username for the ProxmoxVE instance (must use `@pam` or `@pve` realm)
* `proxmox_api_password` - Password for the ProxmoxVE user

Full command: `packer build -var 'proxmox_host=IP_OR_URL' -var 'proxmox_api_user=USERNAME -var 'proxmox_api_password=PASSWORD TEMPLATE_FILE.json'`

__*Use of environment variables or other protected methods for sensitive information is highly encouraged*__
