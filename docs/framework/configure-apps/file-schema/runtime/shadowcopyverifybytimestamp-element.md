---
title: "&lt;shadowCopyVerifyByTimestamp&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 261962819e9b2b37682a13bffb53d2912a660566
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltshadowcopyverifybytimestampgt-element"></a><span data-ttu-id="7daf9-102">&lt;shadowCopyVerifyByTimestamp&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="7daf9-102">&lt;shadowCopyVerifyByTimestamp&gt; Element</span></span>
<span data-ttu-id="7daf9-103">섀도 복사에서 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]에 도입된 기본 시작 동작을 사용하는지 아니면 이전 .NET Framework 버전의 시작 동작으로 되돌아가는지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7daf9-103">Specifies whether shadow copying uses the default startup behavior introduced in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], or reverts to the startup behavior of earlier versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="7daf9-104">\<구성 > 요소</span><span class="sxs-lookup"><span data-stu-id="7daf9-104">\<configuration> Element</span></span>  
<span data-ttu-id="7daf9-105">\<런타임 > 요소</span><span class="sxs-lookup"><span data-stu-id="7daf9-105">\<runtime> Element</span></span>  
<span data-ttu-id="7daf9-106">\<shadowCopyVerifyByTimestamp > 요소</span><span class="sxs-lookup"><span data-stu-id="7daf9-106">\<shadowCopyVerifyByTimestamp> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7daf9-107">구문</span><span class="sxs-lookup"><span data-stu-id="7daf9-107">Syntax</span></span>  
  
```xml  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7daf9-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7daf9-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7daf9-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7daf9-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7daf9-110">특성</span><span class="sxs-lookup"><span data-stu-id="7daf9-110">Attributes</span></span>  
  
|<span data-ttu-id="7daf9-111">특성</span><span class="sxs-lookup"><span data-stu-id="7daf9-111">Attribute</span></span>|<span data-ttu-id="7daf9-112">설명</span><span class="sxs-lookup"><span data-stu-id="7daf9-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7daf9-113">사용</span><span class="sxs-lookup"><span data-stu-id="7daf9-113">enabled</span></span>|<span data-ttu-id="7daf9-114">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="7daf9-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="7daf9-115">섀도 복사를 사용 하는 응용 프로그램 도메인 어셈블리에 어셈블리를 섀도 복사 하기 전에 업데이트 되었는지 여부를 확인 하려면 시작 시 어셈블리 타임 스탬프 비교 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7daf9-115">Specifies whether application domains that use shadow copying compare assembly time stamps when starting up, to determine whether an assembly has been updated before shadow copying the assembly.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="7daf9-116">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="7daf9-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="7daf9-117">값</span><span class="sxs-lookup"><span data-stu-id="7daf9-117">Value</span></span>|<span data-ttu-id="7daf9-118">설명</span><span class="sxs-lookup"><span data-stu-id="7daf9-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7daf9-119">true</span><span class="sxs-lookup"><span data-stu-id="7daf9-119">true</span></span>|<span data-ttu-id="7daf9-120">시작 시 어셈블리 섀도 복사 디렉터리에 마지막으로 복사 된 후이 업데이트 되어를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="7daf9-120">At startup, copies only assemblies that have been updated since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="7daf9-121">에 대 한 기본값은 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="7daf9-121">This is the default for the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span></span>|  
|<span data-ttu-id="7daf9-122">false</span><span class="sxs-lookup"><span data-stu-id="7daf9-122">false</span></span>|<span data-ttu-id="7daf9-123">시작 시 모든 파일을 복사할 이전의 이전 버전의.NET Framework의 시작 동작으로 되돌립니다.</span><span class="sxs-lookup"><span data-stu-id="7daf9-123">Reverts to the startup behavior of previous versions of the .NET Framework, which was to copy all files at startup.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7daf9-124">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7daf9-124">Child Elements</span></span>  
 <span data-ttu-id="7daf9-125">없음</span><span class="sxs-lookup"><span data-stu-id="7daf9-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7daf9-126">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7daf9-126">Parent Elements</span></span>  
  
|<span data-ttu-id="7daf9-127">요소</span><span class="sxs-lookup"><span data-stu-id="7daf9-127">Element</span></span>|<span data-ttu-id="7daf9-128">설명</span><span class="sxs-lookup"><span data-stu-id="7daf9-128">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7daf9-129">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7daf9-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="7daf9-130">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7daf9-130">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7daf9-131">설명</span><span class="sxs-lookup"><span data-stu-id="7daf9-131">Remarks</span></span>  
 <span data-ttu-id="7daf9-132">부터는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], 어셈블리는 해당 타임 스탬프 섀도 복사 디렉터리에 마지막으로 복사 된 이후 변경 된 것을 나타내는 경우에 섀도 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="7daf9-132">Starting with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], assemblies are shadow copied only if their time stamps indicate that they have changed since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="7daf9-133">에 설명 된 대로 섀도 복사를 사용 하는 많은 응용 프로그램에 대 한 시작 시간이 향상 됩니다 [어셈블리 섀도 복사](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7daf9-133">This improves startup times for many applications that use shadow copying, as described in [Shadow Copying Assemblies](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md).</span></span> <span data-ttu-id="7daf9-134">어셈블리 업데이트의 높은 비율과 빈도를 갖는 응용 프로그램은 이 동작 변경이 도움이 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7daf9-134">Applications that have a high percentage and frequency of assembly updates might not benefit from this change in behavior.</span></span> <span data-ttu-id="7daf9-135">이 경우 이 요소를 사용하여 이전 버전의 .NET Framework의 동작을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7daf9-135">In that case, you can use this element to restore the behavior of previous versions of the .NET Framework.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7daf9-136">예제</span><span class="sxs-lookup"><span data-stu-id="7daf9-136">Example</span></span>  
 <span data-ttu-id="7daf9-137">섀도 복사의 기본 시작 동작을 사용 하지 않도록 설정 하는 방법을 보여 주는 다음 예제는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], 이전 버전의.NET Framework의 시작 동작으로 되돌립니다.</span><span class="sxs-lookup"><span data-stu-id="7daf9-137">The following example shows how to disable the default startup behavior of shadow copying in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], and revert to the startup behavior of previous versions of the .NET Framework.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7daf9-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7daf9-138">See Also</span></span>  
 [<span data-ttu-id="7daf9-139">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="7daf9-139">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="7daf9-140">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="7daf9-140">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="7daf9-141">어셈블리 섀도 복사</span><span class="sxs-lookup"><span data-stu-id="7daf9-141">Shadow Copying Assemblies</span></span>](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md)
