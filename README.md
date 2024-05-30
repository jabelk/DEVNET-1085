# DEVNET-1085: Learning YANG Data Modeling By Playing in the NSO Playground

NSO Playground Blog
https://blogs.cisco.com/developer/nsoplayground01

Playground local install:
https://developer.cisco.com/codeexchange/github/repo/CiscoDevNet/NSO-Playground-Local-Install/

System install
https://developer.cisco.com/codeexchange/github/repo/CiscoDevNet/NSO-Playground-System-Install/

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

https://github.com/CiscoDevNet/nso-lab-files
https://developer.cisco.com/learning/labs/yang-nso-101/
https://developer.cisco.com/learning/tracks/get_started_with_nso/nso-yang/yang-nso-201/creating-a-new-model/

### Cloud dev
https://developer.cisco.com/devenv/?id=devenv-base-vscode-nso-local&GITHUB_SOURCE_REPO=https://github.com/CiscoDevNet/NSO-Playground-Local-Install

https://developer.cisco.com/devenv/?id=devenv-base-vscode-nso-local&GITHUB_SOURCE_REPO=https://github.com/jabelk/learn-yang-playground

https://developer.cisco.com/devenv/?id=devenv-base-vscode-nso-local&GITHUB_SOURCE_REPO=https://github.com/CiscoDevNet/NSO-Playground-Local-Install

Jesus example:
https://github.com/jillesca/nso-restconf-dns-example


steps:

```
source $NCS_DIR/ncsrc
ncs-setup --dest ~/nso-instance 
```
copy over files to ~/nso-instance/packages through VS Code GUI drag and drop

```
cd ~/nso-instance 
ncs

```

```
source $NCS_DIR/ncsrc
cd ~/nso-insance/packages/learn-yang/src
make clean all
cd ~/nso-insance/packages/router-model/src
make clean all
ncs_cli -C -u admin
packages reload force

```


```
echo $DEVENV_APP_8080_URL

```

default credentials are: admin/admin

source $NCS_DIR/ncsrc
ncs_cli -C -u admin
show running-config router
show running-config router | display json
show running-config router | display xml

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
conf
router ?
router name ?
router name sjc-gw2
commit
end
show running-config router
```