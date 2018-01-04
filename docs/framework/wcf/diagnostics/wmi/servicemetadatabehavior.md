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
ms.workload: dotnet
ms.openlocfilehash: c05f6be9fc0507b7e2f1de4374e3b9bbe3e2a10e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="servicemetadatabehavior"></a><span data-ttu-id="b80f2-102">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="b80f2-102">ServiceMetadataBehavior</span></span>
<span data-ttu-id="b80f2-103">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="b80f2-103">ServiceMetadataBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b80f2-104">구문</span><span class="sxs-lookup"><span data-stu-id="b80f2-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="b80f2-105">메서드</span><span class="sxs-lookup"><span data-stu-id="b80f2-105">Methods</span></span>  
 <span data-ttu-id="b80f2-106">ServiceMetadataBehavior 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b80f2-106">The ServiceMetadataBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b80f2-107">속성</span><span class="sxs-lookup"><span data-stu-id="b80f2-107">Properties</span></span>  
 <span data-ttu-id="b80f2-108">ServiceMetadataBehavior 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b80f2-108">The ServiceMetadataBehavior class has the following properties:</span></span>  
  
### <a name="externalmetadatalocation"></a><span data-ttu-id="b80f2-109">ExternalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="b80f2-109">ExternalMetadataLocation</span></span>  
 <span data-ttu-id="b80f2-110">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="b80f2-110">Data type: string</span></span>  
  
 <span data-ttu-id="b80f2-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="b80f2-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b80f2-112">서비스가 메타데이터 요청을 리디렉션하는 위치를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b80f2-112">Sets the location to which the service redirects metadata requests.</span></span>  
  
### <a name="httpgetenabled"></a><span data-ttu-id="b80f2-113">HttpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="b80f2-113">HttpGetEnabled</span></span>  
 <span data-ttu-id="b80f2-114">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="b80f2-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="b80f2-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="b80f2-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b80f2-116">`HttpGetUrl` 특성으로 제어되는 주소에서 서비스가 WSDL을 게시할지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="b80f2-116">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httpgeturl"></a><span data-ttu-id="b80f2-117">HttpGetUrl</span><span class="sxs-lookup"><span data-stu-id="b80f2-117">HttpGetUrl</span></span>  
 <span data-ttu-id="b80f2-118">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="b80f2-118">Data type: string</span></span>  
  
 <span data-ttu-id="b80f2-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="b80f2-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b80f2-120">HTTP를 사용한 검색을 위해 서비스 WSDL이 게시되는 위치를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b80f2-120">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpsgetenabled"></a><span data-ttu-id="b80f2-121">HttpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="b80f2-121">HttpsGetEnabled</span></span>  
 <span data-ttu-id="b80f2-122">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="b80f2-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="b80f2-123">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="b80f2-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b80f2-124">`HttpsGetUrl` 특성으로 제어되는 주소에서 서비스가 HTTPS를 통해 WSDL을 게시할지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="b80f2-124">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpsgeturl"></a><span data-ttu-id="b80f2-125">HttpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="b80f2-125">HttpsGetUrl</span></span>  
 <span data-ttu-id="b80f2-126">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="b80f2-126">Data type: string</span></span>  
  
 <span data-ttu-id="b80f2-127">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="b80f2-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b80f2-128">HTTPS를 사용한 검색을 위해 서비스 WSDL이 게시되는 위치를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b80f2-128">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b80f2-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b80f2-129">Requirements</span></span>  
  
|<span data-ttu-id="b80f2-130">MOF</span><span class="sxs-lookup"><span data-stu-id="b80f2-130">MOF</span></span>|<span data-ttu-id="b80f2-131">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b80f2-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b80f2-132">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="b80f2-132">Namespace</span></span>|<span data-ttu-id="b80f2-133">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b80f2-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b80f2-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b80f2-134">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
