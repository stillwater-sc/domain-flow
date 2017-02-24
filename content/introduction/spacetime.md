+++
weight = 4
title = "Spacetime"
date = "2017-02-15T06:58:22-05:00"
toc = true
next = "/introduction/computational-spacetime"
prev = "/introduction/parallel-programming"

tags = [ "spacetime" ]
categories = [ "spacetime", "introduction" ]
series = [ "introduction" ]

+++

If you try to visualize the 'world' from the perspective of an operand flowing through a machine, you realize
that a physical machine creates a specific spatial constraint for the movement of program and data. 
Processing nodes are fixed in space, and information is exchanged between nodes to accomplish some transformation;
we have nodes to generate operands and communication lanes between the nodes to send operands (or programs) around.
This leads to a simple abstraction of a parallel machine consisting of a fixed graph in space that constrains
computation and communication events generated by the parallel algorithm. 

Just like it takes time to compute, it takes time to communicate. 
In an expression, such as, $c = a + b$ we are familiar with the progression of time for the add operation, 
but the assignment operation, which represents the exchange of information and is equivalent to the communication phase,
is taking time just the same. It is this time relationship, the ratio between computational delay and communication delay
that impacts the structure of the optimal parallel algorithm.

Technology impacts the performance of both computation and communication, but in very different ways. Typically,
computational performance, being governed by miniaturization of VLSI manufacturing process geometries, improves
more rapidly than communication performance, which tends to be governed by system integration constraints that
are external to the chip. If we revisit the spatial graph of a parallel machine in our thought experiment, an
improvement in the performance of the computation relative to the communication of information changes the trade-off
between computation and communication in the parallel algorithm. In the vocabulary of spacetime, remote nodes
move farther away. Spacetime has another geometric interpretation of the relationship between space and time, called
the spacetime light cone, as shown here:

{{< figure src="/images/spacetime-light-cone.png" title="Spacetime Light Cone" >}}

The spacetime light cone is a visual mnemomic device to think about which events in spacetime can affect each other.
Parallel computation is the distribution of information to create some useful transformation and is constrained by
the propagation of information. A computational event has to be able 'see' its operands before it could commence. 
Otherwise stated, its operands need to lie in the future cone. 
This is all complicated by the fact that man-made structures today do not communicate through free space yet,
and the physical communication structure adds additional constraints on the shape and extend of the future cone.
These man-made computational structures are dubbed _computational spacetimes_.