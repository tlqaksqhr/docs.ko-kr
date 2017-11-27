---
title: "&lt;generatePublisherEvidence&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 78293c396687f9c0c99ffdfbe94cf1f3c548289d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltgeneratepublisherevidencegt-element"></a><span data-ttu-id="113c0-102">&lt;generatePublisherEvidence&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="113c0-102">&lt;generatePublisherEvidence&gt; Element</span></span>
<span data-ttu-id="113c0-103">런타임에서 만들지 여부를 지정 <xref:System.Security.Policy.Publisher> 코드 액세스 보안 (CA)에 대 한 증거입니다.</span><span class="sxs-lookup"><span data-stu-id="113c0-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
 <span data-ttu-id="113c0-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="113c0-104">\<configuration></span></span>  
<span data-ttu-id="113c0-105">\<런타임 ></span><span class="sxs-lookup"><span data-stu-id="113c0-105">\<runtime></span></span>  
<span data-ttu-id="113c0-106">\<generatePublisherEvidence ></span><span class="sxs-lookup"><span data-stu-id="113c0-106">\<generatePublisherEvidence></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="113c0-107">구문</span><span class="sxs-lookup"><span data-stu-id="113c0-107">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="113c0-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="113c0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="113c0-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="113c0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="113c0-110">특성</span><span class="sxs-lookup"><span data-stu-id="113c0-110">Attributes</span></span>  
  
|<span data-ttu-id="113c0-111">특성</span><span class="sxs-lookup"><span data-stu-id="113c0-111">Attribute</span></span>|<span data-ttu-id="113c0-112">설명</span><span class="sxs-lookup"><span data-stu-id="113c0-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="113c0-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="113c0-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="113c0-114">런타임에서 만들지 여부를 지정 <xref:System.Security.Policy.Publisher> 증명 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="113c0-114">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="113c0-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="113c0-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="113c0-116">값</span><span class="sxs-lookup"><span data-stu-id="113c0-116">Value</span></span>|<span data-ttu-id="113c0-117">설명</span><span class="sxs-lookup"><span data-stu-id="113c0-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="113c0-118">만들지 않고 <xref:System.Security.Policy.Publisher> 증명 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="113c0-118">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="113c0-119">만듭니다 <xref:System.Security.Policy.Publisher> 증명 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="113c0-119">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="113c0-120">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="113c0-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="113c0-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="113c0-121">Child Elements</span></span>  
 <span data-ttu-id="113c0-122">없음</span><span class="sxs-lookup"><span data-stu-id="113c0-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="113c0-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="113c0-123">Parent Elements</span></span>  
  
|<span data-ttu-id="113c0-124">요소</span><span class="sxs-lookup"><span data-stu-id="113c0-124">Element</span></span>|<span data-ttu-id="113c0-125">설명</span><span class="sxs-lookup"><span data-stu-id="113c0-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="113c0-126">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="113c0-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="113c0-127">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="113c0-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="113c0-128">설명</span><span class="sxs-lookup"><span data-stu-id="113c0-128">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="113c0-129">에 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] 및 이상 버전에서는이 요소는 어셈블리 로드 시간에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="113c0-129">In the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="113c0-130">자세한 내용은의 "보안 정책 단순화" 섹션을 참조 하십시오. [보안 변경 내용](../../../../../docs/framework/security/security-changes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="113c0-130">For more information, see the "Security Policy Simplification" section in [Security Changes](../../../../../docs/framework/security/security-changes.md).</span></span>  
  
 <span data-ttu-id="113c0-131">공용 언어 런타임 (CLR) 만들기를 로드할 때 Authenticode 서명을 확인 하려고 <xref:System.Security.Policy.Publisher> 어셈블리에 대 한 증거입니다.</span><span class="sxs-lookup"><span data-stu-id="113c0-131">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="113c0-132">그러나 기본적으로 대부분의 응용 프로그램 불필요 <xref:System.Security.Policy.Publisher> 증명 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="113c0-132">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="113c0-133">표준 CAS 정책에 의존 하지 않습니다는 <xref:System.Security.Policy.PublisherMembershipCondition>합니다.</span><span class="sxs-lookup"><span data-stu-id="113c0-133">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="113c0-134">연결 된 응용 프로그램 사용자 지정 CAS 정책 사용 하는 컴퓨터에서 실행 하거나에 대 한 요구를 충족 하기 위해 의도 하지 않는 한 게시자 서명을 확인 하는 필요 하지 않은 시작 비용을 피하기 위해 해야 <xref:System.Security.Permissions.PublisherIdentityPermission> 부분 신뢰 환경에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="113c0-134">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="113c0-135">(Id 권한 요청이 항상 완전 신뢰 환경에서 성공합니다.)</span><span class="sxs-lookup"><span data-stu-id="113c0-135">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="113c0-136">서비스에서 사용 하는 것이 좋습니다는 `<generatePublisherEvidence>` 시작 성능을 향상 시킬 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="113c0-136">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="113c0-137">이 요소를 사용 하는 시간 제한 및 서비스를 시작한 취소 될 수 있는 지연을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="113c0-137">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="113c0-138">구성 파일</span><span class="sxs-lookup"><span data-stu-id="113c0-138">Configuration File</span></span>  
 <span data-ttu-id="113c0-139">이 요소는 응용 프로그램 구성 파일에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="113c0-139">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="113c0-140">예제</span><span class="sxs-lookup"><span data-stu-id="113c0-140">Example</span></span>  
 <span data-ttu-id="113c0-141">사용 하는 방법을 보여 주는 다음 예제는 `<generatePublisherEvidence>` 요소를 확인 하는 응용 프로그램에 대 한 CAS 게시자 정책을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="113c0-141">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="113c0-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="113c0-142">See Also</span></span>  
 [<span data-ttu-id="113c0-143">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="113c0-143">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="113c0-144">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="113c0-144">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
