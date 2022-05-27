# GPDMA priprity

## Access to bus

The GPDMA is connected to AHB by two ports. 
Port 0 and Port 1. 
The ports can work in paralell and arbitration is done separately for each port. 

![connection to bus](./img/14.svg)

See Allication port chapter. 

## Arbiter

Because GPDMA have multiple channels which cannot access the bus in same time the GPDMA must have arbiter functinality to decide which channel will be handled. For this each channels have settable prioority priority

## Prioritis

We have 4 priorities. For each priority the GPDMA have queue.
There are two descriptions. One used in MX which is more dewcriptive and second in Reference manual which operate only with queues. 

Very High priority (MX) is assigned to Queue 3
High priority (MX) is assigned to Queue 0-2
Medium priority (MX) is asigned to Queue 0-1
Low priority (MX) is assigned to Queue 0.

First we will look at Very High priority Queue. In Fixed priority arbiter. 

### Fixed priority arbiter (FPA)

![FPA](./img/15.svg)

The Very High requests are stored to Queue 3. This request have absolute priority and they will get granted access on port. 

<ainfo>
It is recomend use this only for critical task only. Because it can completly block other requests
</ainfo>

### Round Robin arbiter

If not Queue 3 request is present. A round robun arbiter is used to Queue 0-2

![RRA in](./img/16.svg)

Incoming High priority request is asigned to Queues 0-2. 
Medium priority request is asigned to Queue 0-1
Low priority request is asigned to Queue 0. 

The Low priority request have 50% smaller badnwith than Medium priotiry requests. And 33% bandwith than High priority requests. 

![RRA out](./img/17.svg)

The RRA is exacuting request from Queue 0, Queue 1, Queue 2 and again. 
Each time a request is handled is removed from all queues. 
