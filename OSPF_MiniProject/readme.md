# OSPF_Mini_Project

## Introduction:

We worked in this mini project on **OSPF** (Open Shortest Path First) protocol. For that we implemented a network architecture composed of 2 networks A and B
with the respective IP@ 192.168.1.0/24 155.165.1.0/24 with 3 routers in the middle that will apply the OSPF protocol in order to make communication happen between PC0 and PC1. 

## PCs configuration: 
We start by giving each PC its corresponding IP@ , subnet mask and default gateway

1. For PC0:  
set IP@ to 192.168.1.10  
set subnet mask to 255.255.255.0  
set default gateway to 192.168.1.1  

2. For PC1:  
set IP@ to 155.165.1.10  
set subnet mask to 255.255.255.0  
set default gateway to 155.165.1.1  

## Routers configuration: 

#### Router0: 
Giving the right ip@ for each serial connection

1. Serial2/0:  
set IP@ to 10.0.0.2  
set subnet mask to 255.0.0.0  

2. Serial3/0:  
set IP@ to 20.0.0.1  
set subnet mask to 255.0.0.0  

#### Router1: 
Giving the right ip@ for each serial connection  

1. Serial2/0:  
set IP@ to 10.0.0.1    
set subnet mask to 255.0.0.0  

2. Serial3/0:  
set IP@ to 30.0.0.1  
set subnet mask to 255.0.0.0  
#### Router2: 
Giving the right ip@ for each serial connection

1. Serial2/0:  
set IP@ to 20.0.02  
set subnet mask to 255.0.0.0  

2. Serial3/0:  
set IP@ to 30.0.0.2  
set subnet mask to 255.0.0.0  

## Implementing OSPF protocol: 

1. Router 0:  
Router>en  
Router#conf t  
Router(config)#router ospf 1  
Router(config-router)#network 192.168.1.0 0.0.0.255 area 0  
Router(config-router)#network 10.0.0.0 0.255.255.255 area 0  
Router(config-router)#network 20.0.0.0 0.255.255.255 area 0   
Router(config-router)#exit  

1. Router 1:
Router>en  
Router#conf t  
Router(config)#router ospf 1    
Router(config-router)#network 10.0.0.0 0.255.255.255 area 0  
Router(config-router)#network 30.0.0.0 0.255.255.255 area 0  
Router(config-router)#exit  

1. Router 2:  
Router>en  
Router#conf t  
Router(config)#router ospf 1  
Router(config-router)#network 155.165.1.0 0.0.0.255 area 0  
Router(config-router)#network 20.0.0.0 0.255.255.255 area 0  
Router(config-router)#network 30.0.0.0 0.255.255.255 area 0  
Router(config-router)#exit  

## Summary:

Now PC0 and PC1 can communicate with the packet going through Router0 then to Router1.  
In the end this is a basic network architecture to get a deeper inspection on how OSPF should work.   