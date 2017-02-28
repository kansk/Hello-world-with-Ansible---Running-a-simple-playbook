In this guide, I am going to show you how to set up ansible on CentOS 7 to run a simple playbook. This guide assumes that you have already installed ansible on your machine. If you haven't done that yet, please find the instructions to install ansible [here](https://gist.github.com/swarup-donepudi/868d993c103a85e99c31a64e33de72f5).

The playbook that we are going to use in this guide is going to have instructions to create an empty file in the home folder of the user that ansible runs the playbook as.

I will use the term **controller-node** to refer to the node on which ansible is installed and the playbook run is initiated.
I will use the term **target-node** to refer to the machine to which ansible makes the changes to.

Below is the contents of the playbook:

<pre><code>---
- hosts: all
  user: ansibleuser
  tasks:
  - name: Create an empty file with name myfile.txt
    shell: touch myfile.txt
    
Before executing the playbook we need to do a bunch of things on both controller-node and the target-node.
First let us work on the things that need to be taken care of on controller-node:

1. Create a new directory to store all the files that we need to run a sample playbook

<pre><code>mkdir ansible_workspace</code></pre>

2. Create a file with the name **hosts** and save the IP address of the target-node in line#1 and save & close the file.

<pre><code>vi hosts
192.1.168.1</code></pre>

3. Create a new SSH keypair by following the instructions shown [here](kkkk)