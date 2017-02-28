In this guide, I am going to show you how to set up ansible on CentOS 7 to run a simple playbook. This guide assumes that you have already installed ansible on your machine. If you haven't done that yet, please find the instructions to install ansible [here](https://gist.github.com/swarup-donepudi/868d993c103a85e99c31a64e33de72f5).

The playbook that we are going to use in this guide is going to have instructions to create an empty file in the home folder of the user that ansible runs the playbook as.

<pre><code>---
- hosts: all
  user: root
  tasks:
  - name: Create a new group for tomcat
    shell: groupadd tomcat</code></pre>