---
title: "데이터 전송 및 Serialization"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data serialization [WCF]
- data transfer [WCF]
ms.assetid: 0f03c635-f3e7-4c5c-9463-3cb0135e221e
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 29ca4041e24a99546dfb665b0ce9e695732442d4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="data-transfer-and-serialization"></a><span data-ttu-id="9936d-102">데이터 전송 및 Serialization</span><span class="sxs-lookup"><span data-stu-id="9936d-102">Data Transfer and Serialization</span></span>
<span data-ttu-id="9936d-103">연결된 시스템에서 서비스 및 클라이언트는 데이터 교환에 의존하여 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9936d-103">In a connected system, services and clients depend on the exchange of data to accomplish any task.</span></span> <span data-ttu-id="9936d-104">서비스 또는 클라이언트 개발자는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서 데이터 및 데이터 serialization을 처리하는 방식을 알고 있어야 유지 관리가 효율적이고 쉬운 응용 프로그램을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9936d-104">As a developer of a service or client, you must also understand how [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] handles data and data serialization in order to create applications that are efficient and easy to maintain.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9936d-105">단원 내용</span><span class="sxs-lookup"><span data-stu-id="9936d-105">In This Section</span></span>  
 [<span data-ttu-id="9936d-106">Specifying Data Transfer in Service Contracts</span><span class="sxs-lookup"><span data-stu-id="9936d-106">Specifying Data Transfer in Service Contracts</span></span>](../../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md)  
 <span data-ttu-id="9936d-107">서비스에서 데이터 전송의 기본 개념에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9936d-107">Describes the basic concepts of data transfer in services.</span></span>  
  
 [<span data-ttu-id="9936d-108">데이터 계약 사용</span><span class="sxs-lookup"><span data-stu-id="9936d-108">Using Data Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 <span data-ttu-id="9936d-109">데이터 계약의 정의와 데이터 계약을 만들고 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9936d-109">Describes what data contracts are and how to create and use them.</span></span>  
  
 [<span data-ttu-id="9936d-110">데이터 계약 Serializer</span><span class="sxs-lookup"><span data-stu-id="9936d-110">Data Contract Serializer</span></span>](../../../../docs/framework/wcf/feature-details/data-contract-serializer.md)  
 <span data-ttu-id="9936d-111"><xref:System.Runtime.Serialization.DataContractSerializer> 클래스 또는 <xref:System.Runtime.Serialization.XmlObjectSerializer> 클래스의 확장을 사용하여 데이터의 serialization을 수행하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9936d-111">Describes how to accomplish serialization of data with the <xref:System.Runtime.Serialization.DataContractSerializer> class or any extension of the <xref:System.Runtime.Serialization.XmlObjectSerializer> class.</span></span>  
  
 [<span data-ttu-id="9936d-112">XmlSerializer 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="9936d-112">Using the XmlSerializer Class</span></span>](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md)  
 <span data-ttu-id="9936d-113"><xref:System.Xml.Serialization.XmlSerializer> 클래스 대신 <xref:System.Runtime.Serialization.DataContractSerializer> 클래스를 사용하는 방법 및 이유에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9936d-113">Describes how and why to use the <xref:System.Xml.Serialization.XmlSerializer> class, an alternative to the <xref:System.Runtime.Serialization.DataContractSerializer> class.</span></span>  
  
 [<span data-ttu-id="9936d-114">메시지 계약 사용</span><span class="sxs-lookup"><span data-stu-id="9936d-114">Using Message Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-message-contracts.md)  
 <span data-ttu-id="9936d-115">메시지 계약에서 SOAP 메시지를 정밀하게 제어하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9936d-115">Describes how message contracts allow fine control over SOAP messages.</span></span>  
  
 [<span data-ttu-id="9936d-116">Message 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="9936d-116">Using the Message Class</span></span>](../../../../docs/framework/wcf/feature-details/using-the-message-class.md)  
 <span data-ttu-id="9936d-117">Message 클래스 기능을 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9936d-117">Describes how to use Message class features.</span></span>  
  
 [<span data-ttu-id="9936d-118">필터링</span><span class="sxs-lookup"><span data-stu-id="9936d-118">Filtering</span></span>](../../../../docs/framework/wcf/feature-details/filtering.md)  
 <span data-ttu-id="9936d-119">여러 조건을 기반으로 메시지 전처리를 사용하는 필터링에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9936d-119">Describes filtering, which enables pre-processing of a message based on various criteria.</span></span>  
  
 [<span data-ttu-id="9936d-120">큰 데이터 및 스트리밍</span><span class="sxs-lookup"><span data-stu-id="9936d-120">Large Data and Streaming</span></span>](../../../../docs/framework/wcf/feature-details/large-data-and-streaming.md)  
 <span data-ttu-id="9936d-121">이진 파일과 같은 큰 데이터 블록을 보내는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9936d-121">Describes how to send a large block of data, such as a binary file.</span></span>  
  
 [<span data-ttu-id="9936d-122">데이터에 대 한 보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="9936d-122">Security Considerations for Data</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md)  
 <span data-ttu-id="9936d-123">데이터 전송 및 serialization을 프로그래밍할 때 알고 있어야 하는 항목에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9936d-123">Describes items to be aware of when programming data transfer and serialization.</span></span>  
  
 [<span data-ttu-id="9936d-124">데이터 전송 아키텍처 개요</span><span class="sxs-lookup"><span data-stu-id="9936d-124">Data Transfer Architectural Overview</span></span>](../../../../docs/framework/wcf/feature-details/data-transfer-architectural-overview.md)  
 <span data-ttu-id="9936d-125">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 데이터 전송에 대한 전체적인 설계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9936d-125">Describes a view of the overall design of data transfer in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
## <a name="reference"></a><span data-ttu-id="9936d-126">참조</span><span class="sxs-lookup"><span data-stu-id="9936d-126">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
  
 <xref:System.Xml.Serialization.XmlSerializer>  
  
 <xref:System.Runtime.Serialization>  
  
 <xref:System.Xml.Serialization>  
  
## <a name="related-sections"></a><span data-ttu-id="9936d-127">관련 단원</span><span class="sxs-lookup"><span data-stu-id="9936d-127">Related Sections</span></span>  
 [<span data-ttu-id="9936d-128">인코더 및 Serializer 확장</span><span class="sxs-lookup"><span data-stu-id="9936d-128">Extending Encoders and Serializers</span></span>](../../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md)  
  
## <a name="see-also"></a><span data-ttu-id="9936d-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9936d-129">See Also</span></span>  
 [<span data-ttu-id="9936d-130">모범 사례: 데이터 계약 버전 관리</span><span class="sxs-lookup"><span data-stu-id="9936d-130">Best Practices: Data Contract Versioning</span></span>](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)  
 [<span data-ttu-id="9936d-131">서비스 버전 관리</span><span class="sxs-lookup"><span data-stu-id="9936d-131">Service Versioning</span></span>](../../../../docs/framework/wcf/service-versioning.md)
