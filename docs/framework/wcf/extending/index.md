---
title: WCF 확장
ms.date: 03/30/2017
helpviewer_keywords:
- WCF, extensibility
- extensibility [WCF]
- Windows Communication Foundation, extensibility
ms.assetid: c145e2f6-f402-41f5-8b5a-eee03978737b
ms.openlocfilehash: 24ad74f04a3ac31d0b0d0d87f0d74f88c0521f50
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="extending-wcf"></a><span data-ttu-id="04049-102">WCF 확장</span><span class="sxs-lookup"><span data-stu-id="04049-102">Extending WCF</span></span>
<span data-ttu-id="04049-103">Windows Communication Foundation (WCF) 수정 하 고 정확 하 게 제어 런타임 구성 요소 및 서비스 기반 응용 프로그램을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04049-103">Windows Communication Foundation (WCF) allows you to modify and extend run time components to precisely control and extend service-based applications.</span></span> <span data-ttu-id="04049-104">이 섹션의 항목에서는 확장성 아키텍처에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="04049-104">The topics in this section go in depth about the extensibility architecture.</span></span> <span data-ttu-id="04049-105">기본 프로그래밍에 대 한 자세한 내용은 참조 [기본 WCF 프로그래밍](../../../../docs/framework/wcf/basic-wcf-programming.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="04049-105">For more information about basic programming, see [Basic WCF Programming](../../../../docs/framework/wcf/basic-wcf-programming.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="04049-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="04049-106">In This Section</span></span>  
 [<span data-ttu-id="04049-107">ServiceHost 및 서비스 모델 계층 확장</span><span class="sxs-lookup"><span data-stu-id="04049-107">Extending ServiceHost and the Service Model Layer</span></span>](../../../../docs/framework/wcf/extending/extending-servicehost-and-the-service-model-layer.md)  
 <span data-ttu-id="04049-108">서비스 모델 계층은 기본 채널에서 들어오는 메시지를 끌어와서 응용 프로그램 코드에서 이를 메서드 호출로 변환하여 결과를 다시 호출자에게 보내는 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="04049-108">The service model layer is responsible for pulling incoming messages out of the underlying channels, translating them into method invocations in application code, and sending the results back to the caller.</span></span>  <span data-ttu-id="04049-109">서비스 모델 확장은 디스패처 기능, 사용자 지정 동작, 메시지 및 매개 변수 가로채기 그리고 다른 확장명 기능이 포함된 통신 동작 및 기능 또는 실행을 수정하거나 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="04049-109">Service model extensions modify or implement execution or communication behavior and features involving dispatcher functionality, custom behaviors, message and parameter interception, and other extensibility functionality.</span></span>  
  
 [<span data-ttu-id="04049-110">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="04049-110">Extending Bindings</span></span>](../../../../docs/framework/wcf/extending/extending-bindings.md)  
 <span data-ttu-id="04049-111">바인딩은 끝점에 연결하는 데 필요한 통신 세부 사항을 설명하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="04049-111">Bindings are objects that describe the communication details required to connect to an endpoint.</span></span> <span data-ttu-id="04049-112">바인딩 확장이나 사용자 지정 바인딩은 응용 프로그램 기능을 지원하는 데 필요한 사용자 지정 통신 기능을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="04049-112">Binding extensions or custom bindings implement custom communication functionality required to support application features.</span></span>  
  
 [<span data-ttu-id="04049-113">채널 계층 확장</span><span class="sxs-lookup"><span data-stu-id="04049-113">Extending the Channel Layer</span></span>](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md)  
 <span data-ttu-id="04049-114">채널 계층은 서비스 모델 계층 아래에 있고 클라이언트와 서비스 간의 메시지 교환을 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="04049-114">The channel layer sits beneath the service model layer and is responsible for the exchange of messages between clients and services.</span></span> <span data-ttu-id="04049-115">채널 확장은 보안 등의 새 프로토콜 기능을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04049-115">Channel extensions can implement new protocol functionality, such as security.</span></span> <span data-ttu-id="04049-116">또한 채널 확장은 SOAP 메시지를 전달할 새 네트워크 전송 구현 같은 전송 기능을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="04049-116">Channel extensions also transport functionality, such as implementing a new network transport to carry SOAP messages.</span></span>  
  
 [<span data-ttu-id="04049-117">보안 확장</span><span class="sxs-lookup"><span data-stu-id="04049-117">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
 <span data-ttu-id="04049-118">WCF의 보안 전송 구성 됩니다 (무결성, 기밀성 및 인증), 보안 액세스 제어 (권한 부여) 및 감사 합니다.</span><span class="sxs-lookup"><span data-stu-id="04049-118">Security in WCF consists of transfer security (integrity, confidentiality, and authentication), access control (authorization) and auditing.</span></span> <span data-ttu-id="04049-119">찾을 수는 클래스는 `IdentityModel` 네임 스페이스는 WCF에서 액세스 제어에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04049-119">The classes found in the `IdentityModel` namespace are used by WCF for access control.</span></span> <span data-ttu-id="04049-120">보안 아키텍처를 이해하면 사용자 지정 액세스 제어 시스템을 수용할 사용자 지정 클레임 형식을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04049-120">Understanding the security architecture allows you to create custom claim types to accommodate custom access control systems.</span></span>  
  
 [<span data-ttu-id="04049-121">메타데이터 시스템 확장</span><span class="sxs-lookup"><span data-stu-id="04049-121">Extending the Metadata System</span></span>](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)  
 <span data-ttu-id="04049-122">WCF 메타 데이터 시스템은 서비스 기반 응용 프로그램을 구현 하는 데 필요한 메타 데이터를 나타내는 인터페이스 및 클래스의 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="04049-122">The WCF metadata system is a group of classes and interfaces that represent metadata required to implement service-based applications.</span></span> <span data-ttu-id="04049-123">클래스를 수정 또는 확장하거나 인터페이스를 구현 및 구성하여 WSDL(웹 서비스 기술 언어) 확장이나 사용자 지정 WS-PolicyAttachments 어설션 같은 사용자 지정 메타데이터를 내보내고 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="04049-123">Modify or extend the classes or implement and configure the interfaces to export and import custom metadata such as Web Services Description Language (WSDL) extensions or custom WS-PolicyAttachments assertions.</span></span>  
  
 [<span data-ttu-id="04049-124">인코더 및 직렬 변환기 확장</span><span class="sxs-lookup"><span data-stu-id="04049-124">Extending Encoders and Serializers</span></span>](../../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md)  
 <span data-ttu-id="04049-125">인코더 및 serializer는 데이터를 다른 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="04049-125">Encoders and serializers translate data from one form to another.</span></span> <span data-ttu-id="04049-126">이 섹션의 항목에서는 제공된 클래스를 특별한 요구 사항에 맞게 확장하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="04049-126">The topics in this section discuss how to extend the supplied classes to meet special requirements.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="04049-127">참조</span><span class="sxs-lookup"><span data-stu-id="04049-127">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Tokens>  
  
## <a name="related-sections"></a><span data-ttu-id="04049-128">관련 단원</span><span class="sxs-lookup"><span data-stu-id="04049-128">Related Sections</span></span>  
 [<span data-ttu-id="04049-129">기본 WCF 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="04049-129">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
 [<span data-ttu-id="04049-130">WCF 기능 정보</span><span class="sxs-lookup"><span data-stu-id="04049-130">WCF Feature Details</span></span>](../../../../docs/framework/wcf/feature-details/index.md)  
  
 [<span data-ttu-id="04049-131">지침 및 모범 사례</span><span class="sxs-lookup"><span data-stu-id="04049-131">Guidelines and Best Practices</span></span>](../../../../docs/framework/wcf/guidelines-and-best-practices.md)
