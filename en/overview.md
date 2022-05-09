## Network > Service Gateway > Overview

The **Service Gateway** service allows you to use the **services** of NHN Cloud outside the **VPC** without using a **floating IP** and having the traffic going through the internet. The **service** selected when **creating the service gateway** and the automatically assigned IP maintain a one-to-one relationship. In the **VPC**, you can use the target **service** safely through the NHN Cloud's internal network using the **service gateway**'s IP address.

### Main Features

* You can connect to the services of NHN Cloud provided by the service gateway from your VPC without going through the internet.
* You can use only the services provided in the service list when creating a service gateway.
* The IP address of the service gateway is connected one-to-one with the service selected when creating the service gateway.
* A service gateway can only be used within the VPC in which the service gateway has been created.
* When the VM Instance in the VPC communicates with the IP address of the service gateway, it communicates with the service associated with the service gateway.
* This service is currently only available in the Korea (Pangyo) and Korea (Pyeongchon) regions, and will be supported by other regions gradually.

### Provided Services

Currently, you can use the following services of NHN Cloud by using the service gateway. We plan to support other services gradually.

Service Name  | Provided Region | Description
------------- | ------------- | -------------------
Object Storage|Korea (Pangyo), Korea (Pyeongchon)|**Object Storage** is an online storage service provided by NHN Cloud, which lets you store large amounts of data. If you need to access **object storage** from the VM instance in your VPC without going through the internet, select **Object Storage** to create a service gateway.<br>For details on how to use it, refer to [**User Guide > Storage > Object Storage > Console User Guide**](https://docs.toast.com/ko/Storage/Object%20Storage/ko/console-guide/).
IaaS API Identify|Korea (Pangyo), Korea (Pyeongchon)|An **authentication token** service. If you need to obtain an **authentication token** required to use the **Object Storage API** from the VM instance in your VPC without going through the internet, select **IaaS API Identify** to create a service gateway.<br>For details on how to use it, refer to [**User Guide > Storage > Object Storage > API Guide > Authentication Token Issuance**](https://docs.toast.com/ko/Storage/Object%20Storage/ko/api-guide/).
