---
title: "&lt;GCCpuGroup&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 510896c6993008f30e7eacf2628ae4cceadea7e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltgccpugroupgt-element"></a><span data-ttu-id="175f1-102">&lt;GCCpuGroup&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="175f1-102">&lt;GCCpuGroup&gt; Element</span></span>
<span data-ttu-id="175f1-103">가비지 수집에서 여러 CPU 그룹을 지원할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="175f1-103">Specifies whether garbage collection supports multiple CPU groups.</span></span>  
  
 <span data-ttu-id="175f1-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="175f1-104">\<configuration></span></span>  
<span data-ttu-id="175f1-105">\<런타임 ></span><span class="sxs-lookup"><span data-stu-id="175f1-105">\<runtime></span></span>  
<span data-ttu-id="175f1-106">\<GCCpuGroup ></span><span class="sxs-lookup"><span data-stu-id="175f1-106">\<GCCpuGroup></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="175f1-107">구문</span><span class="sxs-lookup"><span data-stu-id="175f1-107">Syntax</span></span>  
  
```xml  
<GCCpuGroup    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="175f1-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="175f1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="175f1-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="175f1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="175f1-110">특성</span><span class="sxs-lookup"><span data-stu-id="175f1-110">Attributes</span></span>  
  
|<span data-ttu-id="175f1-111">특성</span><span class="sxs-lookup"><span data-stu-id="175f1-111">Attribute</span></span>|<span data-ttu-id="175f1-112">설명</span><span class="sxs-lookup"><span data-stu-id="175f1-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="175f1-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="175f1-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="175f1-114">가비지 수집에서 여러 CPU 그룹을 지원할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="175f1-114">Specifies whether garbage collection supports multiple CPU groups.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="175f1-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="175f1-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="175f1-116">값</span><span class="sxs-lookup"><span data-stu-id="175f1-116">Value</span></span>|<span data-ttu-id="175f1-117">설명</span><span class="sxs-lookup"><span data-stu-id="175f1-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="175f1-118">가비지 수집 여러 CPU 그룹을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="175f1-118">Garbage collection does not support multiple CPU groups.</span></span> <span data-ttu-id="175f1-119">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="175f1-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="175f1-120">가비지 수집이 서버 가비지 수집이 사용 되는 경우 여러 CPU 그룹을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="175f1-120">Garbage collection supports multiple CPU groups, if server garbage collection is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="175f1-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="175f1-121">Child Elements</span></span>  
 <span data-ttu-id="175f1-122">없음</span><span class="sxs-lookup"><span data-stu-id="175f1-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="175f1-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="175f1-123">Parent Elements</span></span>  
  
|<span data-ttu-id="175f1-124">요소</span><span class="sxs-lookup"><span data-stu-id="175f1-124">Element</span></span>|<span data-ttu-id="175f1-125">설명</span><span class="sxs-lookup"><span data-stu-id="175f1-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="175f1-126">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="175f1-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="175f1-127">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="175f1-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="175f1-128">설명</span><span class="sxs-lookup"><span data-stu-id="175f1-128">Remarks</span></span>  
 <span data-ttu-id="175f1-129">때 컴퓨터에 여러 CPU 그룹 및 서버 가비지 수집이 설정 되었는지 (참조는 [ \<gcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) 요소),이 요소를 사용 하도록 설정을 모든 CPU 그룹에서 가비지 수집을 확장 하 고 모든 코어를 사용 합니다. 힙을 분산와 만들 때 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="175f1-129">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="175f1-130">이 요소는 가비지 수집 스레드만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="175f1-130">This element applies only to garbage collection threads.</span></span> <span data-ttu-id="175f1-131">런타임에서 모든 CPU 그룹 사용자 스레드를 분산 시킬 수 있도록,도 설정 해야는 [< Thread_UseAllCpuGroups >](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="175f1-131">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [<Thread_UseAllCpuGroups>](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="175f1-132">예</span><span class="sxs-lookup"><span data-stu-id="175f1-132">Example</span></span>  
 <span data-ttu-id="175f1-133">다음 예제에서는 여러 CPU 그룹에 대 한 가비지 컬렉션을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="175f1-133">The following example shows how to enable garbage collection for multiple CPU groups.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <GCCpuGroup enabled="true"/>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="175f1-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="175f1-134">See Also</span></span>  
 [<span data-ttu-id="175f1-135">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="175f1-135">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="175f1-136">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="175f1-136">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="175f1-137">방법: 동시 가비지 수집을 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="175f1-137">How to: Disable Concurrent Garbage Collection</span></span>](http://msdn.microsoft.com/en-us/ba2c6c67-5778-497c-9fac-5f793b5500c7)  
 [<span data-ttu-id="175f1-138">워크스테이션 및 서버 가비지 수집</span><span class="sxs-lookup"><span data-stu-id="175f1-138">Workstation and server garbage collection</span></span>](../../../../../docs/standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)
