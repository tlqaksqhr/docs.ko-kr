---
title: "x:Arguments 지시문"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
caps.latest.revision: "12"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bb1f5986a0d9f9eb69ade0228925ec06164cee4d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="xarguments-directive"></a><span data-ttu-id="751b6-102">x:Arguments 지시문</span><span class="sxs-lookup"><span data-stu-id="751b6-102">x:Arguments Directive</span></span>
<span data-ttu-id="751b6-103">패키지 생성 인수 XAML에서 기본값이 아닌 생성자 개체 요소 선언에 대 한 또는 팩터리 메서드 개체 선언에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="751b6-103">Packages construction arguments for a non-default constructor object element declaration in XAML, or for a factory method object declaration.</span></span>  
  
## <a name="xaml-element-usage-nondefault-constructor"></a><span data-ttu-id="751b6-104">XAML 요소 사용 (기본이 아닌 생성자)</span><span class="sxs-lookup"><span data-stu-id="751b6-104">XAML Element Usage (Nondefault constructor)</span></span>  
  
```  
<object ...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-element-usage-factory-method"></a><span data-ttu-id="751b6-105">XAML 요소 사용 (factory method)</span><span class="sxs-lookup"><span data-stu-id="751b6-105">XAML Element Usage (factory method)</span></span>  
  
```  
<object x:FactoryMethod="methodName"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="751b6-106">XAML 값</span><span class="sxs-lookup"><span data-stu-id="751b6-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`oneOrMoreObjectElements`|<span data-ttu-id="751b6-107">백업 기본이 아닌 생성자 또는 팩터리 메서드에 전달 될 인수를 지정 하는 하나 이상의 개체 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="751b6-107">One or more object elements that specify arguments to be passed to the backing non-default constructor or factory method.</span></span><br /><br /> <span data-ttu-id="751b6-108">일반적인 사용법 실제 인수 값을 지정 하려면 개체 요소 내의 초기화 텍스트를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="751b6-108">Typical usage is to use initialization text within the object elements to specify the actual argument values.</span></span> <span data-ttu-id="751b6-109">예 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="751b6-109">See Examples section.</span></span><br /><br /> <span data-ttu-id="751b6-110">요소의 순서는 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="751b6-110">The order of the elements is significant.</span></span> <span data-ttu-id="751b6-111">순서로 XAML 형식과 형식과 일치 하 고 지원 생성자 또는 팩터리 메서드 오버 로드의 순서를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="751b6-111">The XAML types in order must match the types and type order of the backing constructor or factory method overload.</span></span>|  
|`methodName`|<span data-ttu-id="751b6-112">처리 해야 하는 팩터리 메서드 이름 `x:Arguments` 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="751b6-112">The name of the factory method that should process any `x:Arguments` arguments.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="751b6-113">종속성</span><span class="sxs-lookup"><span data-stu-id="751b6-113">Dependencies</span></span>  
 <span data-ttu-id="751b6-114">`x:FactoryMethod`범위 및 동작을 수정할 수 있는 `x:Arguments` 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="751b6-114">`x:FactoryMethod` can modify the scope and behavior where `x:Arguments` applies.</span></span>  
  
 <span data-ttu-id="751b6-115">없는 경우 `x:FactoryMethod` 지정 된 `x:Arguments` 지원 생성자의 대체 (비기본) 시그니처에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="751b6-115">If no `x:FactoryMethod` is specified, `x:Arguments` applies to alternate (non-default) signatures of the backing constructors.</span></span>  
  
 <span data-ttu-id="751b6-116">경우 `x:FactoryMethod` 지정 된 `x:Arguments` 명명 된 메서드의 오버 로드에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="751b6-116">If `x:FactoryMethod` is specified, `x:Arguments` applies to an overload of the named method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="751b6-117">설명</span><span class="sxs-lookup"><span data-stu-id="751b6-117">Remarks</span></span>  
 <span data-ttu-id="751b6-118">XAML 2006 기본이 아닌 초기화 초기화 텍스트를 통해 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="751b6-118">XAML 2006 can support non-default initialization through initialization text.</span></span> <span data-ttu-id="751b6-119">하지만 실용적인 응용 프로그램의 초기화 텍스트 생성 방법이 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="751b6-119">However, the practical application of an initialization text construction technique is limited.</span></span> <span data-ttu-id="751b6-120">초기화 텍스트를 단일 텍스트 문자열로 취급 됩니다. 따라서만 사용자 지정 정보 항목 및 사용자 지정 구분 기호 문자열에서을 구문 분석할 수 있는 구성 동작에 대 한 형식 변환기를 정의 하지 않으면 단일 매개 변수 초기화에 대 한 기능을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="751b6-120">Initialization text is treated as a single text string; therefore, it only adds capability for a single parameter initialization unless a type converter is defined for the construction behavior that can parse custom information items and custom delimiters from the string.</span></span> <span data-ttu-id="751b6-121">또한 개체 논리에 텍스트 문자열은 잠재적으로 실제 문자열 이외의 기본 형식을 처리 하기 위한 특정된 XAML 파서에 네이티브 기본 형식 변환기입니다.</span><span class="sxs-lookup"><span data-stu-id="751b6-121">Also, the text string to object logic is potentially a given XAML parser's native default type converter for handling primitives other than a true string.</span></span>  
  
 <span data-ttu-id="751b6-122">`x:Arguments` 지시문 태그가 포함 된 개체 요소 형식을 참조 하지 않기 때문에 XAML 사용은 일반적으로 속성 요소 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="751b6-122">The `x:Arguments` XAML usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="751b6-123">와 같은 기타 지시문과 더 비슷합니다는 `x:Code` 요소는 자식 내용에 대 한 기본값 이외의 다른 태그를 해석 하는 범위 기본값과입니다.</span><span class="sxs-lookup"><span data-stu-id="751b6-123">It is more akin to other directives such as `x:Code` where the element demarks a range in which the markup should be interpreted as other than the default for child contents.</span></span> <span data-ttu-id="751b6-124">각 개체 요소의 XAML 형식을 특정 생성자 팩터리 메서드 서명을 확인 하려면 XAML 파서가에 사용 되는 인수 형식에 대 한 정보를 전달 하는 경우에 `x:Arguments` 사용은 참조 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="751b6-124">In this case, the XAML type of each object element communicates information about the argument types, which is used by XAML parsers to determine which specific constructor factory method signature an `x:Arguments` usage is attempting to reference.</span></span>  
  
 <span data-ttu-id="751b6-125">`x:Arguments`개체 요소에 대해 생성 되 고 앞에 야 다른 속성 요소, 콘텐츠, 내부 텍스트 또는 object 요소의 초기화 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="751b6-125">`x:Arguments` for an object element being constructed must precede any other property elements, content, inner text, or initialization strings of the object element.</span></span> <span data-ttu-id="751b6-126">내에서 개체 요소 `x:Arguments` XAML 형식 및 해당 지원 생성자 또는 팩터리 메서드에에 허용 된 대로 특성 및 초기화 문자열을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="751b6-126">The object elements within `x:Arguments` can include attributes and initialization strings, as permitted by that XAML type and its backing constructor or factory method.</span></span> <span data-ttu-id="751b6-127">개체 또는 인수에 대 한 사용자 지정 XAML 형식 또는 벗어나는 기본 XAML 네임 스페이스 설정 된 접두사 매핑을 참조 하 여 XAML 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="751b6-127">For either the object or the arguments, you can specify custom XAML types or XAML types that are otherwise outside the default XAML namespace by referencing established prefix mappings.</span></span>  
  
 <span data-ttu-id="751b6-128">인수에 지정 하는 방법을 확인 하려면 다음 지침을 사용 하는 XAML 프로세서 `x:Arguments` 개체를 생성 하는 데 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="751b6-128">XAML processors use the following guidelines to determine how the arguments specified in `x:Arguments` should be used to construct an object.</span></span> <span data-ttu-id="751b6-129">경우 `x:FactoryMethod` 정보를 비교 하는 지정 된 지정 된 `x:FactoryMethod` (사항에 유의 값 `x:FactoryMethod` 메서드 이름 및 명명 된 메서드 오버 로드를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="751b6-129">If `x:FactoryMethod` is specified, information is compared to the specified `x:FactoryMethod` (note that the value of `x:FactoryMethod` is the method name, and the named method can have overloads.</span></span> <span data-ttu-id="751b6-130">경우 `x:FactoryMethod` 를 지정 하지 않으면 정보 개체의 모든 public 생성자 오버 로드 집합이 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="751b6-130">If `x:FactoryMethod` is not specified, information is compared to the set of all public constructor overloads of the object.</span></span> <span data-ttu-id="751b6-131">다음 XAML 처리 논리 매개 변수 개수를 비교 하 고 일치 하는 인자 수를 갖는 오버 로드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="751b6-131">XAML processing logic then compares the number of parameters and selects the overload with matching arity.</span></span> <span data-ttu-id="751b6-132">둘 이상의 일치 하는 XAML 프로세서는 유형의 제공 된 개체 요소의 XAML 유형을 기반으로 하는 매개 변수를 비교 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="751b6-132">If there is more than one match, the XAML processor should compare the types of the parameters based on the XAML types of the provided object elements.</span></span> <span data-ttu-id="751b6-133">여전히 둘 이상의 일치 하는 XAML 프로세서 동작이 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="751b6-133">If there is still more than one match, the XAML processor behavior is undefined.</span></span> <span data-ttu-id="751b6-134">경우는 `x:FactoryMethod` 지정는 메서드를 확인할 수 있지만, XAML 프로세서에서 예외를 throw 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="751b6-134">If a `x:FactoryMethod` is specified but the method cannot be resolved, a XAML processor should throw an exception.</span></span>  
  
 <span data-ttu-id="751b6-135">XAML 특성 사용 `<x:Arguments>string</x:Arguments>` 은 기술적으로 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="751b6-135">A XAML attribute usage `<x:Arguments>string</x:Arguments>` is technically possible.</span></span> <span data-ttu-id="751b6-136">그러나 그렇지 않은 경우 초기화 텍스트 및 형식 변환기를 통해 수행할 수 초과 기능은 제공 하 고이 구문을 사용 하 여는 XAML 2009 팩터리 메서드 기능의 디자인 의도 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="751b6-136">However, this provides no capabilities beyond what could be done otherwise through initialization text and type converters, and using this syntax is not the design intention of the XAML 2009 factory method features.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="751b6-137">예제</span><span class="sxs-lookup"><span data-stu-id="751b6-137">Examples</span></span>  
 <span data-ttu-id="751b6-138">다음 예제에서는 시그니처를 다음의 XAML 사용에 기본이 아닌 생성자를 보여 줍니다 `x:Arguments` 서명에 액세스 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="751b6-138">The following example shows a non-default constructor signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>  
  
```csharp  
public class Food {  
    private string _name;  
    private Int32 _calories;  
    public Food(string name, Int32 calories) {  
        _name=name;  
        _calories=calories;  
    }  
}  
```  
  
```xaml  
<my:Food>  
    <x:Arguments>  
        <x:String>Apple</x:String>  
        <x:Int32>150</x:Int32>  
    </x:Arguments>  
</my:Food>  
```  
  
 <span data-ttu-id="751b6-139">다음 예제에서는 대상 팩터리 메서드 시그니처를 다음의 XAML 사용 `x:Arguments` 서명에 액세스 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="751b6-139">The following example shows a target factory method signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>  
  
```csharp  
public Food TryLookupFood(string name)  
{  
  switch (name) {  
    case "Apple": return new Food("Apple",150);  
    case "Chocolate": return new Food("Chocolate",200);  
    case "Cheese": return new Food("Cheese", 450);  
    default: {return new Food(name,0);  
  }  
}  
```  
  
```xaml  
<my:Food x:FactoryMethod="TryLookupFood">  
    <x:Arguments>  
        <x:String>Apple</x:String>  
    </x:Arguments>  
</my:Food>  
```  
  
## <a name="see-also"></a><span data-ttu-id="751b6-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="751b6-140">See Also</span></span>  
 [<span data-ttu-id="751b6-141">.NET Framework XAML 서비스에서 사용할 사용자 지정 형식 정의</span><span class="sxs-lookup"><span data-stu-id="751b6-141">Defining Custom Types for Use with .NET Framework XAML Services</span></span>](../../../docs/framework/xaml-services/defining-custom-types-for-use-with-net-framework-xaml-services.md)  
 [<span data-ttu-id="751b6-142">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="751b6-142">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
