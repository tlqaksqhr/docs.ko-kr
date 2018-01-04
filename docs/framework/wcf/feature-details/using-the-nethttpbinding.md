---
title: "NetHttpBinding 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe134acf-ceca-49de-84a9-05a37e3841f1
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ca19446d286395a744496fa300ad1a72e504e738
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="using-the-nethttpbinding"></a><span data-ttu-id="618aa-102">NetHttpBinding 사용</span><span class="sxs-lookup"><span data-stu-id="618aa-102">Using the NetHttpBinding</span></span>
<span data-ttu-id="618aa-103"><xref:System.ServiceModel.NetHttpBinding>은 HTTP 또는 WebSocket 서비스를 사용하도록 디자인된 바인딩이며 기본적으로 이진 인코딩을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="618aa-103"><xref:System.ServiceModel.NetHttpBinding> is a binding designed for consuming HTTP or WebSocket services and uses binary encoding by default.</span></span> <span data-ttu-id="618aa-104"><xref:System.ServiceModel.NetHttpBinding>은 해당 바인딩이 HTTP 요청-회신 계약에 사용되는지 이중 계약에 사용되는지를 검색하고 그에 맞게 동작을 변경합니다. 요청-회신 계약에는 HTTP가 사용되고 이중 계약에는 WebSocket이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="618aa-104"><xref:System.ServiceModel.NetHttpBinding> will detect whether it is used with a request-reply contract or duplex contract and change its behavior to match - it will use HTTP for request-reply contracts and WebSockets for duplex contracts.</span></span> <span data-ttu-id="618aa-105">사용 하 여이 동작을 재정의할 수 있습니다는 <!--zz <xref:System.ServiceModel.NetHttpBinding.WebSocketTransportUsage%2A> --> `WebSocketTransportUsage` 설정:</span><span class="sxs-lookup"><span data-stu-id="618aa-105">This behavior can be overridden using the <!--zz <xref:System.ServiceModel.NetHttpBinding.WebSocketTransportUsage%2A> --> `WebSocketTransportUsage` setting:</span></span>  
  
1.  <span data-ttu-id="618aa-106">Always - 이 설정은 요청-회신 계약의 경우에도 WebSocket이 사용되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="618aa-106">Always - This forces WebSockets to be used even for request-reply contracts.</span></span>  
  
2.  <span data-ttu-id="618aa-107">Never - 이 설정은 WebSocket이 사용되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="618aa-107">Never - This prevents WebSockets from being used.</span></span> <span data-ttu-id="618aa-108">이 설정 상태에서 이중 계약을 사용하려고 시도하면 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="618aa-108">Attempting to use a duplex contract with this setting will result in an exception.</span></span>  
  
3.  <span data-ttu-id="618aa-109">WhenDuplex - 이 설정은 기본값이며 위에 설명된 대로 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="618aa-109">WhenDuplex - This is the default value and behaves as described above.</span></span>  
  
 <span data-ttu-id="618aa-110"><xref:System.ServiceModel.NetHttpBinding>은 HTTP 모드 및 WebSocket 모드에서 신뢰할 수 있는 세션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="618aa-110"><xref:System.ServiceModel.NetHttpBinding> supports reliable sessions in both HTTP mode and WebSocket mode.</span></span> <span data-ttu-id="618aa-111">WebSocket 모드에서는 세션이 전송에 의해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="618aa-111">In WebSocket mode sessions are provided by the transport.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="618aa-112"><xref:System.ServiceModel.NetHttpBinding>이 사용되고 바인딩의 TransferMode가 TransferMode.Streamed로 설정된 경우 큰 스트림으로 인해 교착 상태가 발생하고 호출이 시간 초과될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="618aa-112">When using the <xref:System.ServiceModel.NetHttpBinding> and the binding’s TransferMode is set to TransferMode.Streamed, large streams may cause a deadlock and the call will timeout.</span></span> <span data-ttu-id="618aa-113">이 문제를 해결하려면 보다 작은 메시지를 보내거나 TransferMode.Buffered를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="618aa-113">To work around this issue send smaller messages or use TransferMode.Buffered.</span></span>  
  
## <a name="configuring-a-service-to-use-nethttpbinding"></a><span data-ttu-id="618aa-114">NetHttpBinding을 사용하도록 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="618aa-114">Configuring a Service to use NetHttpBinding</span></span>  
 <span data-ttu-id="618aa-115">다른 바인딩과 동일하게 <xref:System.ServiceModel.NetHttpBinding>을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="618aa-115">The <xref:System.ServiceModel.NetHttpBinding> can be configured the same as any other binding.</span></span> <span data-ttu-id="618aa-116">다음 구성 조각에서는 <xref:System.ServiceModel.NetHttpBinding>을 사용하여 WCF 서비스를 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="618aa-116">The following configuration snippet illustrates how to configure a WCF service with <xref:System.ServiceModel.NetHttpBinding>.</span></span>  
  
```xml  
<system.serviceModel>  
    <services>  
      <service name="WcfService1.Service1">  
        <endpoint address=""  
                  binding="netHttpBinding"  
                  contract="WcfService1.IService1"/>  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange"/>  
      </service>  
    </services>  
    <bindings>  
      <netHttpBinding>  
        <binding name="My_NetHttpBindingConfig">  
          <webSocketSettings transportUsage="WhenDuplex"/>  
        </binding>  
      </netHttpBinding>  
    </bindings>  
    <!- ... -->   
  </system.serviceModel>  
```  
  
 <span data-ttu-id="618aa-117">다음 코드 조각에서는 코드로 <xref:System.ServiceModel.NetHttpBinding>을 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="618aa-117">The following code snippet shows how to add the <xref:System.ServiceModel.NetHttpBinding> in code.</span></span>  
  
```csharp  
ServiceHost svchost = new ServiceHost(typeof(Service1), baseAddress);  
            NetHttpBinding binding = new NetHttpBinding();  
            svchost.AddServiceEndpoint(typeof(IService1), binding, address);   
        }  
```  
  
## <a name="see-also"></a><span data-ttu-id="618aa-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="618aa-118">See Also</span></span>  
 [<span data-ttu-id="618aa-119">서비스에 대한 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="618aa-119">Configuring Bindings for Services</span></span>](../../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md)  
 [<span data-ttu-id="618aa-120">바인딩</span><span class="sxs-lookup"><span data-stu-id="618aa-120">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)  
 [<span data-ttu-id="618aa-121">시스템 제공 바인딩</span><span class="sxs-lookup"><span data-stu-id="618aa-121">System-Provided Bindings</span></span>](../../../../docs/framework/wcf/system-provided-bindings.md)  
 [<span data-ttu-id="618aa-122">이중 서비스</span><span class="sxs-lookup"><span data-stu-id="618aa-122">Duplex Services</span></span>](../../../../docs/framework/wcf/feature-details/duplex-services.md)
