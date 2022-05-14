# VPS Installation Walkthrough

Since Digital Ocean seems to be a community favorite, we'll follow through this guide with them onward.

## Getting started
- Visit [Digital Ocean](https://cloud.digitalocean.com/registrations/new) and sign up for an account if not already.
- From the projects page go to Create > Droplets (Create cloud servers)
- From the displayed offers, select the following: (Note: The following settings will provide a very basic VPS, do choose accordingly to your needs.)
 - Image:       Ubuntu 20.04 (LTS) x64
 - Plan:        Shared CPU: Basic
 - CPU Options: Regular With SSD
 - Price:       $5/mo (1 GB / 1 CPU, 25 GB SSD Disk, 1000 GB transfer)
- Data Center:
 - You must now pick the datacenter that's nearest to you.
- Authentication
 - You must now add your SSH Keys for a more secure way of authentication. 
 - In the case you don't have them, you can generate them in [Windows](https://phoenixnap.com/kb/generate-ssh-key-windows-10), [Mac](https://docs.joyent.com/public-cloud/getting-started/ssh-keys/generating-an-ssh-key-manually/manually-generating-your-ssh-key-in-mac-os-x), [Linux](https://docs.oracle.com/en/cloud/cloud-at-customer/occ-get-started/generate-ssh-key-pair.html).
- Set a password for the root user.
- Assign a name to the droplet
- Finally click the Create Droplet button.

## Setting up the VPS
