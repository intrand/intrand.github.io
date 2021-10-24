# initVm

`initVm` was a portfolio project to show I understood how to automate every layer of infrastructure.

## Design

The number of components in `initVm` was staggering, including:

* `web`: Allowed users to submit order(s) and view status(es)
* `api`: The gatekeeper for orders, statuses, cancellations, etc
* `dnsmasq`: An installation of `dnsmasq` that got its configuration from a git repo
* `dnsmasq-api`: A custom python module which wrapped `dnsmasq` in an API that was safe to use
* `passbolt`: Secrets storage with a RESTful API
* `phpipam`: Web app to manage IP address usage/reservations within various subnets and vlans
* `vmware`: vmware esxi & vcenter to host virtual machine deployments
* `ansible`:
    * `rabbitmq`: The `celery` message queue system of choice
    * `celery`: Utilized runners to generate an `ansible` inventory, then ran `ansible-playbook` roles against the relevant target(s) for every aspect of infrastructure
    * `discord-alert`: Custom python module which was used by other components to send discord webhooks as the deployment process progressed
    * `passbolt` (client): Custom python module which retrieved secrets needed to authenticate to other resources (eg, vcenter) from passbolt
    * `phpipam` (client): Custom python module which found the next available IP address in a subnet by vlan ID, or removed an exact match if deleting a deployment, in phpipam
    * `dnsmasq` (client): Custom python module which provisioned/removed `dnsmasq` DNS records corresponding to the deployment by calling a custom python module which spoke to the custom dnsmasq wrapper API

## Fatal flaws

Obviously such a huge stack of software is incredibly difficult for a single person to maintain. This was known before I started, but still is the reason none of it is maintained anymore.

## Conclusion

Well worth the effort. I was able to use this stack to show that I knew what I was doing on some level. Keep in mind that a lot of the choices were "of their time" and limited by what I knew at the time. Golang was still brand new, and I hadn't used Hashicorp vault much. If I had to do this over again, I would break things up more and use different projects/products. The process could also be simplified slightly.

Still, worth it in the end!
