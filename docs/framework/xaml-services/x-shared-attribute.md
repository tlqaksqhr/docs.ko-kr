---
title: x:Shared 특성
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
ms.openlocfilehash: bee37735382249d2919ef870ca495e6096532352
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563799"
---
# <a name="xshared-attribute"></a><span data-ttu-id="3c1e8-102">x:Shared 특성</span><span class="sxs-lookup"><span data-stu-id="3c1e8-102">x:Shared Attribute</span></span>
<span data-ttu-id="3c1e8-103">로 설정 하면 `false`, 요청 특성 사용된 하는 리소스에 대 한 모든 요청에 대해 동일한 인스턴스를 공유 하는 대신 각 요청에 대 한 새 인스턴스를 만들 수 있도록 WPF 리소스 검색 동작을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-103">When set to `false`, modifies WPF resource-retrieval behavior so that requests for the attributed resource create a new instance for each request instead of sharing the same instance for all requests.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="3c1e8-104">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="3c1e8-104">XAML Attribute Usage</span></span>  
  
```xaml  
<ResourceDictionary>  
  <object x:Shared="false".../>  
</ResourceDictionary>  
```  
  
## <a name="remarks"></a><span data-ttu-id="3c1e8-105">설명</span><span class="sxs-lookup"><span data-stu-id="3c1e8-105">Remarks</span></span>  
 <span data-ttu-id="3c1e8-106">`x:Shared` XAML 언어 XAML 네임 스페이스에 매핑되고 올바른 XAML 언어 요소도.NET Framework XAML 서비스 및 해당 XAML 판독기에서 인식 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-106">`x:Shared` is mapped to the XAML language XAML namespace and is recognized as a valid XAML language element by .NET Framework XAML Services and its XAML readers.</span></span> <span data-ttu-id="3c1e8-107">그러나의 설명한 기능이 `x:Shared` 만 WPF 응용 프로그램 및 WPF XAML 파서에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-107">However, the stated capabilities of `x:Shared` are only relevant for WPF applications and for the WPF XAML parser.</span></span> <span data-ttu-id="3c1e8-108">WPF에서 `x:Shared` 만 유용 특성으로 WPF 내에 존재 하는 개체에 적용 될 때 <xref:System.Windows.ResourceDictionary>합니다.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-108">In WPF, `x:Shared` is only useful as an attribute when it is applied to an object that exists within a WPF <xref:System.Windows.ResourceDictionary>.</span></span> <span data-ttu-id="3c1e8-109">다른 사용 구문 분석 예외 또는 기타 오류로 반환 하지 않지만 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-109">Other usages do not throw parse exceptions or other errors, but they have no effect.</span></span>  
  
 <span data-ttu-id="3c1e8-110">의미 `x:Shared` XAML 언어 사양에 지정 하지 않으면 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-110">The meaning of `x:Shared` is not specified in the XAML language specification.</span></span> <span data-ttu-id="3c1e8-111">.NET Framework XAML 서비스에 구축 하는 것과 같은 다른 XAML 구현 지원 리소스 공유를 반드시 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-111">Other XAML implementations, such as those that build on .NET Framework XAML Services, do not necessarily provide resource-sharing support.</span></span> <span data-ttu-id="3c1e8-112">이러한 XAML 구현 에서도 사용 하는 지원 프레임 워크에서 비슷한 동작을 제공할 수 `x:Shared` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-112">Such XAML implementations could provide similar behavior in the supporting framework that also used `x:Shared` values.</span></span>  
  
 <span data-ttu-id="3c1e8-113">Wpf에서는 기본 `x:Shared` 리소스에 대 한 조건이 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-113">In WPF, the default `x:Shared` condition for resources is `true`.</span></span> <span data-ttu-id="3c1e8-114">이 조건은 모든 리소스 요청이 항상 동일한 인스턴스를 반환을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-114">This condition means that any given resource request always returns the same instance.</span></span>  
  
 <span data-ttu-id="3c1e8-115">와 같은 리소스 API 통해 반환 되는 개체를 수정 <xref:System.Windows.FrameworkElement.FindResource%2A>, 내에서 직접 개체를 수정 하거나는 <xref:System.Windows.ResourceDictionary>을 원래 리소스를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-115">Modifying an object that is returned through a resource API, such as <xref:System.Windows.FrameworkElement.FindResource%2A>, or modifying an object directly within a <xref:System.Windows.ResourceDictionary>, changes the original resource.</span></span> <span data-ttu-id="3c1e8-116">해당 리소스에 대 한 참조는 동적 리소스 참조 인 경우 해당 리소스의 소비자가 변경 된 리소스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-116">If references to that resource were dynamic resource references, the consumers of that resource get the changed resource.</span></span>  
  
 <span data-ttu-id="3c1e8-117">리소스에 대 한 참조 정적 리소스 참조 인 경우 변경 후 리소스 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 처리 시간이 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-117">If references to the resource were static resource references, changes to the resource after [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processing time are irrelevant.</span></span> <span data-ttu-id="3c1e8-118">정적 및 동적 리소스 참조에 대 한 자세한 내용은 참조 [XAML 리소스](../../../docs/framework/wpf/advanced/xaml-resources.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-118">For more information about static versus dynamic resource references, see [XAML Resources](../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
 <span data-ttu-id="3c1e8-119">명시적으로 지정 `x:Shared="true"` 거의 완료 되 면이 이미 기본 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-119">Explicitly specifying `x:Shared="true"` is rarely done, because that is already the default.</span></span> <span data-ttu-id="3c1e8-120">직접 코드에 대 한 해당가 `x:Shared` XAML 사용에만 지정할 수 있습니다 하 고 처리 해야 기본 WPF 동작 또는 중간 XAML 노드 스트림을 로드 경로에서.NET Framework XAML Se를 사용 하 여 처리 하는 경우을 WPF에서 개체 모델 서비스 및 해당 XAML 판독기입니다.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-120">There is no direct code equivalent for `x:Shared` in the WPF object model; it can only be specified in a XAML usage and must be processed either by the default WPF behavior or in an intermediate XAML node stream on the load path if processed using .NET Framework XAML Services and its XAML readers.</span></span>  
  
 <span data-ttu-id="3c1e8-121">에 대 한 시나리오 `x:Shared="false"` 정의 하는 경우는 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement> 리소스로 클래스를 파생 하 고 다음 요소 리소스 콘텐츠 모델을 도입 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-121">A scenario for `x:Shared="false"` is if you define a <xref:System.Windows.FrameworkElement> or <xref:System.Windows.FrameworkContentElement> derived class as a resource and then you introduce the element resource into a content model.</span></span> <span data-ttu-id="3c1e8-122">`x:Shared="false"` 요소 리소스를 동일한 컬렉션에 여러 번 사용할 수 있습니다 (예: 한 <xref:System.Windows.Controls.UIElementCollection>).</span><span class="sxs-lookup"><span data-stu-id="3c1e8-122">`x:Shared="false"` enables an element resource to be introduced multiple times in the same collection (such as a <xref:System.Windows.Controls.UIElementCollection>).</span></span> <span data-ttu-id="3c1e8-123">없이 `x:Shared="false"` 이 때문에 올바르지 않습니다 컬렉션은 해당 내용의 고유성을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-123">Without `x:Shared="false"` this is invalid because the collection enforces uniqueness of its contents.</span></span> <span data-ttu-id="3c1e8-124">그러나는 `x:Shared="false"` 동작은 동일한 인스턴스를 반환 하는 대신 리소스의 동일한 또 다른 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-124">However, the `x:Shared="false"` behavior creates another identical instance of the resource instead of returning the same instance.</span></span>  
  
 <span data-ttu-id="3c1e8-125">또 다른 시나리오로 `x:Shared="false"` 은 사용 하는 경우는 <xref:System.Windows.Freezable> 애니메이션 값 있지만 애니메이션 별로에 리소스를 수정 하는 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-125">Another scenario for `x:Shared="false"` is if you use a <xref:System.Windows.Freezable> resource for animation values but want to modify the resource on a per animation basis.</span></span>  
  
 <span data-ttu-id="3c1e8-126">문자열 처리 `false` 대/소문자를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-126">The string handling of `false` is not case sensitive.</span></span>  
  
 <span data-ttu-id="3c1e8-127">WPF에서 `x:Shared` 다음과 같은 경우에만 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-127">In WPF, `x:Shared` is only valid under the following conditions:</span></span>  
  
-   <span data-ttu-id="3c1e8-128"><xref:System.Windows.ResourceDictionary> 된 항목이 포함 된 `x:Shared` 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-128">The <xref:System.Windows.ResourceDictionary> that contains the items with `x:Shared` must be compiled.</span></span> <span data-ttu-id="3c1e8-129"><xref:System.Windows.ResourceDictionary> 테마에 사용 하거나 느슨한 XAML 안에 들어갈 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-129">The <xref:System.Windows.ResourceDictionary> cannot be within loose XAML or used for themes.</span></span>  
  
-   <span data-ttu-id="3c1e8-130"><xref:System.Windows.ResourceDictionary> 항목이 포함 된 다른 내에서 중첩 될 수 없습니다 <xref:System.Windows.ResourceDictionary>합니다.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-130">The <xref:System.Windows.ResourceDictionary> that contains the items must not be nested within another <xref:System.Windows.ResourceDictionary>.</span></span> <span data-ttu-id="3c1e8-131">예를 들어 사용할 수 없습니다 `x:Shared` 항목에 대 한 한 <xref:System.Windows.ResourceDictionary> 내는 <xref:System.Windows.Style> 그 이름은 이미는 <xref:System.Windows.ResourceDictionary> 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-131">For example, you cannot use `x:Shared` for items in a <xref:System.Windows.ResourceDictionary> that is within a <xref:System.Windows.Style> that is already a <xref:System.Windows.ResourceDictionary> item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c1e8-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3c1e8-132">See Also</span></span>  
 <xref:System.Windows.ResourceDictionary>  
 [<span data-ttu-id="3c1e8-133">XAML 리소스</span><span class="sxs-lookup"><span data-stu-id="3c1e8-133">XAML Resources</span></span>](../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="3c1e8-134">기본 요소</span><span class="sxs-lookup"><span data-stu-id="3c1e8-134">Base Elements</span></span>](../../../docs/framework/wpf/advanced/base-elements.md)
