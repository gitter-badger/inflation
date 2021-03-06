# Setup and Installation

## Hardware Recommendations
For running vms locally in VirtualBox

* Reasonably fast cpu with 2 or more cores and VT-x (I used a Intel i7-3612QM 2.1GHz, 4 core chip)
* 8gb ram (or more)
* 16gb free drive space  (or more)

For running containers in lxc locally or spawning machine in aws/digitalocean you can get away with comparatively slow computer and you don't need VT-x. In fact, the LXC/EC2/DigitalOcean providers can be managed from a Raspberry Pi. See: https://www.raspberrypi.org/

## Summary of Setup:
You need to install some programs into your host, then you will need to install some Vagrant plugins. You also need to setup full accounts (or login into existing accounts) at DigitalOcean and AWS.

## Supported OS:
[Ubuntu 16.04 or newer](https://www.ubuntu.com/download/desktop)

[OSX](http://www.apple.com/mac-mini/)

## Dependencies:

Download and install your Vagrant and VirtualBox.

- [Vagrant](http://www.vagrantup.com/)

- [VirtualBox 5.1 or newer](https://www.virtualbox.org/)

Note: Vagrant and VirtualBox update frequently, and sometimes with breaking changes. Additionally there are host OS specific dependencies below.

### Dependencies (Ubuntu):
You first need to install some dependencies for your host OS. For Ubuntu based systems, run:

```
#!bash
sudo apt install -y build-essential linux-headers-$(uname -r) lxc lxc-templates cgroup-lite redir xclip
```

### Dependencies (Mac):

There are no additional dependencies for Mac, however, LXC cannot be used as a provider at this time.

#### Install Vagrant plugins:
cd into the `rambo` repo and run:

```
#!bash
bash setup.sh
```

# Providers

Rambo supports various providers, and aims to let you switch between them as easily as possible. Nevertheless, some providers do have particular considerations, such as setting up keys and paymentfor cloud services, or specific dependencies for the host OS. This is a list of Rambo's supported providers, with links to specific documentation pages for each.

- [AWS EC2](https://github.com/terminal-labs/rambo/blob/master/docs/providers/aws-ec2.md)
- [DigitalOcean](https://github.com/terminal-labs/rambo/blob/master/docs/providers/digitalocean.md)
- [Docker](https://github.com/terminal-labs/rambo/blob/master/docs/providers/docker.md)
- [LXC](https://github.com/terminal-labs/rambo/blob/master/docs/providers/lxc.md)
- [VirtualBox](https://github.com/terminal-labs/rambo/blob/master/docs/INSTALL.md#virtualbox-provider)

## VirtualBox Provider:

Assuming that you installed the dependencies you should be able to run 

`vagrant up`

or the more verbose command 

`vagrant --target=virtualbox up`
