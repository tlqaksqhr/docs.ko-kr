---
title: "x:FactoryMethod 지시문"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
caps.latest.revision: "8"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 0d53db49961c2a75e4547f6b57240cefd2cc17c3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="xfactorymethod-directive"></a><span data-ttu-id="f3e0c-102">x:FactoryMethod 지시문</span><span class="sxs-lookup"><span data-stu-id="f3e0c-102">x:FactoryMethod Directive</span></span>
<span data-ttu-id="f3e0c-103">XAML 프로세서는 지원 형식 해결 한 후 개체를 초기화 하는 데 사용 해야 하는 생성자가 아닌 다른 방법을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0c-103">Specifies a method other than a constructor that a XAML processor should use to initialize an object after resolving its backing type.</span></span>  
  
## <a name="xaml-attribute-usage-no-xarguments"></a><span data-ttu-id="f3e0c-104">XAML 특성 사용, x: 인수</span><span class="sxs-lookup"><span data-stu-id="f3e0c-104">XAML Attribute Usage, no x:Arguments</span></span>  
  
```  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a><span data-ttu-id="f3e0c-105">XAML 특성 사용, x: 요소와 인수</span><span class="sxs-lookup"><span data-stu-id="f3e0c-105">XAML Attribute Usage, x:Arguments as Element(s)</span></span>  
  
```  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="f3e0c-106">XAML 값</span><span class="sxs-lookup"><span data-stu-id="f3e0c-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`methodname`|<span data-ttu-id="f3e0c-107">XAML 프로세서 호출로 지정 된 인스턴스를 초기화 하는 메서드의 문자열 메서드 이름을 `object`합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0c-107">The string method name of a method that XAML processors call to initialize the instance specified as `object`.</span></span> <span data-ttu-id="f3e0c-108">설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3e0c-108">See Remarks.</span></span>|  
|`oneOrMoreObjectElements`|<span data-ttu-id="f3e0c-109">팩터리 메서드 매개 변수를 지정 하는 개체에 대 한 하나 이상의 개체 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0c-109">One or more object elements for objects that specify factory method parameters.</span></span> <span data-ttu-id="f3e0c-110">순서는 중요 하지 않습니다. 인수는 팩터리 메서드에 전달 해야 하는 순서를 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0c-110">Order is significant; it signifies the order in which arguments should be passed to the factory method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3e0c-111">설명</span><span class="sxs-lookup"><span data-stu-id="f3e0c-111">Remarks</span></span>  
 <span data-ttu-id="f3e0c-112">경우 `methodname` 는 인스턴스 메서드이므로 정규화 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0c-112">If `methodname` is an instance method, it cannot be qualified.</span></span>  
  
 <span data-ttu-id="f3e0c-113">정적 메서드는 팩터리 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0c-113">Static methods as factory methods are supported.</span></span> <span data-ttu-id="f3e0c-114">경우 `methodname` 정적 메서드입니다 `methodname` 으로 제공 되는 *typeName*. *methodName* 조합, 여기서 *typeName* 정적 팩터리 메서드를 정의 하는 클래스의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0c-114">If `methodname` is a static method, `methodname` is provided as a *typeName*.*methodName* combination, where *typeName* names the class that defines the static factory method.</span></span> <span data-ttu-id="f3e0c-115">*typeName* 접두사로 한정 된 형식에 매핑된 xmlns 참조 하는 경우 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0c-115">*typeName* can be prefix-qualified if referring to a type in a mapped xmlns.</span></span> <span data-ttu-id="f3e0c-116">*typeName* 와 다른 type 수 `typeof(``object``)`합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0c-116">*typeName* can be a different type than `typeof(``object``)`.</span></span>  
  
 <span data-ttu-id="f3e0c-117">팩터리 메서드는 관련 개체 요소를 지 원하는 형식의 선언된 된 공용 메서드가 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0c-117">The factory method must be a declared public method of the type that backs the relevant object element.</span></span>  
  
 <span data-ttu-id="f3e0c-118">팩터리 메서드는 관련 개체에 할당 될 수 있는 인스턴스를 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0c-118">The factory method must return an instance that is assignable to the relevant object.</span></span> <span data-ttu-id="f3e0c-119">팩터리 메서드가 null을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0c-119">Factory methods should never return null.</span></span>  
  
 <span data-ttu-id="f3e0c-120">`x:Arguments`팩터리 메서드의 시그니처에 가장 일치 하는 원칙에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0c-120">`x:Arguments` operates on a principle of best match for signatures of factory methods.</span></span> <span data-ttu-id="f3e0c-121">일치 하는 매개 변수 개수를 먼저 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0c-121">Matching evaluates the parameter count first.</span></span> <span data-ttu-id="f3e0c-122">매개 변수 개수에 대 한 가능한 일치 항목을 여러 개 있으면 계산 되 고 가장 일치 하는 다음 매개 변수 유형이입니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0c-122">If there is more than one possible match for a parameter count, parameter type is then evaluated and best match is determined.</span></span> <span data-ttu-id="f3e0c-123">이 평가 단계 이후에 모호성도 지 XAML 프로세서 동작이 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0c-123">If there is still ambiguity after this phase of evaluation, XAML processor behavior is undefined.</span></span>  
  
 <span data-ttu-id="f3e0c-124">`x:FactoryMethod` 지시문 태그가 포함 된 개체 요소 형식을 참조 하지 않기 때문에 요소 사용이 일반적인 의미에서 속성 요소 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0c-124">The `x:FactoryMethod` element usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="f3e0c-125">예상 하지만 해당 요소의 사용 특성 사용 보다 일반적이 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0c-125">It is expected that element usage is less common than attribute usage.</span></span> <span data-ttu-id="f3e0c-126">`x:Arguments`(특성 또는 요소 사용)와 함께 사용할 수 있습니다 `x:FactoryMethod` 요소를 사용 하지만이 특별히에 표시 되지 않으면 Usage 섹션.</span><span class="sxs-lookup"><span data-stu-id="f3e0c-126">`x:Arguments` (either attribute or element usage) can be used along with `x:FactoryMethod` element usage, but this is not specifically shown in the Usage sections.</span></span>  
  
 <span data-ttu-id="f3e0c-127">`x:FactoryMethod`요소는 다른 속성 요소의 앞에 야, 대로 앞에 야 모든 `x:Arguments` 도 요소로 제공 되며 모든 콘텐츠/내부 텍스트/초기화 텍스트 앞에 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3e0c-127">`x:FactoryMethod` as an element must precede any other property elements, must precede any `x:Arguments` also provided as elements, and must precede any content/inner text/initialization text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3e0c-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f3e0c-128">See Also</span></span>  
 [<span data-ttu-id="f3e0c-129">x:Arguments 지시문</span><span class="sxs-lookup"><span data-stu-id="f3e0c-129">x:Arguments Directive</span></span>](../../../docs/framework/xaml-services/x-arguments-directive.md)
