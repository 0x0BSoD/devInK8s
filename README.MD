# K8S Environment for development

K8s cluster with calico, metallb and heketi. Currently based on OracleLinux 8.

## Community modules
* community.crypto
* community.kubernetes.k8s


## VARS
### Inventory vars
|Name|Group| Comment |
|----|--- | --- |
| k8s_master | masters | True or False |
| lb_priority | lbs | range of 0 to 255  |
| lb_status | lbs | MASTER or BACKUP |

### Roles vars
|Name|Role| Defalt value | Comment |
|----|-- |-----------  | --- |
|i_have_no_dns| common    | Null | If DNS server not using, then add info about hosts to /etc/hosts |
| lb_vip | lb | Null | VIP for keepalived |
| lb_pass| lb | admin123 | password for keepalived |
| docker_data_folder | dkr_kublet  | /var/lib/docker |  |
| containerd_version | dkr_kublet  | 1.4.3 |  |
| docker_version | dkr_kublet  | 20.10.2 |  |
| helm_version | dkr_kublet  | v3.5.0-rc.2 | |
| heketi_admin_api_key | glusterfs | Null | | 
| heketi_user_api_key | glusterfs | Null | | 
| ethernet_name | glusterfs | {{ansible_default_ipv4.interface}} | | 
| heketi_vol_prefix | glusterfs | k8s-dev | | 
| heketi_version | glusterfs | v10.2.0 | | 
| heketi_port | glusterfs | 8080 | | 
| heketi_zone | glusterfs | 1 | | 
| heketi_disks| glusterfs | - /dev/sdc1 | |
| addresses| metallb | 192.168.1.240-192.168.1.250 | |
| metallb_version| metallb | v0.9.5 | |
| k8s_cp_endpoint| masters | 10.1.1.100:6443 | |
| k8s_net| masters | 192.168.0.0/16 | |
| k8s_cp_port| masters | 6443 | |
