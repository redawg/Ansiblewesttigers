# Ansiblewesttigers

Demo playbook library for customer **POCs, trials, and demos** across every major platform and integration. Playbooks are designed to be run from Ansible Automation Platform (AAP) Controller with variables passed via surveys or credential types — no hardcoded secrets.

---

## Variable Convention

All playbooks define blank variables that must be supplied at runtime:

```yaml
vars:
  resource_name: ''          # passed via AAP survey
  AZURE_CLIENT_ID: ''        # passed from AAP Controller credential
  AZURE_SECRET: ''           # passed from AAP Controller credential
  AZURE_SUBSCRIPTION_ID: ''  # passed from AAP Controller credential
  AZURE_TENANT: ''           # passed from AAP Controller credential
```

---

## Platform Coverage

### AWS

| Playbook | Description |
|---|---|
| `createvpc.yml` | Create VPC with subnets and internet gateway |
| `createvms.yml` | Launch EC2 instances |
| `createsecuritygrp.yml` | Create security groups |
| `instancecontrol.yml` | Start / stop / reboot EC2 instances |
| `getinstanceinfo.yml` | Gather EC2 instance facts |
| `deleteinstance.yml` | Terminate an EC2 instance |
| `deletevpc.yml` | Delete a VPC and all resources |

### Azure

| Playbook | Description |
|---|---|
| `createresourcegroup.yml` | Create resource group |
| `createvirtualnet.yml` | Create virtual network |
| `createsubnet.yml` | Add subnet to a VNet |
| `createpublicip.yml` | Allocate public IP |
| `createvmsecgroup.yml` | Create network security group |
| `createvm.yml` | Deploy a VM |
| `createvnetpeering.yml` | Peer two VNets |
| `startserver.yml` / `stopserver.yml` | Start or stop a VM |
| `deleteVM.yml` / `deleteresourcegroup.yml` | Remove VM or resource group |
| `getpubip.yml` | Get VM public IP |

### Google Cloud Platform

| Playbook | Description |
|---|---|
| `create_gcp_instance.yml` | Deploy a GCP VM instance |
| `create_rhel_instance.yml` | Deploy a RHEL instance on GCP |
| `create_vpc.yml` | Create a GCP VPC |
| `create_gcp_disk.yml` | Create a persistent disk |
| `create_snapshot.yml` | Snapshot a GCP disk |
| `create_IPv4_public_IP.yml` | Allocate a public IP |
| `allow_firewall_ports.yml` | Open firewall rules |
| `delete_instance.yml` / `delete_vpc.yml` | Remove instance or VPC |

### VMware

| Playbook | Description |
|---|---|
| `deploy_vm_from_template.yml` | Deploy VM from vCenter template |
| `deploy_vm_from_template_csv.yml` | Bulk deploy VMs from CSV input |
| `deploy_vm_from_template_dhcp.yml` | Deploy VM with DHCP networking |
| `take_vmware_host_snapshot.yml` | Take a VM snapshot |
| `vm_add_hdd.yml` | Add a hard disk to a VM |
| `create_cluster.yml` | Create a vCenter cluster |
| `create_folder.yml` | Create a VM folder |
| `get_vmware_host.yml` / `get_vmware_host_facts.yml` | Gather host facts |

### Network (IOS / NX-OS / EOS / JunOS / Palo Alto / ACI)

| Playbook | Description |
|---|---|
| `ios_backup.yml` | Back up IOS running config |
| `network_backup.yml` / `network_restore.yml` | Multi-platform backup and restore |
| `ios_upgrade.yml` | Upgrade IOS software |
| `ios_snmp_config.yml` | Configure SNMP |
| `ios_replace_ntp.yml` | Replace NTP configuration |
| `ios_facts.yml` / `eos_show_config.yml` | Gather device facts |
| `eos_add_vlan.yml` / `ios_vlan_facts.yml` | VLAN management |
| `eos_dns_compliance.yml` | Validate DNS config compliance |
| `panos_add_bgp_route.yml` | Add BGP route on Palo Alto |
| `panos_add_ntp_rule.yml` | Add NTP rule on Palo Alto |
| `aci_ensure_tenant_exists.yml` | Create or verify ACI tenant |
| `aci_tenant_ap_vrf_bd_epg.yml` | Full ACI tenant network config |
| `junos_update.yml` | Upgrade JunOS software |
| `show_interface_parse.yml` | Parse and display interface data |

### F5 BIG-IP

| Playbook | Description |
|---|---|
| `bigip_pool.yml` | Create a load balancer pool |
| `bigip_pool_members.yml` | Add members to a pool |
| `bigip_virtual_server.yml` | Create a virtual server |
| `clientssl_profile.yml` | Configure a client SSL profile |
| `bigip_cert_import.yml` / `bigip_key_import.yml` | Import SSL cert/key |
| `bigip_tcp_http_profiles.yml` | Configure TCP/HTTP profiles |
| `Ensure_software_version.yml` | Validate running software version |
| `Mitigate_CVE-2020-5902.yml` | Apply CVE-2020-5902 mitigation |
| `add_nodes.yml` | Add nodes to the BIG-IP |

### Windows

| Playbook | Description |
|---|---|
| `update_windows.yml` / `win_updates.yml` | Apply Windows updates |
| `install_windows_iis.yml` | Install IIS web server |
| `restart_windows_iis.yml` / `restart_windows_dns.yml` | Restart services |
| `install_dns_server.yml` | Install Windows DNS Server role |
| `add_windows_dnsrr.yml` / `del_window_dnsrr.yml` | Manage DNS records |
| `backup_Windows_registry.yml` | Back up the Windows registry |
| `validate_CVE-2020-1350.yml` / `mitigate_CVE-2020-1350.yml` | SIGRed CVE handling |
| `run_power_shell.yml` | Execute a PowerShell script |

### RHEL / Linux

| Playbook | Description |
|---|---|
| `yumupdate.yml` | Apply all yum updates |
| `linux_install_package.yml` | Install a package |
| `manage_linux_services.yml` | Start, stop, enable services |
| `check_fs_space.yml` | Check filesystem utilization |
| `RHEL_crypto_policies.yml` | Set RHEL crypto policy |
| `check_and_set_timezone.yml` | Verify and set system timezone |
| `ubuntu_docker_install.yml` | Install Docker on Ubuntu |
| `return_OS_version.yml` | Return OS version as a fact |

### Dynatrace

| Playbook | Description |
|---|---|
| `installagent.yml` | Install Dynatrace OneAgent |
| `linuxclientinstall.yml` | Linux-specific install |
| `uninstalllinux.yml` | Remove OneAgent from Linux |

### KVM

| Playbook | Description |
|---|---|
| `kvm_create.yml` | Create a KVM virtual machine |
| `kvm_create_clone.yml` | Clone an existing KVM VM |
| `kvm_define_vms.yml` | Define VMs from a variable list |

### MySQL

| Playbook | Description |
|---|---|
| `backup_mysql_db.yml` | Back up a MySQL database |
| `restore_mysqldump_db.yml` | Restore from a mysqldump backup |
| `dump_mysql_db.yml` | Dump database to file |

### NetApp

| Playbook | Description |
|---|---|
| `netapp_create_vol.yml` | Create a NetApp volume |
| `netapp_gather_info.yml` | Gather NetApp system facts |

### ServiceNow

| Playbook | Description |
|---|---|
| `show_incident_by_number.yml` | Query and display a specific incident |

### Infoblox

| Playbook | Description |
|---|---|
| `add_new_network.yml` | Add a network to Infoblox IPAM |

### HashiCorp Vault

| Playbook | Description |
|---|---|
| `vault.yml` | Read secrets from HashiCorp Vault |

### Incapsula (Imperva CDN)

| Playbook | Description |
|---|---|
| `uri_geo_block.yml` | Apply a geo-blocking rule via API |
| `uri_install_certificate.yml` | Install an SSL certificate via API |

### HTML Reports

| Playbook | Description |
|---|---|
| `CreateHTMLinventory.yml` | Generate HTML inventory report |
| `IOSHTMLinventory.yml` | Generate HTML IOS device report |

---

## Collections Required

```yaml
# Collections/requirements.yml
collections:
  - name: azure.azcollection
  - name: community.general
  - name: amazon.aws
  - name: ansible.posix
  - name: community.aws
```

Additional collections per platform (install as needed):

```yaml
  - name: google.cloud
  - name: community.vmware
  - name: f5networks.f5_modules
  - name: cisco.ios
  - name: cisco.nxos
  - name: junipernetworks.junos
  - name: paloaltonetworks.panos
  - name: cisco.aci
  - name: servicenow.itsm
  - name: infoblox.nios_modules
  - name: netapp.ontap
  - name: ansible.windows
  - name: dynatrace.event_driven_ansible
```
