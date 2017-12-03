---
title: ServiceDebugBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a5ec9061-1e95-43fb-b0d9-dbd0a7bc3c44
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5c829f68fe994b47fe880febb4d3ac2020fde2d1
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="servicedebugbehavior"></a><span data-ttu-id="d4948-102">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="d4948-102">ServiceDebugBehavior</span></span>
<span data-ttu-id="d4948-103">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="d4948-103">ServiceDebugBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4948-104">구문</span><span class="sxs-lookup"><span data-stu-id="d4948-104">Syntax</span></span>  
  
```  
class ServiceDebugBehavior : Behavior  
{  
  boolean HttpHelpPageEnabled;  
  string HttpHelpPageUrl;  
  boolean HttpsHelpPageEnabled;  
  string HttpsHelpPageUrl;  
  boolean IncludeExceptionDetailInFaults;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d4948-105">메서드</span><span class="sxs-lookup"><span data-stu-id="d4948-105">Methods</span></span>  
 <span data-ttu-id="d4948-106">ServiceDebugBehavior 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4948-106">The ServiceDebugBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d4948-107">속성</span><span class="sxs-lookup"><span data-stu-id="d4948-107">Properties</span></span>  
 <span data-ttu-id="d4948-108">ServiceDebugBehavior 클래스에는 다음 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4948-108">The ServiceDebugBehavior class has the following properties:</span></span>  
  
### <a name="httphelppageenabled"></a><span data-ttu-id="d4948-109">HttpHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="d4948-109">HttpHelpPageEnabled</span></span>  
 <span data-ttu-id="d4948-110">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="d4948-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="d4948-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="d4948-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d4948-112">`HttpGetUrl` 특성으로 제어되는 주소에서 서비스가 WSDL을 게시할지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="d4948-112">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httphelppageurl"></a><span data-ttu-id="d4948-113">HttpHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="d4948-113">HttpHelpPageUrl</span></span>  
 <span data-ttu-id="d4948-114">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="d4948-114">Data type: string</span></span>  
  
 <span data-ttu-id="d4948-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="d4948-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d4948-116">HTTP를 사용한 검색을 위해 서비스 WSDL이 게시되는 위치를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d4948-116">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpshelppageenabled"></a><span data-ttu-id="d4948-117">HttpsHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="d4948-117">HttpsHelpPageEnabled</span></span>  
 <span data-ttu-id="d4948-118">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="d4948-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="d4948-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="d4948-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d4948-120">`HttpsGetUrl` 특성으로 제어되는 주소에서 서비스가 HTTPS를 통해 WSDL을 게시할지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="d4948-120">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpshelppageurl"></a><span data-ttu-id="d4948-121">HttpsHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="d4948-121">HttpsHelpPageUrl</span></span>  
 <span data-ttu-id="d4948-122">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="d4948-122">Data type: string</span></span>  
  
 <span data-ttu-id="d4948-123">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="d4948-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d4948-124">HTTPS를 사용한 검색을 위해 서비스 WSDL이 게시되는 위치를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d4948-124">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="d4948-125">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="d4948-125">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="d4948-126">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="d4948-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="d4948-127">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="d4948-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d4948-128">디버깅 목적으로 클라이언트에 반환되는 SOAP 오류 정보에 관리되는 예외 정보를 포함할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d4948-128">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4948-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d4948-129">Requirements</span></span>  
  
|<span data-ttu-id="d4948-130">MOF</span><span class="sxs-lookup"><span data-stu-id="d4948-130">MOF</span></span>|<span data-ttu-id="d4948-131">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4948-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d4948-132">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="d4948-132">Namespace</span></span>|<span data-ttu-id="d4948-133">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4948-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d4948-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d4948-134">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceDebugBehavior>
