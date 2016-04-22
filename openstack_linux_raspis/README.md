CSAR_Template openstack_linux_raspis
=============

A Template CSAR using openstack/linux and two raspberry pis.

It contains a small topology consisting of:
* an OpenStack virtual machine node;
* a linux operating system node;
* two raspberry pi nodes;
* a sensor adapter node;
* an actuator adapter node.

The OpenStack node has an attached implementation artifact for calling the OpenStack API from within a build plan.

The linux node has an attached implementation artifact that allows sending SSH-commands to the linux-VM from within a plan.

The raspberry and adapter nodes behaves like the linux node since they are of the same node type.

It contains an executable BPEL build plan which will provision a single virtual machine running linux, 
and install and starts the message broker Mosquitto on it via SSH. Furthermore, the plan installs the sensor and 
actuator adapters on the given Raspberry pis via SSH. 

It contains self-service data and can be used from the self-service portal Vinothek.

TODO: an ANT script for re-packaging the CSAR file after manual extraction/modification

The following properties must be adapted in the service template:
* In node template name="InstallOpenStackVMTemplate"
  + credentials -> tenantid, password credentials

* In node templates name="Raspi_1" and name="Raspi_2"
  + hostname -> the ip address of the raspberry pi
  + sshUser -> the user name if differs from 'pi'
  + sshKey -> the public key for connecting with the raspberry pi
