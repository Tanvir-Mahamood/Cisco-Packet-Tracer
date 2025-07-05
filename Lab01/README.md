# <p align='center'> Building a Simple Network </p>
## Topology
<p align='center'>

| |
|-----|
| ![Topology](topology.jpg) |

</p>

## Addressing Table 
| Device | Interface | IP Address   | Subnet Mask   |
|--------|-----------|--------------|---------------|
| PC0    | NIC       | 192.168.1.10 | 255.255.255.0 |
| PC1    | NIC       | 192.168.1.11 | 255.255.255.0 |

## Objectives 
- Part 1: Initializing and Reloading Switch.
- Part 2: Set Up the Network Topology (Ethernet only) 
- Part 3: Configure PC Hosts 
- Part 4: Configure and Verify Basic Switch Settings 
- Part 5: Login and Logout Switch

## Background / Scenario 
Networks are constructed of three major components: hosts, switches, and routers. In this lab, you will build a 
simple network with two hosts and two switches. You will also configure basic settings including hostname, 
local passwords, and login banner. Use show commands to display the running configuration, IOS version, 
and interface status. Use the copy command to save device configurations. 
You will apply IP addressing for this lab to the PCs to enable communication between these two devices. Use 
the ping utility to verify connectivity.

> [!NOTE]
>  The switches used are Cisco Catalyst 2960s with Cisco IOS Release 15.0(2) (lanbasek9 image). Other 
switches and Cisco IOS versions can be used. Depending on the model and Cisco IOS version, the 
commands available and output produced might vary from what is shown in the labs.

> [!NOTE]
>  Make sure that the switches have been erased and have no startup configurations. Refer to Appendix A 
for the procedure to initialize and reload a switch. 

## Required Resources 
- 2 Switches (Cisco 2960 with Cisco IOS Release 15.0(2) lanbasek9 image or comparable) 
- 2 PCs 
- Console cables to configure the Cisco IOS devices via the console ports 
- Ethernet cables as shown in the topology 


> [!NOTE]
>  The Ethernet ports on the 2960 switches are autosensing and will accept either a straight
through or a cross-over cable for all connections. If the switches used in the topology are other than the 2960 
model, then it is likely that a cross-over cable will be needed to connect the two switches.

## Procedures:

### Part1: Initializing and Reloading Switch
[Read only <Part 3: Initialize the Switch and Reload> and return here. ](/Initialize%20and%20Reload/README.md#Part-3-Initialize-the-Switch-and-Reload)

### Part2: Set Up the Network Topology (Ethernet only) 
> [!NOTE]
> The Ethernet ports on the 2960 switches are autosensing and will accept either a straight through or a cross-over cable for all connections. If the switches used in the topology are other than the 2960  model, then it is likely that a cross-over cable will be needed to connect the two switches. 

1. **Power on the devices.** <br>
   Power on all devices in the topology. The switches do not have a power switch; they will power on as soon as you plug in the power cord. 
2. **Connect the two switches.** <br> 
   Connect one end of an Ethernet cable to F0/1 on S1 and the other end of the cable to F0/1 on S2. You should  see the lights for F0/1 on both switches turn amber and then green. This indicates that the switches have been connected correctly. 
3. **Connect the PCs to their respective switches.** <br> 
   - Connect one end of the second Ethernet cable to the NIC port on PC-A. Connect the other end of the  cable to F0/6 on S1. After       connecting the PC to the switch, you should see the light for F0/6 turn amber 
     and then green, indicating that PC-A has been connected correctly.    
   - Connect one end of the last Ethernet cable to the NIC port on PC-B. Connect the other end of the cable 
     to F0/18 on S2. After connecting the PC to the switch, you should see the light for F0/18 turn amber and 
     then green, indicating that the PC-B has been connected correctly.
4. **Visually inspect network connections.** <br> 
   After cabling the network devices, take a moment to carefully verify the connections to minimize the time 
   required to troubleshoot network connectivity issues later.
### Part3: Configure PC Hosts 
1. **Set the IP addresss to each host as instructed.**

### Part4: Configure and Verify Basic Switch Settings 
1. **Console into the switch.** <br>
   Using Tera Term, establish a console connection to the switch from PC-A. 

2. **Enter privileged EXEC mode.** <br>
   You can access all switch commands in privileged EXEC mode. The privileged EXEC command set includes those commands contained in user EXEC mode, as well as the configure command through which access to the remaining command modes are gained. Enter privileged EXEC mode by entering the enable command. 
   ```bash
   Switch> enable 
   Switch# 
   ```

   The prompt changed from Switch> to Switch# which indicates privileged EXEC mode. 

3. **Enter configuration mode.** <br> 
   Use the configuration terminal command to enter configuration mode. 
   ```bash
   Switch# configure terminal 
   ```

   Enter configuration commands, one per line. End with CNTL/Z. 
   ```bash
   Switch(config)# 
   The prompt changed to reflect global configuration mode. 
   ```

4. **Give the switch a name.** <br> 
   Use the hostname command to change the switch name to S1. 
   ```bash
   Switch(config)# hostname S1 
   S1(config)# 
   ```

5. **Prevent unwanted DNS lookups.** <br> 
   To prevent the switch from attempting to translate incorrectly entered commands as though they were hostnames, disable the Domain Name System (DNS) lookup. 
   ```bash
   S1(config)# no ip domain-lookup 
   S1(config)# 
   ```

6. **Enter local passwords.** <br> 
   To prevent unauthorized access to the switch, passwords must be configured. 
   ```bash
   S1(config)# enable secret class 
   S1(config)# line con 0 
   S1(config-line)# password cisco 
   S1(config-line)# login 
   S1(config-line)# exit 
   S1(config)# 
   ```

7. **Enter a login MOTD banner.** <br> 
   A login banner, known as the message of the day (MOTD) banner, should be configured to warn anyone accessing the switch that unauthorized access will not be tolerated. The banner motd command requires the use of delimiters to identify the content of the banner message. The  delimiting character can be any character as long as it does not occur in the message. For this reason, symbols, such as the #, are often used. 
   ```bash
   S1(config)# banner motd # 
   Enter TEXT message. End with the character '#'. 
   Unauthorized access is strictly prohibited and prosecuted to the full extent of the law. # 
   S1(config)# exit 
   S1# 
   ```

8. **Save the configuration.** <br>
   Use the copy command to save the running configuration to the startup file on non-volatile random access memory (NVRAM). 
   ```bash
   S1# copy running-config startup-config 
   Destination filename [startup-config]? [Enter] 
   Building configuration... 
   [OK] 
   S1#
   ```

9. **Display the current configuration.** <br>
   The show running-config command displays the entire running configuration, one page at a time. Use the spacebar to advance paging. The commands configured in Steps 1 – 8 are highlighted below. 
   ```bash
   S1# show running-config 
   ```

10. **Display the IOS version and other useful switch information.** <br>
    Use the show version command to display the IOS version that the switch is running, along with other useful information. Again, you will  need to use the spacebar to advance through the displayed information. 
    ```bash
    S1# show version 
    ```
  
11. **Display the status of the connected interfaces on the switch.** <br>
    To check the status of the connected interfaces, use the show ip interface brief command. Press the spacebar to advance to the end of the list. 
    ```bash
    S1# show ip interface brief
    ```

12. **Repeat these same process to configure second switch.** <br>
    The only difference for this step is to change the hostname to S2.


### Part 5: Login and Logout Switch
<h3><p align='center'> Login </p></h3>
Connect a pc with S1 using console cable.the console cable is what gives terminal access (for initial configuration and login). 
The Ethernet cable is for network communication (ping, telnet, etc.).

1. Click on PC0 in Packet Tracer.
2. Click Desktop tab.
3. Click Terminal.
4. Leave the default settings (Baud rate: 9600, etc.) → Click OK.
5. If the switch is correctly configured, you'll see:
```makefile
User Access Verification
Password: cisco
```

6. Then, to enter privileged EXEC mode:
```pgsql
Switch> enable
Password: class
```

📝 Important Notes
✅ You configured:
```bash
line con 0
password cisco
login
```

That means the console access now requires password `cisco`.

✅ You configured:

```bash
enable secret class
```

That means enable mode requires password `class`.

### How to logout?
Type: 
```bash
exit
```
