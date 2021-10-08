## Scenario 3

Currently needs approx. 3 GB of RAM. We're working on usign KSM/UKSM for the containers to leverage memory deduplication.

![Diagram of a 4 cEOS diamond shape network topology](scenario123.PNG)

Start the topology using, e.g.:

    user@host: cd acn-lab2-dcn-clab
    user@host: sudo clab deploy -t acn-dcn-scenario3-mlag.yml

Use the lab sheet to see how many links can be used in the topology. E.g. by using:

See how MLAG can be used to aggregate links in the topology.

    ceos1# show mlag [ detail ]
    ceos1# show mlag interfaces [ detail ]

Undeploy the topology and the containers:

    user@host: sudo clab destroy -t acn-dcn-scenario3-mlag.yml

## Discussion

* What are the benefits of MLAG?
* How many links are active in each scenario?
* How can fabrics/leaf-spine topologies be used to further improve the situation, e.g., as required for data center networking?

[Next: Fabric](fabric.md)