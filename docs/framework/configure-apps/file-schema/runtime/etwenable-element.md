---
title: "&lt;etwEnable&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1d94d49fcb2c395de5172a730923dbe42f67cf35
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltetwenablegt-element"></a><span data-ttu-id="9e2b4-102">&lt;etwEnable&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="9e2b4-102">&lt;etwEnable&gt; Element</span></span>
<span data-ttu-id="9e2b4-103">공용 언어 런타임 이벤트에 대해 ETW(Windows용 이벤트 추적)를 사용하도록 설정할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e2b4-103">Specifies whether to enable event tracing for Windows (ETW) for common language runtime events.</span></span>  
  
 <span data-ttu-id="9e2b4-104">\<구성 > 요소</span><span class="sxs-lookup"><span data-stu-id="9e2b4-104">\<configuration> Element</span></span>  
<span data-ttu-id="9e2b4-105">\<런타임 > 요소</span><span class="sxs-lookup"><span data-stu-id="9e2b4-105">\<runtime> Element</span></span>  
<span data-ttu-id="9e2b4-106">\<etwEnabled ></span><span class="sxs-lookup"><span data-stu-id="9e2b4-106">\<etwEnabled></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e2b4-107">구문</span><span class="sxs-lookup"><span data-stu-id="9e2b4-107">Syntax</span></span>  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9e2b4-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9e2b4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9e2b4-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9e2b4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9e2b4-110">특성</span><span class="sxs-lookup"><span data-stu-id="9e2b4-110">Attributes</span></span>  
  
|<span data-ttu-id="9e2b4-111">특성</span><span class="sxs-lookup"><span data-stu-id="9e2b4-111">Attribute</span></span>|<span data-ttu-id="9e2b4-112">설명</span><span class="sxs-lookup"><span data-stu-id="9e2b4-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9e2b4-113">사용</span><span class="sxs-lookup"><span data-stu-id="9e2b4-113">enabled</span></span>|<span data-ttu-id="9e2b4-114">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="9e2b4-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="9e2b4-115">ETW를 사용 해야 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e2b4-115">Specifies whether ETW should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="9e2b4-116">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="9e2b4-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="9e2b4-117">값</span><span class="sxs-lookup"><span data-stu-id="9e2b4-117">Value</span></span>|<span data-ttu-id="9e2b4-118">설명</span><span class="sxs-lookup"><span data-stu-id="9e2b4-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9e2b4-119">true</span><span class="sxs-lookup"><span data-stu-id="9e2b4-119">true</span></span>|<span data-ttu-id="9e2b4-120">ETW를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e2b4-120">Enable ETW.</span></span> <span data-ttu-id="9e2b4-121">Windows Vista 및 Windows Server 2008 운영 체제부터 Windows 버전에 대 한 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="9e2b4-121">This is the default for versions of Windows beginning with the Windows Vista and Windows Server 2008 operating systems.</span></span>|  
|<span data-ttu-id="9e2b4-122">False</span><span class="sxs-lookup"><span data-stu-id="9e2b4-122">false</span></span>|<span data-ttu-id="9e2b4-123">ETW를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e2b4-123">Disable ETW.</span></span> <span data-ttu-id="9e2b4-124">이전 버전의 Windows에 대 한 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="9e2b4-124">This is the default for earlier versions of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9e2b4-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9e2b4-125">Child Elements</span></span>  
 <span data-ttu-id="9e2b4-126">없음</span><span class="sxs-lookup"><span data-stu-id="9e2b4-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9e2b4-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9e2b4-127">Parent Elements</span></span>  
  
|<span data-ttu-id="9e2b4-128">요소</span><span class="sxs-lookup"><span data-stu-id="9e2b4-128">Element</span></span>|<span data-ttu-id="9e2b4-129">설명</span><span class="sxs-lookup"><span data-stu-id="9e2b4-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9e2b4-130">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9e2b4-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="9e2b4-131">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9e2b4-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e2b4-132">설명</span><span class="sxs-lookup"><span data-stu-id="9e2b4-132">Remarks</span></span>  
 <span data-ttu-id="9e2b4-133">Windows Vista부터, ETW 기본적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e2b4-133">Beginning with Windows Vista, ETW is enabled by default.</span></span> <span data-ttu-id="9e2b4-134">이 요소를 사용 하 여 응용 프로그램에 대 한 ETW를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e2b4-134">Use this element to disable ETW for an application.</span></span> <span data-ttu-id="9e2b4-135">이전 버전의 Windows에서 응용 프로그램에 대 한 ETW를 사용 하도록 설정 하려면이 요소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e2b4-135">In earlier versions of Windows, use this element to enable ETW for an application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e2b4-136">ETW는 사용 하도록 설정 또는 레지스트리 설정을 사용 하 여 서버에 전체적으로 해제 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e2b4-136">ETW can be enabled or disabled globally on a server by using a registry setting.</span></span> <span data-ttu-id="9e2b4-137">참조 [.NET Framework 로깅 제어](../../../../../docs/framework/performance/controlling-logging.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9e2b4-137">See [Controlling .NET Framework Logging](../../../../../docs/framework/performance/controlling-logging.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e2b4-138">예</span><span class="sxs-lookup"><span data-stu-id="9e2b4-138">Example</span></span>  
 <span data-ttu-id="9e2b4-139">다음 예제에서는 응용 프로그램에 대 한 ETW 추적을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9e2b4-139">The following example shows how to enable ETW tracing for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9e2b4-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9e2b4-140">See Also</span></span>  
 [<span data-ttu-id="9e2b4-141">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="9e2b4-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="9e2b4-142">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="9e2b4-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="9e2b4-143">.NET Framework 로깅 제어</span><span class="sxs-lookup"><span data-stu-id="9e2b4-143">Controlling .NET Framework Logging</span></span>](../../../../../docs/framework/performance/controlling-logging.md)
