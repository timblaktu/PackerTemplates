# Overview
[Packer](https://www.packer.io/intro/getting-started/install.html) provides a reproduceable build system for creating Virtual Machine Templates used at Biamp.
You do not need to use Packer if you are only using our Virtual Machine Templates, and are not tasked with maintaining them.

The templates and scripts in this project are used with [Packer](https://www.packer.io/intro/getting-started/install.html) to create the Virtual Machine templates that
Biamp Developers use with the [vagrant project](../vagrant) to create and manage their Virtual Machine instances. 

Each subfolder of this project constitutes a recipe for creating a Virtual Machine template that represents 
the smallest possible version of a uniquely-configured base OS that someone needs at Biamp. 

The output of Packer is a minimal Virtual Machine image, e.g. a VirtualBox .vdi or a Vagrant .box file, that 
can be further customized with Ansible or other provisioners, as well as a base Vagrantfile that can be used
by developers to use the template.

The VM images output from Packer are of course huge. These are considered intermediate files and are ignored by
this git repo. They are manually placed on [(TODO: fix this link)this http server](), where they are accessible
to developers on the Biamp network.

# HOWTO Create a Virtual Machine Template
## Installation Requirements
1. Install [Vagrant](https://www.vagrantup.com/docs/installation).
2. Install [Packer](https://www.packer.io/intro/getting-started/install.html).
3. Clone this repo, making sure to update all of its submodules.

## Doing the Packer Build (for Windows 10 Pro)

See [the original Windows Packer Templates readme](README.windows.md) for details.

The entire Packer build can be done from running the following command from the packer directory:
    .\build.ps1 --settings_skipverification=true -Target "virtualbox-local" -os="Windows10"
        
 The Windows 10 Pro packer build is composed of multiple stages to facilitate resumption after errors:
 
    
# References
## Windows Packer Templates
1. Much of the windows Packer work was borrowed/gleaned from the work of [Matt Wrock](https://github.com/mwrock/packer-templates) and [Matt Hodge](https://github.com/MattHodge/PackerTemplates).
2. http://huestones.co.uk/node/305
3. http://www.hurryupandwait.io/blog/how-can-we-most-optimally-shrink-a-windows-base-image
4. http://www.hurryupandwait.io/blog/creating-windows-base-images-for-virtualbox-and-hyper-v-using-packer-boxstarter-and-vagrant
5. https://hodgkins.io/best-practices-with-packer-and-windows#best-practices
6. 

## Debian Packer Templates
1. https://github.com/geerlingguy/packer-debian-9/blob/master/debian9.json
2. 
