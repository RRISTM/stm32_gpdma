# GPDMA requests

The GPDMA is reacting upon request. 
We have two main options for requests. 
* Software request
* Hardware request

## Software request 

In this mode the GPDMA is creating requests automatically. When last transfer is complete new request is created. 
This is mainly useful when we want to transfer data from one memory to second memory. 

![m2m transfer](./img/hw_m2m_request.json)

## Hardware request

Here the GPDMA request is comming from other peripheries. 
Like from ADC when data are ready. 

![rx transfer](./img/hw_rx_request.json)

Or from memory to UART where there are data in RX register

![tx transfer](./img/hw_tx_request.json)

<ainfo>
The request can be still combined with GPDMA triggers to condition this request
</ainfo>