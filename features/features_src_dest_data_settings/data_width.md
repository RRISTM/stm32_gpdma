# Data Width

The GPDMA can set different data width for the source and destination. 
The options are:
* Byte
* Half Word
* Word
  
The main purpose is how bytes will be transfered for each request. Second purpose is to increment the address correctly after transfer. 

<awarning>
The GPDMA counting transfers in bytes. So event if it set to **Half Word** or **Word**. The size must be still in bytes. So dividable by 2 for **Half Word** and 4 for **Word**
</awarning>