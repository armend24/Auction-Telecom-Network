In this network, the devices communicate thanks to the OSPF routing protocol.
OSPF (Open Shortest Path First) is a dynamic link-state routing protocol that efficiently exchanges routing information within an autonomous system, employing the Shortest Path First (SPF) algorithm to calculate optimal routes.
Below are the commands used to configure OSPF on each router.

Router1 Configuration:

R1(config-if)#ip add 1.1.1.1 255.255.255.255
R1(config-if)#exit
R1(config)#
R1(config)#router ospf 1
R1(config-router)#network 192.168.49.0 0.0.0.255 area 0
R1(config-router)#network 70.70.0.0 0.0.0.3 area 0
R1(config-router)#network 203.0.114.0 0.0.0.63 area 0
R1(config-router)#exit
R1(config)#



Router2 Configuration:

R2(config)#router ospf 1
R2(config-router)#network 192.168.52.0 0.0.0.31 area 0
R2(config-router)#network 192.168.51.0 0.0.0.63 area 0
R2(config-router)#network 77.77.0.0 0.0.0.3 area 0
R2(config-router)#network 70.70.0.0 0.0.0.3 area 0
R2(config-router)#
R2(config-router)#exit
R2(config)#


Router3 Configuration:

R3(config)#router ospf 1
R3(config-router)#network 77.77.0.0 0.0.0.3 area 0	
R3(config-router)#network 192.168.53.0 0.0.0.15 area 0
R3(config-router)#network 192.168.50.0 0.0.0.127 area 0
R3(config-router)#
R3(config-router)#exit
R3(config)#


Some of the commands we used to verify functionality and troubleshoot OSPF are:
-show ip ospf neighbor
-show ip ospf route
-show ip ospf interface

