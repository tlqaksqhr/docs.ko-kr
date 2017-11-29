---
title: '&lt;persistenceProvider&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b506b8ef14246ee954adb0a16102f4bb208106b0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltpersistenceprovidergt"></a><span data-ttu-id="5e655-102">&lt;persistenceProvider&gt;</span><span class="sxs-lookup"><span data-stu-id="5e655-102">&lt;persistenceProvider&gt;</span></span>
<span data-ttu-id="5e655-103">사용할 지속성 공급자 구현 형식 및 지속성 작업에 사용할 제한 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5e655-103">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>  
  
 <span data-ttu-id="5e655-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="5e655-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5e655-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="5e655-105">\<behaviors></span></span>  
<span data-ttu-id="5e655-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="5e655-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="5e655-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="5e655-107">\<behavior></span></span>  
<span data-ttu-id="5e655-108">\<persistenceProvider ></span><span class="sxs-lookup"><span data-stu-id="5e655-108">\<persistenceProvider></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e655-109">구문</span><span class="sxs-lookup"><span data-stu-id="5e655-109">Syntax</span></span>  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"  
   type="String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5e655-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5e655-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5e655-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5e655-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5e655-112">특성</span><span class="sxs-lookup"><span data-stu-id="5e655-112">Attributes</span></span>  
  
|<span data-ttu-id="5e655-113">특성</span><span class="sxs-lookup"><span data-stu-id="5e655-113">Attribute</span></span>|<span data-ttu-id="5e655-114">설명</span><span class="sxs-lookup"><span data-stu-id="5e655-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5e655-115">persistenceOperationTimeout</span><span class="sxs-lookup"><span data-stu-id="5e655-115">persistenceOperationTimeout</span></span>|<span data-ttu-id="5e655-116">지속성 작업에 사용되는 제한 시간을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5e655-116">A <xref:System.TimeSpan> value that specifies the time-out used for persistence operations.</span></span> <span data-ttu-id="5e655-117">기본값은 "00: 00:30"입니다.</span><span class="sxs-lookup"><span data-stu-id="5e655-117">The default is "00:00:30".</span></span>|  
|<span data-ttu-id="5e655-118">type</span><span class="sxs-lookup"><span data-stu-id="5e655-118">type</span></span>|<span data-ttu-id="5e655-119">사용할 지속성 공급자 팩터리의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5e655-119">A string that specifies the type of the persistence provider factory to use.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5e655-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5e655-120">Child Elements</span></span>  
 <span data-ttu-id="5e655-121">없음</span><span class="sxs-lookup"><span data-stu-id="5e655-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5e655-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5e655-122">Parent Elements</span></span>  
  
|<span data-ttu-id="5e655-123">요소</span><span class="sxs-lookup"><span data-stu-id="5e655-123">Element</span></span>|<span data-ttu-id="5e655-124">설명</span><span class="sxs-lookup"><span data-stu-id="5e655-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5e655-125">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="5e655-125">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="5e655-126">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5e655-126">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e655-127">설명</span><span class="sxs-lookup"><span data-stu-id="5e655-127">Remarks</span></span>  
 <span data-ttu-id="5e655-128">이 요소는 WCF 서비스의 상태를 serialize하는 데 사용되는 지속성 공급자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5e655-128">This element specifies the persistence provider to be used to serialize the state of a WCF service.</span></span> <span data-ttu-id="5e655-129">이 요소는 HTTP 헤더에서 상태 정보를 전달하는 `wsHttpContextBinding`과 함께 사용되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e655-129">It should be used together with the `wsHttpContextBinding` which passes state information in HTTP headers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e655-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5e655-130">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PersistenceProviderElement>  
 <xref:System.ServiceModel.Persistence.PersistenceProvider>
