# Monitoring project

## Prerequisites 
You need to install Vagrant and Ansible before you start
## Summary
VM will be initiated via Vagrant, in VM Prometheus node_exporter will be installed, Prometheus and Grafana containers will up. Grafana will be available on host.
## How to Run
`
vagrant up
`

When preparation will be completed you can access Grafana on *http://localhost:3000*

## Issues


1) If you have Windows + WSL base environment you can meet next problem. Your WSL and VM networks is not connected by default. You need to configure forwarding(interfaces names can be different)
`
Get-NetIPInterface | where {$_.InterfaceAlias -eq 'vEthernet (WSL)' -or $_.InterfaceAlias -eq 'vEthernet (Default Switch)'} | Set-NetIPInterface -Forwarding Enabled
`

2) If you have Windows + VM with some Linux as base env. During starting project you can meet a problem with VT technology is not available in VM. You need to expose virtualization into your VM
`
Set-VMProcessor -VMName <vm name> -ExposeVirtualizationExtensions $true
`