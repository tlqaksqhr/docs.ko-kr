---
title: "메시지 검사자"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9bd1f305-ad03-4dd7-971f-fa1014b97c9b
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7ed4f31e004ddeb69a29568b3892ab7379715457
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="message-inspectors"></a><span data-ttu-id="4c9b2-102">메시지 검사자</span><span class="sxs-lookup"><span data-stu-id="4c9b2-102">Message Inspectors</span></span>
<span data-ttu-id="4c9b2-103">이 샘플에서는 클라이언트 및 서비스 메시지 검사자를 구현하고 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-103">This sample demonstrates how to implement and configure client and service message inspectors.</span></span>  
  
 <span data-ttu-id="4c9b2-104">메시지 검사자는 서비스 모델의 클라이언트 런타임 및 디스패치 런타임에서 프로그래밍 방식으로나 구성을 통해 사용할 수 있으며, 메시지를 받은 후나 보내기 전에 해당 메시지를 검사하고 변경할 수 있는 확장성 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-104">A message inspector is an extensibility object that can be used in the service model's client runtime and dispatch runtime programmatically or through configuration and that can inspect and alter messages after they are received or before they are sent.</span></span>  
  
 <span data-ttu-id="4c9b2-105">이 샘플에서는 구성 가능한 XML 스키마 문서 집합에 대해 들어오는 메시지의 유효성을 검사하는 기본 클라이언트 및 서비스 메시지 유효성 검사 메커니즘을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-105">This sample implements a basic client and service message validation mechanism that validates incoming messages against a set of configurable XML Schema documents.</span></span> <span data-ttu-id="4c9b2-106">이 샘플에서는 각 작업에 대해 메시지의 유효성을 검사하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-106">Note that this sample does not validate messages for each operation.</span></span> <span data-ttu-id="4c9b2-107">이는 의도적으로 작업을 단순화하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-107">This is an intentional simplification.</span></span>  
  
## <a name="message-inspector"></a><span data-ttu-id="4c9b2-108">메시지 검사자</span><span class="sxs-lookup"><span data-stu-id="4c9b2-108">Message Inspector</span></span>  
 <span data-ttu-id="4c9b2-109">클라이언트 메시지 검사자는 <xref:System.ServiceModel.Dispatcher.IClientMessageInspector> 인터페이스를 구현하고 서비스 메시지 검사자는 <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector> 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-109">Client message inspectors implement the <xref:System.ServiceModel.Dispatcher.IClientMessageInspector> interface and service message inspectors implement the <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector> interface.</span></span> <span data-ttu-id="4c9b2-110">이러한 구현을 단일 클래스로 결합하여 양쪽에서 작동하는 메시지 검사자를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-110">The implementations can be combined into a single class to form a message inspector that works for both sides.</span></span> <span data-ttu-id="4c9b2-111">이 샘플에서는 이렇게 결합된 메시지 검사자를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-111">This sample implements such a combined message inspector.</span></span> <span data-ttu-id="4c9b2-112">검사자는 들어오는 메시지와 나가는 메시지의 유효성을 검사하는 스키마 집합에 전달되어 구성되며, 이 검사자를 통해 개발자는 들어오는 메시지나 나가는 메시지의 유효성을 검사할지 여부와 검사자가 디스패치 모드에 있는지 클라이언트 모드에 있는지를 지정합니다. 이는 이 항목의 뒷부분에서 설명하는 오류 처리에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-112">The inspector is constructed passing in a set of schemas against which incoming and outgoing messages are validated and allows the developer to specify whether incoming or outgoing messages are validated and whether the inspector is in dispatch or client mode, which affects the error handling as discussed later in this topic.</span></span>  
  
```  
public class SchemaValidationMessageInspector : IClientMessageInspector, IDispatchMessageInspector  
{  
    XmlSchemaSet schemaSet;  
    bool validateRequest;  
    bool validateReply;  
    bool isClientSide;  
    [ThreadStatic]  
    bool isRequest;  
  
    public SchemaValidationMessageInspector(XmlSchemaSet schemaSet,  
         bool validateRequest, bool validateReply, bool isClientSide)  
    {  
        this.schemaSet = schemaSet;  
        this.validateReply = validateReply;  
        this.validateRequest = validateRequest;  
        this.isClientSide = isClientSide;  
    }  
```  
  
 <span data-ttu-id="4c9b2-113">모든 서비스(디스패처) 메시지 검사자는 <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector> 메서드 <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A>와 <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%28System.ServiceModel.Channels.Message%40%2CSystem.Object%29>를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-113">Any service (dispatcher) message inspector must implement the two <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector> methods <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> and <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%28System.ServiceModel.Channels.Message%40%2CSystem.Object%29>.</span></span>  
  
 <span data-ttu-id="4c9b2-114">메시지를 받아 채널 스택에서 처리한 후 서비스에 할당한 경우 deserialize하여 작업에 디스패치하기 전에 디스패처에서 <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-114"><xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> is invoked by the dispatcher when a message has been received, processed by the channel stack and assigned to a service, but before it is deserialized and dispatched to an operation.</span></span> <span data-ttu-id="4c9b2-115">들어오는 메시지가 암호화된 경우 메시지 검사자에 도달하면 해당 메시지는 이미 암호가 해독되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-115">If the incoming message was encrypted, the message is already decrypted when it reaches the message inspector.</span></span> <span data-ttu-id="4c9b2-116">메서드는 참조 매개 변수로 전달된 `request` 메시지를 가져오며, 이를 통해 필요에 따라 메시지를 검사, 조작 또는 대체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-116">The method gets the `request` message passed as a reference parameter, which allows the message to be inspected, manipulated or replaced as required.</span></span> <span data-ttu-id="4c9b2-117">반환 값은 임의의 개체가 될 수 있으며 서비스에서 현재 메시지에 대한 회신을 반환할 때 <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%2A>에 전달되는 상관 관계 상태 개체로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-117">The return value can be any object and is used as a correlation state object that is passed to <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%2A> when the service returns a reply to the current message.</span></span> <span data-ttu-id="4c9b2-118">이 샘플에서 <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A>는 메시지의 검사(유효성 검사)를 전용 로컬 메서드 `ValidateMessageBody`에 위임하며 상관 관계 상태 개체를 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-118">In this sample, <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> delegates the inspection (validation) of the message to the private, local method `ValidateMessageBody` and returns no correlation state object.</span></span> <span data-ttu-id="4c9b2-119">이 메서드는 잘못된 메시지가 서비스에 전달되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-119">This method ensures that no invalid messages pass into the service.</span></span>  
  
```  
object IDispatchMessageInspector.AfterReceiveRequest(ref System.ServiceModel.Channels.Message request, System.ServiceModel.IClientChannel channel, System.ServiceModel.InstanceContext instanceContext)  
{  
    if (validateRequest)  
    {  
        // inspect the message. If a validation error occurs,  
        // the thrown fault exception bubbles up.  
        ValidateMessageBody(ref request, true);  
    }  
    return null;  
}  
```  
  
 <span data-ttu-id="4c9b2-120"><xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%28System.ServiceModel.Channels.Message%40%2CSystem.Object%29>는 클라이언트로 회신을 다시 보낼 준비가 될 때마다 호출되며 단방향 메시지인 경우에는 들어오는 메시지가 처리되면 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-120"><xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%28System.ServiceModel.Channels.Message%40%2CSystem.Object%29> is invoked whenever a reply is ready to be sent back to a client, or in the case of one-way messages, when the incoming message has been processed.</span></span> <span data-ttu-id="4c9b2-121">따라서 MEP에 관계없이 대칭적으로 확장을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-121">This allows extensions to count on being called symmetrically, regardless of MEP.</span></span> <span data-ttu-id="4c9b2-122"><xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A>와 마찬가지로 메시지는 참조 매개 변수로 전달되며 검사, 수정 또는 대체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-122">As with <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A>, the message is passed as a reference parameter and can be inspected, modified or replaced.</span></span> <span data-ttu-id="4c9b2-123">이 샘플에서 수행되는 메시지 유효성 검사는 `ValidMessageBody` 메서드에 다시 위임되지만 이 경우 유효성 검사 오류 처리가 약간 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-123">The validation of the message that is performed in this sample is again delegated to the `ValidMessageBody` method, but the handling of validation errors is slightly different in this case.</span></span>  
  
 <span data-ttu-id="4c9b2-124">서비스에서 유효성 검사 오류가 발생하면 `ValidateMessageBody` 메서드에서 <xref:System.ServiceModel.FaultException> 파생 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-124">If a validation error occurs on the service, the `ValidateMessageBody` method throws <xref:System.ServiceModel.FaultException>-derived exceptions.</span></span> <span data-ttu-id="4c9b2-125"><xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A>에서는 SOAP 오류로 자동 변환되어 클라이언트로 전달되는 서비스 모델 인프라에 이러한 예외를 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-125">In <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A>, these exceptions can be put into the service model infrastructure where they are automatically transformed into SOAP faults and relayed to the client.</span></span> <span data-ttu-id="4c9b2-126"><xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%2A>에서는 서비스에서 throw된 오류 예외가 메시지 검사자가 호출되기 전에 변환되므로 <xref:System.ServiceModel.FaultException> 예외를 인프라에 넣으면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-126">In <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%2A>, <xref:System.ServiceModel.FaultException> exceptions must not be put into the infrastructure, because the transformation of fault exceptions thrown by the service occurs before the message inspector is called.</span></span> <span data-ttu-id="4c9b2-127">따라서 다음 구현에서는 알려진 `ReplyValidationFault` 예외를 catch하고 회신 메시지를 명시적인 오류 메시지로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-127">Therefore the following implementation catches the known `ReplyValidationFault` exception and replaces the reply message with an explicit fault message.</span></span> <span data-ttu-id="4c9b2-128">이 메서드는 서비스 구현에서 잘못된 메시지를 반환하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-128">This method ensures that no invalid messages are returned by the service implementation.</span></span>  
  
```  
void IDispatchMessageInspector.BeforeSendReply(ref System.ServiceModel.Channels.Message reply, object correlationState)  
{  
    if (validateReply)  
    {  
        // Inspect the reply, catch a possible validation error   
        try  
        {  
            ValidateMessageBody(ref reply, false);  
        }  
        catch (ReplyValidationFault fault)  
        {  
            // if a validation error occurred, the message is replaced  
            // with the validation fault.  
            reply = Message.CreateMessage(reply.Version,   
                    fault.CreateMessageFault(), reply.Headers.Action);  
        }  
    }  
```  
  
 <span data-ttu-id="4c9b2-129">클라이언트 메시지 검사자는 서비스 메시지 검사자와 매우 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-129">The client message inspector is very similar.</span></span> <span data-ttu-id="4c9b2-130"><xref:System.ServiceModel.Dispatcher.IClientMessageInspector>에서 구현되어야 하는 두 가지 메서드는 <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.AfterReceiveReply%2A>와 <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A>입니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-130">The two methods that must be implemented from <xref:System.ServiceModel.Dispatcher.IClientMessageInspector> are <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.AfterReceiveReply%2A> and <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A>.</span></span>  
  
 <span data-ttu-id="4c9b2-131"><xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A>는 클라이언트 응용 프로그램이나 작업 포맷터에서 메시지가 작성되면 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-131"><xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A> is invoked when the message has been composed either by the client application or by the operation formatter.</span></span> <span data-ttu-id="4c9b2-132">디스패처 메시지 검사자와 마찬가지로 메시지를 검사만 하거나 완전히 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-132">As with the dispatcher message inspectors, the message can just be inspected or entirely replaced.</span></span> <span data-ttu-id="4c9b2-133">이 샘플에서 검사자는 디스패치 메시지 검사자에도 사용된 동일한 로컬 `ValidateMessageBody` 도우미 메서드에 위임합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-133">In this sample, the inspector delegates to the same local `ValidateMessageBody` helper method that is also used for the dispatch message inspectors.</span></span>  
  
 <span data-ttu-id="4c9b2-134">생성자에 지정된 대로 클라이언트 유효성 검사와 서비스 유효성 검사에는 동작 면에서 차이가 있는데, 클라이언트 유효성 검사에서는 서비스 오류 때문이 아니라 로컬에서 이러한 예외가 발생하기 때문에 사용자 코드에 들어가는 로컬 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-134">The behavioral difference between the client and service validation (as specified in the constructor) is that the client validation throws local exceptions that are put into the user code because they occur locally and not because of a service failure.</span></span> <span data-ttu-id="4c9b2-135">일반적으로 서비스 디스패처 검사자는 오류를 throw하고 클라이언트 검사자는 예외를 throw하는 규칙이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-135">Generally, the rule is that service dispatcher inspectors throw faults and that client inspectors throw exceptions.</span></span>  
  
 <span data-ttu-id="4c9b2-136">이 <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A> 구현에서는 잘못된 메시지를 서비스로 보내지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-136">This <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A> implementation ensures that no invalid messages are sent to the service.</span></span>  
  
```  
object IClientMessageInspector.BeforeSendRequest(ref System.ServiceModel.Channels.Message request, System.ServiceModel.IClientChannel channel)  
{  
    if (validateRequest)  
    {  
        ValidateMessageBody(ref request, true);  
    }  
    return null;  
}  
```  
  
 <span data-ttu-id="4c9b2-137">`AfterReceiveReply` 구현에서는 서비스에서 받은 잘못된 메시지가 클라이언트 사용자 코드로 전달되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-137">The `AfterReceiveReply` implementation ensures that no invalid messages received from the service are relayed to the client user code.</span></span>  
  
```  
void IClientMessageInspector.AfterReceiveReply(ref System.ServiceModel.Channels.Message reply, object correlationState)  
{  
    if (validateReply)  
    {  
        ValidateMessageBody(ref reply, false);  
    }  
}  
```  
  
 <span data-ttu-id="4c9b2-138">이러한 특정 메시지 검사자에서는 `ValidateMessageBody` 메서드가 가장 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-138">The heart of this particular message inspector is the `ValidateMessageBody` method.</span></span> <span data-ttu-id="4c9b2-139">작업을 수행하기 위해 이 메서드는 전달된 메시지의 본문 내용 하위 트리 주위로 유효성을 검사하는 <xref:System.Xml.XmlReader>를 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-139">To perform its work, it wraps a validating <xref:System.Xml.XmlReader> around the body content sub-tree of the passed message.</span></span> <span data-ttu-id="4c9b2-140">판독기는 메시지 검사자가 보유하는 스키마 집합으로 채워지고 유효성 검사 콜백은 이 메서드와 함께 정의된 `InspectionValidationHandler`를 나타내는 대리자로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-140">The reader is populated with the set of schemas that the message inspector holds and the validation callback is set to a delegate referring to the `InspectionValidationHandler` that is defined alongside this method.</span></span> <span data-ttu-id="4c9b2-141">유효성 검사를 수행하려면 메시지를 읽고 메모리 스트림 지원 <xref:System.Xml.XmlDictionaryWriter>로 스풀링합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-141">To perform the validation, the message is then read and spooled into a memory stream-backed <xref:System.Xml.XmlDictionaryWriter>.</span></span> <span data-ttu-id="4c9b2-142">프로세스 중에 유효성 검사 오류나 경고가 발생하면 콜백 메서드가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-142">If a validation error or warning occurs in the process, the callback method is invoked.</span></span>  
  
 <span data-ttu-id="4c9b2-143">오류가 발생하지 않으면 원본 메시지에서 속성 및 헤더를 복사하고 메모리 스트림에서 현재 유효성이 검사된 infoset을 사용하는 새 메시지가 생성됩니다. 이 메시지는 <xref:System.Xml.XmlDictionaryReader>에 의해 래핑되고 대체 메시지에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-143">If no error occurs, a new message is constructed that copies the properties and headers from the original message and uses the now-validated infoset in the memory stream, which is wrapped by an <xref:System.Xml.XmlDictionaryReader> and added to the replacement message.</span></span>  
  
```  
void ValidateMessageBody(ref System.ServiceModel.Channels.Message message, bool isRequest)  
{  
    if (!message.IsFault)  
    {  
        XmlDictionaryReaderQuotas quotas =   
                new XmlDictionaryReaderQuotas();  
        XmlReader bodyReader =   
            message.GetReaderAtBodyContents().ReadSubtree();  
        XmlReaderSettings wrapperSettings =   
                              new XmlReaderSettings();  
        wrapperSettings.CloseInput = true;  
        wrapperSettings.Schemas = schemaSet;  
        wrapperSettings.ValidationFlags =   
                                XmlSchemaValidationFlags.None;  
        wrapperSettings.ValidationType = ValidationType.Schema;  
        wrapperSettings.ValidationEventHandler += new   
           ValidationEventHandler(InspectionValidationHandler);  
        XmlReader wrappedReader = XmlReader.Create(bodyReader,   
                                            wrapperSettings);  
  
        // pull body into a memory backed writer to validate  
        this.isRequest = isRequest;  
        MemoryStream memStream = new MemoryStream();  
        XmlDictionaryWriter xdw =  
              XmlDictionaryWriter.CreateBinaryWriter(memStream);  
        xdw.WriteNode(wrappedReader, false);  
        xdw.Flush(); memStream.Position = 0;  
        XmlDictionaryReader xdr =   
        XmlDictionaryReader.CreateBinaryReader(memStream, quotas);  
  
        // reconstruct the message with the validated body  
        Message replacedMessage =   
            Message.CreateMessage(message.Version, null, xdr);  
        replacedMessage.Headers.CopyHeadersFrom(message.Headers);  
        replacedMessage.Properties.CopyProperties(message.Properties);  
        message = replacedMessage;  
    }  
}  
```  
  
 <span data-ttu-id="4c9b2-144">`InspectionValidationHandler` 메서드는 스키마 유효성 검사 오류나 경고가 발생할 때마다 유효성을 검사하는 <xref:System.Xml.XmlReader>에 의해 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-144">The `InspectionValidationHandler` method is called by the validating <xref:System.Xml.XmlReader> whenever a schema validation error or warning occurs.</span></span> <span data-ttu-id="4c9b2-145">다음 구현은 오류가 발생할 때만 작동하며 경고는 모두 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-145">The following implementation only works with errors and ignores all warnings.</span></span>  
  
 <span data-ttu-id="4c9b2-146">무엇보다도 유효성을 검사하는 <xref:System.Xml.XmlReader>를 메시지 검사자와 함께 메시지에 삽입하고 메시지가 처리될 때 메시지를 버퍼링하지 않고 유효성 검사가 수행되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-146">On first consideration, it might seem possible to inject a validating <xref:System.Xml.XmlReader> into the message with the message inspector and let the validation happen as the message is processed and without buffering the message.</span></span> <span data-ttu-id="4c9b2-147">그러나 이 콜백에서는 잘못된 XML 노드가 검색되면 서비스 모델 인프라나 사용자 코드의 다른 위치에서 유효성 검사 예외가 throw되어 예기치 않은 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-147">That, however, means that this callback throws the validation exceptions somewhere into the service model infrastructure or the user code as invalid XML nodes are detected, resulting in unpredictable behavior.</span></span> <span data-ttu-id="4c9b2-148">버퍼링 접근 방식을 사용하면 잘못된 메시지로부터 사용자 코드를 완전히 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-148">The buffering approach shields the user code from invalid messages, entirely.</span></span>  
  
 <span data-ttu-id="4c9b2-149">앞에서 설명한 대로 처리기에 의해 throw된 예외는 클라이언트와 서비스 간에 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-149">As previously discussed, the exceptions thrown by the handler differ between the client and the service.</span></span> <span data-ttu-id="4c9b2-150">서비스에서는 예외가 <xref:System.ServiceModel.FaultException>에서 파생되고, 클라이언트에서는 예외가 일반적인 사용자 지정 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-150">On the service, the exceptions are derived from <xref:System.ServiceModel.FaultException>, on the client the exceptions are regular custom exceptions.</span></span>  
  
```  
        void InspectionValidationHandler(object sender, ValidationEventArgs e)  
{  
    if (e.Severity == XmlSeverityType.Error)  
    {  
        // We are treating client and service side validation errors  
        // differently here. Client side errors cause exceptions  
        // and are thrown straight up to the user code. Service side  
        // validations cause faults.  
        if (isClientSide)  
        {  
            if (isRequest)  
            {  
                throw new RequestClientValidationException(e.Message);  
            }  
            else  
            {  
                throw new ReplyClientValidationException(e.Message);  
            }  
        }  
        else  
        {  
            if (isRequest)  
            {  
                // this fault is caught by the ServiceModel   
                // infrastructure and turned into a fault reply.  
                throw new RequestValidationFault(e.Message);  
             }  
             else  
             {  
                // this fault is caught and turned into a fault message  
                // in BeforeSendReply in this class  
                throw new ReplyValidationFault(e.Message);  
              }  
          }  
      }  
    }  
```  
  
## <a name="behavior"></a><span data-ttu-id="4c9b2-151">동작</span><span class="sxs-lookup"><span data-stu-id="4c9b2-151">Behavior</span></span>  
 <span data-ttu-id="4c9b2-152">메시지 검사자는 클라이언트 런타임이나 디스패치 런타임의 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-152">Message inspectors are extensions to the client runtime or the dispatch runtime.</span></span> <span data-ttu-id="4c9b2-153">이러한 확장은 사용 하 여 구성 된 *동작*합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-153">Such extensions are configured using *behaviors*.</span></span> <span data-ttu-id="4c9b2-154">동작은 기본 구성을 변경하거나 메시지 검사자와 같은 확장을 기본 구성에 추가하여 서비스 모델 런타임의 동작을 변경하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-154">A behavior is a class that changes the behavior of the service model runtime by changing the default configuration or adding extensions (such as message inspectors) to it.</span></span>  
  
 <span data-ttu-id="4c9b2-155">다음 `SchemaValidationBehavior` 클래스는 클라이언트 런타임이나 디스패치 런타임에 이 샘플의 메시지 검사자를 추가하는 데 사용된 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-155">The following `SchemaValidationBehavior` class is the behavior used to add this sample's message inspector to the client or dispatch runtime.</span></span> <span data-ttu-id="4c9b2-156">두 경우 모두 기본 구현에 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-156">The implementation is rather basic in both cases.</span></span> <span data-ttu-id="4c9b2-157"><xref:System.ServiceModel.Description.IEndpointBehavior.ApplyClientBehavior%2A> 및 <xref:System.ServiceModel.Description.IEndpointBehavior.ApplyDispatchBehavior%2A>에서는 메시지 검사자를 만들어 해당 런타임의 <xref:System.ServiceModel.Dispatcher.ClientRuntime.MessageInspectors%2A> 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-157">In <xref:System.ServiceModel.Description.IEndpointBehavior.ApplyClientBehavior%2A> and <xref:System.ServiceModel.Description.IEndpointBehavior.ApplyDispatchBehavior%2A>, the message inspector is created and added to the <xref:System.ServiceModel.Dispatcher.ClientRuntime.MessageInspectors%2A> collection of the respective runtime.</span></span>  
  
```  
public class SchemaValidationBehavior : IEndpointBehavior  
{  
    XmlSchemaSet schemaSet;   
    bool validateRequest;   
    bool validateReply;  
  
    public SchemaValidationBehavior(XmlSchemaSet schemaSet, bool   
                           inspectRequest, bool inspectReply)  
    {  
        this.schemaSet = schemaSet;  
        this.validateReply = inspectReply;  
        this.validateRequest = inspectRequest;  
    }  
    #region IEndpointBehavior Members  
  
    public void AddBindingParameters(ServiceEndpoint endpoint,   
       System.ServiceModel.Channels.BindingParameterCollection   
                                            bindingParameters)  
    {  
    }  
  
    public void ApplyClientBehavior(ServiceEndpoint endpoint,   
            System.ServiceModel.Dispatcher.ClientRuntime clientRuntime)  
    {  
        SchemaValidationMessageInspector inspector =   
           new SchemaValidationMessageInspector(schemaSet,   
                      validateRequest, validateReply, true);  
            clientRuntime.MessageInspectors.Add(inspector);  
    }  
  
    public void ApplyDispatchBehavior(ServiceEndpoint endpoint,   
         System.ServiceModel.Dispatcher.EndpointDispatcher   
                                          endpointDispatcher)  
    {  
        SchemaValidationMessageInspector inspector =   
           new SchemaValidationMessageInspector(schemaSet,   
                        validateRequest, validateReply, false);  
   endpointDispatcher.DispatchRuntime.MessageInspectors.Add(inspector);  
    }  
  
   public void Validate(ServiceEndpoint endpoint)  
   {  
   }  
  
    #endregion  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="4c9b2-158">이 특정 동작은 특성을 겸용하지 않으므로 서비스 유형의 계약 형식에 선언적으로 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-158">This particular behavior does not double as an attribute and therefore cannot be added declaratively onto a contract type of a service type.</span></span> <span data-ttu-id="4c9b2-159">이 동작은 특성 선언에서 스키마 컬렉션을 로드할 수 없기 때문에 디자인에 따라 결정되며 이 특성의 추가 구성 위치(예: 응용 프로그램 설정)를 참조하는 것은 나머지 서비스 모델 구성과 일치하지 않는 구성 요소를 만든다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-159">This is a by-design decision made because the schema collection cannot be loaded in an attribute declaration and referring to an extra configuration location (for instance to the application settings) in this attribute means creating a configuration element that is not consistent with the rest of the service model configuration.</span></span> <span data-ttu-id="4c9b2-160">따라서 이 동작은 코드와 서비스 모델 구성 확장을 통해 명령적으로만 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-160">Therefore, this behavior can only be added imperatively through code and through a service model configuration extension.</span></span>  
  
## <a name="adding-the-message-inspector-through-configuration"></a><span data-ttu-id="4c9b2-161">구성을 통해 메시지 검사자 추가</span><span class="sxs-lookup"><span data-stu-id="4c9b2-161">Adding the Message Inspector through Configuration</span></span>  
 <span data-ttu-id="4c9b2-162">서비스 모델에는 구성을 만들 수 필요한 응용 프로그램 구성 파일의 끝점에서 사용자 지정 동작을 구성을 *확장 요소가* 에서 파생 된 클래스로 표현 <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-162">For configuring a custom behavior on an endpoint in the application configuration file, the service model requires implementers to create a configuration *extension element* represented by a class derived from <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>.</span></span> <span data-ttu-id="4c9b2-163">그런 다음 이 섹션에 설명된 다음 확장에 대해 표시된 대로 확장에 대한 서비스 모델의 구성 섹션에 이 확장을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-163">This extension must then be added to the service model's configuration section for extensions as shown for the following extension discussed in this section.</span></span>  
  
```xml  
<system.serviceModel>  
…  
   <extensions>  
      <behaviorExtensions>  
        <add name="schemaValidator" type="Microsoft.ServiceModel.Samples.SchemaValidationBehaviorExtensionElement, MessageInspectors, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
      </behaviorExtensions>  
    </extensions>  
…  
</system.serviceModel>  
```  
  
 <span data-ttu-id="4c9b2-164">확장은 가장 일반적인 응용 프로그램이나 ASP.NET 구성 파일 또는 컴퓨터 구성 파일에서 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-164">Extensions can be added in the application or ASP.NET configuration file, which is the most common choice, or in the machine configuration file.</span></span>  
  
 <span data-ttu-id="4c9b2-165">구성 범위에 확장을 추가하면 다음 코드와 같이 동작 구성에 동작을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-165">When the extension is added to a configuration scope, the behavior can be added to a behavior configuration as it is shown in the following code.</span></span> <span data-ttu-id="4c9b2-166">동작 구성은 필요에 따라 여러 끝점에 적용할 수 있는 재사용 가능한 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-166">Behavior configurations are reusable elements that can be applied to multiple endpoints as required.</span></span> <span data-ttu-id="4c9b2-167">여기에서 구성할 특정 동작은 <xref:System.ServiceModel.Description.IEndpointBehavior>를 구현하므로 이 동작은 구성 파일의 해당 구성 섹션에서만 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-167">Because the particular behavior to be configured here implements <xref:System.ServiceModel.Description.IEndpointBehavior>, it is only valid in the respective configuration section in the configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
   <behaviors>  
      …  
     <endpointBehaviors>  
        <behavior name="HelloServiceEndpointBehavior">  
          <schemaValidator validateRequest="True" validateReply="True">  
            <schemas>  
              <add location="messages.xsd" />    
            </schemas>  
          </schemaValidator>  
        </behavior>  
      </endpointBehaviors>  
      …  
    </behaviors>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="4c9b2-168">메시지 검사자를 구성하는 `<schemaValidator>` 요소는 `SchemaValidationBehaviorExtensionElement` 클래스에서 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-168">The `<schemaValidator>` element that configures the message inspector is backed by the `SchemaValidationBehaviorExtensionElement` class.</span></span> <span data-ttu-id="4c9b2-169">이 클래스는 `ValidateRequest`와 `ValidateReply`라는 두 가지 부울 공용 속성을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-169">The class exposes two Boolean public properties named `ValidateRequest` and `ValidateReply`.</span></span> <span data-ttu-id="4c9b2-170">이러한 속성은 모두 <xref:System.Configuration.ConfigurationPropertyAttribute>로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-170">Both of these are marked with a <xref:System.Configuration.ConfigurationPropertyAttribute>.</span></span> <span data-ttu-id="4c9b2-171">이 특성은 앞에서 설명한 XML 구성 요소에 표시되는 코드 속성과 XML 특성 간의 링크를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-171">This attribute constitutes the link between the code properties and the XML attributes that can be seen on the preceding XML configuration element.</span></span> <span data-ttu-id="4c9b2-172">이 클래스에는 추가로 `Schemas`로 표시되고 <xref:System.Configuration.ConfigurationCollectionAttribute> 형식인 `SchemaCollection` 속성도 있습니다. 이 속성도 이 샘플의 일부이지만 간단한 설명을 위해 이 문서에서 생략되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-172">The class also has a property `Schemas` that is additionally marked with the <xref:System.Configuration.ConfigurationCollectionAttribute> and is of the type `SchemaCollection`, which is also part of this sample but omitted from this document for brevity.</span></span> <span data-ttu-id="4c9b2-173">컬렉션 및 컬렉션 요소 클래스 `SchemaConfigElement`와 함께 이 속성은 이전 구성 조각의 `<schemas>` 요소를 지원하며 이 속성을 통해 스키마 컬렉션을 유효성 검사 집합에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-173">This property along with the collection and the collection element class `SchemaConfigElement` backs the `<schemas>` element in the preceding configuration snippet and allows adding a collection of schemas to the validation set.</span></span>  
  
 <span data-ttu-id="4c9b2-174">재정의된 `CreateBehavior` 메서드는 런타임에서 클라이언트나 끝점을 빌드할 때 구성 데이터를 확인하여 동작 개체로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-174">The overridden `CreateBehavior` method turns the configuration data into a behavior object when the runtime evaluates the configuration data as it builds a client or an endpoint.</span></span>  
  
```  
public class SchemaValidationBehaviorExtensionElement : BehaviorExtensionElement  
{  
    public SchemaValidationBehaviorExtensionElement()  
    {  
    }  
  
    public override Type BehaviorType   
    {   
        get  
        {  
            return typeof(SchemaValidationBehavior);  
        }   
    }  
  
    protected override object CreateBehavior()  
    {  
        XmlSchemaSet schemaSet = new XmlSchemaSet();  
        foreach (SchemaConfigElement schemaCfg in this.Schemas)  
        {  
            Uri baseSchema = new   
                Uri(AppDomain.CurrentDomain.BaseDirectory);  
            string location = new   
                Uri(baseSchema,schemaCfg.Location).ToString();  
            XmlSchema schema =   
                XmlSchema.Read(new XmlTextReader(location), null);  
            schemaSet.Add(schema);  
        }  
     return new   
     SchemaValidationBehavior(schemaSet,ValidateRequest,ValidateReply);  
    }  
  
[ConfigurationProperty("validateRequest",DefaultValue=false,IsRequired=false)]  
public bool ValidateRequest  
{  
    get { return (bool)base["validateRequest"]; }  
    set { base["validateRequest"] = value; }  
}  
  
[ConfigurationProperty("validateReply", DefaultValue = false, IsRequired = false)]  
        public bool ValidateReply  
        {  
            get { return (bool)base["validateReply"]; }  
            set { base["validateReply"] = value; }  
        }  
  
     //Declare the Schema collection property.  
     //Note: the "IsDefaultCollection = false" instructs   
     //.NET Framework to build a nested section of   
     //the kind <Schema> ...</Schema>.  
    [ConfigurationProperty("schemas", IsDefaultCollection = true)]  
    [ConfigurationCollection(typeof(SchemasCollection),  
        AddItemName = "add",  
        ClearItemsName = "clear",  
        RemoveItemName = "remove")]  
    public SchemasCollection Schemas  
    {  
        get  
        {  
            SchemasCollection SchemasCollection =  
            (SchemasCollection)base["schemas"];  
            return SchemasCollection;  
        }  
    }  
}  
```  
  
## <a name="adding-message-inspectors-imperatively"></a><span data-ttu-id="4c9b2-175">명령으로 메시지 검사자 추가</span><span class="sxs-lookup"><span data-stu-id="4c9b2-175">Adding Message Inspectors Imperatively</span></span>  
 <span data-ttu-id="4c9b2-176">앞에서 설명한 이유로 인해 이 샘플에서 지원되지 않는 특성 및 구성이 아닌 동작은 명령 코드를 사용하여 클라이언트 및 서비스 런타임에 매우 쉽게 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-176">Except through attributes (which is not supported in this sample for the reason cited previously) and configuration, behaviors can quite easily be added to a client and service runtime using imperative code.</span></span> <span data-ttu-id="4c9b2-177">이 샘플에서는 클라이언트 응용 프로그램에서 이 작업을 수행하여 클라이언트 메시지 검사자를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-177">In this sample, this is done in the client application to test the client message inspector.</span></span> <span data-ttu-id="4c9b2-178">`GenericClient` 클래스는 끝점 구성을 사용자 코드에 노출하는 <xref:System.ServiceModel.ClientBase%601>에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-178">The `GenericClient` class is derived from <xref:System.ServiceModel.ClientBase%601>, which exposes the endpoint configuration to the user code.</span></span> <span data-ttu-id="4c9b2-179">예를 들어, 다음 코드와 같이 동작을 추가하면 클라이언트를 암시적으로 열기 전에 끝점 구성을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-179">Before the client is implicitly opened the endpoint configuration can be changed, for instance by adding behaviors as shown in the following code.</span></span> <span data-ttu-id="4c9b2-180">서비스에서 동작을 추가하는 작업은 여기에 표시된 클라이언트 기술과 거의 동일하며 서비스 호스트를 열기 전에 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-180">Adding the behavior on the service is largely equivalent to the client technique shown here and must be performed before the service host is opened.</span></span>  
  
```  
try  
{  
    Console.WriteLine("*** Call 'Hello' with generic client, with client behavior");  
    GenericClient client = new GenericClient();  
  
    // Configure client programmatically, adding behavior  
    XmlSchema schema = XmlSchema.Read(new StreamReader("messages.xsd"),   
                                                          null);  
    XmlSchemaSet schemaSet = new XmlSchemaSet();  
    schemaSet.Add(schema);  
    client.Endpoint.Behaviors.Add(new   
                SchemaValidationBehavior(schemaSet, true, true));  
  
    Console.WriteLine("--- Sending valid client request:");  
    GenericCallValid(client, helloAction);  
    Console.WriteLine("--- Sending invalid client request:");  
    GenericCallInvalid(client, helloAction);  
  
    client.Close();  
}  
catch (Exception e)  
{  
    DumpException(e);  
}  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="4c9b2-181">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="4c9b2-181">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="4c9b2-182">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-182">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="4c9b2-183">지침에 따라 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-183">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="4c9b2-184">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-184">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4c9b2-185">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-185">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4c9b2-186">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-186">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="4c9b2-187">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-187">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4c9b2-188">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c9b2-188">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageInspectors`  
  
## <a name="see-also"></a><span data-ttu-id="4c9b2-189">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4c9b2-189">See Also</span></span>
