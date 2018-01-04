---
title: "x:Reference 태그 확장명"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- x:Reference markup extension [XAML Services]
- XAML [XAML Services], x:Reference Markup Extension
- Reference markup extension [XAML Services]
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
caps.latest.revision: "8"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 03b63cb40e57223d5c66c03fb60780689cd6c925
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="xreference-markup-extension"></a><span data-ttu-id="b19e8-102">x:Reference 태그 확장명</span><span class="sxs-lookup"><span data-stu-id="b19e8-102">x:Reference Markup Extension</span></span>
<span data-ttu-id="b19e8-103">XAML 태그에 선언 된 인스턴스를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="b19e8-103">References an instance that is declared elsewhere in XAML markup.</span></span> <span data-ttu-id="b19e8-104">요소의 참조 `x:Name`합니다.</span><span class="sxs-lookup"><span data-stu-id="b19e8-104">The reference refers to an element's `x:Name`.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="b19e8-105">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="b19e8-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Reference instancexName}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="b19e8-106">XAML 개체 요소 사용</span><span class="sxs-lookup"><span data-stu-id="b19e8-106">XAML Object Element Usage</span></span>  
  
```xaml  
<object>  
  <object.property>  
    <x:Reference Name="instancexName"/>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="b19e8-107">XAML 값</span><span class="sxs-lookup"><span data-stu-id="b19e8-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`instancexName`|<span data-ttu-id="b19e8-108">`x:Name` 값 (또는 값의는 <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-식별 된 속성) 참조 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="b19e8-108">The `x:Name` value (or value of the <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-identified property) of the referenced instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b19e8-109">설명</span><span class="sxs-lookup"><span data-stu-id="b19e8-109">Remarks</span></span>  
 <span data-ttu-id="b19e8-110">`x:Reference`WPF와 같은 특정 프레임 워크에서 구현 된 요소 참조 개념에 대 한 XAML 언어 수준 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b19e8-110">`x:Reference` provides XAML language-level support for an element reference concept that was otherwise implemented in specific frameworks such as WPF.</span></span>  
  
## <a name="xreference-and-wpf"></a><span data-ttu-id="b19e8-111">X:reference 및 WPF</span><span class="sxs-lookup"><span data-stu-id="b19e8-111">x:Reference and WPF</span></span>  
 <span data-ttu-id="b19e8-112">WPF 및 XAML 2006에서는 요소 참조의 프레임 워크 수준 기능에 의해 해결 <xref:System.Windows.Data.Binding.ElementName%2A> 바인딩.</span><span class="sxs-lookup"><span data-stu-id="b19e8-112">In WPF and XAML 2006, element references are addressed by the framework-level feature of <xref:System.Windows.Data.Binding.ElementName%2A> binding.</span></span> <span data-ttu-id="b19e8-113">대부분의 WPF 응용 프로그램과 시나리오에 대 한 <xref:System.Windows.Data.Binding.ElementName%2A> 바인딩을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b19e8-113">For most WPF applications and scenarios, <xref:System.Windows.Data.Binding.ElementName%2A> binding should still be used.</span></span> <span data-ttu-id="b19e8-114">이 일반 지침에 대 한 예외 데이터 컨텍스트 또는 데이터 바인딩 불가능할 수 있는 기타 영역 지정 고려 사항 하 고 태그 컴파일에 포함 되지 않은 경우 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b19e8-114">Exceptions to this general guidance might include cases where there are data context or other scoping considerations that make data binding impractical and where markup compilation is not involved.</span></span>  
  
 <span data-ttu-id="b19e8-115">`x:Reference`XAML 2009에서 정의 된 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="b19e8-115">`x:Reference` is a construct defined in XAML 2009.</span></span> <span data-ttu-id="b19e8-116">WPF에서 XAML 2009 기능을 사용할 수 있지만 WPF 태그 컴파일된 XAML에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b19e8-116">In WPF, you can use XAML 2009 features, but only for XAML that is not WPF markup-compiled.</span></span> <span data-ttu-id="b19e8-117">태그 컴파일된 XAML 및 BAML 형식의 XAML은 현재 XAML 2009 언어 키워드 및 기능을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b19e8-117">Markup-compiled XAML and the BAML form of XAML do not currently support the XAML 2009 language keywords and features.</span></span>
