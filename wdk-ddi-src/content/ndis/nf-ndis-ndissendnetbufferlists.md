---
UID: NF:ndis.NdisSendNetBufferLists
title: NdisSendNetBufferLists function (ndis.h)
description: Protocol drivers call the NdisSendNetBufferLists function to send network data that is contained in a list of NET_BUFFER_LIST structures.
old-location: netvista\ndissendnetbufferlists.htm
tech.root: netvista
ms.assetid: f615acc4-7e3e-4390-8a6a-e68663fcc162
ms.date: 05/02/2018
ms.keywords: NdisSendNetBufferLists, NdisSendNetBufferLists function [Network Drivers Starting with Windows Vista], ndis/NdisSendNetBufferLists, ndis_sendrcv_ref_c63c443f-ecd0-4ff3-8a60-b25cef2a5cd3.xml, netvista.ndissendnetbufferlists
f1_keywords:
 - "ndis/NdisSendNetBufferLists"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_SendRcv_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisSendNetBufferLists
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisSendNetBufferLists function


## -description


Protocol drivers call the 
  <b>NdisSendNetBufferLists</b> function to send network data that is contained in a list of 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures.


## -parameters




### -param NdisBindingHandle [in]

A handle that identifies the target adapter. A previous call to 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a> returned this
     handle.


### -param NetBufferLists [in]

A pointer to a linked list of 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures. Each
     NET_BUFFER_LIST structure describes a list of 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structures.


### -param PortNumber [in]

A port number that identifies a miniport adapter port. The default port number of a miniport
     adapter is zero. Protocol drivers that do not use miniport adapter ports should specify the default
     port.


### -param SendFlags [in]

Flags that define attributes for the send operation. The flags can be combined with an OR
     operation. To clear all the flags, set this member to zero. This function supports the following flags:
     





#### NDIS_SEND_FLAGS_DISPATCH_LEVEL

Specifies that the current IRQL is DISPATCH_LEVEL. For more information about this flag, see 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/network/dispatch-irql-tracking">Dispatch IRQL Tracking</a>.



#### NDIS_SEND_FLAGS_CHECK_FOR_LOOPBACK

Specifies that NDIS should check for loopback. By default, NDIS does not loop back data to the
       driver that submitted the send request. An overlying driver can override this behavior by setting this
       flag. When this flag is set, NDIS identifies all the NET_BUFFER structures that contain data that
       matches the receive criteria for the binding. NDIS indicates NET_BUFFER structures that match the
       criteria to the overlying driver. This flag has no effect on checking for loopback, or looping back,
       on other bindings.


## -remarks



After a protocol driver calls 
    <b>NdisSendNetBufferLists</b>, NDIS submits the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures to an underlying
    driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_send_net_buffer_lists">
    MiniportSendNetBufferLists</a> function.

The protocol driver must allocate each NET_BUFFER_LIST structure from a pool by calling one of the
    following functions:

<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlist">NdisAllocateNetBufferList</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferandnetbufferlist">
       NdisAllocateNetBufferAndNetBufferList</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocateclonenetbufferlist">
       NdisAllocateCloneNetBufferList</a>


</li>
</ul>
The protocol driver can preallocate NET_BUFFER_LIST structures--for example, in its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine. Alternatively, the driver,
    can allocate the structures just prior to calling 
    <b>NdisSendNetBufferLists</b> and then free them when the send operation is complete. When NDIS returns a
    NET_BUFFER_LIST structure to 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_send_net_buffer_lists_complete">
    ProtocolSendNetBufferListsComplete</a>, the miniport driver can prepare the NET_BUFFER_LIST structure
    and any associated resources for reuse. Reusing the NET_BUFFER_LIST structures can yield better
    performance than returning the structures to a pool and then reallocating them for another send
    operation.

A protocol driver must set the 
    <b>SourceHandle</b> member of each NET_BUFFER_LIST structure to the same value that it passes to the 
    <i>NdisBindingHandle</i> parameter. The binding handle provides the information that
    NDIS requires to return the NET_BUFFER_LIST structure to the protocol driver after the underlying
    miniport driver calls 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsendnetbufferlistscomplete">
    NdisMSendNetBufferListsComplete</a>.

Before calling 
    <b>NdisSendNetBufferLists</b>, a protocol driver can set information that accompanies the send request
    with the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-list-info">NET_BUFFER_LIST_INFO</a> macro . The
    underlying driver can retrieve this information with the NET_BUFFER_LIST_INFO macro.

Before a protocol driver calls 
    <b>NdisSendNetBufferLists</b> with a list of NET_BUFFER_LIST structures, the protocol driver must ensure
    that the NET_BUFFER_LIST structures are set up in the order that the network data should be sent over the
    wire.

As soon as a protocol driver calls 
    <b>NdisSendNetBufferLists</b>, it relinquishes ownership of the NET_BUFFER_LIST structures and all
    associated resources. NDIS calls the 
    <i>ProtocolSendNetBufferListsComplete</i> function to return the structures and data
    to the protocol driver. NDIS can collect the structures and data from multiple send requests into a
    single linked list of NET_BUFFER_LIST structures before it passes the list to 
    <i>ProtocolSendNetBufferListsComplete.</i>

Until NDIS calls 
    <i>ProtocolSendNetBufferListsComplete</i>, the current status of a
    protocol-driver-initiated send is not available to the protocol driver. A protocol driver temporarily
    releases ownership of all resources that it allocated for a send request when it calls 
    <b>NdisSendNetBufferLists</b>. A protocol driver should 
    <i>never</i> attempt to examine the NET_BUFFER_LIST structures or any associated data
    after calling 
    <b>NdisSendNetBufferLists</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_send_net_buffer_lists">MiniportSendNetBufferLists</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-list-info">NET_BUFFER_LIST_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocateclonenetbufferlist">
   NdisAllocateCloneNetBufferList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferandnetbufferlist">
   NdisAllocateNetBufferAndNetBufferList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlist">NdisAllocateNetBufferList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismallocateport">NdisMAllocatePort</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsendnetbufferlistscomplete">
   NdisMSendNetBufferListsComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_send_net_buffer_lists_complete">
   ProtocolSendNetBufferListsComplete</a>
 

 

