

******* dict******

@C1
conf t
vlan 31
name DICT.GOV.PH
Interface vlan 31
 desc DICT.GOV.PH
 no shut
 ip add 10.0.0.63 255.255.255.192
ip dhcp excluded-add 10.0.0.63 10.0.0.100
ip dhcp pool DICT.GOV.PH
 network 10.0.0.64 255.255.255.192
 default-router 10.0.0.63
domain-name DICT.GOV.PH
int e1/0
no shut
switchport access vlan 31
switchport mode access

@S1

conf t
int e1/0
no shut
ip add dhcp
do bp


**********DPWH**********
@C1
conf t
vlan 32
name DPWH.GOV.PH
Interface vlan 32
 desc DPWH.GOV.PH
 no shut
 ip add 10.0.32.1 255.255.224.0
ip dhcp excluded-add 10.0.32.1 10.0.32.100
ip dhcp pool DPWH.GOV.PH
 network 10.0.32.0 255.255.224.0
 default-router 10.0.32.1
domain-name DPWH.GOV.PH
end

@a1
conf t
int e0/0
no shut
switchport access vlan 32
switchport mode access

P1

conf t
int e0/0
no shut
ip add dhcp
do bp

*********DEPED.GOV.PH******


@C2
conf t
vlan 22
name PNP.GOV.PH
Interface vlan 34
 desc PNP.GOV.PH
 no shut
 ip add 10.0.64.1 255.255.192.0
ip dhcp excluded-add 10.0.64.1 10.0.16.100
ip dhcp pool PNP.GOV.PH
 network 10.0.64.0 255.255.192.0
 default-router 10.0.16.1
domain-name PNP.GOV.PH



do sh run | sec dhcp
end

@a2
conf t
int e1/0
no shut
switchport access vlan 22
switchport mode access

P2

conf t
int e1/0
no shut
ip add dhcp
do bp


****** fuel save ***
@C2
conf t
NO vlan 23
name FUELSAVE.COM
Interface vlan 23
 desc FUELSAVE.COM
 no shut
 ip add 10.0.2.1 255.255.254.0
ip dhcp excluded-add 10.0.2.1 10.0.2.100
ip dhcp pool FUELSAVE.COM
 network 10.0.2.0 255.255.254.0
 default-router 10.0.2.1
domain-name FUELSAVE.COM
do sh run | sec dhcp
end

@a2
conf t
int e1/0
no shut
switchport access vlan 23
switchport mode access

P2

conf t
int e1/0
no shut
ip add dhcp
do bp

