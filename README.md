### Overview
This playbook installs Globus Connect Server (GCS) v4 directly from Globus Yum repository. It is not intended for production use; it should be meaningful as a bootstrap to get GCS deployment integrated into your configuration.

### Assumptions
This playbook assumes you:
* want to install GCS directly from the Globus YUM repository
* are using RHEL 7.x
* block both incoming and outgoing ports using the INPUT/OUTPUT chains only
* are using MyProxy authentication
* want MyProxy and GCS installed on the same node
* want only single node installation with MyProxy and GCS installed

### How to use this playbook
This playbook requires that you modify several files prior to execution.  

##### gcs.yml
Modify `hosts:` for the target installation node(s).

##### secrets.yml
Set your Globus ID username and password necessary for configuring Globus Connect Server. See [https://www.globusid.org/](https://www.globusid.org/).

##### variables.yml
Set `globus_endpoint_name` to the display name of the endpoint. If the endpoint does not already exist, it is created. If it already exists, this node is added to it.
