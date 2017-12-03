---
title: ServiceMetadataBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f194476-72f1-467e-bdce-674306316e64
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f17b31e1dfe9ba60b2042a85a6d673d986fe0a33
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="servicemetadatabehavior"></a><span data-ttu-id="6e5b9-102">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="6e5b9-102">ServiceMetadataBehavior</span></span>
<span data-ttu-id="6e5b9-103">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="6e5b9-103">ServiceMetadataBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e5b9-104">구문</span><span class="sxs-lookup"><span data-stu-id="6e5b9-104">Syntax</span></span>  
  
```  
class ServiceMetadataBehavior : Behavior  
{  
  string ExternalMetadataLocation;  
  boolean HttpGetEnabled;  
  string HttpGetUrl;  
  boolean HttpsGetEnabled;  
  string HttpsGetUrl;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="6e5b9-105">메서드</span><span class="sxs-lookup"><span data-stu-id="6e5b9-105">Methods</span></span>  
 <span data-ttu-id="6e5b9-106">ServiceMetadataBehavior 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6e5b9-106">The ServiceMetadataBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6e5b9-107">속성</span><span class="sxs-lookup"><span data-stu-id="6e5b9-107">Properties</span></span>  
 <span data-ttu-id="6e5b9-108">ServiceMetadataBehavior 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e5b9-108">The ServiceMetadataBehavior class has the following properties:</span></span>  
  
### <a name="externalmetadatalocation"></a><span data-ttu-id="6e5b9-109">ExternalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="6e5b9-109">ExternalMetadataLocation</span></span>  
 <span data-ttu-id="6e5b9-110">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="6e5b9-110">Data type: string</span></span>  
  
 <span data-ttu-id="6e5b9-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="6e5b9-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6e5b9-112">서비스가 메타데이터 요청을 리디렉션하는 위치를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6e5b9-112">Sets the location to which the service redirects metadata requests.</span></span>  
  
### <a name="httpgetenabled"></a><span data-ttu-id="6e5b9-113">HttpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="6e5b9-113">HttpGetEnabled</span></span>  
 <span data-ttu-id="6e5b9-114">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="6e5b9-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="6e5b9-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="6e5b9-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6e5b9-116">`HttpGetUrl` 특성으로 제어되는 주소에서 서비스가 WSDL을 게시할지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="6e5b9-116">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httpgeturl"></a><span data-ttu-id="6e5b9-117">HttpGetUrl</span><span class="sxs-lookup"><span data-stu-id="6e5b9-117">HttpGetUrl</span></span>  
 <span data-ttu-id="6e5b9-118">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="6e5b9-118">Data type: string</span></span>  
  
 <span data-ttu-id="6e5b9-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="6e5b9-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6e5b9-120">HTTP를 사용한 검색을 위해 서비스 WSDL이 게시되는 위치를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6e5b9-120">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpsgetenabled"></a><span data-ttu-id="6e5b9-121">HttpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="6e5b9-121">HttpsGetEnabled</span></span>  
 <span data-ttu-id="6e5b9-122">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="6e5b9-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="6e5b9-123">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="6e5b9-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6e5b9-124">`HttpsGetUrl` 특성으로 제어되는 주소에서 서비스가 HTTPS를 통해 WSDL을 게시할지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="6e5b9-124">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpsgeturl"></a><span data-ttu-id="6e5b9-125">HttpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="6e5b9-125">HttpsGetUrl</span></span>  
 <span data-ttu-id="6e5b9-126">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="6e5b9-126">Data type: string</span></span>  
  
 <span data-ttu-id="6e5b9-127">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="6e5b9-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6e5b9-128">HTTPS를 사용한 검색을 위해 서비스 WSDL이 게시되는 위치를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6e5b9-128">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e5b9-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6e5b9-129">Requirements</span></span>  
  
|<span data-ttu-id="6e5b9-130">MOF</span><span class="sxs-lookup"><span data-stu-id="6e5b9-130">MOF</span></span>|<span data-ttu-id="6e5b9-131">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e5b9-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="6e5b9-132">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="6e5b9-132">Namespace</span></span>|<span data-ttu-id="6e5b9-133">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e5b9-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6e5b9-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6e5b9-134">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
