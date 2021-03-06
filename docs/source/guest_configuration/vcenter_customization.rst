.. _vcenter_customization:

=====================
vCenter Customization
=====================

vCenter offers a way to prepare the guest OS on boot. For example configuring its network, licenses, Active Directory server, etc. vOneCloud vCenter drivers offers a way to tie one vOneCloud template with one of these customizations so it is applied on VM startup. You can get more information about this system in `VMware documentation <https://pubs.vmware.com/vsphere-60/index.jsp?topic=%2Fcom.vmware.vsphere.vm_admin.doc%2FGUID-EB5F090E-723C-4470-B640-50B35D1EC016.html>`__.

There are a couple of things to take into account:

* This system is not compatible with OpenNebula contextualization as this customization overwrites the networking changes made by context scripts.
* VM network configuration must be done externally to OpenNebula. Either with a DHCP server or manually setting IPs for each interface.
* This method can be used in all the `Guest OSs supported by vCenter <https://pubs.vmware.com/vsphere-60/index.jsp?topic=%2Fcom.vmware.vsphere.vm_admin.doc%2FGUID-E63B6FAA-8D35-428D-B40C-744769845906.html>`__.


Template Customization Using Sunstone
=====================================

For vCenter templates there are two options in the context tab. To use vCenter Customization select "vCenter" in the as "Contextualization type". This will show a drop down with all the customizations from all the hosts. There you can select from these possibilities:

* **None**: No customization will be applied
* **Custom**: You will be able to type manually the name of one customization
* The name of customizations found in vCenter

Make sure that the customization applied is available in the vCenter where the VM template reside.

|sunstone_vcenter_customization|


.. |sunstone_vcenter_customization| image:: /images/sunstone_vcenter_customization.png

