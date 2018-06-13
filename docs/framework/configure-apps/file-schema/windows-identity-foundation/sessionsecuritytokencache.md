---
title: '&lt;sessionSecurityTokenCache&gt;'
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 0b0d3c01a81f110f79f64d75aa2ab2ff2873fedd
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755047"
---
# <a name="ltsessionsecuritytokencachegt"></a><span data-ttu-id="3a112-102">&lt;sessionSecurityTokenCache&gt;</span><span class="sxs-lookup"><span data-stu-id="3a112-102">&lt;sessionSecurityTokenCache&gt;</span></span>
<span data-ttu-id="3a112-103">세션 토큰에 대 한 캐시 서비스 또는 보안 토큰 처리기 컬렉션에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="3a112-103">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="3a112-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="3a112-104">\<system.identityModel></span></span>  
<span data-ttu-id="3a112-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="3a112-105">\<identityConfiguration></span></span>  
<span data-ttu-id="3a112-106">\<캐시 ></span><span class="sxs-lookup"><span data-stu-id="3a112-106">\<caches></span></span>  
<span data-ttu-id="3a112-107">\<sessionSecurityTokenCache ></span><span class="sxs-lookup"><span data-stu-id="3a112-107">\<sessionSecurityTokenCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a112-108">구문</span><span class="sxs-lookup"><span data-stu-id="3a112-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <sessionSecurityTokenCache type=xs:string>  
      </sessionSecurityTokenCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a112-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3a112-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3a112-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3a112-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a112-111">특성</span><span class="sxs-lookup"><span data-stu-id="3a112-111">Attributes</span></span>  
  
|<span data-ttu-id="3a112-112">특성</span><span class="sxs-lookup"><span data-stu-id="3a112-112">Attribute</span></span>|<span data-ttu-id="3a112-113">설명</span><span class="sxs-lookup"><span data-stu-id="3a112-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3a112-114">type</span><span class="sxs-lookup"><span data-stu-id="3a112-114">type</span></span>|<span data-ttu-id="3a112-115">파생 되는 형식을 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="3a112-115">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3a112-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3a112-116">Child Elements</span></span>  
 <span data-ttu-id="3a112-117">없음</span><span class="sxs-lookup"><span data-stu-id="3a112-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3a112-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3a112-118">Parent Elements</span></span>  
  
|<span data-ttu-id="3a112-119">요소</span><span class="sxs-lookup"><span data-stu-id="3a112-119">Element</span></span>|<span data-ttu-id="3a112-120">설명</span><span class="sxs-lookup"><span data-stu-id="3a112-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a112-121">\<캐시 ></span><span class="sxs-lookup"><span data-stu-id="3a112-121">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="3a112-122">서비스 또는 보안 토큰 처리기 컬렉션에서 사용 하는 캐시에 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a112-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3a112-123">예제</span><span class="sxs-lookup"><span data-stu-id="3a112-123">Example</span></span>  
 <span data-ttu-id="3a112-124">다음 XML에 세션 보안 토큰을 보관 하기 위한 사용자 지정 캐시의 구성을 보여 줍니다 (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="3a112-124">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="3a112-125">구성에서 가져온 것은 `ClaimsAwareWebFarm` 샘플.</span><span class="sxs-lookup"><span data-stu-id="3a112-125">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="3a112-126">이 샘플에 대 한 자세한 내용은 참조 [WIF 코드 샘플 인덱스](../../../../../docs/framework/security/wif-code-sample-index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3a112-126">For more information about this sample, see [WIF Code Sample Index](../../../../../docs/framework/security/wif-code-sample-index.md).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3a112-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3a112-127">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
