Ansible role for deploying Knative
==================================

Ansible role to deploy [Knative](https://knative.dev) on [OpenShift](https://openshift.com) cluster.

The role can also be used to install and configure:

- [x] Knative, both Serving and Eventing

Requirements
------------

- [Docker Desktop](https://www.docker.com/products/docker-desktop) or Docker for Linux

- [Ansible](https://ansible.com) >= v2.9.10 

```shell
pip3 install \
  -r https://raw.githubusercontent.com/kameshsampath/ansible-role-knative/master/requirements.txt
ansible-galaxy role install kameshsampath.knative
ansible-galaxy collection install community.kubernetes
```
__NOTE__: For Windows its recommended to use Windows Subsystem for Linux (WSL)

Role Variables
--------------

| Variable Name| Description | Default |
|--|--|--|
| skip_prereqs| Skip pre-requistes like download kubectl, oc etc., | False |
| deploy_knative | Deploy Knative | True |
| knative_version | The Knative version | v0.16.0 |
| knative_serving_version | The Knative Serving version | v0.16.0 |
| knative_eventing_version | The Knative Eventing version | v0.16.0 |
| oc_version | OpenShift cliebt version | v4.5.2 |
| okd_image | [OKD](https://okd.io) image version | quay.io/openshift/okd:4.5.0-0.okd-2020-07-14-153706-ga |
| kubectl_version | The kubectl version | v1.18.2 |
| use_okd  | Use OKD as Kubernetes distro  | True |


Example Playbooks
----------------
The plybook.yml shows how to deploy Knative to the OKD(Kubernetes) cluster

License
-------

[Apache v2](https://github.com/kameshsampath/ansible-role-kind/tree/master/LICENSE)

Author Information
------------------

[Kamesh Sampath](mailto:kamesh.sampath@hotmail.com)

Issues
=======

[Issues](https://github.com/kameshsampath/ansible-role-kind/issues)

Testing
=======

Requirements
------------
- Extra Python modules
```shell
pip3 install \
  -r https://raw.githubusercontent.com/kameshsampath/ansible-role-kind/master/molecule/requirements.txt
```

All tests are built using [molecule](https://molecule.readthedocs.io/en/latest/index.html) with following scenarios:

* default 
```shell
molecule test
```

