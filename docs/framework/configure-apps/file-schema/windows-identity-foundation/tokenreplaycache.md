---
title: '&lt;tokenReplayCache&gt;'
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 79022319944c4042c6f62a7521784b826b90d4ce
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755125"
---
# <a name="lttokenreplaycachegt"></a><span data-ttu-id="9fad2-102">&lt;tokenReplayCache&gt;</span><span class="sxs-lookup"><span data-stu-id="9fad2-102">&lt;tokenReplayCache&gt;</span></span>
<span data-ttu-id="9fad2-103">토큰 재생 캐시는 서비스 또는 보안 토큰 처리기 컬렉션에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="9fad2-103">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="9fad2-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="9fad2-104">\<system.identityModel></span></span>  
<span data-ttu-id="9fad2-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="9fad2-105">\<identityConfiguration></span></span>  
<span data-ttu-id="9fad2-106">\<캐시 ></span><span class="sxs-lookup"><span data-stu-id="9fad2-106">\<caches></span></span>  
<span data-ttu-id="9fad2-107">\<tokenReplayCache ></span><span class="sxs-lookup"><span data-stu-id="9fad2-107">\<tokenReplayCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fad2-108">구문</span><span class="sxs-lookup"><span data-stu-id="9fad2-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <tokenReplayCache type=xs:string>  
      </tokenReplayCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9fad2-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9fad2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9fad2-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9fad2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9fad2-111">특성</span><span class="sxs-lookup"><span data-stu-id="9fad2-111">Attributes</span></span>  
  
|<span data-ttu-id="9fad2-112">특성</span><span class="sxs-lookup"><span data-stu-id="9fad2-112">Attribute</span></span>|<span data-ttu-id="9fad2-113">설명</span><span class="sxs-lookup"><span data-stu-id="9fad2-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9fad2-114">type</span><span class="sxs-lookup"><span data-stu-id="9fad2-114">type</span></span>|<span data-ttu-id="9fad2-115">파생 되는 형식을 <xref:System.IdentityModel.Tokens.TokenReplayCache> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="9fad2-115">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="9fad2-116">사용자 지정 하는 방법에 대 한 자세한 내용은 `type`, [사용자 지정 형식 참조]를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9fad2-116">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="9fad2-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9fad2-117">Child Elements</span></span>  
 <span data-ttu-id="9fad2-118">없음</span><span class="sxs-lookup"><span data-stu-id="9fad2-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9fad2-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9fad2-119">Parent Elements</span></span>  
  
|<span data-ttu-id="9fad2-120">요소</span><span class="sxs-lookup"><span data-stu-id="9fad2-120">Element</span></span>|<span data-ttu-id="9fad2-121">설명</span><span class="sxs-lookup"><span data-stu-id="9fad2-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9fad2-122">\<캐시 ></span><span class="sxs-lookup"><span data-stu-id="9fad2-122">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="9fad2-123">서비스 또는 보안 토큰 처리기 컬렉션에서 사용 하는 캐시에 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fad2-123">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9fad2-124">설명</span><span class="sxs-lookup"><span data-stu-id="9fad2-124">Remarks</span></span>  
 <span data-ttu-id="9fad2-125">토큰 재생 캐시가 재생 된 토큰을 검색 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fad2-125">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="9fad2-126">토큰 재생 검색으로 사용 되는 [ \<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) 또한 토큰에 대 한 최대 만료 시간을 지정 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9fad2-126">Token replay detection is enabled by the [\<tokenReplayDetection>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9fad2-127">예제</span><span class="sxs-lookup"><span data-stu-id="9fad2-127">Example</span></span>  
 <span data-ttu-id="9fad2-128">다음 XML에서는 토큰 재생된 검색에 대 한 사용자 지정 캐시의 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9fad2-128">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9fad2-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9fad2-129">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.TokenReplayCache>  
 [<span data-ttu-id="9fad2-130">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="9fad2-130">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)
