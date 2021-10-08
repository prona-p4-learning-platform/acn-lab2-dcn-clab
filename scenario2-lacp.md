## Scenario 2

Currently needs approx. 3 GB of RAM. We're working on usign KSM/UKSM for the containers to leverage memory deduplication.

![Diagram of a 4 cEOS diamond shape network topology](scenario123.PNG)

Start the topology using, e.g.:

    user@host: cd acn-lab2-dcn-clab
    user@host: sudo clab deploy -t acn-dcn-scenario2-lacp.yml

Use the lab sheet to see how many links can be used in the topology. E.g. by using:

    ceos1# show running - config
    ceos1# show interfaces status
    ceos1# show spanning - tree [ blockedports | detail | bridge ]
    ceos1# show port - channel [ brief | detailed | traffic | summary ]

Shutdown links and examine the effect of the topology.

    ceos1# configure terminal
    ceos1(config)# interface <interface> (e.g., Ethernet X, Port - Channel Y)
    ceos1(config-if-Et1)# shutdown | no shutdown

Undeploy the topology and the containers:

    user@host: sudo clab destroy -t acn-dcn-scenario2-lacp.yml

## Discussion

* What are the benefits of LACP?
* How many links are active in each scenario?

[Next: Scenario 3](scenario3-mlag.md)