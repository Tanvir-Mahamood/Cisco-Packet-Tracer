# Cisco Packet Tracer (Computer Network Lab)
This repository contains .pkt simulation files created using Cisco Packet Tracer for various computer network lab exercises. It is intended to support students and enthusiasts who want to practice and explore the fundamentals of computer networking through simulation.

## 📚 Basic Definitions
Before diving into the simulations, here are a few essential terms in computer networking:

- **Computer Network:** A computer network is a group of interconnected computers that share resources and information. These networks can be wired or wireless and vary in scale from small local networks (LANs) to wide-area networks (WANs) like the Internet.

- **Host:** A host is any device (such as a computer, server, or smartphone) that can send or receive data on a network. Each host typically has an IP address for identification.

- **Router:** A router is a network device that connects different networks together. It forwards data packets between computer networks and determines the best path for data to travel.

- **Switch:** A switch is a device that connects multiple devices within the same network (usually a LAN) and uses MAC addresses to forward data to the correct destination.

- **Packet Tracer:** Cisco Packet Tracer is a powerful simulation tool developed by Cisco that allows users to create virtual network topologies, configure devices, and simulate network behavior without physical hardware.

🔌 Cables:
- **Console Cable (Roll-over Cable)** <br>
Purpose: Used to configure or manage a network device like a switch or router via Command-Line Interface (CLI).
Connection: From the PC's serial/USB port to the console port of a router or switch.
Usage: Not for data transfer between network devices, only for initial setup, maintenance, or troubleshooting.
Typical Tools: Terminal software like PuTTY, Tera Term, or Cisco Packet Tracer.
Example: You use a console cable to connect your PC to a switch to set IP address, enable interfaces, etc.

- **Straight-Through Cable (Ethernet Cable)** <br>
Purpose: Connect different types of devices.
Connection Examples:
   ```
   PC ↔ Switch
   Router ↔ Switch
   PC ↔ Hub
   ```

   Wire Configuration: Pins on both ends have the same color order (T568A–T568A or T568B–T568B).
   Usage: Most commonly used for connecting end devices to the network infrastructure.
   Example: Connecting your laptop to a LAN port on a switch.

3. Crossover Cable
Purpose: Connect similar types of devices directly, without a switch in between.
Connection Examples:
   ```
   PC ↔ PC
   Switch ↔ Switch
   Router ↔ Router
   ```

   Wire Configuration: One end is T568A, the other end is T568B.
   Usage: Allows data to cross over transmit and receive lines directly.
   Example: Two computers communicating directly with each other for file sharing without a switch.

## 🛠️ Installation Guide: Cisco Packet Tracer
To run the .pkt files provided in this repository, you need to have Cisco Packet Tracer installed on your system.

### 🔽 Step 1: Download
Visit the official [Cisco Networking Academy site](https://www.netacad.com/)
Create a free account (if you don't have one).
Navigate to `Resources → Download Packet Tracer` after logging in.
Download the appropriate version for your operating system (Windows/Linux/macOS).

> [!NOTE]
> I have installed Cisco Packet Tracer v8.2.2 from [here](https://www.netacad.com/articles/news/download-cisco-packet-tracer).

### 💻 Step 2: Install
- Windows:
  Run the .exe installer and follow the setup instructions.
  After installation, log in using your NetAcad credentials.

- Linux:
  - Download the .deb or .tar.gz file depending on your distro.
  - Install using the terminal (sudo dpkg -i file_name.deb) or extract and run the binary.


# Tasks
| Lab No            | Name of Experiment        | Procedures in details          |
|-------------------|---------------------------|--------------------------------|
| [Lab 00](/Initialize%20and%20Reload/) | Initializing & Reloading a Router and Switch | [Click here](/Initialize%20and%20Reload/README.md)
| [Lab 01](/Lab01/) | Building a Simple Network | [Click Here](/Lab01/README.md) |
| [Lab 02](/Lab02/) | Configuring a Switch Management Address  | [Click Here](/Lab02/README.md) |
| [Lab 03](/Lab03/) | Building a Switch and Router Network <br> [6.4.1.3 Packet Tracer - Configure Initial Router Settings.pka](/Activity%20Files/6.4.1.3%20Packet%20Tracer%20-%20Configure%20Initial%20Router%20Settings.pka) <br> [6.4.3.3 Packet Tracer - Connect a Router to a LAN.pka](/Activity%20Files/6.4.3.3%20Packet%20Tracer%20-%20Connect%20a%20Router%20to%20a%20LAN.pka) | [Click Here for first file](/Lab03/README.md) |
| Lab 04 | [8.1.4.7 Packet Tracer - Subnetting Scenario.pka](/Activity%20Files/8.1.4.7%20Packet%20Tracer%20-%20Subnetting%20Scenario.pka) <br> [8.1.4.7 Packet Tracer - Subnetting Scenario 1.pka](/Activity%20Files/8.1.4.7%20Packet%20Tracer%20-%20Subnetting%20Scenario%201.pka) <br> [8.2.1.4 Packet Tracer - Designing and Implementing a VLSM Addressing Scheme.pka](/Activity%20Files/8.2.1.4%20Packet%20Tracer%20-%20Designing%20and%20Implementing%20a%20VLSM%20Addressing%20Scheme.pka) | |
| Lab 05 | [Configuring Secure Passwords and SSH.pka](/Activity%20Files/Configuring%20Secure%20Passwords%20and%20SSH.pka) <br> [DNS and DHCP.pka](/Activity%20Files/DNS%20and%20DHCP.pka) <br> [FTP.pka](/Activity%20Files/FTP.pka) <br> [Web and Email.pka](/Activity%20Files/Web%20and%20Email.pka) | |
| [Lab 06](/Lab07/) | Accessing Network Devices with SSH <br> Securing Network Devices | [Click Here](/Lab07/README.md) |
| [Lab 07](/Lab08/) | Configuring A Basic Network | [Click Here](/Lab08/README.md) |
| Lab 08 | [Configuring Floating Static Routes](/Activity%20Files/2.2.5.5%20Packet%20Tracer%20-%20Configuring%20Floating%20Static%20Routes.pka) <br> [Configuring RIPv2](/Activity%20Files/3.2.1.8%20Packet%20Tracer%20-%20Configuring%20RIPv2.pka) | |


## 📝 License

This project is licensed under the [MIT License](./LICENSE). Feel free to use, modify, and distribute the lab files for educational purposes.