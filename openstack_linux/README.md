CSAR_Template
=============

* an eclipse project for a Template CSAR using openstack/linux

* It contains a small topology consiting only of an OpenStack virtual machine node and a linux operating system node

* The OpenStack node has an attached implementation artifact for calling the OpenStack API from within a build plan

* The linux node has an attached implementation artifact that allows sending SSH-commands to the linux-VM from within a plan

* It contains an executable BPEL build plan which will provision a single virtual machine running linux, and then execute a single command on that machine via SSH

* It contains self-service data and can be used from the self-service portal Vinothek

* It contains an ANT script for re-packaging the CSAR file after manual extraction/modification

# Syntax for IA input:

## credentials:

{"auth":{"tenantId":"4114e1b404404565ac2ccbcc76b8078e","passwordCredentials":{"username":"username","password":"password"}}}


## endpoints
{"os-identity-api":"http:\/\/129.69.209.131:5000\/v2.0","os-tenantId":"4114e1b404404565ac2ccbcc76b8078e"}

flovorid:
3

imagename:
ubuntu-14.04-trusty-server-cloudimg
