---
title: "&lt;TimeSpan_LegacyFormatMode&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- <TimeSpan_LegacyFormatMode> element
- TimeSpan_LegacyFormatMode element
ms.assetid: 865e7207-d050-4442-b574-57ea29d5e2d6
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: be4b26cdc79cef0854221172b8dea0bcc0f50981
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="lttimespanlegacyformatmodegt-element"></a><span data-ttu-id="a3deb-102">&lt;TimeSpan_LegacyFormatMode&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="a3deb-102">&lt;TimeSpan_LegacyFormatMode&gt; Element</span></span>
<span data-ttu-id="a3deb-103">런타임에서 사용 하는 작업 서식 지정에 레거시 동작을 유지할지 여부를 결정 <xref:System.TimeSpan?displayProperty=nameWithType> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a3deb-103">Determines whether the runtime preserves legacy behavior in formatting operations with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>  
  
 <span data-ttu-id="a3deb-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a3deb-104">\<configuration></span></span>  
<span data-ttu-id="a3deb-105">\<런타임 ></span><span class="sxs-lookup"><span data-stu-id="a3deb-105">\<runtime></span></span>  
<span data-ttu-id="a3deb-106">< TimeSpan_LegacyFormatMode ></span><span class="sxs-lookup"><span data-stu-id="a3deb-106"><TimeSpan_LegacyFormatMode></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3deb-107">구문</span><span class="sxs-lookup"><span data-stu-id="a3deb-107">Syntax</span></span>  
  
```xml  
<TimeSpan_LegacyFormatMode    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a3deb-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a3deb-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a3deb-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a3deb-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a3deb-110">특성</span><span class="sxs-lookup"><span data-stu-id="a3deb-110">Attributes</span></span>  
  
|<span data-ttu-id="a3deb-111">특성</span><span class="sxs-lookup"><span data-stu-id="a3deb-111">Attribute</span></span>|<span data-ttu-id="a3deb-112">설명</span><span class="sxs-lookup"><span data-stu-id="a3deb-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="a3deb-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="a3deb-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="a3deb-114">런타임이 레거시 서식 지정 동작을 사용할지 여부 지정 <xref:System.TimeSpan?displayProperty=nameWithType> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a3deb-114">Specifies whether the runtime uses legacy formatting behavior with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="a3deb-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="a3deb-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="a3deb-116">값</span><span class="sxs-lookup"><span data-stu-id="a3deb-116">Value</span></span>|<span data-ttu-id="a3deb-117">설명</span><span class="sxs-lookup"><span data-stu-id="a3deb-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="a3deb-118">런타임이 레거시 서식 동작을 복원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3deb-118">The runtime does not restore legacy formatting behavior.</span></span>|  
|`true`|<span data-ttu-id="a3deb-119">런타임이 레거시 서식 동작을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="a3deb-119">The runtime restores legacy formatting behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a3deb-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a3deb-120">Child Elements</span></span>  
 <span data-ttu-id="a3deb-121">없음</span><span class="sxs-lookup"><span data-stu-id="a3deb-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a3deb-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a3deb-122">Parent Elements</span></span>  
  
|<span data-ttu-id="a3deb-123">요소</span><span class="sxs-lookup"><span data-stu-id="a3deb-123">Element</span></span>|<span data-ttu-id="a3deb-124">설명</span><span class="sxs-lookup"><span data-stu-id="a3deb-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a3deb-125">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a3deb-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a3deb-126">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a3deb-126">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3deb-127">설명</span><span class="sxs-lookup"><span data-stu-id="a3deb-127">Remarks</span></span>  
 <span data-ttu-id="a3deb-128">부터는 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], <xref:System.TimeSpan?displayProperty=nameWithType> 구현 구조는 <xref:System.IFormattable> 인터페이스와 표준 및 사용자 지정 형식 문자열을 사용 하는 작업 서식 지정을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3deb-128">Starting with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], the <xref:System.TimeSpan?displayProperty=nameWithType> structure implements the <xref:System.IFormattable> interface and supports formatting operations with standard and custom format strings.</span></span> <span data-ttu-id="a3deb-129">Throw 구문 분석 방법을 지정 자가 지원 되지 않는 형식 또는 형식 문자열을에서 발생 한 <xref:System.FormatException>합니다.</span><span class="sxs-lookup"><span data-stu-id="a3deb-129">If a parsing method encounters an unsupported format specifier or format string, it throws a <xref:System.FormatException>.</span></span>  
  
 <span data-ttu-id="a3deb-130">이전 버전의.NET Framework에는 <xref:System.TimeSpan> 구조를 구현 하지 않았습니다 <xref:System.IFormattable> 및 형식 문자열을 지원 하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="a3deb-130">In previous versions of the .NET Framework, the <xref:System.TimeSpan> structure did not implement <xref:System.IFormattable> and did not support format strings.</span></span> <span data-ttu-id="a3deb-131">그러나 많은 개발자에 게 실수로 것으로 간주 <xref:System.TimeSpan> 형식 문자열 집합을 지원 않았습니다 고에 사용 되는 [합성 서식 지정 작업](../../../../../docs/standard/base-types/composite-formatting.md) 와 같은 메서드로 <xref:System.String.Format%2A?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="a3deb-131">However, many developers mistakenly assumed that <xref:System.TimeSpan> did support a set of format strings and used them in [composite formatting operations](../../../../../docs/standard/base-types/composite-formatting.md) with methods such as <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a3deb-132">일반적으로 해당 형식이 구현 하는 경우 <xref:System.IFormattable> 지원 형식 문자열, 문자열 일반적으로 throw 하는 지원 되지 않는 형식으로 서식 지정 메서드를 호출 하 고는 <xref:System.FormatException>합니다.</span><span class="sxs-lookup"><span data-stu-id="a3deb-132">Ordinarily, if a type implements <xref:System.IFormattable> and supports format strings, calls to formatting methods with unsupported format strings usually throw a <xref:System.FormatException>.</span></span> <span data-ttu-id="a3deb-133">그러나 때문에 <xref:System.TimeSpan> 구현 하지 않았습니다. <xref:System.IFormattable>, 런타임에서 형식 문자열을 무시 하 고 대신 호출는 <xref:System.TimeSpan.ToString?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="a3deb-133">However, because <xref:System.TimeSpan> did not implement <xref:System.IFormattable>, the runtime ignored the format string and instead called the <xref:System.TimeSpan.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="a3deb-134">즉, 즉, 형식 문자열 서식 지정 작업에 영향을 주지 않지만 있으면 발생 하지 않는 한 <xref:System.FormatException>합니다.</span><span class="sxs-lookup"><span data-stu-id="a3deb-134">This means that, although the format strings had no effect on the formatting operation, their presence did not result in a <xref:System.FormatException>.</span></span>  
  
 <span data-ttu-id="a3deb-135">사용할 수 있는 레거시 코드는 합성 형식 지정 메서드와 잘못 된 형식 문자열을 전달 하 고 해당 코드를 다시 컴파일할 수 없는 경우에는 `<TimeSpan_LegacyFormatMode>` 레거시를 복원 하는 요소 <xref:System.TimeSpan> 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3deb-135">For cases in which legacy code passes a composite formatting method and an invalid format string, and that code cannot be recompiled, you can use the `<TimeSpan_LegacyFormatMode>` element to restore the legacy <xref:System.TimeSpan> behavior.</span></span> <span data-ttu-id="a3deb-136">설정 하는 경우는 `enabled` 이 요소의 특성 `true`, 복합 형식 지정 메서드를 호출 <xref:System.TimeSpan.ToString?displayProperty=nameWithType> 대신 <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, 및 <xref:System.FormatException> throw 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3deb-136">When you set the `enabled` attribute of this element to `true`, the composite formatting method results in a call to <xref:System.TimeSpan.ToString?displayProperty=nameWithType> rather than <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, and a <xref:System.FormatException> is not thrown.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3deb-137">예</span><span class="sxs-lookup"><span data-stu-id="a3deb-137">Example</span></span>  
 <span data-ttu-id="a3deb-138">다음 예제는 <xref:System.TimeSpan> 개체와 사용 하 여 서식을 지정 하려는 시도 <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> 메서드는 지원 되지 않는 표준 형식 문자열을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3deb-138">The following example instantiates a <xref:System.TimeSpan> object and attempts to format it with the <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> method by using an unsupported standard format string.</span></span>  
  
 [!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
 [!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]  
  
 <span data-ttu-id="a3deb-139">예제를 실행 하는 [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] 하거나 이전 버전에는 다음과 같은 출력 표시:</span><span class="sxs-lookup"><span data-stu-id="a3deb-139">When you run the example on the [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] or on an earlier version, it displays the following output:</span></span>  
  
```  
12:30:45  
```  
  
 <span data-ttu-id="a3deb-140">이는 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] 이상 버전에서 예제를 실행하는 경우 출력과 다르게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3deb-140">This differs markedly from the output if you run the example on the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] or later version:</span></span>  
  
```  
Invalid Format  
```  
  
 <span data-ttu-id="a3deb-141">그러나 다음 구성 파일을 예제 디렉터리에 추가한 다음 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] 이상 버전에서 예제를 실행하는 경우 출력은 [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)]에서 실행할 때 예제가 생성한 출력과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="a3deb-141">However, if you add the following configuration file to the example's directory and then run the example on the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] or later version, the output is identical to that produced by the example when it is run on [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <TimeSpan_LegacyFormatMode enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a3deb-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a3deb-142">See Also</span></span>  
 [<span data-ttu-id="a3deb-143">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="a3deb-143">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="a3deb-144">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="a3deb-144">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
