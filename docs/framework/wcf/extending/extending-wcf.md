---
title: "WCF 확장"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF, extensibility
- extensibility [WCF]
- Windows Communication Foundation, extensibility
ms.assetid: c145e2f6-f402-41f5-8b5a-eee03978737b
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3faa09a550bdc32437aeac864f09ec7711bdaf97
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="extending-wcf"></a><span data-ttu-id="f1bad-102">WCF 확장</span><span class="sxs-lookup"><span data-stu-id="f1bad-102">Extending WCF</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="f1bad-103">에서는 런타임 구성 요소를 수정하고 확장하여 서비스 기반 응용 프로그램을 정확하게 제어하고 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1bad-103"> allows you to modify and extend run time components to precisely control and extend service-based applications.</span></span> <span data-ttu-id="f1bad-104">이 섹션의 항목에서는 확장성 아키텍처에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f1bad-104">The topics in this section go in depth about the extensibility architecture.</span></span> <span data-ttu-id="f1bad-105">기본 프로그래밍에 대 한 자세한 내용은 참조 [기본 WCF 프로그래밍](../../../../docs/framework/wcf/basic-wcf-programming.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f1bad-105">For more information about basic programming, see [Basic WCF Programming](../../../../docs/framework/wcf/basic-wcf-programming.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f1bad-106">단원 내용</span><span class="sxs-lookup"><span data-stu-id="f1bad-106">In This Section</span></span>  
 [<span data-ttu-id="f1bad-107">확장 ServiceHost 및 서비스 모델 계층</span><span class="sxs-lookup"><span data-stu-id="f1bad-107">Extending ServiceHost and the Service Model Layer</span></span>](../../../../docs/framework/wcf/extending/extending-servicehost-and-the-service-model-layer.md)  
 <span data-ttu-id="f1bad-108">서비스 모델 계층은 기본 채널에서 들어오는 메시지를 끌어와서 응용 프로그램 코드에서 이를 메서드 호출로 변환하여 결과를 다시 호출자에게 보내는 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1bad-108">The service model layer is responsible for pulling incoming messages out of the underlying channels, translating them into method invocations in application code, and sending the results back to the caller.</span></span>  <span data-ttu-id="f1bad-109">서비스 모델 확장은 디스패처 기능, 사용자 지정 동작, 메시지 및 매개 변수 가로채기 그리고 다른 확장명 기능이 포함된 통신 동작 및 기능 또는 실행을 수정하거나 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="f1bad-109">Service model extensions modify or implement execution or communication behavior and features involving dispatcher functionality, custom behaviors, message and parameter interception, and other extensibility functionality.</span></span>  
  
 [<span data-ttu-id="f1bad-110">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="f1bad-110">Extending Bindings</span></span>](../../../../docs/framework/wcf/extending/extending-bindings.md)  
 <span data-ttu-id="f1bad-111">바인딩은 끝점에 연결하는 데 필요한 통신 세부 사항을 설명하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f1bad-111">Bindings are objects that describe the communication details required to connect to an endpoint.</span></span> <span data-ttu-id="f1bad-112">바인딩 확장이나 사용자 지정 바인딩은 응용 프로그램 기능을 지원하는 데 필요한 사용자 지정 통신 기능을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="f1bad-112">Binding extensions or custom bindings implement custom communication functionality required to support application features.</span></span>  
  
 [<span data-ttu-id="f1bad-113">채널 계층 확장</span><span class="sxs-lookup"><span data-stu-id="f1bad-113">Extending the Channel Layer</span></span>](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md)  
 <span data-ttu-id="f1bad-114">채널 계층은 서비스 모델 계층 아래에 있고 클라이언트와 서비스 간의 메시지 교환을 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="f1bad-114">The channel layer sits beneath the service model layer and is responsible for the exchange of messages between clients and services.</span></span> <span data-ttu-id="f1bad-115">채널 확장은 보안 등의 새 프로토콜 기능을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1bad-115">Channel extensions can implement new protocol functionality, such as security.</span></span> <span data-ttu-id="f1bad-116">또한 채널 확장은 SOAP 메시지를 전달할 새 네트워크 전송 구현 같은 전송 기능을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="f1bad-116">Channel extensions also transport functionality, such as implementing a new network transport to carry SOAP messages.</span></span>  
  
 [<span data-ttu-id="f1bad-117">보안 확장</span><span class="sxs-lookup"><span data-stu-id="f1bad-117">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
 <span data-ttu-id="f1bad-118">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 보안은 전송 보안(무결성, 기밀성 및 인증), 액세스 제어(권한 부여) 및 감사로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1bad-118">Security in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] consists of transfer security (integrity, confidentiality, and authentication), access control (authorization) and auditing.</span></span> <span data-ttu-id="f1bad-119">`IdentityModel` 네임스페이스에 있는 클래스는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 액세스 제어에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f1bad-119">The classes found in the `IdentityModel` namespace are used by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] for access control.</span></span> <span data-ttu-id="f1bad-120">보안 아키텍처를 이해하면 사용자 지정 액세스 제어 시스템을 수용할 사용자 지정 클레임 형식을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1bad-120">Understanding the security architecture allows you to create custom claim types to accommodate custom access control systems.</span></span>  
  
 [<span data-ttu-id="f1bad-121">메타 데이터 시스템 확장</span><span class="sxs-lookup"><span data-stu-id="f1bad-121">Extending the Metadata System</span></span>](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)  
 <span data-ttu-id="f1bad-122">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 메타데이터 시스템은 서비스 기반 응용 프로그램 구현에 필요한 메타데이터를 나타내는 클래스 및 인터페이스 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="f1bad-122">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] metadata system is a group of classes and interfaces that represent metadata required to implement service-based applications.</span></span> <span data-ttu-id="f1bad-123">클래스를 수정 또는 확장하거나 인터페이스를 구현 및 구성하여 WSDL(웹 서비스 기술 언어) 확장이나 사용자 지정 WS-PolicyAttachments 어설션 같은 사용자 지정 메타데이터를 내보내고 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f1bad-123">Modify or extend the classes or implement and configure the interfaces to export and import custom metadata such as Web Services Description Language (WSDL) extensions or custom WS-PolicyAttachments assertions.</span></span>  
  
 [<span data-ttu-id="f1bad-124">인코더 및 Serializer 확장</span><span class="sxs-lookup"><span data-stu-id="f1bad-124">Extending Encoders and Serializers</span></span>](../../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md)  
 <span data-ttu-id="f1bad-125">인코더 및 serializer는 데이터를 다른 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="f1bad-125">Encoders and serializers translate data from one form to another.</span></span> <span data-ttu-id="f1bad-126">이 섹션의 항목에서는 제공된 클래스를 특별한 요구 사항에 맞게 확장하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f1bad-126">The topics in this section discuss how to extend the supplied classes to meet special requirements.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f1bad-127">참조</span><span class="sxs-lookup"><span data-stu-id="f1bad-127">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Tokens>  
  
## <a name="related-sections"></a><span data-ttu-id="f1bad-128">관련 단원</span><span class="sxs-lookup"><span data-stu-id="f1bad-128">Related Sections</span></span>  
 [<span data-ttu-id="f1bad-129">기본 WCF 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="f1bad-129">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
 [<span data-ttu-id="f1bad-130">WCF 기능 정보</span><span class="sxs-lookup"><span data-stu-id="f1bad-130">WCF Feature Details</span></span>](../../../../docs/framework/wcf/feature-details/index.md)  
  
 [<span data-ttu-id="f1bad-131">지침 및 모범 사례</span><span class="sxs-lookup"><span data-stu-id="f1bad-131">Guidelines and Best Practices</span></span>](../../../../docs/framework/wcf/guidelines-and-best-practices.md)
