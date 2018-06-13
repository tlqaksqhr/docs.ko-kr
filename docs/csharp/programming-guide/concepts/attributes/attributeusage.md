---
title: AttributeUsage(C#)
ms.date: 04/25/2018
ms.openlocfilehash: 869e6509e55268767915a783a8652f7f950d7137
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2018
ms.locfileid: "33955930"
---
# <a name="attributeusage-c"></a><span data-ttu-id="db1ee-102">AttributeUsage(C#)</span><span class="sxs-lookup"><span data-stu-id="db1ee-102">AttributeUsage (C#)</span></span>

<span data-ttu-id="db1ee-103">사용자 지정 특성 클래스를 사용하는 방법을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="db1ee-103">Determines how a custom attribute class can be used.</span></span> <span data-ttu-id="db1ee-104"><xref:System.AttributeUsageAttribute>는 사용자 지정 특성 정의에 적용되는 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="db1ee-104"><xref:System.AttributeUsageAttribute> is an attribute you apply to custom attribute definitions.</span></span> <span data-ttu-id="db1ee-105">`AttributeUsage` 특성을 사용하면 다음을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db1ee-105">The `AttributeUsage` attribute enables you to control:</span></span>

- <span data-ttu-id="db1ee-106">적용할 수 있는 프로그램 요소 특성</span><span class="sxs-lookup"><span data-stu-id="db1ee-106">Which program elements attribute may be applied to.</span></span> <span data-ttu-id="db1ee-107">사용을 제한하지 않으면 다음과 같은 프로그램 요소 중 하나에 특성이 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db1ee-107">Unless you restrict is usage, an attribute may be applied to any of the following program elements:</span></span>
  - <span data-ttu-id="db1ee-108">어셈블리</span><span class="sxs-lookup"><span data-stu-id="db1ee-108">assembly</span></span>
  - <span data-ttu-id="db1ee-109">name</span><span class="sxs-lookup"><span data-stu-id="db1ee-109">module</span></span>
  - <span data-ttu-id="db1ee-110">필드(field)</span><span class="sxs-lookup"><span data-stu-id="db1ee-110">field</span></span>
  - <span data-ttu-id="db1ee-111">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="db1ee-111">event</span></span>
  - <span data-ttu-id="db1ee-112">메서드</span><span class="sxs-lookup"><span data-stu-id="db1ee-112">method</span></span>
  - <span data-ttu-id="db1ee-113">param</span><span class="sxs-lookup"><span data-stu-id="db1ee-113">param</span></span>
  - <span data-ttu-id="db1ee-114">속성</span><span class="sxs-lookup"><span data-stu-id="db1ee-114">property</span></span>
  - <span data-ttu-id="db1ee-115">return</span><span class="sxs-lookup"><span data-stu-id="db1ee-115">return</span></span>
  - <span data-ttu-id="db1ee-116">type</span><span class="sxs-lookup"><span data-stu-id="db1ee-116">type</span></span>
- <span data-ttu-id="db1ee-117">특성을 단일 프로그램 요소에 여러 번 적용할 수 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="db1ee-117">Whether an attribute can be applied to a single program element multiple times.</span></span>
- <span data-ttu-id="db1ee-118">특성이 파생 클래스에 의해 상속되는지 여부</span><span class="sxs-lookup"><span data-stu-id="db1ee-118">Whether attributes are inherited by derived classes.</span></span>

<span data-ttu-id="db1ee-119">명시적으로 적용될 경우 기본 설정은 다음 예제와 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="db1ee-119">The default settings look like the following example when applied explicitly:</span></span>

[!code-csharp[Define a new attribute](../../../../../samples/snippets/csharp/attributes/NewAttribute.cs#1)]

<span data-ttu-id="db1ee-120">이 예제에서 `NewAttribute` 클래스는 모든 지원되는 프로그램 요소에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db1ee-120">In this example, the `NewAttribute` class can be applied to any supported program element.</span></span> <span data-ttu-id="db1ee-121">하지만 각 엔터티에 한 번만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db1ee-121">But it can be applied only once to each entity.</span></span> <span data-ttu-id="db1ee-122">이 특성은 기본 클래스에 적용될 때 파생 클래스에 의해 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="db1ee-122">The attribute is inherited by derived classes when applied to a base class.</span></span>

<span data-ttu-id="db1ee-123"><xref:System.AttributeUsageAttribute.AllowMultiple> 및 <xref:System.AttributeUsageAttribute.Inherited> 인수는 선택 사항이므로 다음 코드에 미치는 영향은 같습니다.</span><span class="sxs-lookup"><span data-stu-id="db1ee-123">The <xref:System.AttributeUsageAttribute.AllowMultiple> and <xref:System.AttributeUsageAttribute.Inherited> arguments are optional, so the following code has the same effect:</span></span>

[!code-csharp[Omit optional attributes](../../../../../samples/snippets/csharp/attributes/NewAttribute.cs#2)]

<span data-ttu-id="db1ee-124">첫 번째 <xref:System.AttributeUsageAttribute> 인수는 <xref:System.AttributeTargets> 열거형의 요소가 하나 이상이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="db1ee-124">The first <xref:System.AttributeUsageAttribute> argument must be one or more elements of the <xref:System.AttributeTargets> enumeration.</span></span> <span data-ttu-id="db1ee-125">다음 예제와 같이 OR 연산자를 사용하여 여러 대상 형식을 함께 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db1ee-125">Multiple target types can be linked together with the OR operator, like the following example shows:</span></span>

[!code-csharp[Create an attribute for fields or properties](../../../../../samples/snippets/csharp/attributes/NewPropertyOrFieldAttribute.cs#1)]

<span data-ttu-id="db1ee-126">C# 7.3부터 특성은 속성 또는 자동 구현 속성의 지원 필드에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db1ee-126">Beginning in C# 7.3, attributes can be applied to either the property or the backing field for an auto-implemented property.</span></span> <span data-ttu-id="db1ee-127">특성에 `field` 지정자를 지정하지 않으면 특성이 속성에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="db1ee-127">The attribute applies to the property, unless you specify the `field` specifier on the attribute.</span></span> <span data-ttu-id="db1ee-128">모두 다음 예제에서 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="db1ee-128">Both are shown in the following example:</span></span>

[!code-csharp[Create an attribute for fields or properties](../../../../../samples/snippets/csharp/attributes/NewPropertyOrFieldAttribute.cs#2)]

<span data-ttu-id="db1ee-129"><xref:System.AttributeUsageAttribute.AllowMultiple> 인수가 `true`인 경우 다음 예제와 같이 결과 특성을 단일 엔터티에 두 번 이상 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db1ee-129">If the <xref:System.AttributeUsageAttribute.AllowMultiple> argument is `true`, then the resulting attribute can be applied more than once to a single entity, as shown in the following example:</span></span>

[!code-csharp[Create and use an attribute that can be applied multiple times](../../../../../samples/snippets/csharp/attributes/MultiUseAttribute.cs#1)]

<span data-ttu-id="db1ee-130">이 경우 `AllowMultiple`이 `true`로 설정되므로 `MultiUseAttribute`를 반복적으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db1ee-130">In this case, `MultiUseAttribute` can be applied repeatedly because `AllowMultiple` is set to `true`.</span></span> <span data-ttu-id="db1ee-131">여러 특성을 적용하기 위해 표시된 두 형식이 모두 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="db1ee-131">Both formats shown for applying multiple attributes are valid.</span></span>

<span data-ttu-id="db1ee-132"><xref:System.AttributeUsageAttribute.Inherited>이 `false`인 경우 특성은 특성 클래스에서 파생된 클래스에서 상속하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db1ee-132">If <xref:System.AttributeUsageAttribute.Inherited> is `false`, then the attribute isn't inherited by classes derived from an attributed class.</span></span> <span data-ttu-id="db1ee-133">예:</span><span class="sxs-lookup"><span data-stu-id="db1ee-133">For example:</span></span>

[!code-csharp[Create and use an attribute that can be applied multiple times](../../../../../samples/snippets/csharp/attributes/NonInheritedAttribute.cs#1)]

<span data-ttu-id="db1ee-134">이 경우에 `NonInheritedAttribute`은 상속을 통해 `DClass`에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db1ee-134">In this case `NonInheritedAttribute` isn't applied to `DClass` via inheritance.</span></span>

## <a name="remarks"></a><span data-ttu-id="db1ee-135">설명</span><span class="sxs-lookup"><span data-stu-id="db1ee-135">Remarks</span></span>

<span data-ttu-id="db1ee-136">`AttributeUsage` 특성은 단일 사용 특성입니다. 같은 클래스에 두 번 이상 적용될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="db1ee-136">The `AttributeUsage` attribute is a single-use attribute--it can't be applied more than once to the same class.</span></span> <span data-ttu-id="db1ee-137">`AttributeUsage`는 <xref:System.AttributeUsageAttribute>의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="db1ee-137">`AttributeUsage` is an alias for <xref:System.AttributeUsageAttribute>.</span></span>

<span data-ttu-id="db1ee-138">자세한 내용은 [리플렉션을 사용하여 특성 액세스(C#)](accessing-attributes-by-using-reflection.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="db1ee-138">For more information, see [Accessing Attributes by Using Reflection (C#)](accessing-attributes-by-using-reflection.md).</span></span>

## <a name="example"></a><span data-ttu-id="db1ee-139">예</span><span class="sxs-lookup"><span data-stu-id="db1ee-139">Example</span></span>

<span data-ttu-id="db1ee-140">다음 예제에서는 <xref:System.AttributeUsageAttribute> 특성에 대한 <xref:System.AttributeUsageAttribute.Inherited> 및 <xref:System.AttributeUsageAttribute.AllowMultiple>의 영향과 클래스에 적용되는 사용자 지정 특성을 열거하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="db1ee-140">The following example demonstrates the effect of the <xref:System.AttributeUsageAttribute.Inherited> and <xref:System.AttributeUsageAttribute.AllowMultiple> arguments to the <xref:System.AttributeUsageAttribute> attribute, and how the custom attributes applied to a class can be enumerated.</span></span>

[!code-csharp[Applying and querying attributes](../../../../../samples/snippets/csharp/attributes/Program.cs#1)]

## <a name="sample-output"></a><span data-ttu-id="db1ee-141">샘플 출력</span><span class="sxs-lookup"><span data-stu-id="db1ee-141">Sample Output</span></span>

```text
Attributes on Base Class:
FirstAttribute
SecondAttribute
Attributes on Derived Class:
ThirdAttribute
ThirdAttribute
SecondAttribute
```

## <a name="see-also"></a><span data-ttu-id="db1ee-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="db1ee-142">See Also</span></span>
 <xref:System.Attribute>  
 <xref:System.Reflection>  
 [<span data-ttu-id="db1ee-143">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="db1ee-143">C# Programming Guide</span></span>](../..//index.md)  
 [<span data-ttu-id="db1ee-144">특성</span><span class="sxs-lookup"><span data-stu-id="db1ee-144">Attributes</span></span>](../../../..//standard/attributes/index.md)  
 [<span data-ttu-id="db1ee-145">리플렉션(C#)</span><span class="sxs-lookup"><span data-stu-id="db1ee-145">Reflection (C#)</span></span>](../reflection.md)  
 [<span data-ttu-id="db1ee-146">특성</span><span class="sxs-lookup"><span data-stu-id="db1ee-146">Attributes</span></span>](index.md)  
 [<span data-ttu-id="db1ee-147">사용자 지정 특성 만들기(C#)</span><span class="sxs-lookup"><span data-stu-id="db1ee-147">Creating Custom Attributes (C#)</span></span>](creating-custom-attributes.md)  
 [<span data-ttu-id="db1ee-148">리플렉션을 사용하여 특성 액세스(C#)</span><span class="sxs-lookup"><span data-stu-id="db1ee-148">Accessing Attributes by Using Reflection (C#)</span></span>](accessing-attributes-by-using-reflection.md)
