manage-rhv-infra
================

This role deploys and manages the underlying OCP required Infrastructure in RHV based in the variables defined in the inventory.

As this is a shared environment, specific tags not related to OCP are added as well to every ec2 and ebs created objects so they can be easily identified. These can be found and modified under 'instance_tags' option on every ec2 instance creation.

Requirements
------------

Ansible version >= 2.4

Role Variables
--------------

The majority of the variables required to use the role are defined under the **cloud_infrastructure** object. This object definition is the representation for the underlaying infrastructure and all the required components to deploy an OpenShift Cluster on top of it.

Many of these required variables have default values. These are the **mandatory** variables you need to specify in order the role to work.

Infrastructure skeleton variables
---------------------------------

```yaml
cloud_infrastructure:
   masters:
     count: **mandatory**
     cpu_count: **defaulted**
     memory: **defaulted**
     network: **defaulted**
     template_name: **defaulted**
     network_netmask: **defaulted**
     network_gateway: **defaulted**
     network_nic_name: **defaulted**
     name_prefix: **defaulted**
     rhv_cluster: **defaulted**
     root_volume_size: **defaulted**
     rhv_storage_domain: **defaulted**
     docker_storage_domain: **defaulted**
     docker_volume_size: **defaulted**
     etcd_storage_domain: **defaulted**
     etcd_volume_size: **defaulted**
   etcdnodes:
     count: **mandatory**
     cpu_count: **defaulted**
     memory: **defaulted**
     network: **defaulted**
     template_name: **defaulted**
     network_netmask: **defaulted**
     network_gateway: **defaulted**
     network_nic_name: **defaulted**
     name_prefix: **defaulted**
     rhv_cluster: **defaulted**
     root_volume_size: **defaulted**
     rhv_storage_domain: **defaulted**
     docker_storage_domain: **defaulted**
     docker_volume_size: **defaulted**
     etcd_storage_domain: **defaulted**
     etcd_volume_size: **defaulted**
   appnodes:
     count: **mandatory**
     cpu_count: **defaulted**
     memory: **defaulted**
     network: **defaulted**
     template_name: **defaulted**
     network_netmask: **defaulted**
     network_gateway: **defaulted**
     network_nic_name: **defaulted**
     name_prefix: **defaulted**
     rhv_cluster: **defaulted**
     root_volume_size: **defaulted**
     rhv_storage_domain: **defaulted**
     docker_storage_domain: **defaulted**
     docker_volume_size: **defaulted**
     origin_storage_domain: **defaulted**
     origin_volume_size: **defaulted**
   infranodes:
     count: **mandatory**
     cpu_count: **defaulted**
     memory: **defaulted**
     network: **defaulted**
     template_name: **defaulted**
     network_netmask: **defaulted**
     network_gateway: **defaulted**
     network_nic_name: **defaulted**
     name_prefix: **defaulted**
     rhv_cluster: **defaulted**
     root_volume_size: **defaulted**
     rhv_storage_domain: **defaulted**
     docker_storage_domain: **defaulted**
     docker_volume_size: **defaulted**
     origin_storage_domain: **defaulted**
     origin_volume_size: **defaulted**
   cnsnodes:
     count: **mandatory**
     cpu_count: **defaulted**
     memory: **defaulted**
     network: **defaulted**
     template_name: **defaulted**
     network_netmask: **defaulted**
     network_gateway: **defaulted**
     network_nic_name: **defaulted**
     name_prefix: **defaulted**
     rhv_cluster: **defaulted**
     root_volume_size: **defaulted**
     rhv_storage_domain: **defaulted**
     docker_storage_domain: **defaulted**
     docker_volume_size: **defaulted**
     gluster_storage_domain: **mandatory**
     gluster_volume_size: **mandatory**

```

Other variables
---------------

| Variable        | Description                           |
|:---------------:|:-------------------------------------:|
