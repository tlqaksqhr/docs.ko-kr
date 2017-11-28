---
title: "본문 요소에 의한 디스패치"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f64a3c04-62b4-47b2-91d9-747a3af1659f
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1f727b5d4a1e2689b4a90971f5b5c93efb55c475
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="dispatch-by-body-element"></a><span data-ttu-id="1d685-102">본문 요소에 의한 디스패치</span><span class="sxs-lookup"><span data-stu-id="1d685-102">Dispatch by Body Element</span></span>
<span data-ttu-id="1d685-103">이 샘플에서는 들어오는 메시지를 작업에 할당하는 대체 알고리즘을 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-103">This sample demonstrates how to implement an alternate algorithm for assigning incoming messages to operations.</span></span>  
  
 <span data-ttu-id="1d685-104">기본적으로 서비스 모델 디스패처는 메시지의 WS-Addressing "Action" 헤더나 HTTP SOAP 요청의 동일한 정보에 따라 들어오는 메시지에 적합한 처리 방법을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-104">By default, the service model dispatcher selects the appropriate handling method for an incoming message based on the message's WS-Addressing "Action" header or the equivalent information in the HTTP SOAP request.</span></span>  
  
 <span data-ttu-id="1d685-105">WS-I Basic Profile 1.1 지침을 따르지 않는 일부 SOAP 1.1 웹 서비스 스택은 동작 URI 대신 SOAP 본문 내 첫 번째 요소의 정규화된 XML 이름에 따라 메시지를 디스패치합니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-105">Some SOAP 1.1 Web services stacks that do not follow the WS-I Basic Profile 1.1 guidelines do not dispatch messages based on the Action URI, but rather based on the XML qualified name of the first element inside the SOAP body.</span></span> <span data-ttu-id="1d685-106">마찬가지로 이러한 스택의 클라이언트측은 SOAP 1.1 사양에 허용된 빈 HTTP SoapAction 헤더나 임의의 HTTP SoapAction 헤더를 사용하여 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-106">Likewise, the client side of these stacks might send messages with an empty or arbitrary HTTP SoapAction header, which was permitted by the SOAP 1.1 specification.</span></span>  
  
 <span data-ttu-id="1d685-107">메시지가 메서드로 디스패치되는 방법을 변경하기 위해 이 샘플에서는 <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector>에서 `DispatchByBodyElementOperationSelector` 확장성 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-107">To change the way messages are dispatched to methods, the sample implements the <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> extensibility interface on the `DispatchByBodyElementOperationSelector`.</span></span> <span data-ttu-id="1d685-108">이 클래스는 메시지 본문의 첫 번째 요소에 따라 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-108">This class selects operations based on the first element of the message body.</span></span>  
  
 <span data-ttu-id="1d685-109">클래스 생성자에는 `XmlQualifiedName`과 문자열 쌍으로 채워진 사전이 필요합니다. 여기에서 정규화된 이름은 SOAP 본문에서 첫 번째 자식의 이름을 나타내고 문자열은 일치하는 작업 이름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-109">The class constructor expects a dictionary populated with pairs of `XmlQualifiedName` and strings, whereby the qualified names indicate the name of the first child of the SOAP body and the strings indicate the matching operation name.</span></span> <span data-ttu-id="1d685-110">`defaultOperationName`은 이 사전과 일치하지 않는 모든 메시지를 받는 작업의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-110">The `defaultOperationName` is the name of the operation that receives all messages that cannot be matched against this dictionary:</span></span>  
  
```  
class DispatchByBodyElementOperationSelector : IDispatchOperationSelector  
{  
    Dictionary<XmlQualifiedName, string> dispatchDictionary;  
    string defaultOperationName;  
  
    public DispatchByBodyElementOperationSelector(Dictionary<XmlQualifiedName,string> dispatchDictionary, string defaultOperationName)  
    {  
        this.dispatchDictionary = dispatchDictionary;  
        this.defaultOperationName = defaultOperationName;  
    }  
```  
  
 <span data-ttu-id="1d685-111"><xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> 구현은 인터페이스 <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A>에 메서드가 하나만 있으므로 매우 간단하게 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-111"><xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> implementations are very straightforward to build as there is only one method on the interface: <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A>.</span></span> <span data-ttu-id="1d685-112">이 메서드의 작업은 들어오는 메시지를 검사하고 현재 끝점에 대한 서비스 계약의 메서드 이름과 동일한 문자열을 반환하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-112">The job of this method is to inspect an incoming message and to return a string that equals the name of a method on the service contract for the current endpoint.</span></span>  
  
 <span data-ttu-id="1d685-113">이 샘플에서 작업 선택기는 <xref:System.Xml.XmlDictionaryReader>를 사용하여 들어오는 메시지의 본문에 대한 <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A>를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-113">In this sample, the operation selector acquires an <xref:System.Xml.XmlDictionaryReader> for the incoming message's body using <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A>.</span></span> <span data-ttu-id="1d685-114">이 메서드는 메시지 본문의 첫 번째 자식에 판독기를 미리 배치하여 현재 요소의 이름과 네임스페이스 URI를 가져와서 `XmlQualifiedName`에 결합한 다음 작업 선택기에서 보유하고 있는 사전에서 해당 작업을 조회하는 데 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-114">This method already positions the reader on the first child of the message's body so that it is sufficient to get the current element's name and namespace URI and combine them into an `XmlQualifiedName` that is then used for looking up the corresponding operation from the dictionary held by the operation selector.</span></span>  
  
```  
public string SelectOperation(ref System.ServiceModel.Channels.Message message)  
{  
    XmlDictionaryReader bodyReader = message.GetReaderAtBodyContents();  
    XmlQualifiedName lookupQName = new  
       XmlQualifiedName(bodyReader.LocalName, bodyReader.NamespaceURI);  
    message = CreateMessageCopy(message,bodyReader);  
    if (dispatchDictionary.ContainsKey(lookupQName))  
    {  
         return dispatchDictionary[lookupQName];  
    }  
    else  
    {  
        return defaultOperationName;  
    }  
}  
```  
  
 <span data-ttu-id="1d685-115"><xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A> 또는 메시지 본문 내용에 액세스할 수 있는 권한을 제공하는 다른 메서드를 사용하여 메시지 본문에 액세스하면 메시지가 "읽음"으로 표시됩니다. 즉, 메시지를 추가로 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-115">Accessing the message body with <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A> or any of the other methods that provide access to the message's body content causes the message to be marked as "read", which means that the message is invalid for any further processing.</span></span> <span data-ttu-id="1d685-116">따라서 작업 선택기는 다음 코드에 표시된 메서드를 사용하여 들어오는 메시지의 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-116">Therefore, the operation selector creates a copy of the incoming message with the method shown in the following code.</span></span> <span data-ttu-id="1d685-117">판독기의 위치는 검사 중에 변경되지 않기 때문에 새로 만든 메시지에서 이를 참조할 수 있습니다. 입력 메시지의 메시지 속성 및 메시지 헤더도 이 새 메시지에 복사되므로 원본 메시지가 정확하게 복제됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-117">Because the reader's position has not been changed during the inspection, it can be referenced by the newly created message to which the message properties and the message headers are also copied, which results in an exact clone of the original message:</span></span>  
  
```  
private Message CreateMessageCopy(Message message,   
                                     XmlDictionaryReader body)  
{  
    Message copy = Message.CreateMessage(message.Version,message.Headers.Action,body);  
    copy.Headers.CopyHeaderFrom(message,0);  
    copy.Properties.CopyProperties(message.Properties);  
    return copy;  
}  
```  
  
## <a name="adding-an-operation-selector-to-a-service"></a><span data-ttu-id="1d685-118">서비스에 작업 선택기 추가</span><span class="sxs-lookup"><span data-stu-id="1d685-118">Adding an Operation Selector to a Service</span></span>  
 <span data-ttu-id="1d685-119">서비스 디스패치 작업 선택기는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 디스패처의 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-119">Service dispatch operation selectors are extensions to the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] dispatcher.</span></span> <span data-ttu-id="1d685-120">이중 계약의 콜백 채널에서 메서드를 선택하기 위한 클라이언트 작업 선택기도 있습니다. 이 작업 선택기는 여기에서 설명하는 디스패치 작업 선택기와 매우 유사하게 작동하지만 이 샘플에서 명시적으로 설명하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-120">For selecting methods on the callback channel of duplex contracts, there are also client operation selectors, which work very much like the dispatch operation selectors described here, but which are not explicitly covered in this sample.</span></span>  
  
 <span data-ttu-id="1d685-121">대부분의 서비스 모델 확장처럼 디스패치 작업 선택기도 동작을 사용하여 디스패처에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-121">Like most service model extensions, dispatch operation selectors are added to the dispatcher using behaviors.</span></span> <span data-ttu-id="1d685-122">A *동작* 은 디스패치 런타임이나 (또는 클라이언트 런타임을) 하나 이상의 확장을 추가 하거나 해당 설정을 변경 하는 구성 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-122">A *behavior* is a configuration object, which either adds one or more extensions to the dispatch runtime (or to the client runtime) or otherwise changes its settings.</span></span>  
  
 <span data-ttu-id="1d685-123">작업 선택기에는 계약 범위가 있으므로 여기서 구현하기에 적합한 동작은 <xref:System.ServiceModel.Description.IContractBehavior>입니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-123">Because operation selectors have contract scope, the appropriate behavior to implement here is the <xref:System.ServiceModel.Description.IContractBehavior>.</span></span> <span data-ttu-id="1d685-124">다음 코드와 같이 인터페이스는 <xref:System.Attribute> 파생 클래스에 구현되므로 이 동작을 서비스 계약에 선언적으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-124">Because the interface is implemented on a <xref:System.Attribute> derived class as shown in the following code, the behavior can be declaratively added to any service contract.</span></span> <span data-ttu-id="1d685-125"><xref:System.ServiceModel.ServiceHost>를 열고 디스패치 런타임을 빌드할 때마다 계약, 작업 및 서비스 구현의 특성이나 서비스 구성의 요소로 검색되는 모든 동작은 자동으로 추가된 후 확장을 적용하거나 기본 구성을 수정하라는 요청을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-125">Whenever a <xref:System.ServiceModel.ServiceHost> is opened and the dispatch runtime is built, all behaviors found either as attributes on contracts, operations, and service implementations or as element in the service configuration are automatically added and subsequently asked to contribute extensions or modify the default configuration.</span></span>  
  
 <span data-ttu-id="1d685-126">간단한 설명을 위해 다음에 인용된 코드에서는 이 샘플에 사용된 디스패처의 구성 변경에 영향을 주는 <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%2A> 메서드의 구현만 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-126">For brevity, the following code excerpt only shows the implementation of the method <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%2A>, which effects the configuration changes for the dispatcher in this sample.</span></span> <span data-ttu-id="1d685-127">다른 메서드는 작업을 수행하지 않고 호출자에게 반환되기 때문에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-127">The other methods are not shown because they return to the caller without doing any work.</span></span>  
  
```  
[AttributeUsage(AttributeTargets.Class|AttributeTargets.Interface)]  
class DispatchByBodyElementBehaviorAttribute : Attribute, IContractBehavior  
{  
    // public void AddBindingParameters(...)   
    // public void ApplyClientBehavior(...)  
    // public void Validate(...)  
```  
  
 <span data-ttu-id="1d685-128">먼저 <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%2A> 구현에서는 서비스 끝점의 <xref:System.ServiceModel.Description.OperationDescription>에서 <xref:System.ServiceModel.Description.ContractDescription> 요소를 반복하여 작업 선택기에 대한 조회 사전을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-128">First, the <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%2A> implementation sets up the lookup dictionary for the operation selector by iterating over the <xref:System.ServiceModel.Description.OperationDescription> elements in the service endpoint's <xref:System.ServiceModel.Description.ContractDescription>.</span></span> <span data-ttu-id="1d685-129">그런 다음 각 작업 설명을 검사하여 이 샘플에도 정의되어 있는 `DispatchBodyElementAttribute`의 구현인 <xref:System.ServiceModel.Description.IOperationBehavior> 동작이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-129">Then, each operation description is inspected for the presence of the `DispatchBodyElementAttribute` behavior, an implementation of <xref:System.ServiceModel.Description.IOperationBehavior> that is also defined in this sample.</span></span> <span data-ttu-id="1d685-130">이 클래스도 동작이지만 수동적이며 디스패치 런타임에 구성 변경 내용을 능동적으로 적용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-130">While this class is also a behavior, it is passive and does not actively contribute any configuration changes to the dispatch runtime.</span></span> <span data-ttu-id="1d685-131">클래스의 모든 메서드가 작업을 수행하지 않고 호출자에게 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-131">All of its methods return to the caller without taking any actions.</span></span> <span data-ttu-id="1d685-132">작업 동작만 존재하므로 새 디스패치 메커니즘에 필요한 메타데이터 즉, 작업이 선택되는 본문 요소의 정규화된 이름을 해당 작업에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-132">The operation behavior only exists so that the metadata required for the new dispatch mechanism, namely the qualified name of the body element on whose occurrence an operation is selected, can be associated with the respective operations.</span></span>  
  
 <span data-ttu-id="1d685-133">이러한 동작이 있으면 정규화된 XML 이름(`QName` 속성)과 작업 이름(`Name` 속성)으로 만들어진 값 쌍이 사전에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-133">If such a behavior is found, a value pair created from the XML qualified name (`QName` property) and the operation name (`Name` property) is added to the dictionary.</span></span>  
  
 <span data-ttu-id="1d685-134">사전이 채워지면 이 정보로 새 `DispatchByBodyElementOperationSelector`가 생성되고 디스패치 런타임의 작업 선택기로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-134">Once the dictionary is populated, a new `DispatchByBodyElementOperationSelector` is constructed with this information and set as the operation selector of the dispatch runtime:</span></span>  
  
```  
public void ApplyDispatchBehavior(ContractDescription contractDescription, ServiceEndpoint endpoint, System.ServiceModel.Dispatcher.DispatchRuntime dispatchRuntime)  
{  
    Dictionary<XmlQualifiedName,string> dispatchDictionary =   
                     new Dictionary<XmlQualifiedName,string>();  
    foreach( OperationDescription operationDescription in   
                              contractDescription.Operations )  
    {  
        DispatchBodyElementAttribute dispatchBodyElement =   
   operationDescription.Behaviors.Find<DispatchBodyElementAttribute>();  
        if ( dispatchBodyElement != null )  
        {  
             dispatchDictionary.Add(dispatchBodyElement.QName,   
                              operationDescription.Name);  
        }  
    }  
    dispatchRuntime.OperationSelector =   
            new DispatchByBodyElementOperationSelector(  
               dispatchDictionary,   
               dispatchRuntime.UnhandledDispatchOperation.Name);  
    }  
}  
```  
  
## <a name="implementing-the-service"></a><span data-ttu-id="1d685-135">서비스 구현</span><span class="sxs-lookup"><span data-stu-id="1d685-135">Implementing the Service</span></span>  
 <span data-ttu-id="1d685-136">이 샘플에 구현된 동작은 네트워크의 메시지가 해석되고 디스패치되는 방식에 직접적인 영향을 주며, 이는 서비스 계약의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-136">The behavior implemented in this sample directly affects how messages from the wire are interpreted and dispatched, which is a function of the service contract.</span></span> <span data-ttu-id="1d685-137">따라서 이 동작을 사용하도록 선택하는 서비스 구현에서는 서비스 계약 수준으로 동작을 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-137">Consequently, the behavior should be declared on the service contract level in any service implementation that chooses to use it.</span></span>  
  
 <span data-ttu-id="1d685-138">샘플 프로젝트 서비스에 적용 되는 `DispatchByBodyElementBehaviorAttribute` 계약 동작을는 `IDispatchedByBody` 서비스 계약 및 각 레이블을 두 동작 `OperationForBodyA()` 및 `OperationForBodyB()` 와 `DispatchBodyElementAttribute` 작업 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-138">The sample project service applies the `DispatchByBodyElementBehaviorAttribute` contract behavior to the `IDispatchedByBody` service contract and labels each of the two operations `OperationForBodyA()` and `OperationForBodyB()` with a `DispatchBodyElementAttribute` operation behavior.</span></span> <span data-ttu-id="1d685-139">이 계약을 구현하는 서비스에 대한 서비스 호스트를 열면 앞에서 설명한 대로 디스패처 작성기에서 이 메타데이터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-139">When a service host for a service that implements this contract is opened, this metadata is picked up by the dispatcher builder as previously described.</span></span>  
  
 <span data-ttu-id="1d685-140">작업 선택기는 메시지 본문 요소만을 기준으로 디스패치하고 "Action"을 무시하므로 `ReplyAction`의 <xref:System.ServiceModel.OperationContractAttribute> 속성에 와일드카드 "*"를 할당하여 반환된 회신에서 "Action" 헤더를 검사하지 않도록 런타임에 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-140">Because the operation selector dispatches solely based on the message body element and ignores the "Action", it is required to tell the runtime not to check the "Action" header on the returned replies by assigning the wildcard "*" to the `ReplyAction` property of <xref:System.ServiceModel.OperationContractAttribute>.</span></span> <span data-ttu-id="1d685-141">또한 "Action" 속성이 와일드 카드로 설정 된 기본 작업이 있어야 하는 "\*"입니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-141">Furthermore, it is required to have a default operation that has the "Action" property set to the wildcard "\*".</span></span> <span data-ttu-id="1d685-142">기본 작업은 디스패치할 수 없는 모든 메시지를 받으므로 `DispatchBodyElementAttribute`이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-142">The default operation receives all messages which cannot be dispatched and does not have a `DispatchBodyElementAttribute`:</span></span>  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples"),  
                            DispatchByBodyElementBehavior]  
public interface IDispatchedByBody  
{  
    [OperationContract(ReplyAction="*"),   
     DispatchBodyElement("bodyA","http://tempuri.org")]  
    Message OperationForBodyA(Message msg);  
    [OperationContract(ReplyAction = "*"),   
     DispatchBodyElement("bodyB", "http://tempuri.org")]  
    Message OperationForBodyB(Message msg);  
    [OperationContract(Action="*", ReplyAction="*")]  
    Message DefaultOperation(Message msg);  
}  
```  
  
 <span data-ttu-id="1d685-143">샘플 서비스 구현은 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-143">The sample service implementation is straightforward.</span></span> <span data-ttu-id="1d685-144">모든 메서드는 수신된 메시지를 회신 메시지로 래핑하고 클라이언트에 다시 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-144">Every method wraps the received message into a reply message and echoes it back to the client.</span></span>  
  
## <a name="running-and-building-the-sample"></a><span data-ttu-id="1d685-145">샘플 실행 및 빌드</span><span class="sxs-lookup"><span data-stu-id="1d685-145">Running and Building the Sample</span></span>  
 <span data-ttu-id="1d685-146">샘플을 실행하면 작업 응답의 본문 내용이 형식이 지정된 다음 출력과 유사하게 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-146">When you run the sample, the body content of the operation responses are displayed in the client console window similar to the following (formatted) output.</span></span>  
  
 <span data-ttu-id="1d685-147">클라이언트는 본문 내용 요소의 이름이 각각 `bodyA`, `bodyB` 및 `bodyX`인 세 개의 메시지를 서비스로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-147">The client sends three messages to the service whose body content element is named `bodyA`, `bodyB`, and `bodyX`, respectively.</span></span> <span data-ttu-id="1d685-148">이전 설명과 표시된 서비스 계약에서 알 수 있듯이, `bodyA` 요소가 있는 들어오는 메시지는 `OperationForBodyA()` 메서드로 디스패치됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-148">As can be deferred from the previous description and the service contract shown, the incoming message with the `bodyA` element is dispatched to the `OperationForBodyA()` method.</span></span> <span data-ttu-id="1d685-149">`bodyX` 본문 요소가 있는 메시지의 경우에는 명시적인 디스패치 대상이 없으므로 메시지가 `DefaultOperation()`으로 디스패치됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-149">Because there is no explicit dispatch target for the message with the `bodyX` body element, the message is dispatched to the `DefaultOperation()`.</span></span> <span data-ttu-id="1d685-150">각 서비스 작업은 수신된 메시지 본문을 메서드 관련 요소로 래핑하여 반환하며, 이 작업은 이 샘플의 입력 및 출력 메시지를 명확하게 상호 연결하기 위해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-150">Each of the service operations wraps the received message body into an element specific to the method and returns it, which is done to correlate input and output messages clearly for this sample:</span></span>  
  
```xml  
<?xml version="1.0" encoding="IBM437"?>  
<replyBodyA xmlns="http://tempuri.org">  
   <q:bodyA xmlns:q="http://tempuri.org">test</q:bodyA>  
</replyBodyA>  
<?xml version="1.0" encoding="IBM437"?>  
<replyBodyB xmlns="http://tempuri.org">  
  <q:bodyB xmlns:q="http://tempuri.org">test</q:bodyB>  
</replyBodyB>  
<?xml version="1.0" encoding="IBM437"?>  
<replyDefault xmlns="http://tempuri.org">  
   <q:bodyX xmlns:q="http://tempuri.org">test</q:bodyX>  
</replyDefault>  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="1d685-151">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="1d685-151">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="1d685-152">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-152">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="1d685-153">지침에 따라 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-153">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="1d685-154">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-154">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1d685-155">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-155">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1d685-156">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="1d685-156">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="1d685-157">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="1d685-157">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1d685-158">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d685-158">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Interop\AdvancedDispatchByBody`  
  
## <a name="see-also"></a><span data-ttu-id="1d685-159">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d685-159">See Also</span></span>
