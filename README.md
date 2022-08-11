## Create an app

Prerequisite:  
- APIC Toolkit  
- Privileged user (administrator access)  
  
  
1. Log into the APIM:  
  ```  
  apic login -s manager_endpoint_here -u username_here -p password_here --realm provider/default-idp-2  
  ```  
Note: the realm can be found by using the following apic command if you're not using the local user repository, which is the above example.  
  ```  
  apic identity-providers:list -s platform_endpoint_here --scope provider  
  ```  


2. Create file called app.json with the details you want the app to have:  
```
{
  "name": "app_name_here_lowercase",
  "title": "title_here",
  "client_id": "clientid_here", 
  "client_secret": "client_secret_here"
}
```  

3. Create the app in the desired catalog:  
```
apic apps:create -s manager_endpoint_here -o provider_organization_here -c catalog_here --consumer-org consumer_organization_here app.json  
```  
Example:
![image](https://user-images.githubusercontent.com/66093865/184047882-2d07acad-3ca8-435e-8e16-f3cc8ac5914c.png)  
  

