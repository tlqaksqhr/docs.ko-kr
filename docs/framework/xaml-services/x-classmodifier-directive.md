---
title: "x:ClassModifier 지시문"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xClassModifier
- x:ClassModifier
- ClassModifier
helpviewer_keywords:
- XAML [XAML Services], x:ClassModifier attribute
- x:ClassModifier attribute [XAML Services]
- ClassModifier attribute in XAML [XAML Services]
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
caps.latest.revision: "22"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1a4918e23a915ee07eace388ea2cea512c2e479d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="xclassmodifier-directive"></a><span data-ttu-id="ee48c-102">x:ClassModifier 지시문</span><span class="sxs-lookup"><span data-stu-id="ee48c-102">x:ClassModifier Directive</span></span>
<span data-ttu-id="ee48c-103">XAML 컴파일 동작을 수정 하는 경우 `x:Class` 도 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee48c-103">Modifies XAML compilation behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="ee48c-104">특히 부분을 만드는 대신 `class` 있는 `Public` 액세스 수준 (기본값), 제공 된 `x:Class` 사용 하 여 만든는 `NotPublic` 액세스 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="ee48c-104">Specifically, instead of creating a partial `class` that has a `Public` access level (the default), the provided `x:Class` is created with a `NotPublic` access level.</span></span> <span data-ttu-id="ee48c-105">이 문제는 생성된 된 어셈블리의 클래스에 대 한 액세스 수준을 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ee48c-105">This behavior affects the access level for the class in the generated assemblies.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="ee48c-106">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="ee48c-106">XAML Attribute Usage</span></span>  
  
```  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="ee48c-107">XAML 값</span><span class="sxs-lookup"><span data-stu-id="ee48c-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ee48c-108">*NotPublic*</span><span class="sxs-lookup"><span data-stu-id="ee48c-108">*NotPublic*</span></span>|<span data-ttu-id="ee48c-109">정확한 문자열을 지정 하기 위해 전달 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 와 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 사용 하는 코드 숨김 프로그래밍 언어에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="ee48c-109">The exact string to pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that you use.</span></span> <span data-ttu-id="ee48c-110">설명 부분을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ee48c-110">See Remarks.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="ee48c-111">종속성</span><span class="sxs-lookup"><span data-stu-id="ee48c-111">Dependencies</span></span>  
 <span data-ttu-id="ee48c-112">[X:class](../../../docs/framework/xaml-services/x-class-directive.md) 같은 요소에도 제공 해야 하며 해당 요소는 페이지의 루트 요소 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee48c-112">[x:Class](../../../docs/framework/xaml-services/x-class-directive.md) must also be provided on the same element, and that element must be the root element in a page.</span></span> <span data-ttu-id="ee48c-113">자세한 내용은 참조 [ \[MS-XAML\] 섹션 4.3.1.8](http://go.microsoft.com/fwlink/?LinkId=114525)합니다.</span><span class="sxs-lookup"><span data-stu-id="ee48c-113">For more information, see [\[MS-XAML\] Section 4.3.1.8](http://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee48c-114">설명</span><span class="sxs-lookup"><span data-stu-id="ee48c-114">Remarks</span></span>  
 <span data-ttu-id="ee48c-115">값 `x:ClassModifier` .NET Framework XAML 서비스에서 사용 현황 프로그래밍 언어에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="ee48c-115">The value of `x:ClassModifier` in .NET Framework XAML Services usage varies by programming language.</span></span> <span data-ttu-id="ee48c-116">사용할 문자열을 각 언어 구현 하는 방법에 따라 달라 집니다 해당 <xref:System.CodeDom.Compiler.CodeDomProvider> 및 형식 변환기에 대 한 의미를 정의 하려면 반환 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 및 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, 해당 언어는 대/소문자 구분 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="ee48c-116">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>  
  
-   <span data-ttu-id="ee48c-117">에 대 한 [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)]를 지정 하려면 전달할 문자열 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 은 `internal`합니다.</span><span class="sxs-lookup"><span data-stu-id="ee48c-117">For [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `internal`.</span></span>  
  
-   <span data-ttu-id="ee48c-118">에 대 한 [!INCLUDE[TLA2#tla_visualbnet](../../../includes/tla2sharptla-visualbnet-md.md)]를 지정 하려면 전달할 문자열 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 은 `Friend`합니다.</span><span class="sxs-lookup"><span data-stu-id="ee48c-118">For [!INCLUDE[TLA2#tla_visualbnet](../../../includes/tla2sharptla-visualbnet-md.md)], the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `Friend`.</span></span>  
  
-   <span data-ttu-id="ee48c-119">에 대 한 [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], 대상이 존재 XAML 컴파일을 지 원하는; 따라서 전달할 값을 지정 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="ee48c-119">For [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], no targets exist that support compiling XAML; therefore, the value to pass is unspecified.</span></span>  
  
 <span data-ttu-id="ee48c-120">지정할 수도 있습니다 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` 에 [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], `Public` 에 [!INCLUDE[TLA2#tla_visualb](../../../includes/tla2sharptla-visualb-md.md)]) 소비량이 적어지지만 지정 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 때문에 자주 수행 됩니다 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 이미 기본 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="ee48c-120">You can also specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], `Public` in [!INCLUDE[TLA2#tla_visualb](../../../includes/tla2sharptla-visualb-md.md)]); however, specifying <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is infrequently done because <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is already the default behavior.</span></span>  
  
 <span data-ttu-id="ee48c-121">다른 값을 해당 하는 사용자 코드와 액세스 수준 제한 사항 등 `private` 에 [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], 관련이 없으므로 `x:ClassModifier` XAML에서 중첩 된 클래스 참조는 지원 되지 않으므로 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 한정자가 동일한 효과입니다.</span><span class="sxs-lookup"><span data-stu-id="ee48c-121">Other values with equivalent user code access-level restrictions, such as `private` in [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], are not relevant for `x:ClassModifier` because nested class references are not supported in XAML, and therefore, the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modifier has the same effect.</span></span>  
  
## <a name="security-notes"></a><span data-ttu-id="ee48c-122">보안 정보</span><span class="sxs-lookup"><span data-stu-id="ee48c-122">Security Notes</span></span>  
 <span data-ttu-id="ee48c-123">액세스 수준에서 선언 된 `x:ClassModifier` 특정 프레임 워크와 기능에서 여전히 해석 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee48c-123">The access level as declared in `x:ClassModifier` is still subject to interpretation by particular frameworks and their capabilities.</span></span> <span data-ttu-id="ee48c-124">WPF에 로드 하 고 형식을 인스턴스화합니다 기능이 포함 되어 있습니다. 여기서 `x:ClassModifier` 은 `internal`pack URI 참조를 통해 WPF 리소스에서 해당 클래스를 참조 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="ee48c-124">WPF includes capabilities to load and instantiate types where `x:ClassModifier` is `internal`, if that class is referenced from a WPF resource through a pack URI reference.</span></span> <span data-ttu-id="ee48c-125">이 대/이 소문자 및 다른 사용자 같은 다른 프레임 워크에 의해 구현 된을 결과로 마십시오에 의존 하지 `x:ClassModifier` 가능한 모든 인스턴스화를 차단 하도록 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee48c-125">As a consequence of this case and potentially others like it implemented by other frameworks, do not rely exclusively on `x:ClassModifier` to block all possible instantiation attempts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee48c-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ee48c-126">See Also</span></span>  
 [<span data-ttu-id="ee48c-127">x:Class 지시문</span><span class="sxs-lookup"><span data-stu-id="ee48c-127">x:Class Directive</span></span>](../../../docs/framework/xaml-services/x-class-directive.md)  
 [<span data-ttu-id="ee48c-128">WPF의 코드 숨김 및 XAML</span><span class="sxs-lookup"><span data-stu-id="ee48c-128">Code-Behind and XAML in WPF</span></span>](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)  
 [<span data-ttu-id="ee48c-129">x:FieldModifier 지시문</span><span class="sxs-lookup"><span data-stu-id="ee48c-129">x:FieldModifier Directive</span></span>](../../../docs/framework/xaml-services/x-fieldmodifier-directive.md)  
 [<span data-ttu-id="ee48c-130">보안 (WPF)</span><span class="sxs-lookup"><span data-stu-id="ee48c-130">Security (WPF)</span></span>](../../../docs/framework/wpf/security-wpf.md)  
 [<span data-ttu-id="ee48c-131">WPF에서 System.Xaml로 마이그레이션된 형식</span><span class="sxs-lookup"><span data-stu-id="ee48c-131">Types Migrated from WPF to System.Xaml</span></span>](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)
