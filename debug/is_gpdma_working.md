# Is the GPDMA working?

To detect if the GPDMA is working or not is possible to check **IDLE** flag in CxSR(channel X status register). 
If the **IDLE** flag is set the GPDMA channel is stopped and will not work. 

There can be few reasons for it. 

1. The GPDMA have only one note do execude without link and it is finished
2. The error in configuration occurs and the GPDMA stopped with user setting error **USEF**

3. The GPDMA cannot transfer into or from selected destination (can happen in LPDMA limited to LP domain) this will trigger **DTEF** flag

4. New node in link is not possible to load this will trigger **ULEF** flag. 
   