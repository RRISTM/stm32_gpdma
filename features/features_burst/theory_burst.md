# Single & Burst transfer

## Basic GPDMA functionality

The main GPDMA functionality is that we will select source address from where to read data. The destination address where will the those data transfered and how many bytes we want to transfer. This is called **block**

## Single transfer

For this block. In single mode each request there will be done one transfer from source to destination. 

## Burst transfer

We can specify also burst size. The single transfer is burst size 1. 
Is possible to select burst size up to 64. 
Which means upon one request we can transfer up to 64 elements.

<awarning>
This can be mainly used for M2M software requests. For request from peripherals the periphery must support this feature. 
</awarning>

