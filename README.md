![image](https://user-images.githubusercontent.com/18219467/189523406-1da330b7-080b-4a06-95f5-701cbe1e21d3.png)

iris-energy-isodata app access energy data from the major Independent System Operators (ISOs) in the United States to Ensure sustainable consumption and production patterns (SDG's 16)


Application is using [**PEX**](https://docs.intersystems.com/irislatest/csp/docbook/DocBook.UI.Page.cls?KEY=EPEX_INTRO) **iris interoperability framework** and [**ISODATA**](https://github.com/kmax12/isodata) Python library with the help of **embedded python**. 

## Get production, demand and supply of below Independent systems operators(ISOs) 
* California ISO (caiso)
* Electric Reliability Council of Texas (ercot)
* New York ISO (nyiso)
* Southwest Power Pool (spp)
* PJM (pjm)
* Midcontinent ISO (miso)
* ISO New England (isone)

## Get today total production of following energies
* Natural Gas 
* Solar       
* Imports     
* Wind        
* Large Hydro 
* Nuclear     
* Batteries   
* Geothermal  
* Biomass     
* Small hydro 
* Biogas      
* Coal       

## Repo Contents   
* Dockerfile, docker-compose.yml, and Installer.cls to create container
* iris.script, contains script to execute during container initialization 
* /src with source files 
* /.vscode/settings.json for automatic server connections when opened in VS Code.

## Requirements:  
* [Docker desktop]( https://www.docker.com/products/docker-desktop)
* Get the latest InterSystems IRIS for Health image for use in the Dockerfile: https://hub.docker.com/_/intersystems-iris-for-health  

## To Run on Windows:  
```
	git clone https://github.com/mwaseem75/iris-energy-isodata.git  
	docker-compose up -d  
```
## To Run on macOS:  

```
	git clone https://github.com/mwaseem75/iris-energy-isodata.git
	docker-compose up -d  
```
Log in with credentials: SuperUser | SYS

## Getting Started 
Navigate to production
http://localhost:52795/csp/irisapp/EnsPortal.ProductionConfig.zen?PRODUCTION=PEX.Production  by using SuperUser | SYS

Start the production
![image](https://user-images.githubusercontent.com/18219467/189573043-49dd6f92-dc29-4bc8-9298-f9fd34359c83.png)
Production contains 7 Business Services, 1 Business Process and 7 Business Operations.

Business Service fetch data from ISOdata and pass to business process which is sending message to business process based on the title. 


Visual Trace
![image](https://user-images.githubusercontent.com/18219467/189573214-36d3f351-f688-4be1-8b12-cbde9b18fec4.png)

Message
The following message passed to operation contains today total production of Natural Gas, Solar, Imports, Wind, Large Hydro, Nuclear, Batteries, Geothermal, Biomass, Small hydro, Biogas and Coal energies  
![image](https://user-images.githubusercontent.com/18219467/189573344-f32fbb6c-73bf-4e5f-8453-8effc396f556.png)

## Online Demo
For online demo navigate to 
http://irisisodata.demo.community.intersystems.com/csp/irisapp/EnsPortal.ProductionConfig.zen?PRODUCTION=PEX.Production by using SuperUser | SYS
![image](https://user-images.githubusercontent.com/18219467/189644037-81ddd698-afef-4b81-9b26-8b287ee09003.png)


## Special Thanks to:
Guillaume Rongier for: [https://openexchange.intersystems.com/package/secured-rest-api](https://openexchange.intersystems.com/package/interoperability-embedded-python) template for guidance
