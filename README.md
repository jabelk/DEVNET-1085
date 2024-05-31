# DEVNET-1085: Learning YANG Data Modeling By Playing in the NSO Playground

NSO Playground Blog
https://blogs.cisco.com/developer/nsoplayground01

Playground local install:
https://developer.cisco.com/codeexchange/github/repo/CiscoDevNet/NSO-Playground-Local-Install/


Session Type
DevNet

DevNet Session Type
DevNet Classroom

Length*
45 Min

Technical Level*
Introductory

Have you tried to learn YANG before and just gotten confused? Join me as I visualize and explain basic YANG concepts, which will help you both in certifications and out in the wild world of automation.

This session will clarify YANG basics and its applications through the engaging and interactive capabilities of Cisco Network Services Orchestrator (NSO).

Attend this session to:

Grasp YANG Basics Quickly: Learn YANG's key principles with hands-on NSO exercises, designed to provide clear understanding and immediate visual feedback.
Enhance Your Professional Toolkit: Acquire critical YANG knowledge essential for network automation, boosting your capabilities for certifications and practical deployment.
Cultivate a Learning Mindset: Discover how exploring YANG within the NSO environment fosters a deeper comprehension, laying the groundwork for mastering more complex automation concepts.


## NSO YANG Courses

https://developer.cisco.com/learning/labs/yang-nso-101/
https://developer.cisco.com/learning/tracks/get_started_with_nso/nso-yang/yang-nso-201/creating-a-new-model/

## Steps for this lab

steps:

```
source $NCS_DIR/ncsrc
ncs-setup --dest ~/nso-instance 
```

Move over the packages using git clone to the home directory and then soft link them to packages directory:

```
git clone https://github.com/jabelk/DEVNET-1085

# Navigate to the packages directory and ensure it's clean
cd ~/nso-instance/packages

# Move the directories from DEVNET-1085 to the packages directory
mv ~/DEVNET-1085/learn-yang ~/nso-instance/packages/
mv ~/DEVNET-1085/router-model ~/nso-instance/packages/

```

re-compile the packages 

```
cd ~/nso-instance/packages/learn-yang/src
make clean all
cd ~/nso-instance/packages/router-model/src
make clean all
```


```
cd ~/nso-instance
ncs
ncs_cli -C -u admin
packages reload force

```


```
echo $DEVENV_APP_8080_URL
# put that link in your browser
# default credentials for the Web UI are: admin/admin
```

Configuring NSO CLI example
```
source $NCS_DIR/ncsrc
ncs_cli -C -u admin
show running-config router
show running-config router | display json
show running-config router | display xml
```

output example
```
admin@ncs# conf
Entering configuration mode terminal
admin@ncs(config)# router ?
Possible completions:
  address  name  operational-status
admin@ncs(config)# router name ?
Possible completions:
  <string>[rno-gw1]
admin@ncs(config)# router name sjc-gw2
admin@ncs(config)# commit
Commit complete.
admin@ncs(config)# end
admin@ncs# show running-config router
router name        sjc-gw2
router address     10.20.30.40
router operational-status up
admin@ncs#
```

changing configuration that is already existing example

```
conf
router ?
router name ?
router name sjc-gw2
commit
end
show running-config router
```