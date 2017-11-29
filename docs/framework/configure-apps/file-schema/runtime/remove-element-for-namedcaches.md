---
title: "&lt;제거&gt; 요소에 대 한 &lt;namedCaches&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 6170b59e87948225708c9e697cba1542d756d2f4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltremovegt-element-for-ltnamedcachesgt"></a><span data-ttu-id="6a118-102">&lt;제거&gt; 요소에 대 한 &lt;namedCaches&gt;</span><span class="sxs-lookup"><span data-stu-id="6a118-102">&lt;remove&gt; Element for &lt;namedCaches&gt;</span></span>
<span data-ttu-id="6a118-103">메모리 캐시용으로 명명된 캐시 항목을 `namedCaches` 컬렉션에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6a118-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="6a118-104">\<system.runtime.caching ></span><span class="sxs-lookup"><span data-stu-id="6a118-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="6a118-105">\<memoryCache ></span><span class="sxs-lookup"><span data-stu-id="6a118-105">\<memoryCache></span></span>  
<span data-ttu-id="6a118-106">\<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="6a118-106">\<namedCaches></span></span>  
<span data-ttu-id="6a118-107">\<제거 ></span><span class="sxs-lookup"><span data-stu-id="6a118-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a118-108">구문</span><span class="sxs-lookup"><span data-stu-id="6a118-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="6a118-109">형식</span><span class="sxs-lookup"><span data-stu-id="6a118-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6a118-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6a118-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6a118-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6a118-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6a118-112">특성</span><span class="sxs-lookup"><span data-stu-id="6a118-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="6a118-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6a118-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="6a118-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6a118-114">Parent Elements</span></span>  
  
|<span data-ttu-id="6a118-115">요소</span><span class="sxs-lookup"><span data-stu-id="6a118-115">Element</span></span>|<span data-ttu-id="6a118-116">설명</span><span class="sxs-lookup"><span data-stu-id="6a118-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6a118-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="6a118-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="6a118-118">명명 된 구성 설정의 컬렉션을 포함 <xref:System.Runtime.Caching.MemoryCache> 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="6a118-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a118-119">설명</span><span class="sxs-lookup"><span data-stu-id="6a118-119">Remarks</span></span>  
 <span data-ttu-id="6a118-120">`remove` 요소 제거는 `namedCache` 메모리 내 캐시에 대 한 명명 된 캐시 컬렉션의 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="6a118-120">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a118-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6a118-121">See Also</span></span>  
 [<span data-ttu-id="6a118-122">\<namedCaches > 요소 (캐시 설정)</span><span class="sxs-lookup"><span data-stu-id="6a118-122">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
