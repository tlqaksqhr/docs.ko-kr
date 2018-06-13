---
title: '&lt;tokenReplayDetection&gt;'
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 7f0cef2590bb301e6897aa4922454942ecdd0957
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755229"
---
# <a name="lttokenreplaydetectiongt"></a><span data-ttu-id="725a7-102">&lt;tokenReplayDetection&gt;</span><span class="sxs-lookup"><span data-stu-id="725a7-102">&lt;tokenReplayDetection&gt;</span></span>
<span data-ttu-id="725a7-103">토큰 재생 검색을 사용 하도록 설정 하 고 토큰에 대 한 만료 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="725a7-103">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
 <span data-ttu-id="725a7-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="725a7-104">\<system.identityModel></span></span>  
<span data-ttu-id="725a7-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="725a7-105">\<identityConfiguration></span></span>  
<span data-ttu-id="725a7-106">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="725a7-106">\<tokenReplayDetection></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="725a7-107">구문</span><span class="sxs-lookup"><span data-stu-id="725a7-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="725a7-108">형식</span><span class="sxs-lookup"><span data-stu-id="725a7-108">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="725a7-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="725a7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="725a7-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="725a7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="725a7-111">특성</span><span class="sxs-lookup"><span data-stu-id="725a7-111">Attributes</span></span>  
  
|<span data-ttu-id="725a7-112">특성</span><span class="sxs-lookup"><span data-stu-id="725a7-112">Attribute</span></span>|<span data-ttu-id="725a7-113">설명</span><span class="sxs-lookup"><span data-stu-id="725a7-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="725a7-114">사용</span><span class="sxs-lookup"><span data-stu-id="725a7-114">enabled</span></span>|<span data-ttu-id="725a7-115">토큰 재생 검색; 사용할지 여부를 지정 하는 값 토큰을 사용 하도록 설정 하려면 "true" 재생 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="725a7-115">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="725a7-116">expirationPeriod</span><span class="sxs-lookup"><span data-stu-id="725a7-116">expirationPeriod</span></span>|<span data-ttu-id="725a7-117">A <xref:System.TimeSpan> 항목 만료 된 것으로 간주 되어 캐시에서 제거 하기 전의 시간을 최대 크기를 지정 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="725a7-117">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="725a7-118">지정 하는 방법에 대 한 자세한 내용은 <xref:System.TimeSpan> 값, 참조 [Timespan 값](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="725a7-118">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="725a7-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="725a7-119">Child Elements</span></span>  
 <span data-ttu-id="725a7-120">없음</span><span class="sxs-lookup"><span data-stu-id="725a7-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="725a7-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="725a7-121">Parent Elements</span></span>  
  
|<span data-ttu-id="725a7-122">요소</span><span class="sxs-lookup"><span data-stu-id="725a7-122">Element</span></span>|<span data-ttu-id="725a7-123">설명</span><span class="sxs-lookup"><span data-stu-id="725a7-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="725a7-124">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="725a7-124">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="725a7-125">서비스 수준 id 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="725a7-125">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="725a7-126">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="725a7-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="725a7-127">구성 컬렉션의 보안 토큰 처리기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="725a7-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="725a7-128">설명</span><span class="sxs-lookup"><span data-stu-id="725a7-128">Remarks</span></span>  
 <span data-ttu-id="725a7-129">A `<tokenReplayDetection>` 에서 서비스 수준에서 요소를 지정할 수 있습니다는 `<identityConfiguration>` 요소 또는 보안 토큰 처리기 컬렉션 수준 아래에 `<securityTokenHandlerConfiguration>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="725a7-129">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="725a7-130">서비스에 지정 된 토큰 처리기 컬렉션에 대 한 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="725a7-130">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="725a7-131">변수로 지정 된 토큰 재생 캐시 형식은 [ \<tokenReplayCache >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="725a7-131">The type of the token replay cache is specified by the [\<tokenReplayCache>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) element.</span></span>
