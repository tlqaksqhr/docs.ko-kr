---
title: 서비스 구성
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [WCF]
ms.assetid: beac771e-f28e-4f84-9ff1-ad9251c726d3
ms.openlocfilehash: 7718edaefbad18afa11b3e3680fac39da585a610
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="configuring-services"></a><span data-ttu-id="85af7-102">서비스 구성</span><span class="sxs-lookup"><span data-stu-id="85af7-102">Configuring Services</span></span>
<span data-ttu-id="85af7-103">서비스 계약을 디자인하고 구현했으면 서비스를 구성할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="85af7-103">Once you have designed and implemented your service contract, you are ready to configure your service.</span></span> <span data-ttu-id="85af7-104">여기서 서비스를 찾을 수 있는 주소, 메시지를 보내고 받는 데 사용하는 전송 및 메시지 인코딩, 서비스에 필요한 보안 형식 지정 등 서비스가 클라이언트에 노출되는 방법을 정의하고 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85af7-104">This is where you define and customize how your service is exposed to clients, including specifying the address where it can be found, the transport and message encoding it uses to send and receive messages, and the type of security it requires.</span></span>  
  
 <span data-ttu-id="85af7-105">여기서 사용되는 구성은 코드에서 명령적으로 또는 구성 파일을 사용하여 끝점 주소, 사용된 전송 및 보안 체계 지정 같은 서비스의 다양한 측면을 정의하고 사용자 지정할 수 있는 모든 방식이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="85af7-105">Configuration as used here includes all the ways, imperatively in code or by using a configuration file, in which you can define and customize the various aspects of a service, such as specifying its endpoint addresses, the transports used, and its security schemes.</span></span> <span data-ttu-id="85af7-106">실제로 구성 작성은 주요 WCF 응용 프로그램 프로그래밍의 일부가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85af7-106">In practice, writing configuration is a major part of programming WCF applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="85af7-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="85af7-107">In This Section</span></span>  
 [<span data-ttu-id="85af7-108">단순화된 구성</span><span class="sxs-lookup"><span data-stu-id="85af7-108">Simplified Configuration</span></span>](../../../docs/framework/wcf/simplified-configuration.md)  
 <span data-ttu-id="85af7-109">부터는 [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], WCF WCF 구성 요구 사항을 간소화 하는 새로운 기본 구성 모델이 함께 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="85af7-109">Starting with [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], WCF comes with a new default configuration model that simplifies WCF configuration requirements.</span></span> <span data-ttu-id="85af7-110">특정 서비스에 대 한 모든 WCF 구성 정보를 제공 하지 않으면 런타임에서 기본 끝점, 바인딩 및 동작으로 서비스에 자동으로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="85af7-110">If you do not provide any WCF configuration for a particular service, the runtime automatically configures your service with default endpoints, bindings, and behaviors.</span></span>  
  
 [<span data-ttu-id="85af7-111">구성 파일을 사용하여 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="85af7-111">Configuring Services Using Configuration Files</span></span>](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)  
 <span data-ttu-id="85af7-112">Windows Communication Foundation (WCF) 서비스를 사용 하 여 구성할 수는 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 기술을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="85af7-112">A Windows Communication Foundation (WCF) service is configurable using the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] configuration technology.</span></span> <span data-ttu-id="85af7-113">가장 일반적으로 XML 요소는 WCF 서비스를 호스트 하는 인터넷 정보 서비스 (IIS) 사이트의 Web.config 파일에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85af7-113">Most commonly, XML elements are added to the Web.config file for an Internet Information Services (IIS) site that hosts a WCF service.</span></span> <span data-ttu-id="85af7-114">이 요소를 사용하여 끝점 주소(서비스와의 통신에 사용되는 실제 주소) 등의 세부 사항을 컴퓨터별로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85af7-114">The elements allow you to change details, such as the endpoint addresses (the actual addresses used to communicate with the service) on a machine-by-machine basis.</span></span>  
  
 [<span data-ttu-id="85af7-115">바인딩</span><span class="sxs-lookup"><span data-stu-id="85af7-115">Bindings</span></span>](../../../docs/framework/wcf/bindings.md)  
 <span data-ttu-id="85af7-116">또한 WCF 신속 하 게 전송, 보안 및 메시지 인코딩을 사용 되는 등 클라이언트와 서비스가 통신 하는 방법에 대 한 가장 기본적인 기능을 선택할 수 있도록 하는 바인딩 형태로 여러 시스템 제공 일반 구성이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85af7-116">In addition, WCF includes several system-provided common configurations in the form of bindings that allow you to quickly select the most basic features for how a client and service communicate, such as the transports, security, and message encodings used.</span></span>  
  
 [<span data-ttu-id="85af7-117">끝점</span><span class="sxs-lookup"><span data-stu-id="85af7-117">Endpoints</span></span>](../../../docs/framework/wcf/endpoints.md)  
 <span data-ttu-id="85af7-118">WCF 서비스와 모든 통신을 통해 수행 된 *끝점* 서비스의 합니다.</span><span class="sxs-lookup"><span data-stu-id="85af7-118">All communication with a WCF service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="85af7-119">끝점에는 계약, 바인딩에 지정된 구성 정보 및 서비스를 찾을 위치나 서비스 정보를 얻을 수 있는 위치를 나타내는 주소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85af7-119">Endpoints contain the contract, the configuration information that is specified in the bindings, and the addresses that indicate where to find the service or where to obtain information about the service.</span></span>  
  
 [<span data-ttu-id="85af7-120">서비스에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="85af7-120">Securing Services</span></span>](../../../docs/framework/wcf/securing-services.md)  
 <span data-ttu-id="85af7-121">WCF를 사용 하 고 기존 보안 메커니즘, 기밀성, 무결성, 인증 및 권한 부여를 서비스에 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85af7-121">Using WCF and existing security mechanisms, you can implement confidentiality, integrity, authentication, and authorization into any service.</span></span> <span data-ttu-id="85af7-122">보안 성공 및 실패를 감사할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85af7-122">You can also audit for security successes and failures.</span></span>  
  
 [<span data-ttu-id="85af7-123">WS-I Basic Profile 1.1 상호 운용할 수 있는 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="85af7-123">Creating WS-I Basic Profile 1.1 Interoperable Services</span></span>](../../../docs/framework/wcf/creating-ws-i-basic-profile-1-1-interoperable-services.md)  
 <span data-ttu-id="85af7-124">다른 플랫폼 또는 운영 체제의 서비스 및 클라이언트와 상호 운용될 수 있는 서비스를 배포하기 위한 요구 사항은 WS-I Basic Profile 1.1 사양에 간략하게 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85af7-124">The requirements for deploying a service that is interoperable with services and clients on any other platform or operating system are outlined in the WS-I Basic Profile 1.1 specification.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="85af7-125">참조</span><span class="sxs-lookup"><span data-stu-id="85af7-125">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
## <a name="related-sections"></a><span data-ttu-id="85af7-126">관련 단원</span><span class="sxs-lookup"><span data-stu-id="85af7-126">Related Sections</span></span>  
 [<span data-ttu-id="85af7-127">기본 프로그래밍 수명 주기</span><span class="sxs-lookup"><span data-stu-id="85af7-127">Basic Programming Lifecycle</span></span>](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
  
 [<span data-ttu-id="85af7-128">서비스 디자인 및 구현</span><span class="sxs-lookup"><span data-stu-id="85af7-128">Designing and Implementing Services</span></span>](../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
 [<span data-ttu-id="85af7-129">서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="85af7-129">Hosting Services</span></span>](../../../docs/framework/wcf/hosting-services.md)  
  
 [<span data-ttu-id="85af7-130">클라이언트 빌드</span><span class="sxs-lookup"><span data-stu-id="85af7-130">Building Clients</span></span>](../../../docs/framework/wcf/building-clients.md)  
  
 [<span data-ttu-id="85af7-131">확장성 소개</span><span class="sxs-lookup"><span data-stu-id="85af7-131">Introduction to Extensibility</span></span>](../../../docs/framework/wcf/introduction-to-extensibility.md)  
  
 [<span data-ttu-id="85af7-132">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="85af7-132">Administration and Diagnostics</span></span>](../../../docs/framework/wcf/diagnostics/index.md)  
  
## <a name="see-also"></a><span data-ttu-id="85af7-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="85af7-133">See Also</span></span>  
 [<span data-ttu-id="85af7-134">기본 WCF 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="85af7-134">Basic WCF Programming</span></span>](../../../docs/framework/wcf/basic-wcf-programming.md)  
 [<span data-ttu-id="85af7-135">개념적 개요</span><span class="sxs-lookup"><span data-stu-id="85af7-135">Conceptual Overview</span></span>](../../../docs/framework/wcf/conceptual-overview.md)  
 [<span data-ttu-id="85af7-136">WCF 기능 정보</span><span class="sxs-lookup"><span data-stu-id="85af7-136">WCF Feature Details</span></span>](../../../docs/framework/wcf/feature-details/index.md)
