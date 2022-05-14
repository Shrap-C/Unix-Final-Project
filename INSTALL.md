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
- Select your Droplet in the Home Page.
- Click `Console` (Note: You will be logged in as root by default).
- Upgrading and Updating the system
  - use the command `apt update && apt upgrade` and confirm them.
- Creating a user.
  - use the command `adduser (username)`.
- Changing the password of the user.
  - use the command `passwd (username)`.
- Installing Nginx for the web server.
  - use the command `apt install nginx`.
- Enable NginX on startup using the command `systemctl enable nginx`.
- Start the NginX service using the command `systemctl start nginx`.
- Set the firewall settings using the following commands:
    - `ufw default deny incoming`
    - `ufw default allow outgoing`
    - `ufw allow OpenSSH`
    - `ufw allow 'Nginx Full'`
- Check the added UFW rules 
  - use the command `ufw show added` and confirm Nginx is added.
- Enabling the firewall 
  - use the command `ufw enable`.

## Installing a Web server

In hosting a web server you could use a domain of your own if you can afford it. Otherwise take a look serverpilot. It easen the process to set it up with Digital Ocean. [Serverpilot](https://serverpilot.io/) is free for basic use and helps you setup a webserver on Digital Ocean. Follow these more [in-depth steps](##In-depth tutorial)

## In-depth tutorial: ServerPilot
- Connect Your Server to ServerPilot
Your server provider will tell you the IP address and password for your new server. You'll give that info to ServerPilot so our automated systems can configure your server. If you use SSH keys instead of passwords, that will work great, too.

It takes only a couple of minutes for ServerPilot to finish configuring your server. ServerPilot will install Nginx, Apache, MySQL, multiple PHP versions, and all other software your server needs.

Once configured, your server will always keep a secure connection open to ServerPilot. ServerPilot will never need to initiate a connection to your server and there is no control panel running on your server. This keeps your server extremely secure and doesn't waste any of your server's CPU or memory.

- Create or Transfer Your Sites
You're now ready to host WordPress or any other PHP app. Websites are called "apps" in ServerPilot. An app can be WordPress, a custom PHP web application, or a static HTML site. You can have more than one app on your server.

You'll tell ServerPilot which PHP version to use and your app's domain names. You can either use the built-in WordPress installer or upload an existing site's files to your server. It takes only seconds for ServerPilot to create the new app on your server.

- Enable Free SSL
Once you've changed your domain's DNS to point to your server's IP address, ServerPilot's AutoSSL feature can secure your app with a free SSL certificate from Let's Encrypt.

You'll never pay for an SSL certificate and you'll never need to worry about renewing certificates before they expire. ServerPilot will automatically renew certificates to your app.

## Alternatives

Perhaps you'd prefer adding a domain of your own rather then files. 

A service that can provide domains is [Namecheap](https://www.namecheap.com/).

Another similar service is [Name](https://www.name.com/).
