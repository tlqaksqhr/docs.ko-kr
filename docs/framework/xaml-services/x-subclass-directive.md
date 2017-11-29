---
title: "x:Subclass 지시문"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Subclass
- xSubclass
- x:Subclass
helpviewer_keywords:
- x:Subclass attribute [XAML Services]
- XAML [XAML Services], x:Subclass attribute
- Subclass attribute in XAML [XAML Services]
ms.assetid: 99f66072-8107-4362-ab99-8171dc83b469
caps.latest.revision: "20"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 5c6e91fcecb60dee2577ea62c2313f8b2c7eecbf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="xsubclass-directive"></a><span data-ttu-id="c672a-102">x:Subclass 지시문</span><span class="sxs-lookup"><span data-stu-id="c672a-102">x:Subclass Directive</span></span>
<span data-ttu-id="c672a-103">XAML 태그 컴파일 동작을 수정 하는 경우 `x:Class` 도 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c672a-103">Modifies XAML markup compile behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="c672a-104">기반으로 하는 partial 클래스를 만드는 대신 `x:Class`, 제공 된 `x:Class` 중간 클래스로 생성 한 다음 제공 된 파생된 클래스는 기반으로 해야 하 고 `x:Class`합니다.</span><span class="sxs-lookup"><span data-stu-id="c672a-104">Instead of creating a partial class that is based on `x:Class`, the provided `x:Class` is created as an intermediate class, and then your provided derived class is expected to be based on `x:Class`.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="c672a-105">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="c672a-105">XAML Attribute Usage</span></span>  
  
```  
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="c672a-106">XAML 값</span><span class="sxs-lookup"><span data-stu-id="c672a-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`namespace`|<span data-ttu-id="c672a-107">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c672a-107">Optional.</span></span> <span data-ttu-id="c672a-108">포함 된 CLR 네임 스페이스 지정 `classname`합니다.</span><span class="sxs-lookup"><span data-stu-id="c672a-108">Specifies a CLR namespace that contains `classname`.</span></span> <span data-ttu-id="c672a-109">경우 `namespace` 점 (.) 지정 된 `namespace` 및 `classname`합니다.</span><span class="sxs-lookup"><span data-stu-id="c672a-109">If `namespace` is specified, a dot (.) separates `namespace` and `classname`.</span></span>|  
|`classname`|<span data-ttu-id="c672a-110">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="c672a-110">Required.</span></span> <span data-ttu-id="c672a-111">로드 된 XAML 및 해당 XAML에 대 한 코드 숨김을 연결 하는 partial 클래스의 CLR 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672a-111">Specifies the CLR name of the partial class that connects the loaded XAML and your code-behind for that XAML.</span></span> <span data-ttu-id="c672a-112">설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c672a-112">See Remarks.</span></span>|  
|`subclassNamespace`|<span data-ttu-id="c672a-113">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c672a-113">Optional.</span></span> <span data-ttu-id="c672a-114">다를 수 있습니다 `namespace` 각 네임 스페이스는 다른 확인할 수 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="c672a-114">Can be different from `namespace` if each namespace can resolve the other.</span></span> <span data-ttu-id="c672a-115">포함 된 CLR 네임 스페이스 지정 `subclassName`합니다.</span><span class="sxs-lookup"><span data-stu-id="c672a-115">Specifies a CLR namespace that contains `subclassName`.</span></span> <span data-ttu-id="c672a-116">경우 `subclassName` 점 (.) 지정 된 `subclassNamespace` 및 `subclassName`합니다.</span><span class="sxs-lookup"><span data-stu-id="c672a-116">If `subclassName` is specified, a dot (.) separates `subclassNamespace` and `subclassName`.</span></span>|  
|`subclassName`|<span data-ttu-id="c672a-117">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="c672a-117">Required.</span></span> <span data-ttu-id="c672a-118">하위 클래스의 CLR 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c672a-118">Specifies the CLR name of the subclass.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="c672a-119">종속성</span><span class="sxs-lookup"><span data-stu-id="c672a-119">Dependencies</span></span>  
 <span data-ttu-id="c672a-120">[X:class 지시문](../../../docs/framework/xaml-services/x-class-directive.md) 동일한 개체에도 제공 해야 하며 해당 개체에는 XAML 프로덕션의 루트 요소 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672a-120">[x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md) must also be provided on the same object, and that object must be the root element of the XAML production.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c672a-121">설명</span><span class="sxs-lookup"><span data-stu-id="c672a-121">Remarks</span></span>  
 <span data-ttu-id="c672a-122">`x:Subclass`부분 클래스 선언만 지원 하지 않는 언어에 대 한 사용 현황 주로 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c672a-122">`x:Subclass` usage is primarily intended for languages that do not support partial class declarations.</span></span>  
  
 <span data-ttu-id="c672a-123">로 사용 되는 클래스는 `x:Subclass` 중첩된 클래스일 수 없습니다 및 `x:Subclass` "종속성" 섹션에 설명 된 대로 루트 개체를 참조 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672a-123">The class used as the `x:Subclass` cannot be a nested class, and `x:Subclass` must refer to the root object as explained in the "Dependencies" section.</span></span>  
  
 <span data-ttu-id="c672a-124">그렇지 않은 경우의 개념적 의미 `x:Subclass` .NET Framework XAML 서비스 구현으로 정의 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c672a-124">Otherwise, the conceptual meaning of `x:Subclass` is undefined by a .NET Framework XAML Services implementation.</span></span> <span data-ttu-id="c672a-125">즉,.NET Framework XAML 서비스 동작이 있는 xaml 태그 및 코드를 백업 합니다. 연결 된 전체 프로그래밍 모델을 지정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c672a-125">This is because .NET Framework XAML Services behavior does not specify the overall programming model by which XAML markup and backing code are connected.</span></span> <span data-ttu-id="c672a-126">와 관련 된 추가 개념 구현 `x:Class` 및 `x:Subclass` 프로그래밍 모델 또는 응용 프로그램 모델을 사용 하 여 XAML 태그, 컴파일된 태그 및 코드 숨김을 CLR 기반 연결 하는 방법을 정의 하는 특정 프레임 워크에 의해 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c672a-126">Implementations of further concepts related to `x:Class` and `x:Subclass` are performed by specific frameworks that use programming models or application models to define how to connect XAML markup, compiled markup, and CLR-based code-behind.</span></span> <span data-ttu-id="c672a-127">각 프레임에는 동작 또는 빌드 환경에 포함 해야 하는 특정 구성 요소 중 일부를 사용 하는 자체 빌드 작업이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c672a-127">Each framework might have its own build actions that enable some of the behavior, or specific components that must be included in the build environment.</span></span> <span data-ttu-id="c672a-128">프레임 워크 내에서 빌드 작업 이면의 코드에 사용 되는 특정 CLR 언어에 따라 다 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c672a-128">Within a framework, build actions can also vary based on the specific CLR language that is used for the code-behind.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="c672a-129">WPF 사용 정보</span><span class="sxs-lookup"><span data-stu-id="c672a-129">WPF Usage Notes</span></span>  
 <span data-ttu-id="c672a-130">`x:Subclass`페이지 루트 또는 가능는 <xref:System.Windows.Application> 이미 있는 응용 프로그램 정의에 루트 `x:Class`합니다.</span><span class="sxs-lookup"><span data-stu-id="c672a-130">`x:Subclass` can be on a page root or on the <xref:System.Windows.Application> root in the application definition, which already has `x:Class`.</span></span> <span data-ttu-id="c672a-131">선언 `x:Subclass` 페이지나 응용 프로그램 루트 또는 없는 위치에서 지정 이외의 모든 요소에 대해 `x:Class` 존재, 컴파일 타임 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672a-131">Declaring `x:Subclass` on any element other than a page or application root, or specifying it where no `x:Class` exists, causes a compile-time error.</span></span>  
  
 <span data-ttu-id="c672a-132">파생 클래스를 만드는 올바르게 동작 하는 `x:Subclass` 시나리오는 매우 복잡 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672a-132">Creating derived classes that work correctly for the `x:Subclass` scenario is fairly complex.</span></span> <span data-ttu-id="c672a-133">중간 파일 (.g 태그 컴파일 이름이.xaml 파일 이름을 통합 하 여 프로젝트의 obj 폴더에 생성 된 파일)을 검사 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672a-133">You might need to examine the intermediate files (the .g files produced in the obj folder of your project by markup compile, with names that incorporate the .xaml file names).</span></span> <span data-ttu-id="c672a-134">이러한 중간 파일의 컴파일된 응용 프로그램에 결합된 된 partial 클래스 프로그래밍 구문의 출처를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c672a-134">These intermediate files can help you determine the origin of certain programming constructs in the joined partial classes in the compiled application.</span></span>  
  
 <span data-ttu-id="c672a-135">파생된 클래스에서 이벤트 처리기 해야 `internal override` (`Friend Overrides` 에 [!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)]) 컴파일하는 동안 중간 클래스에서 생성 되는 처리기에 대 한 스텁의 재정의 하기 위해.</span><span class="sxs-lookup"><span data-stu-id="c672a-135">Event handlers in the derived class must be `internal override` (`Friend Overrides` in [!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)]) in order to override the stubs for the handlers as created in the intermediate class during compilation.</span></span> <span data-ttu-id="c672a-136">그렇지 않으면 파생된 클래스 구현은 숨기고 중간 클래스 구현 및 중간 클래스 처리기가 호출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c672a-136">Otherwise, the derived class implementations hide (shadow) the intermediate class implementation and the intermediate class handlers are not invoked.</span></span>  
  
 <span data-ttu-id="c672a-137">둘 다 정의 하는 경우 `x:Class` 및 `x:Subclass`에서 참조 되는 클래스에 대 한 구현을 제공할 필요가 없습니다 `x:Class`합니다.</span><span class="sxs-lookup"><span data-stu-id="c672a-137">When you define both `x:Class` and `x:Subclass`, you do not need to provide any implementation for the class that is referenced by `x:Class`.</span></span> <span data-ttu-id="c672a-138">통해 이름을 지정 하기만 하면는 `x:Class` 특성 컴파일러 중간 파일 (컴파일러 선택 하지 못하는 기본 이름이 경우)에 생성 된 클래스에 대 한 몇 가지 지침을 갖도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c672a-138">You only need to give it a name via the `x:Class` attribute so that the compiler has some guidance for the class that it creates in the intermediate files (the compiler does not select a default name in this case).</span></span> <span data-ttu-id="c672a-139">제공할 수 있습니다는 `x:Class` 구현 클래스 이며 이때는 둘 다를 사용 하는 일반적인 시나리오 `x:Class` 및 `x:Subclass`합니다.</span><span class="sxs-lookup"><span data-stu-id="c672a-139">You can give the `x:Class` class an implementation; however, this is not the typical scenario for using both `x:Class` and `x:Subclass`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c672a-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c672a-140">See Also</span></span>  
 [<span data-ttu-id="c672a-141">x:Class 지시문</span><span class="sxs-lookup"><span data-stu-id="c672a-141">x:Class Directive</span></span>](../../../docs/framework/xaml-services/x-class-directive.md)  
 [<span data-ttu-id="c672a-142">WPF에 대한 XAML 및 사용자 지정 클래스</span><span class="sxs-lookup"><span data-stu-id="c672a-142">XAML and Custom Classes for WPF</span></span>](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
