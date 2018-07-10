# Devops Challenge

You should aim to provide a simple but robust solution which others could 
easily use and extend. We ask you to complete this challenge within 48 hours 
of downloading it, but don’t expect you to spend more than 3 to 5 hours on it.

Your solution should be implemented in a standard open-source tool chain 
using commonly available libraries and tools. Favor terse simplicity over 
attempting to guard against all edge cases.

Your submission should include:

* Instructions on how to build / execute your code
* Source code
* Discussion topics - *A paragraph or two around each topic should suffice*
    
Once you have finished, please email your solution to your Tesla contact.

## Challenge

Imagine that an application development team needs a new server 
configured to run their new internal application. 

*(To minimize the scope of this exercise, we won’t worry about how the server 
is built.)* 

We will use `Vagrant` and `Virtualbox` (or `Kitchen` and `Virtualbox`) 
to manage a local instance, and the `Vagrant` “provision” (or 
`kitchen converge`) functionality to configure the server. 

See the `Vagrant` section below for more info.

Write code that brings the server from the base OS installation 
to being ready for your developers to deploy their application.

The application requires the following:

* Nginx as a reverse proxy
* NodeJS
* MemcacheD
* A simple MySQL server
* Host-based firewall configuration (such as iptables or netfilter) 
  so that the application is only accessible from the 10.0.0.0/8 subnet
  
A simple example NodeJS application is provided in the `application/`
directory.

For the scope of this exercise, Nginx, MemcacheD, and MySQL will 
run on the same host as the application.

## Discussion Topics

As part of your submission, include some thoughts around the 
discussion topics below:

* How would you make the destination port of the application 
  configurable, so this could be used for other applications?
* How would you test the repeatability of this automation?
* How would you monitor the application and dependent services?

## Vagrant

Vagrant ( http://vagrantup.com ) supports many of the common 
configuration management frameworks. If you’re unfamiliar with 
these tool chains, I would recommend starting with the `shell` 
provisioner ( https://www.vagrantup.com/docs/provisioning/shell.html ).

We have supplied basic templates for `Chef`, `Puppet`, and `Ansible`.

### Install

You should be able to install Vagrant and Virtualbox from the respective sites:

http://vagrantup.com and http://virtualbox.org 

## Get Started

A Vagrantfile is included alongside this README.

Create a new directory and copy the included files into it.

Run this command to bring up the box:

> vagrant up

The following will allow you to SSH into the box

> vagrant ssh

Once you’ve configured provisioning, you can run:

> vagrant provision

Feel free to reach out to your Tesla contact, if you run into problems.
