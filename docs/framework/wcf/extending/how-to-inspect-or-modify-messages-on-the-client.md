---
title: "방법: 클라이언트에서 메시지 검사 또는 수정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b8256335-f1c2-419f-b862-9f220ccad84c
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 164e19891e576b6d310839a1221ad8ed0d315444
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-inspect-or-modify-messages-on-the-client"></a><span data-ttu-id="e41b5-102">방법: 클라이언트에서 메시지 검사 또는 수정</span><span class="sxs-lookup"><span data-stu-id="e41b5-102">How to: Inspect or Modify Messages on the Client</span></span>
<span data-ttu-id="e41b5-103">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 구현하고 클라이언트 런타임에 삽입하여 들어오거나 보내는 메시지를 <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>에서 검사하거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e41b5-103">You can inspect or modify the incoming or outgoing messages across a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client by implementing a <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType> and inserting it into the client runtime.</span></span> <span data-ttu-id="e41b5-104">자세한 내용은 참조 [클라이언트 확장](../../../../docs/framework/wcf/extending/extending-clients.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e41b5-104">For more information, see [Extending Clients](../../../../docs/framework/wcf/extending/extending-clients.md).</span></span> <span data-ttu-id="e41b5-105">서비스의 해당 기능은 <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="e41b5-105">The equivalent feature on the service is the <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e41b5-106">전체 코드 예제에 대 한 참조는 [메시지 검사자](../../../../docs/framework/wcf/samples/message-inspectors.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="e41b5-106">For a complete code example see the [Message Inspectors](../../../../docs/framework/wcf/samples/message-inspectors.md) sample.</span></span>  
  
### <a name="to-inspect-or-modify-messages"></a><span data-ttu-id="e41b5-107">메시지를 검사하거나 수정하려면</span><span class="sxs-lookup"><span data-stu-id="e41b5-107">To inspect or modify messages</span></span>  
  
1.  <span data-ttu-id="e41b5-108"><xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType> 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="e41b5-108">Implement the <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType> interface.</span></span>  
  
2.  <span data-ttu-id="e41b5-109">클라이언트 메시지 검사자를 삽입하려는 범위에 따라 <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> 또는 <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="e41b5-109">Implement a <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> or <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> depending upon the scope at which you want to insert the client message inspector.</span></span> <span data-ttu-id="e41b5-110"><xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>끝점 수준에서 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e41b5-110"><xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> allows you to change behavior at the endpoint level.</span></span> <span data-ttu-id="e41b5-111"><xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>계약 수준에서 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e41b5-111"><xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> allows you to change behavior at the contract level.</span></span>  
  
3.  <span data-ttu-id="e41b5-112"><xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType>에서 <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> 또는 <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> 메서드를 호출하여 동작을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="e41b5-112">Insert the behavior prior to calling the <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> or the <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> method on the <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e41b5-113">자세한 내용은 참조 [구성 하 고 런타임 동작을 확장](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e41b5-113">For details, see [Configuring and Extending the Runtime with Behaviors](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e41b5-114">예제</span><span class="sxs-lookup"><span data-stu-id="e41b5-114">Example</span></span>  
 <span data-ttu-id="e41b5-115">다음 코드 예제는 아래 순서대로 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e41b5-115">The following code examples show, in order:</span></span>  
  
-   <span data-ttu-id="e41b5-116">클라이언트 검사자 구현.</span><span class="sxs-lookup"><span data-stu-id="e41b5-116">A client inspector implementation.</span></span>  
  
-   <span data-ttu-id="e41b5-117">검사자를 삽입하는 끝점 동작.</span><span class="sxs-lookup"><span data-stu-id="e41b5-117">An endpoint behavior that inserts the inspector.</span></span>  
  
-   <span data-ttu-id="e41b5-118">구성 파일에 동작을 추가하는 데 사용할 수 있는 <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> 파생 클래스.</span><span class="sxs-lookup"><span data-stu-id="e41b5-118">A <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>- derived class that allows you to add the behavior in a configuration file.</span></span>  
  
-   <span data-ttu-id="e41b5-119">클라이언트 메시지 검사자를 클라이언트 런타임에 삽입하는 끝점 동작을 추가하는 구성 파일.</span><span class="sxs-lookup"><span data-stu-id="e41b5-119">A configuration file that adds the endpoint behavior which inserts the client message inspector into the client runtime.</span></span>  
  
```csharp  
// Client message inspector  
public class SimpleMessageInspector : IClientMessageInspector  
{  
    public void AfterReceiveReply(ref System.ServiceModel.Channels.Message reply, object correlationState)  
    {  
        // Implement this method to inspect/modify messages after a message  
        // is received but prior to passing it back to the client   
        Console.WriteLine("AfterReceiveReply called");  
    }  
  
    public object BeforeSendRequest(ref System.ServiceModel.Channels.Message request, IClientChannel channel)  
    {  
        // Implement this method to inspect/modify messages before they   
        // are sent to the service  
        Console.WriteLine("BeforeSendRequest called");  
        return null;  
    }  
}  
```  
  
```csharp  
// Endpoint behavior  
public class SimpleEndpointBehavior : IEndpointBehavior  
{  
    public void AddBindingParameters(ServiceEndpoint endpoint, System.ServiceModel.Channels.BindingParameterCollection bindingParameters)  
    {  
         // No implementation necessary  
    }  
  
    public void ApplyClientBehavior(ServiceEndpoint endpoint, ClientRuntime clientRuntime)  
    {  
        clientRuntime.MessageInspectors.Add(new SimpleMessageInspector());  
    }  
  
    public void ApplyDispatchBehavior(ServiceEndpoint endpoint, EndpointDispatcher endpointDispatcher)  
    {  
         // No implementation necessary  
    }  
  
    public void Validate(ServiceEndpoint endpoint)  
    {  
         // No implementation necessary  
    }  
}  
```  
  
```csharp  
// Configuration element   
public class SimpleBehaviorExtensionElement : BehaviorExtensionElement  
{  
    public override Type BehaviorType  
    {  
        get { return typeof(SimpleEndpointBehavior); }  
    }  
  
    protected override object CreateBehavior()  
    {  
         // Create the  endpoint behavior that will insert the message  
         // inspector into the client runtime  
        return new SimpleEndpointBehavior();  
    }  
}  
```  
  
```xml
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
    <system.serviceModel>  
        <client>  
            <endpoint address="http://localhost:8080/SimpleService/"   
                      binding="wsHttpBinding"  
                      contract="ServiceReference1.IService1"  
                      name="WSHttpBinding_IService1"/>  
        </client>  
  
      <behaviors>  
        <endpointBehaviors>  
          <behavior name="clientInspectorsAdded">  
            <simpleBehaviorExtension />  
          </behavior>  
        </endpointBehaviors>  
      </behaviors>  
      <extensions>  
        <behaviorExtensions>  
          <add  
            name="simpleBehaviorExtension"  
            type="SimpleServiceLib.SimpleBehaviorExtensionElement, Host, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
        </behaviorExtensions>  
      </extensions>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e41b5-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e41b5-120">See Also</span></span>  
 <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>  
 <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>  
 [<span data-ttu-id="e41b5-121">구성 하 고 런타임 동작을 확장</span><span class="sxs-lookup"><span data-stu-id="e41b5-121">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
