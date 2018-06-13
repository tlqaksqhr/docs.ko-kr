---
title: x:Null 태그 확장명
ms.date: 03/30/2017
f1_keywords:
- NullExtension
- x:NullExtension
- x:Null
- "Null"
- xNull
helpviewer_keywords:
- Null markup extension in XAML [XAML Services]
- x:Null markup extension [XAML Services]
- XAML [XAML Services], x:Null markup extension
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
ms.openlocfilehash: 94cfaee9a0a9a9f3892b9df50ac59103709a3b14
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562351"
---
# <a name="xnull-markup-extension"></a><span data-ttu-id="6e0e8-102">x:Null 태그 확장명</span><span class="sxs-lookup"><span data-stu-id="6e0e8-102">x:Null Markup Extension</span></span>
<span data-ttu-id="6e0e8-103">지정 `null` XAML 멤버에 대 한 값으로.</span><span class="sxs-lookup"><span data-stu-id="6e0e8-103">Specifies `null` as a value for a XAML member.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="6e0e8-104">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="6e0e8-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Null}" .../>  
```  
  
## <a name="remarks"></a><span data-ttu-id="6e0e8-105">설명</span><span class="sxs-lookup"><span data-stu-id="6e0e8-105">Remarks</span></span>  
 <span data-ttu-id="6e0e8-106">C#에서 null 참조에 대 한 키워드 및 [!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)] null입니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e8-106">The keyword for a null reference in C# and [!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)] is null.</span></span> <span data-ttu-id="6e0e8-107">Null 참조에 대 한 Microsoft Visual Basic 키워드는 `Nothing`, 항상 사용 되지만 `{x:Null}` XAML 사용에 관계 없이 XAML과 연결 하는 코드 숨김 언어도 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e8-107">The Microsoft Visual Basic keyword for a null reference is `Nothing`, but you always use `{x:Null}` as the XAML usage regardless which code-behind language you associate with the XAML.</span></span>  
  
 <span data-ttu-id="6e0e8-108">`x:Null` 태그 확장은 설정 가능한 속성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e8-108">The `x:Null` markup extension has no settable properties.</span></span>  
  
 <span data-ttu-id="6e0e8-109">널 사용은 종종 clr XAML 멤버 노출 연관 <xref:System.Nullable%601> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e8-109">A null usage is often associated with the XAML member exposure of a CLR <xref:System.Nullable%601> value.</span></span>  
  
 <span data-ttu-id="6e0e8-110">`x:Null` 태그 확장, 모든 XAML 태그 확장 처럼 중괄호를 사용 하 여 (`{,}`) 이스케이프를 리터럴 또는 이벤트 처리기 참조 이외의 특성 값의 처리에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e8-110">The `x:Null` markup extension, like all XAML markup extensions, uses the braces (`{,}`) for escaping the handling of attribute values to be other than literals or event-handler references.</span></span> <span data-ttu-id="6e0e8-111">특성 구문은 이러한 태그 확장 가장 자주 사용 되는 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e8-111">Attribute syntax is the syntax most frequently used with this markup extension.</span></span> <span data-ttu-id="6e0e8-112">개체 요소 구문 `<x:Null />` 은 기술적으로 가능 하지만 때문에 거의 사용 되지 않습니다는 `x:Null` 태그 확장에는 위치 매개 변수 또는 생성 인수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e8-112">An object element syntax `<x:Null />` is technically possible, but is rarely used because the `x:Null` markup extension has no positional parameters or construction arguments.</span></span>  
  
 <span data-ttu-id="6e0e8-113">태그 확장에 대 한 정보를 참조 하십시오. [태그 확장명 및 WPF XAML](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e8-113">For information about markup extensions, see [Markup Extensions and WPF XAML](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
 <span data-ttu-id="6e0e8-114">이 태그 확장에 대 한 처리 정의한.NET Framework XAML 서비스에서는 <xref:System.Windows.Markup.NullExtension> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e8-114">In .NET Framework XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.NullExtension> class.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="6e0e8-115">WPF 사용 정보</span><span class="sxs-lookup"><span data-stu-id="6e0e8-115">WPF Usage Notes</span></span>  
 <span data-ttu-id="6e0e8-116">`null` 참조 형식 종속성 속성에 대 한 초기 설정 되지 않은 값일 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e8-116">Note that `null` is not necessarily the initial unset value for a reference-type dependency property.</span></span> <span data-ttu-id="6e0e8-117">초기 기본값 각 종속성 속성에 따라 다를 수 있습니다 및 속성별 메타 데이터에 따라 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e8-117">The initial default value can vary for each dependency property and can be based on property-specific metadata.</span></span> <span data-ttu-id="6e0e8-118">많은 종속성 속성이 동의 하지 않으면 `null` 태그 또는 유효성 검사 콜백 구현 때문에 코드를 통해 값으로.</span><span class="sxs-lookup"><span data-stu-id="6e0e8-118">Many dependency properties do not accept `null` as a value, either through markup or code because of their validation callback implementations.</span></span> <span data-ttu-id="6e0e8-119">종속성 속성에 대 한 자세한 내용은 참조 [종속성 속성 개요](../../../docs/framework/wpf/advanced/dependency-properties-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e8-119">For more information about dependency properties, see [Dependency Properties Overview](../../../docs/framework/wpf/advanced/dependency-properties-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e0e8-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6e0e8-120">See Also</span></span>  
 <xref:System.Windows.DependencyProperty.UnsetValue>  
 [<span data-ttu-id="6e0e8-121">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="6e0e8-121">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="6e0e8-122">태그 확장 및 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="6e0e8-122">Markup Extensions and WPF XAML</span></span>](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
