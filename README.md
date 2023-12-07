# Packer and Ansible Demo

- [Packer and Ansible Demo](#packer-and-ansible-demo)
  - [1. Download GCP credentials](#1-download-gcp-credentials)
  - [2. Edit parameters](#2-edit-parameters)
  - [3. Allow SSH](#3-allow-ssh)
  - [4. Create the image](#4-create-the-image)

## 1. Download GCP credentials

Download the GCP service account key from your GCP project, rename it to `credential.json` and copy it to the `packer` and also `terraform` folders.

## 2. Edit parameters

Edit packer parameters within `packer/variables.pkrvars.hcl` with your public key hash and your private key path. Also, change your project ID (you can get it from GCP main dashboard).

## 3. Allow SSH

Since we will be using the `default` network, ensure the network has a firewall rule to allow SSH to your IP address or anyone (0.0.0.0/0). The rule should be created with network tag = `allow-ssh`.

## 4. Create the image

```
cd packer
./run.sh
```
