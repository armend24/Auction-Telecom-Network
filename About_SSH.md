While devices can be configured on directly, they can also be configured remotely by authorized persons.
This is made possible through SSH(Secure Shell), a protocol which enables secure remote access to devices, over an untrusted network. SSH achieves this through encryption and autentification.
Below is the SSH(Secure Shell) configuration.


R1(config)#banner motd 'Welcome to the inner core of the Top Router'
R1(config)#ip domain-name admin.org
R1(config)#username benita secret Maloku
R1(config)#username armend secret Bytyqi
R1(config)#service password-encryption 
R1(config)#crypto key generate rsa
The name for the keys will be: R1.admin.org
Choose the size of the key modulus in the range of 360 to 4096 for your
  General Purpose Keys. Choosing a key modulus greater than 512 may take
  a few minutes.

How many bits in the modulus [512]: 1024
% Generating 1024 bit RSA keys, keys will be non-exportable...[OK]

R1(config)#ip ssh version 2
*Mar 1 1:21:18.947: %SSH-5-ENABLED: SSH 1.99 has been enabled
R1(config)#line vty 0 15
R1(config-line)#transport input ssh
R1(config-line)#login local 
R1(config-line)#


Some of the commands we used to ensure functionality:
-show ssh
-show crypto key mypubkey rsa

PC PT - Desktop - Command Prompt:
C:\> ssh -l <username> <ip address>

Password: <secret>

