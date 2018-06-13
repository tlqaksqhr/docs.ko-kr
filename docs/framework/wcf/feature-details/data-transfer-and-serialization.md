---
title: 데이터 전송 및 Serialization
ms.date: 03/30/2017
helpviewer_keywords:
- data serialization [WCF]
- data transfer [WCF]
ms.assetid: 0f03c635-f3e7-4c5c-9463-3cb0135e221e
ms.openlocfilehash: 53c1421bf14c598611e116c61353c4ecd465f1aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33489208"
---
# <a name="data-transfer-and-serialization"></a><span data-ttu-id="e3086-102">데이터 전송 및 Serialization</span><span class="sxs-lookup"><span data-stu-id="e3086-102">Data Transfer and Serialization</span></span>
<span data-ttu-id="e3086-103">연결된 시스템에서 서비스 및 클라이언트는 데이터 교환에 의존하여 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e3086-103">In a connected system, services and clients depend on the exchange of data to accomplish any task.</span></span> <span data-ttu-id="e3086-104">개발자는 서비스 또는 클라이언트의 Windows Communication Foundation (WCF)는 효율적이 고 유지 관리 하기 쉬운 응용 프로그램을 만들기 위해 데이터 및 데이터 serialization을 처리 방법을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3086-104">As a developer of a service or client, you must also understand how Windows Communication Foundation (WCF) handles data and data serialization in order to create applications that are efficient and easy to maintain.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e3086-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="e3086-105">In This Section</span></span>  
 [<span data-ttu-id="e3086-106">서비스 계약에서 데이터 전송 지정</span><span class="sxs-lookup"><span data-stu-id="e3086-106">Specifying Data Transfer in Service Contracts</span></span>](../../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md)  
 <span data-ttu-id="e3086-107">서비스에서 데이터 전송의 기본 개념에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e3086-107">Describes the basic concepts of data transfer in services.</span></span>  
  
 [<span data-ttu-id="e3086-108">데이터 계약 사용</span><span class="sxs-lookup"><span data-stu-id="e3086-108">Using Data Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 <span data-ttu-id="e3086-109">데이터 계약의 정의와 데이터 계약을 만들고 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e3086-109">Describes what data contracts are and how to create and use them.</span></span>  
  
 [<span data-ttu-id="e3086-110">데이터 계약 직렬 변환기</span><span class="sxs-lookup"><span data-stu-id="e3086-110">Data Contract Serializer</span></span>](../../../../docs/framework/wcf/feature-details/data-contract-serializer.md)  
 <span data-ttu-id="e3086-111"><xref:System.Runtime.Serialization.DataContractSerializer> 클래스 또는 <xref:System.Runtime.Serialization.XmlObjectSerializer> 클래스의 확장을 사용하여 데이터의 serialization을 수행하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e3086-111">Describes how to accomplish serialization of data with the <xref:System.Runtime.Serialization.DataContractSerializer> class or any extension of the <xref:System.Runtime.Serialization.XmlObjectSerializer> class.</span></span>  
  
 [<span data-ttu-id="e3086-112">XmlSerializer 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="e3086-112">Using the XmlSerializer Class</span></span>](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md)  
 <span data-ttu-id="e3086-113"><xref:System.Xml.Serialization.XmlSerializer> 클래스 대신 <xref:System.Runtime.Serialization.DataContractSerializer> 클래스를 사용하는 방법 및 이유에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e3086-113">Describes how and why to use the <xref:System.Xml.Serialization.XmlSerializer> class, an alternative to the <xref:System.Runtime.Serialization.DataContractSerializer> class.</span></span>  
  
 [<span data-ttu-id="e3086-114">메시지 계약 사용</span><span class="sxs-lookup"><span data-stu-id="e3086-114">Using Message Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-message-contracts.md)  
 <span data-ttu-id="e3086-115">메시지 계약에서 SOAP 메시지를 정밀하게 제어하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e3086-115">Describes how message contracts allow fine control over SOAP messages.</span></span>  
  
 [<span data-ttu-id="e3086-116">Message 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="e3086-116">Using the Message Class</span></span>](../../../../docs/framework/wcf/feature-details/using-the-message-class.md)  
 <span data-ttu-id="e3086-117">Message 클래스 기능을 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e3086-117">Describes how to use Message class features.</span></span>  
  
 [<span data-ttu-id="e3086-118">필터링</span><span class="sxs-lookup"><span data-stu-id="e3086-118">Filtering</span></span>](../../../../docs/framework/wcf/feature-details/filtering.md)  
 <span data-ttu-id="e3086-119">여러 조건을 기반으로 메시지 전처리를 사용하는 필터링에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e3086-119">Describes filtering, which enables pre-processing of a message based on various criteria.</span></span>  
  
 [<span data-ttu-id="e3086-120">큰 데이터 및 스트리밍</span><span class="sxs-lookup"><span data-stu-id="e3086-120">Large Data and Streaming</span></span>](../../../../docs/framework/wcf/feature-details/large-data-and-streaming.md)  
 <span data-ttu-id="e3086-121">이진 파일과 같은 큰 데이터 블록을 보내는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e3086-121">Describes how to send a large block of data, such as a binary file.</span></span>  
  
 [<span data-ttu-id="e3086-122">데이터에 대한 보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="e3086-122">Security Considerations for Data</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md)  
 <span data-ttu-id="e3086-123">데이터 전송 및 serialization을 프로그래밍할 때 알고 있어야 하는 항목에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e3086-123">Describes items to be aware of when programming data transfer and serialization.</span></span>  
  
 [<span data-ttu-id="e3086-124">데이터 전송 아키텍처 개요</span><span class="sxs-lookup"><span data-stu-id="e3086-124">Data Transfer Architectural Overview</span></span>](../../../../docs/framework/wcf/feature-details/data-transfer-architectural-overview.md)  
 <span data-ttu-id="e3086-125">WCF에서 전송할 데이터의 전체 디자인의 보기를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e3086-125">Describes a view of the overall design of data transfer in WCF.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e3086-126">참조</span><span class="sxs-lookup"><span data-stu-id="e3086-126">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
  
 <xref:System.Xml.Serialization.XmlSerializer>  
  
 <xref:System.Runtime.Serialization>  
  
 <xref:System.Xml.Serialization>  
  
## <a name="related-sections"></a><span data-ttu-id="e3086-127">관련 단원</span><span class="sxs-lookup"><span data-stu-id="e3086-127">Related Sections</span></span>  
 [<span data-ttu-id="e3086-128">인코더 및 직렬 변환기 확장</span><span class="sxs-lookup"><span data-stu-id="e3086-128">Extending Encoders and Serializers</span></span>](../../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md)  
  
## <a name="see-also"></a><span data-ttu-id="e3086-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e3086-129">See Also</span></span>  
 [<span data-ttu-id="e3086-130">모범 사례: 데이터 계약 버전 관리</span><span class="sxs-lookup"><span data-stu-id="e3086-130">Best Practices: Data Contract Versioning</span></span>](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)  
 [<span data-ttu-id="e3086-131">서비스 버전 관리</span><span class="sxs-lookup"><span data-stu-id="e3086-131">Service Versioning</span></span>](../../../../docs/framework/wcf/service-versioning.md)
