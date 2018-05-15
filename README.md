### HCP Reporter

This plugin provides detailed admin level reports in both a Web UI and CSV format. Fields can filtered & sorted for quick global views across a tenancy. 

Currently supports the following instance details: Created By User, Email, Instance Name, Host/IP, End Point Type (Cloud Provider), Region, Hardware Type, Connectivity Status, Image, HCP Id, Docker cluster name, Network, Hardware size details, Image Id (template, AMI, etc). 

With this you can quickly:
* View all instances in a specific cloud provider - "Show me all AWS instances"
* View all instances on a single subnet - "Show me all instances on 10.0.8.x"
* View all instances of a certain size - "Show me all m4.large", or "Sort by Size"
* View all instances owned by a certain user
* Find the most popular AMIs deployed by users
* Find the most popular cloud regions for users

Setup: In the blueprint YAML, be sure to change the HG User, HG Password, and URL

#### Demo

![alt text](https://github.com/hypergrid-inc/HyperCloud-Blueprints/blob/master/HCP%20Reporter/HCP-Reporter.gif?raw=true)

YAML
```
nginx:
  image: nginx:latest
  publish_all: true
  restart: always
  plugins:
    - !plugin
      id: 9Ud4X
      restart: true
      arguments:
        - hguser=admin@web.url
        - hgtoken=password
        - hcpurl=https://hcpurl.com
 ```
