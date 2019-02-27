# nginx-vmss
A VMSS for deploying NGINX as a TCP Stream Broker


<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fjgmitter%2Fnginx-vmss%2Fmaster%2Fazuredeploy.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>

This template allows you to deploy a VM Scale Set of NGINX Ubuntu VMs using the latest patched version of Ubuntu Linux 18.04 LTS. These VMs are behind an internal load-balancer. Because the load-balancer is internal, you must first ssh into the jumpbox, then ssh from there into a specific VM behind the load balancer. To connect from the load-balancer to a VM in the scale set, you would go to the Azure Portal, find the jumpbox public ip, examine the NAT rules, then connect using the NAT rule you want. For example, if there is a NAT rule on port 50000, you could use the following command from the jumpbox:

ssh to your jumpbox, than:

ssh -p 50000 {username}@{loadbalancer-ip-address} to each NGINX VM to update its NGINX.conf

Sample NGINX Configs:  https://github.com/jgmitter/TCPStreamBroker



