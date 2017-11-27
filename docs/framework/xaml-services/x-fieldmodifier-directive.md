---
title: "x:FieldModifier 지시문"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
caps.latest.revision: "15"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 77745744c0da1e4b4425af6d8e4319faaf524908
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="xfieldmodifier-directive"></a><span data-ttu-id="318ae-102">x:FieldModifier 지시문</span><span class="sxs-lookup"><span data-stu-id="318ae-102">x:FieldModifier Directive</span></span>
<span data-ttu-id="318ae-103">명명 된 개체 참조에 대 한 필드 정의 된 XAML 컴파일 동작을 수정 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 대신 액세스는 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 기본 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="318ae-103">Modifies XAML compilation behavior so that fields for named object references are defined with <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> access instead of the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> default behavior.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="318ae-104">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="318ae-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object x:FieldModifier="Public".../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="318ae-105">XAML 값</span><span class="sxs-lookup"><span data-stu-id="318ae-105">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="318ae-106">*공용*</span><span class="sxs-lookup"><span data-stu-id="318ae-106">*Public*</span></span>|<span data-ttu-id="318ae-107">지정 하기 위해 전달 된 정확한 문자열 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 와 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 사용 되는 코드 숨김 프로그래밍 언어에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="318ae-107">The exact string you pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that is used.</span></span> <span data-ttu-id="318ae-108">설명 부분을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="318ae-108">See Remarks.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="318ae-109">종속성</span><span class="sxs-lookup"><span data-stu-id="318ae-109">Dependencies</span></span>  
 <span data-ttu-id="318ae-110">XAML 프로덕션에 사용 하는 경우 `x:FieldModifier` 어디에서 든 지 해당 XAML 프로덕션의 루트 요소를 선언 해야 합니다는 [X:class 지시문](../../../docs/framework/xaml-services/x-class-directive.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="318ae-110">If a XAML production uses `x:FieldModifier` anywhere, the root element of that XAML production must declare an [x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="318ae-111">설명</span><span class="sxs-lookup"><span data-stu-id="318ae-111">Remarks</span></span>  
 <span data-ttu-id="318ae-112">`x:FieldModifier`클래스 또는 해당 멤버의 일반 액세스 수준 선언에 대 한 관련이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="318ae-112">`x:FieldModifier` is not relevant for declaring the general access level of a class or its members.</span></span> <span data-ttu-id="318ae-113">XAML 처리 동작에 대해서만 때 관련이 XAML 프로덕션의 일부인 특정 XAML 개체가 처리 되 고 응용 프로그램의 개체 그래프에서 액세스할 수 있는 개체가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="318ae-113">It is relevant only for XAML-processing behavior when a particular XAML object that is part of a XAML production is processed, and becomes an object that is potentially accessible in the object graph of an application.</span></span> <span data-ttu-id="318ae-114">기본적으로 소비자는 개체 그래프를 직접 수정할 수 없도록 방지 하는 이러한 개체에 대 한 필드 참조를 비공개로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="318ae-114">By default, the field reference for such an object is kept private, which prevents control consumers from modifying the object graph directly.</span></span> <span data-ttu-id="318ae-115">대신 소비자 레이아웃 루트, 자식 요소 컬렉션을 전용된 공용 속성을 가져옴으로써와 같은 프로그래밍 모델에 의해 설정 된 표준 패턴을 사용 하 여 개체 그래프를 수정 해야 등에입니다.</span><span class="sxs-lookup"><span data-stu-id="318ae-115">Instead, control consumers are expected to modify the object graph by using standard patterns that are enabled by programming models, such as by obtaining the layout root, the child element collections, the dedicated public properties, and so on.</span></span>  
  
 <span data-ttu-id="318ae-116">에 대 한 값은 `x:FieldModifier` 특성 프로그래밍 언어에 따라 다르며 특정 프레임 워크의 목적은 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="318ae-116">The value for the `x:FieldModifier` attribute varies by programming language, and its purpose can vary in specific frameworks.</span></span> <span data-ttu-id="318ae-117">사용할 문자열을 각 언어 구현 하는 방법에 따라 달라 집니다 해당 <xref:System.CodeDom.Compiler.CodeDomProvider> 및 형식 변환기에 대 한 의미를 정의 하려면 반환 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 및 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, 해당 언어는 대/소문자 구분 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="318ae-117">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>  
  
-   <span data-ttu-id="318ae-118">에 대 한 [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)]를 지정 하려면 전달할 문자열 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 은 `public`합니다.</span><span class="sxs-lookup"><span data-stu-id="318ae-118">For [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], the string to pass to designate <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is `public`.</span></span>  
  
-   <span data-ttu-id="318ae-119">에 대 한 [!INCLUDE[TLA2#tla_visualbnet](../../../includes/tla2sharptla-visualbnet-md.md)]를 지정 하려면 전달할 문자열 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 은 `Public`합니다.</span><span class="sxs-lookup"><span data-stu-id="318ae-119">For [!INCLUDE[TLA2#tla_visualbnet](../../../includes/tla2sharptla-visualbnet-md.md)], the string to pass to designate <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is `Public`.</span></span>  
  
-   <span data-ttu-id="318ae-120">에 대 한 [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], XAML 위한 대상이 현재 존재 하는 이므로 전달할 문자열 이므로 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="318ae-120">For [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], no targets for XAML currently exist; therefore, the string to pass is undefined.</span></span>  
  
 <span data-ttu-id="318ae-121">지정할 수 있습니다 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> (`internal` 에 [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], `Friend` 에 [!INCLUDE[TLA2#tla_visualb](../../../includes/tla2sharptla-visualb-md.md)]) 지정 하지만 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 별로 사용 되지 않습니다 때문에 `NotPublic` 동작은 기본적으로 이미로 합니다.</span><span class="sxs-lookup"><span data-stu-id="318ae-121">You can also specify <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> (`internal` in [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], `Friend` in [!INCLUDE[TLA2#tla_visualb](../../../includes/tla2sharptla-visualb-md.md)]) but specifying <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is unusual because `NotPublic` as the behavior is already the default.</span></span>  
  
 <span data-ttu-id="318ae-122"><xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>어셈블리 외부의 코드는 XAML을 컴파일한 XAML을 만든 요소에 대 한 액세스를 해야 함을 자주 없기 때문에 기본 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="318ae-122"><xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is the default behavior because it is infrequent that code outside the assembly that compiled the XAML needs access to a XAML-created element.</span></span> <span data-ttu-id="318ae-123">WPF 보안 아키텍처 XAML 컴파일 동작와 함께 설정 하지 않으면 공용으로 요소 인스턴스를 저장 하는 필드를 선언 하지 것입니다는 `x:FieldModifier` 공용 액세스를 허용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="318ae-123">WPF security architecture together with XAML compilation behavior will not declare fields that store element instances as public, unless you specifically set the `x:FieldModifier` to allow public access.</span></span>  
  
 <span data-ttu-id="318ae-124">`x:FieldModifier`사용 하 여 요소에만 관련이 [X:name 지시문](../../../docs/framework/xaml-services/x-name-directive.md) 공개 된 후 필드를 참조 하도록 해당 이름을 사용 되기 때문에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="318ae-124">`x:FieldModifier` is only relevant for elements with an [x:Name Directive](../../../docs/framework/xaml-services/x-name-directive.md) because that name is used to reference the field after it is public.</span></span>  
  
 <span data-ttu-id="318ae-125">기본적으로 루트 요소에 대 한 partial 클래스는 공용 필드 그러나 해야 public이 아닌를 사용 하 여는 [X:classmodifier 지시문](../../../docs/framework/xaml-services/x-classmodifier-directive.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="318ae-125">By default, the partial class for the root element is public; however, you can make it nonpublic by using the [x:ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md).</span></span> <span data-ttu-id="318ae-126">[X:classmodifier 지시문](../../../docs/framework/xaml-services/x-classmodifier-directive.md) 루트 요소 클래스의 인스턴스 액세스 수준에도 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="318ae-126">The [x:ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md) also affects the access level of the instance of the root element class.</span></span> <span data-ttu-id="318ae-127">모두 넣을 수 `x:Name` 및 `x:FieldModifier` 루트에 요소를 하지만이 공용 필드의 복사본을 만듭니다는 true 루트 요소 클래스 액세스 수준으로 여전히 루트 요소에 의해 제어 [X:classmodifier 지시문](../../../docs/framework/xaml-services/x-classmodifier-directive.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="318ae-127">You can put both `x:Name` and `x:FieldModifier` on the root element, but this only makes a public field copy of the root element, with the true root element class access level still controlled by [x:ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="318ae-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="318ae-128">See Also</span></span>  
 [<span data-ttu-id="318ae-129">WPF에 대한 XAML 및 사용자 지정 클래스</span><span class="sxs-lookup"><span data-stu-id="318ae-129">XAML and Custom Classes for WPF</span></span>](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)  
 [<span data-ttu-id="318ae-130">WPF의 코드 숨김 및 XAML</span><span class="sxs-lookup"><span data-stu-id="318ae-130">Code-Behind and XAML in WPF</span></span>](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)  
 [<span data-ttu-id="318ae-131">x:Name 지시문</span><span class="sxs-lookup"><span data-stu-id="318ae-131">x:Name Directive</span></span>](../../../docs/framework/xaml-services/x-name-directive.md)  
 [<span data-ttu-id="318ae-132">WPF 응용 프로그램 빌드(WPF)</span><span class="sxs-lookup"><span data-stu-id="318ae-132">Building a WPF Application (WPF)</span></span>](../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)  
 [<span data-ttu-id="318ae-133">x:ClassModifier 지시문</span><span class="sxs-lookup"><span data-stu-id="318ae-133">x:ClassModifier Directive</span></span>](../../../docs/framework/xaml-services/x-classmodifier-directive.md)
