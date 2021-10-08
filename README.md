# Advanced Computer Networks - Lab 2 - Data Center Networking

Proof-of-conept using [containerlab](https://containerlab.srlinux.dev/) instead of GNS3 for our Data Center Networking Lab Intro, initially developed by Christoph Hardegen and Sebastian Rieger @ [Fulda University of Applied Sciences](https://hs-fulda.de/en/netlab). 

The lab shows three scenarios based on a diamond share topology using four virtual Arista cEOS switches. Scenario 1 uses only MSTP to establish the layer 2 topology, scenario 2 adds LACP and in scenario 3 MLAG is added. Students experiment with the scenarios using a lab sheet to see how many links can be actively used in each case. Afterwards a leaf-spine topology is discussed as previously covered in the theoretical content of the masters' course Advanced Computer Networks.

# Usage

You need to install containerlab to use this repo. See, e.g., [https://containerlab.srlinux.dev/install/]. Make sure that the pre-requisites are satisfied (access to a Linux host/VM with sudo/root privileges, [Docker](https://docs.docker.com/engine/install/) needs to be installed on the machine).

Get cEOS from [https://www.arista.com/en/support/software-download], if you do not have access to it already, you need to create an account. Afterwards, install the cEOS image on the host on which you installed containerlab:

    user@host:~$ sudo docker image install cEOS-lab-4.26.1F.tar.xz ceos:4.26.1F

Giving the version as a tag at the end of the command is optional, but allows you to use separate versions of cEOS or explicitly specify them. See the yml files in this repo to see the currently recommended and tested cEOS version for the lab.

    user@host:~$ sudo docker images | grep -E "ceos"
    ceos                              4.26.1F    787b1581728a   2 months ago   1.65GB
    ceosimage                         4.26.2F    71ddf2de968e   7 weeks ago    1.74GB

Run containerlab and use the scenarios.

# Lab Topologies and Scenarios

[Scenario 1 MSTP](scenario1-mstp.md)

[Scenario 2 LACP](scenario2-lacp.md)

[Scenario 3 MLAG](scenario3-mlag.md)

[Fabric / Leaf-Spine Topology](fabric.md)

## Hints, CLI help, SSH access, external/remote access

You can get help in the EOS Cli by typing "?", e.g., after command or directly in the console. You can also press &lt;TAB&gt; to 

    ceos1# show lldp nei?
    neighbors

    ceos1# ?
    agent              Configure agent settings
    bash               field engineer bash command
    cd                 Move to another directory
    ...

Use abbreviations of commands, as long as they are not ambiguous to speed up typing in the Cli

    ceos1# ena (enable)
    ceos1# conf t (configure terminal)
    ceos1# show run (show running-config)
    ceos1# show int sta (show interface status)

You can also use the management IP address and connect to it via SSH (cEOS default login: admin, password: admin) or even forward the ports of running container nodes to be able to access them from external networks, e.g., over the internet. See, e.g., [https://containerlab.srlinux.dev/manual/published-ports/].
