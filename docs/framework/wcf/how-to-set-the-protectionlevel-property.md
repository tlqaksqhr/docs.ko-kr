---
title: "방법: ProtectionLevel 속성 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, security
- ProtectionLevel property
ms.assetid: 3d4e8f80-0f9e-4a26-9899-beb6584e78df
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3a5c1104ca38f625d5869b4c34e6c48dbb145fed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-the-protectionlevel-property"></a><span data-ttu-id="9276c-102">방법: ProtectionLevel 속성 설정</span><span class="sxs-lookup"><span data-stu-id="9276c-102">How to: Set the ProtectionLevel Property</span></span>
<span data-ttu-id="9276c-103">적절한 특성을 적용하고 속성을 설정하여 보호 수준을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9276c-103">You can set the protection level by applying an appropriate attribute and setting the property.</span></span> <span data-ttu-id="9276c-104">각 메시지의 모든 부분에 영향을 주도록 서비스 수준에서 보호를 설정하거나 메서드에서 메시지 부분으로 점차 세부적인 수준에서 보호를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9276c-104">You can set protection at the service level to affect all parts of every message, or you can set protection at increasingly granular levels, from methods to message parts.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="9276c-105">`ProtectionLevel` 속성 참조 [보호 수준 이해](../../../docs/framework/wcf/understanding-protection-level.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9276c-105"> the `ProtectionLevel` property, see [Understanding Protection Level](../../../docs/framework/wcf/understanding-protection-level.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9276c-106">구성이 아닌 코드에서만 보호 수준을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9276c-106">You can set protection levels only in code, not in configuration.</span></span>  
  
### <a name="to-sign-all-messages-for-a-service"></a><span data-ttu-id="9276c-107">서비스의 모든 메시지를 서명하려면</span><span class="sxs-lookup"><span data-stu-id="9276c-107">To sign all messages for a service</span></span>  
  
1.  <span data-ttu-id="9276c-108">서비스에 대한 인터페이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9276c-108">Create an interface for the service.</span></span>  
  
2.  <span data-ttu-id="9276c-109">다음 코드에 표시된 것처럼 <xref:System.ServiceModel.ServiceContractAttribute> 특성을 서비스에 적용하고 <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> 속성을 <xref:System.Net.Security.ProtectionLevel.Sign>으로 설정합니다. 기본 수준은 <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>입니다.</span><span class="sxs-lookup"><span data-stu-id="9276c-109">Apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the service and set the <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> property to <xref:System.Net.Security.ProtectionLevel.Sign>, as shown in the following code (the default level is <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>).</span></span>  
  
     [!code-csharp[C_ProtectionLevel#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#1)]
     [!code-vb[C_ProtectionLevel#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#1)]  
  
### <a name="to-sign-all-message-parts-for-an-operation"></a><span data-ttu-id="9276c-110">작업에 대한 모든 메시지 부분을 서명하려면</span><span class="sxs-lookup"><span data-stu-id="9276c-110">To sign all message parts for an operation</span></span>  
  
1.  <span data-ttu-id="9276c-111">서비스에 대한 인터페이스를 만들고 <xref:System.ServiceModel.ServiceContractAttribute> 특성을 인터페이스에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="9276c-111">Create an interface for the service and apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the interface.</span></span>  
  
2.  <span data-ttu-id="9276c-112">메서드 선언을 인터페이스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9276c-112">Add a method declaration to the interface.</span></span>  
  
3.  <span data-ttu-id="9276c-113">다음 코드에 표시된 것처럼 <xref:System.ServiceModel.OperationContractAttribute> 특성을 메서드에 적용하고 <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> 속성을 <xref:System.Net.Security.ProtectionLevel.Sign>으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9276c-113">Apply the <xref:System.ServiceModel.OperationContractAttribute> attribute to the method, and set the <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> property to <xref:System.Net.Security.ProtectionLevel.Sign>, as shown in the following code.</span></span>  
  
     [!code-csharp[C_ProtectionLevel#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#2)]
     [!code-vb[C_ProtectionLevel#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#2)]  
  
## <a name="protecting-fault-messages"></a><span data-ttu-id="9276c-114">오류 메시지 보호</span><span class="sxs-lookup"><span data-stu-id="9276c-114">Protecting Fault Messages</span></span>  
 <span data-ttu-id="9276c-115">서비스에서 throw된 예외는 클라이언트에 SOAP 오류로 전송될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9276c-115">Exceptions that are thrown on a service can be sent to a client as SOAP faults.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="9276c-116">강력한 형식의 만들고 오류를 참조 하십시오. [지정 및 계약 및 서비스에서 오류 처리](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md) 및 [하는 방법: 서비스 계약에 선언 오류](../../../docs/framework/wcf/how-to-declare-faults-in-service-contracts.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9276c-116"> creating strongly typed faults, see [Specifying and Handling Faults in Contracts and Services](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md) and [How to: Declare Faults in Service Contracts](../../../docs/framework/wcf/how-to-declare-faults-in-service-contracts.md).</span></span>  
  
#### <a name="to-protect-a-fault-message"></a><span data-ttu-id="9276c-117">오류 메시지를 보호하려면</span><span class="sxs-lookup"><span data-stu-id="9276c-117">To protect a fault message</span></span>  
  
1.  <span data-ttu-id="9276c-118">오류 메시지를 나타내는 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9276c-118">Create a type that represents the fault message.</span></span> <span data-ttu-id="9276c-119">다음 예제에서는 두 개의 필드를 사용하여 `MathFault`라는 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9276c-119">The following example creates a class named `MathFault` with two fields.</span></span>  
  
2.  <span data-ttu-id="9276c-120">다음 코드에 표시된 것처럼 <xref:System.Runtime.Serialization.DataContractAttribute> 특성을 형식에 적용하고 <xref:System.Runtime.Serialization.DataMemberAttribute> 특성을 serialize해야 하는 각 필드에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="9276c-120">Apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to the type and a <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to each field that should be serialized, as shown in the following code.</span></span>  
  
     [!code-csharp[C_ProtectionLevel#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#3)]
     [!code-vb[C_ProtectionLevel#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#3)]  
  
3.  <span data-ttu-id="9276c-121">오류를 반환할 인터페이스에서 <xref:System.ServiceModel.FaultContractAttribute> 특성을 오류를 반환할 메서드에 적용하고 `detailType` 매개 변수를 오류 클래스 형식으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9276c-121">In the interface that will return the fault, apply the <xref:System.ServiceModel.FaultContractAttribute> attribute to the method that will return the fault and set the `detailType` parameter to the type of the fault class.</span></span>  
  
4.  <span data-ttu-id="9276c-122">또한 다음 코드에 표시된 것처럼 생성자에서 <xref:System.ServiceModel.FaultContractAttribute.ProtectionLevel%2A> 속성을 <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9276c-122">Also in the constructor, set the <xref:System.ServiceModel.FaultContractAttribute.ProtectionLevel%2A> property to <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>, as shown in the following code.</span></span>  
  
     [!code-csharp[C_ProtectionLevel#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#4)]
     [!code-vb[C_ProtectionLevel#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#4)]  
  
## <a name="protecting-message-parts"></a><span data-ttu-id="9276c-123">메시지 부분 보호</span><span class="sxs-lookup"><span data-stu-id="9276c-123">Protecting Message Parts</span></span>  
 <span data-ttu-id="9276c-124">메시지 계약을 사용하여 메시지의 일부분을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="9276c-124">Use a message contract to protect parts of a message.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="9276c-125">메시지 계약과, 참조 [메시지 계약을 사용 하 여](../../../docs/framework/wcf/feature-details/using-message-contracts.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9276c-125"> message contracts, see [Using Message Contracts](../../../docs/framework/wcf/feature-details/using-message-contracts.md).</span></span>  
  
#### <a name="to-protect-a-message-body"></a><span data-ttu-id="9276c-126">메시지 본문을 보호하려면</span><span class="sxs-lookup"><span data-stu-id="9276c-126">To protect a message body</span></span>  
  
1.  <span data-ttu-id="9276c-127">메시지를 나타내는 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9276c-127">Create a type that represents the message.</span></span> <span data-ttu-id="9276c-128">다음 예제에서는 `Company` 및 `CompanyName` 필드를 사용하여 `CompanyID`를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9276c-128">The following example creates a `Company` class with two fields, `CompanyName` and `CompanyID`.</span></span>  
  
2.  <span data-ttu-id="9276c-129"><xref:System.ServiceModel.MessageContractAttribute> 특성을 클래스에 적용하고 <xref:System.ServiceModel.MessageContractAttribute.ProtectionLevel%2A> 속성을 <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9276c-129">Apply the <xref:System.ServiceModel.MessageContractAttribute> attribute to the class and set the <xref:System.ServiceModel.MessageContractAttribute.ProtectionLevel%2A> property to <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.</span></span>  
  
3.  <span data-ttu-id="9276c-130"><xref:System.ServiceModel.MessageHeaderAttribute> 특성을 메시지 헤더로 표시될 필드에 적용하고 `ProtectionLevel` 특성을 <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9276c-130">Apply the <xref:System.ServiceModel.MessageHeaderAttribute> attribute to a field that will be expressed as a message header and set the `ProtectionLevel` property to <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.</span></span>  
  
4.  <span data-ttu-id="9276c-131">적용 된 <xref:System.ServiceModel.MessageBodyMemberAttribute> 메시지 본문의 일부로 표현 되 고 설정 하는 모든 필드에는 `ProtectionLevel` 속성을 <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>다음 예제에 나온 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="9276c-131">Apply the <xref:System.ServiceModel.MessageBodyMemberAttribute> to any field that will be expressed as part of the message body, and set the `ProtectionLevel` property to <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>, as shown in the following example.</span></span>  
  
     [!code-csharp[C_ProtectionLevel#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#5)]
     [!code-vb[C_ProtectionLevel#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="9276c-132">예제</span><span class="sxs-lookup"><span data-stu-id="9276c-132">Example</span></span>  
 <span data-ttu-id="9276c-133">다음 예제에서는 서비스의 다양한 위치에서 여러 특성 클래스의 `ProtectionLevel` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9276c-133">The following example sets the `ProtectionLevel` property of several attribute classes at various places in a service.</span></span>  
  
 [!code-csharp[C_ProtectionLevel#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#6)]
 [!code-vb[C_ProtectionLevel#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#6)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9276c-134">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="9276c-134">Compiling the Code</span></span>  
 <span data-ttu-id="9276c-135">다음 코드에서는 예제 코드를 컴파일하는 데 필요한 네임스페이스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9276c-135">The following code shows the namespaces required to compile the example code.</span></span>  
  
 [!code-csharp[C_ProtectionLevel#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#0)]
 [!code-vb[C_ProtectionLevel#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="9276c-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9276c-136">See Also</span></span>  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>  
 <xref:System.ServiceModel.FaultContractAttribute>  
 <xref:System.ServiceModel.MessageContractAttribute>  
 <xref:System.ServiceModel.MessageBodyMemberAttribute>  
 [<span data-ttu-id="9276c-137">보호 수준 이해</span><span class="sxs-lookup"><span data-stu-id="9276c-137">Understanding Protection Level</span></span>](../../../docs/framework/wcf/understanding-protection-level.md)
