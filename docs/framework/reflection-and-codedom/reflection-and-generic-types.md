---
title: "리플렉션 및 제네릭 형식"
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
- generics [.NET Framework], reflection emit
- reflection emit, generic types
- reflection, generic types
- type arguments
- generics [.NET Framework], reflection
- viewing type information
- type information, viewing
- types, generic
- type parameters
ms.assetid: f7180fc5-dd41-42d4-8a8e-1b34288e06de
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2c6ace8f34999a6d98fc6784dd21ce88baf2af42
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="reflection-and-generic-types"></a><span data-ttu-id="f09d6-102">리플렉션 및 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="f09d6-102">Reflection and Generic Types</span></span>
<a name="top"></a> <span data-ttu-id="f09d6-103">리플렉션의 관점에서 제네릭 형식과 일반 형식 간 차이점은 제네릭 형식이 형식 매개 변수(제네릭 형식 정의인 경우) 또는 형식 인수(생성된 형식인 경우)의 집합과 연결되어 있다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-103">From the point of view of reflection, the difference between a generic type and an ordinary type is that a generic type has associated with it a set of type parameters (if it is a generic type definition) or type arguments (if it is a constructed type).</span></span> <span data-ttu-id="f09d6-104">제네릭 메서드는 동일한 방식으로 일반 메서드와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-104">A generic method differs from an ordinary method in the same way.</span></span>  
  
 <span data-ttu-id="f09d6-105">다음과 같이 리플렉션이 제네릭 형식 및 메서드를 처리하는 방법을 이해하기 위한 두 가지 키가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-105">There are two keys to understanding how reflection handles generic types and methods:</span></span>  
  
-   <span data-ttu-id="f09d6-106">제네릭 형식 정의 및 제네릭 메서드 정의의 형식 매개 변수는 <xref:System.Type> 클래스의 인스턴스로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-106">The type parameters of generic type definitions and generic method definitions are represented by instances of the <xref:System.Type> class.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f09d6-107"><xref:System.Type> 의 여러 속성 및 메서드는 <xref:System.Type> 개체가 제네릭 형식 매개 변수를 나타낼 때 다른 동작을 내포합니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-107">Many properties and methods of <xref:System.Type> have different behavior when a <xref:System.Type> object represents a generic type parameter.</span></span> <span data-ttu-id="f09d6-108">이러한 차이는 속성 및 메서드 항목에 설명되어있습니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-108">These differences are documented in the property and method topics.</span></span> <span data-ttu-id="f09d6-109">예제는 <xref:System.Type.IsAutoClass%2A> 및 <xref:System.Type.DeclaringType%2A>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f09d6-109">For example, see <xref:System.Type.IsAutoClass%2A> and <xref:System.Type.DeclaringType%2A>.</span></span> <span data-ttu-id="f09d6-110">또한 일부 멤버는 <xref:System.Type> 개체가 제네릭 형식 매개 변수를 나타낼 경우에만 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-110">In addition, some members are valid only when a <xref:System.Type> object represents a generic type parameter.</span></span> <span data-ttu-id="f09d6-111">예제는 <xref:System.Type.GetGenericTypeDefinition%2A>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f09d6-111">For example, see <xref:System.Type.GetGenericTypeDefinition%2A>.</span></span>  
  
-   <span data-ttu-id="f09d6-112"><xref:System.Type> 의 인스턴스가 제네릭 형식을 나타내면 형식 매개 변수(제네릭 형식 정의의 경우) 또는 형식 인수(생성된 형식의 경우)를 나타내는 형식의 배열이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-112">If an instance of <xref:System.Type> represents a generic type, then it includes an array of types that represent the type parameters (for generic type definitions) or the type arguments (for constructed types).</span></span> <span data-ttu-id="f09d6-113">제네릭 메서드를 나타내는 <xref:System.Reflection.MethodInfo> 클래스의 인스턴스에서도 똑같습니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-113">The same is true of an instance of the <xref:System.Reflection.MethodInfo> class that represents a generic method.</span></span>  
  
 <span data-ttu-id="f09d6-114">리플렉션은 <xref:System.Type> 및 <xref:System.Reflection.MethodInfo>의 메서드를 제공합니다. 이 메서드를 통해 형식 매개 변수의 배열에 액세스할 수 있으며, <xref:System.Type>의 인스턴스가 형식 매개 변수를 나타내는지 또는 실제 형식을 나타내는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-114">Reflection provides methods of <xref:System.Type> and <xref:System.Reflection.MethodInfo> that allow you to access the array of type parameters, and to determine whether an instance of <xref:System.Type> represents a type parameter or an actual type.</span></span>  
  
 <span data-ttu-id="f09d6-115">여기에서 논의한 메서드를 보여 주는 예제 코드는 [방법: 리플렉션을 사용하여 제네릭 형식 검사 및 인스턴스화](../../../docs/framework/reflection-and-codedom/how-to-examine-and-instantiate-generic-types-with-reflection.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f09d6-115">For example code demonstrating the methods discussed here, see [How to: Examine and Instantiate Generic Types with Reflection](../../../docs/framework/reflection-and-codedom/how-to-examine-and-instantiate-generic-types-with-reflection.md).</span></span>  
  
 <span data-ttu-id="f09d6-116">다음 논의에서는 형식 매개 변수 및 인수와 개방형 또는 폐쇄형의 생성된 형식 간 차이점과 같은 제네릭 용어에 익숙하다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-116">The following discussion assumes familiarity with the terminology of generics, such as the difference between type parameters and arguments and open or closed constructed types.</span></span> <span data-ttu-id="f09d6-117">자세한 내용은 [제네릭](../../../docs/standard/generics/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f09d6-117">For more information, see [Generics](../../../docs/standard/generics/index.md).</span></span>  
  
 <span data-ttu-id="f09d6-118">이 개요는 다음과 같은 섹션으로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-118">This overview consists of the following sections:</span></span>  
  
-   [<span data-ttu-id="f09d6-119">제네릭 형식인가요 아니면 제네릭 메서드인가요?</span><span class="sxs-lookup"><span data-stu-id="f09d6-119">Is This a Generic Type or Method?</span></span>](#is_this_a_generic_type_or_method)  
  
-   [<span data-ttu-id="f09d6-120">폐쇄형 제네릭 형식 생성</span><span class="sxs-lookup"><span data-stu-id="f09d6-120">Generating Closed Generic Types</span></span>](#generating_closed_generic_types)  
  
-   [<span data-ttu-id="f09d6-121">형식 인수 및 형식 매개 변수 검사</span><span class="sxs-lookup"><span data-stu-id="f09d6-121">Examining Type Arguments and Type Parameters</span></span>](#examining_type_arguments)  
  
-   [<span data-ttu-id="f09d6-122">고정</span><span class="sxs-lookup"><span data-stu-id="f09d6-122">Invariants</span></span>](#invariants)  
  
-   [<span data-ttu-id="f09d6-123">관련 항목</span><span class="sxs-lookup"><span data-stu-id="f09d6-123">Related Topics</span></span>](#related_topics)  
  
<a name="is_this_a_generic_type_or_method"></a>   
## <a name="is-this-a-generic-type-or-method"></a><span data-ttu-id="f09d6-124">제네릭 형식인가요 아니면 제네릭 메서드인가요?</span><span class="sxs-lookup"><span data-stu-id="f09d6-124">Is This a Generic Type or Method?</span></span>  
 <span data-ttu-id="f09d6-125">리플렉션을 사용하여 <xref:System.Type>의 인스턴스에서 나타내는 알 수 없는 형식을 검사할 때 알 수 없는 형식이 제네릭인지 여부를 확인하는 데 <xref:System.Type.IsGenericType%2A> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-125">When you use reflection to examine an unknown type, represented by an instance of <xref:System.Type>, use the <xref:System.Type.IsGenericType%2A> property to determine whether the unknown type is generic.</span></span> <span data-ttu-id="f09d6-126">형식이 제네릭 경우 `true` 를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-126">It returns `true` if the type is generic.</span></span> <span data-ttu-id="f09d6-127">마찬가지로 리플렉션을 사용하여 <xref:System.Reflection.MethodInfo> 클래스의 인스턴스에서 나타내는 알 수 없는 메서드를 검사할 때 메서드가 제네릭인지 여부를 확인하는 데 <xref:System.Reflection.MethodInfo.IsGenericMethod%2A> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-127">Similarly, when you examine an unknown method, represented by an instance of the <xref:System.Reflection.MethodInfo> class, use the <xref:System.Reflection.MethodInfo.IsGenericMethod%2A> property to determine whether the method is generic.</span></span>  
  
### <a name="is-this-a-generic-type-or-method-definition"></a><span data-ttu-id="f09d6-128">제네릭 형식인가요 아니면 메서드 정의인가요?</span><span class="sxs-lookup"><span data-stu-id="f09d6-128">Is This a Generic Type or Method Definition?</span></span>  
 <span data-ttu-id="f09d6-129"><xref:System.Type.IsGenericTypeDefinition%2A> 속성을 사용하여 <xref:System.Type> 개체가 제네릭 형식 정의를 나타내는지를 확인하고, <xref:System.Reflection.MethodInfo.IsGenericMethodDefinition%2A> 메서드를 사용하여 <xref:System.Reflection.MethodInfo> 개체가 제네릭 메서드 정의를 나타내는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-129">Use the <xref:System.Type.IsGenericTypeDefinition%2A> property to determine whether a <xref:System.Type> object represents a generic type definition, and use the <xref:System.Reflection.MethodInfo.IsGenericMethodDefinition%2A> method to determine whether a <xref:System.Reflection.MethodInfo> represents a generic method definition.</span></span>  
  
 <span data-ttu-id="f09d6-130">제네릭 형식 및 메서드 정의는 인스턴스화할 수 있는 형식을 생성하는 템플릿입니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-130">Generic type and method definitions are the templates from which instantiable types are created.</span></span> <span data-ttu-id="f09d6-131"><xref:System.Collections.Generic.Dictionary%602>와 같은 .NET Framework 클래스 라이브러리의 제네릭 형식은 제네릭 형식 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-131">Generic types in the .NET Framework class library, such as <xref:System.Collections.Generic.Dictionary%602>, are generic type definitions.</span></span>  
  
### <a name="is-the-type-or-method-open-or-closed"></a><span data-ttu-id="f09d6-132">형식 또는 메서드가 개방형인가요 아니면 폐쇄형인가요?</span><span class="sxs-lookup"><span data-stu-id="f09d6-132">Is the Type or Method Open or Closed?</span></span>  
 <span data-ttu-id="f09d6-133">인스턴스화할 수 있는 형식이 모든 바깥쪽 형식의 모든 형식 매개 변수를 비롯하여 모든 해당 형식 매개 변수를 대체한 경우 제네릭 형식 또는 메서드는 폐쇄형입니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-133">A generic type or method is closed if instantiable types have been substituted for all its type parameters, including all the type parameters of all enclosing types.</span></span> <span data-ttu-id="f09d6-134">폐쇄형인 경우 제네릭 형식의 인스턴스만 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-134">You can only create an instance of a generic type if it is closed.</span></span> <span data-ttu-id="f09d6-135">형식이 개방형인 경우 <xref:System.Type.ContainsGenericParameters%2A?displayProperty=nameWithType> 속성에서 `true` 를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-135">The <xref:System.Type.ContainsGenericParameters%2A?displayProperty=nameWithType> property returns `true` if a type is open.</span></span> <span data-ttu-id="f09d6-136">메서드의 경우 <xref:System.Reflection.MethodInfo.ContainsGenericParameters%2A?displayProperty=nameWithType> 메서드가 같은 기능을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-136">For methods, the <xref:System.Reflection.MethodInfo.ContainsGenericParameters%2A?displayProperty=nameWithType> method performs the same function.</span></span>  
  
 [<span data-ttu-id="f09d6-137">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="f09d6-137">Back to top</span></span>](#top)  
  
<a name="generating_closed_generic_types"></a>   
## <a name="generating-closed-generic-types"></a><span data-ttu-id="f09d6-138">폐쇄형 제네릭 형식 생성</span><span class="sxs-lookup"><span data-stu-id="f09d6-138">Generating Closed Generic Types</span></span>  
 <span data-ttu-id="f09d6-139">제네릭 형식 또는 메서드 정의가 있으면 <xref:System.Type.MakeGenericType%2A> 메서드를 사용하여 폐쇄형 제네릭 형식을 만들거나 <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A> 메서드를 사용하여 폐쇄형 제네릭 형식의 <xref:System.Reflection.MethodInfo> 를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-139">Once you have a generic type or method definition, use the <xref:System.Type.MakeGenericType%2A> method to create a closed generic type or the <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A> method to create a <xref:System.Reflection.MethodInfo> for a closed generic method.</span></span>  
  
### <a name="getting-the-generic-type-or-method-definition"></a><span data-ttu-id="f09d6-140">제네릭 형식 또는 메서드 정의 가져오기</span><span class="sxs-lookup"><span data-stu-id="f09d6-140">Getting the Generic Type or Method Definition</span></span>  
 <span data-ttu-id="f09d6-141">제네릭 형식 또는 메서드 정의가 아닌 개방형 제네릭 형식 또는 메서드가 있는 경우 해당 인스턴스를 만들 수 없으며 누락된 형식 매개 변수를 제공할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-141">If you have an open generic type or method that is not a generic type or method definition, you cannot create instances of it and you cannot supply the type parameters that are missing.</span></span> <span data-ttu-id="f09d6-142">제네릭 형식 또는 메서드 정의가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-142">You must have a generic type or method definition.</span></span> <span data-ttu-id="f09d6-143"><xref:System.Type.GetGenericTypeDefinition%2A> 메서드를 사용하여 제네릭 형식 정의를 가져오거나 <xref:System.Reflection.MethodInfo.GetGenericMethodDefinition%2A> 메서드를 사용하여 제네릭 메서드 정의를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-143">Use the <xref:System.Type.GetGenericTypeDefinition%2A> method to obtain the generic type definition or the <xref:System.Reflection.MethodInfo.GetGenericMethodDefinition%2A> method to obtain the generic method definition.</span></span>  
  
 <span data-ttu-id="f09d6-144">예를 들어 <xref:System.Type> (Visual Basic의 `Dictionary<int, string>` )을 나타내는`Dictionary(Of Integer, String)` 개체가 있으며 `Dictionary<string, MyClass>`형식을 만들려는 경우 <xref:System.Type.GetGenericTypeDefinition%2A> 메서드를 사용하여 <xref:System.Type> 를 나타내는 `Dictionary<TKey, TValue>` 을 가져온 후 <xref:System.Type.MakeGenericType%2A> 메서드를 사용하여 <xref:System.Type> 를 나타내는 `Dictionary<int, MyClass>`을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-144">For example, if you have a <xref:System.Type> object representing `Dictionary<int, string>` (`Dictionary(Of Integer, String)` in Visual Basic) and you want to create the type `Dictionary<string, MyClass>`, you can use the <xref:System.Type.GetGenericTypeDefinition%2A> method to get a <xref:System.Type> representing `Dictionary<TKey, TValue>` and then use the <xref:System.Type.MakeGenericType%2A> method to produce a <xref:System.Type> representing `Dictionary<int, MyClass>`.</span></span>  
  
 <span data-ttu-id="f09d6-145">제네릭 형식이 아닌 개방형 제네릭 형식의 예제는 이 항목의 뒷부분에 나오는 "형식 매개 변수 또는 형식 인수"를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f09d6-145">For an example of an open generic type that is not a generic type, see "Type Parameter or Type Argument" later in this topic.</span></span>  
  
 [<span data-ttu-id="f09d6-146">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="f09d6-146">Back to top</span></span>](#top)  
  
<a name="examining_type_arguments"></a>   
## <a name="examining-type-arguments-and-type-parameters"></a><span data-ttu-id="f09d6-147">형식 인수 및 형식 매개 변수 검사</span><span class="sxs-lookup"><span data-stu-id="f09d6-147">Examining Type Arguments and Type Parameters</span></span>  
 <span data-ttu-id="f09d6-148"><xref:System.Type.GetGenericArguments%2A?displayProperty=nameWithType> 메서드를 사용하여 제네릭 형식의 형식 매개 변수 또는 형식 인수를 나타내는 <xref:System.Type> 개체의 배열을 가져오고, <xref:System.Reflection.MethodInfo.GetGenericArguments%2A?displayProperty=nameWithType> 메서드를 사용하여 제네릭 메서드에 대해 동일한 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-148">Use the <xref:System.Type.GetGenericArguments%2A?displayProperty=nameWithType> method to obtain an array of <xref:System.Type> objects that represent the type parameters or type arguments of a generic type, and use the <xref:System.Reflection.MethodInfo.GetGenericArguments%2A?displayProperty=nameWithType> method to do the same for a generic method.</span></span>  
  
 <span data-ttu-id="f09d6-149"><xref:System.Type> 개체가 형식 매개 변수를 나타내는 것을 알고 있다면 리플렉션이 대답할 수 있는 추가 질문이 많습니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-149">Once you know that a <xref:System.Type> object represents a type parameter, there are many additional questions reflection can answer.</span></span> <span data-ttu-id="f09d6-150">형식 매개 변수의 소스, 해당 위치 및 해당 제약 조건을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-150">You can determine the type parameter's source, its position, and its constraints.</span></span>  
  
### <a name="type-parameter-or-type-argument"></a><span data-ttu-id="f09d6-151">형식 매개 변수 또는 형식 인수</span><span class="sxs-lookup"><span data-stu-id="f09d6-151">Type Parameter or Type Argument</span></span>  
 <span data-ttu-id="f09d6-152">배열의 특정 요소가 형식 매개 변수인지 또는 형식 인수인지 확인하려면 <xref:System.Type.IsGenericParameter%2A> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-152">To determine whether a particular element of the array is a type parameter or a type argument, use the <xref:System.Type.IsGenericParameter%2A> property.</span></span> <span data-ttu-id="f09d6-153">요소가 형식 매개 변수인 경우 <xref:System.Type.IsGenericParameter%2A> 속성은 `true` 입니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-153">The <xref:System.Type.IsGenericParameter%2A> property is `true` if the element is a type parameter.</span></span>  
  
 <span data-ttu-id="f09d6-154">제네릭 형식은 제네릭 형식 정의 없이 열릴 수 있으며, 이 경우에 형식 인수 및 형식 매개 변수가 혼합됩니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-154">A generic type can be open without being a generic type definition, in which case it has a mixture of type arguments and type parameters.</span></span> <span data-ttu-id="f09d6-155">예를 들어 다음 코드에서 `D` 클래스는 `D` 의 첫 번째 형식 매개 변수로 `B`의 두 번째 형식 매개 변수를 대체하여 생성한 형식에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-155">For example, in the following code, class `D` derives from a type created by substituting the first type parameter of `D` for the second type parameter of `B`.</span></span>  
  
```csharp  
class B<T, U> {}  
class D<V, W> : B<int, V> {}  
```  
  
```vb  
Class B(Of T, U)  
End Class  
Class D(Of V, W)  
    Inherits B(Of Integer, V)  
End Class  
```  
  
```cpp  
generic<typename T, typename U> ref class B {};  
generic<typename V, typename W> ref class D : B<int, V> {};  
```  
  
 <span data-ttu-id="f09d6-156"><xref:System.Type> 를 나타내는 `D<V, W>` 개체를 가져오고 <xref:System.Type.BaseType%2A> 속성을 사용하여 해당 기본 형식을 가져오는 경우 결과적으로 `type B<int, V>` 가 열리지만 제네릭 형식 정의는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-156">If you obtain a <xref:System.Type> object representing `D<V, W>` and use the <xref:System.Type.BaseType%2A> property to obtain its base type, the resulting `type B<int, V>` is open, but it is not a generic type definition.</span></span>  
  
### <a name="source-of-a-generic-parameter"></a><span data-ttu-id="f09d6-157">제네릭 매개 변수의 소스</span><span class="sxs-lookup"><span data-stu-id="f09d6-157">Source of a Generic Parameter</span></span>  
 <span data-ttu-id="f09d6-158">제네릭 형식 매개 변수는 검사 중인 형식, 바깥쪽 형식 또는 제네릭 메서드에서 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-158">A generic type parameter might come from the type you are examining, from an enclosing type, or from a generic method.</span></span> <span data-ttu-id="f09d6-159">다음과 같이 제네릭 형식 매개 변수의 소스를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-159">You can determine the source of the generic type parameter as follows:</span></span>  
  
-   <span data-ttu-id="f09d6-160">먼저, <xref:System.Type.DeclaringMethod%2A> 속성을 사용하여 형식 매개 변수가 제네릭 메서드에서 가져온 것인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-160">First, use the <xref:System.Type.DeclaringMethod%2A> property to determine whether the type parameter comes from a generic method.</span></span> <span data-ttu-id="f09d6-161">속성 값이 null 참조(Visual Basic의`Nothing` )가 아니면 소스가 제네릭 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-161">If the property value is not a null reference (`Nothing` in Visual Basic), then the source is a generic method.</span></span>  
  
-   <span data-ttu-id="f09d6-162">소스가 제네릭 메서드가 아닌 경우 <xref:System.Type.DeclaringType%2A> 속성을 사용하여 제네릭 형식 매개 변수가 속한 제네릭 형식을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-162">If the source is not a generic method, use the <xref:System.Type.DeclaringType%2A> property to determine the generic type the generic type parameter belongs to.</span></span>  
  
 <span data-ttu-id="f09d6-163">형식 매개 변수가 제네릭 메서드에 속한 경우 <xref:System.Type.DeclaringType%2A> 속성은 관련이 없는 제네릭 메서드를 선언한 형식을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-163">If the type parameter belongs to a generic method, the <xref:System.Type.DeclaringType%2A> property returns the type that declared the generic method, which is irrelevant.</span></span>  
  
### <a name="position-of-a-generic-parameter"></a><span data-ttu-id="f09d6-164">제네릭 매개 변수의 위치</span><span class="sxs-lookup"><span data-stu-id="f09d6-164">Position of a Generic Parameter</span></span>  
 <span data-ttu-id="f09d6-165">선언하는 해당 클래스의 형식 매개 변수 목록에서 형식 매개 변수의 위치를 확인할 필요가 가끔 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-165">In rare situations, it is necessary to determine the position of a type parameter in the type parameter list of its declaring class.</span></span> <span data-ttu-id="f09d6-166">예를 들어 앞의 예제에서 <xref:System.Type> 형식을 나타내는 `B<int, V>` 개체가 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-166">For example, suppose you have a <xref:System.Type> object representing the `B<int, V>` type from the preceding example.</span></span> <span data-ttu-id="f09d6-167"><xref:System.Type.GetGenericArguments%2A> 메서드는 형식 인수의 목록을 제공하므로 `V` 를 검사할 경우 <xref:System.Type.DeclaringMethod%2A> 및 <xref:System.Type.DeclaringType%2A> 속성을 사용하여 어디에서 가져왔는지 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-167">The <xref:System.Type.GetGenericArguments%2A> method gives you a list of type arguments, and when you examine `V` you can use the <xref:System.Type.DeclaringMethod%2A> and <xref:System.Type.DeclaringType%2A> properties to discover where it comes from.</span></span> <span data-ttu-id="f09d6-168">그런 다음 <xref:System.Type.GenericParameterPosition%2A> 속성을 사용하여 원래 정의된 형식 매개 변수 목록에서 해당 위치를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-168">You can then use the <xref:System.Type.GenericParameterPosition%2A> property to determine its position in the type parameter list where it was defined.</span></span> <span data-ttu-id="f09d6-169">이 예제에서 `V` 는 원래 정의된 형식 매개 변수 목록에서 0(영) 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-169">In this example, `V` is at position 0 (zero) in the type parameter list where it was defined.</span></span>  
  
### <a name="base-type-and-interface-constraints"></a><span data-ttu-id="f09d6-170">기본 형식 및 인터페이스 제약 조건</span><span class="sxs-lookup"><span data-stu-id="f09d6-170">Base Type and Interface Constraints</span></span>  
 <span data-ttu-id="f09d6-171"><xref:System.Type.GetGenericParameterConstraints%2A> 메서드를 사용하여 형식 매개 변수의 기본 형식 제약 조건 및 인터페이스 제약 조건을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-171">Use the <xref:System.Type.GetGenericParameterConstraints%2A> method to obtain the base type constraint and interface constraints of a type parameter.</span></span> <span data-ttu-id="f09d6-172">배열 요소의 순서는 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-172">The order of the elements of the array is not significant.</span></span> <span data-ttu-id="f09d6-173">요소는 인터페이스 형식인 경우 인터페이스 제약 조건을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-173">An element represents an interface constraint if it is an interface type.</span></span>  
  
### <a name="generic-parameter-attributes"></a><span data-ttu-id="f09d6-174">제네릭 매개 변수 특성</span><span class="sxs-lookup"><span data-stu-id="f09d6-174">Generic Parameter Attributes</span></span>  
 <span data-ttu-id="f09d6-175"><xref:System.Type.GenericParameterAttributes%2A> 속성은 형식 매개 변수의 분산(공 분산 및 반공 분산) 및 특별 제약 조건을 나타내는 <xref:System.Reflection.GenericParameterAttributes> 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-175">The <xref:System.Type.GenericParameterAttributes%2A> property gets a <xref:System.Reflection.GenericParameterAttributes> value that indicates the variance (covariance or contravariance) and the special constraints of a type parameter.</span></span>  
  
#### <a name="covariance-and-contravariance"></a><span data-ttu-id="f09d6-176">공 분산 및 반공 분산</span><span class="sxs-lookup"><span data-stu-id="f09d6-176">Covariance and Contravariance</span></span>  
 <span data-ttu-id="f09d6-177">형식 매개 변수가 공 분산인지 또는 반공 분산인지 확인하려면 <xref:System.Reflection.GenericParameterAttributes.VarianceMask?displayProperty=nameWithType> 마스크를 <xref:System.Reflection.GenericParameterAttributes> 속성에서 반환한 <xref:System.Type.GenericParameterAttributes%2A> 값에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-177">To determine whether a type parameter is covariant or contravariant, apply the <xref:System.Reflection.GenericParameterAttributes.VarianceMask?displayProperty=nameWithType> mask to the <xref:System.Reflection.GenericParameterAttributes> value that is returned by the <xref:System.Type.GenericParameterAttributes%2A> property.</span></span> <span data-ttu-id="f09d6-178">결과가 <xref:System.Reflection.GenericParameterAttributes.None?displayProperty=nameWithType>인 경우 형식 매개 변수는 고정입니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-178">If the result is <xref:System.Reflection.GenericParameterAttributes.None?displayProperty=nameWithType>, the type parameter is invariant.</span></span> <span data-ttu-id="f09d6-179">[공변성(Covariance) 및 반공변성(Contravariance)](../../../docs/standard/generics/covariance-and-contravariance.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f09d6-179">See [Covariance and Contravariance](../../../docs/standard/generics/covariance-and-contravariance.md).</span></span>  
  
#### <a name="special-constraints"></a><span data-ttu-id="f09d6-180">특별 제약 조건</span><span class="sxs-lookup"><span data-stu-id="f09d6-180">Special Constraints</span></span>  
 <span data-ttu-id="f09d6-181">형식 매개 변수의 특별 제약 조건을 확인하려면 <xref:System.Reflection.GenericParameterAttributes.SpecialConstraintMask?displayProperty=nameWithType> 마스크를 <xref:System.Reflection.GenericParameterAttributes> 속성에서 반환한 <xref:System.Type.GenericParameterAttributes%2A> 값에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-181">To determine the special constraints of a type parameter, apply the <xref:System.Reflection.GenericParameterAttributes.SpecialConstraintMask?displayProperty=nameWithType> mask to the <xref:System.Reflection.GenericParameterAttributes> value that is returned by the <xref:System.Type.GenericParameterAttributes%2A> property.</span></span> <span data-ttu-id="f09d6-182">결과가 <xref:System.Reflection.GenericParameterAttributes.None?displayProperty=nameWithType>인 경우 특별 제약 조건이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-182">If the result is <xref:System.Reflection.GenericParameterAttributes.None?displayProperty=nameWithType>, there are no special constraints.</span></span> <span data-ttu-id="f09d6-183">형식 매개 변수는 참조 형식이어야 하고 Nullable이 아닌 값 형식이어야 하며 그리고 기본 생성자를 보유해야 하는 제약을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-183">A type parameter can be constrained to be a reference type, to be a non-nullable value type, and to have a default constructor.</span></span>  
  
 [<span data-ttu-id="f09d6-184">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="f09d6-184">Back to top</span></span>](#top)  
  
<a name="invariants"></a>   
## <a name="invariants"></a><span data-ttu-id="f09d6-185">고정</span><span class="sxs-lookup"><span data-stu-id="f09d6-185">Invariants</span></span>  
 <span data-ttu-id="f09d6-186">제네릭 형식에 대한 리플렉션의 일반적인 용어에 대한 고정 조건 표는 <xref:System.Type.IsGenericType%2A?displayProperty=nameWithType>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f09d6-186">For a table of the invariant conditions for common terms in reflection for generic types, see <xref:System.Type.IsGenericType%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f09d6-187">제네릭 메서드와 관련된 추가 용어는 <xref:System.Reflection.MethodInfo.IsGenericMethod%2A?displayProperty=nameWithType>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f09d6-187">For additional terms relating to generic methods, see <xref:System.Reflection.MethodInfo.IsGenericMethod%2A?displayProperty=nameWithType>.</span></span>  
  
 [<span data-ttu-id="f09d6-188">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="f09d6-188">Back to top</span></span>](#top)  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a><span data-ttu-id="f09d6-189">관련 항목</span><span class="sxs-lookup"><span data-stu-id="f09d6-189">Related Topics</span></span>  
  
|<span data-ttu-id="f09d6-190">제목</span><span class="sxs-lookup"><span data-stu-id="f09d6-190">Title</span></span>|<span data-ttu-id="f09d6-191">설명</span><span class="sxs-lookup"><span data-stu-id="f09d6-191">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="f09d6-192">방법: 리플렉션을 사용하여 제네릭 형식 검사 및 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="f09d6-192">How to: Examine and Instantiate Generic Types with Reflection</span></span>](../../../docs/framework/reflection-and-codedom/how-to-examine-and-instantiate-generic-types-with-reflection.md)|<span data-ttu-id="f09d6-193"><xref:System.Type> 및 <xref:System.Reflection.MethodInfo>의 속성 및 메서드를 사용하여 제네릭 형식을 검사하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-193">Shows how to use the properties and methods of <xref:System.Type> and <xref:System.Reflection.MethodInfo> to examine generic types.</span></span>|  
|[<span data-ttu-id="f09d6-194">제네릭</span><span class="sxs-lookup"><span data-stu-id="f09d6-194">Generics</span></span>](../../../docs/standard/generics/index.md)|<span data-ttu-id="f09d6-195">제네릭 기능 및 .NET Framework에서 제네릭 기능을 지원하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-195">Describes the generics feature and how it is supported in the .NET Framework.</span></span>|  
|[<span data-ttu-id="f09d6-196">방법: 리플렉션 내보내기를 사용하여 제네릭 형식 정의</span><span class="sxs-lookup"><span data-stu-id="f09d6-196">How to: Define a Generic Type with Reflection Emit</span></span>](../../../docs/framework/reflection-and-codedom/how-to-define-a-generic-type-with-reflection-emit.md)|<span data-ttu-id="f09d6-197">리플렉션 내보내기를 사용하여 동적 어셈블리에서 제네릭 형식을 생성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-197">Shows how to use reflection emit to generate generic types in dynamic assemblies.</span></span>|  
|[<span data-ttu-id="f09d6-198">형식 정보 보기</span><span class="sxs-lookup"><span data-stu-id="f09d6-198">Viewing Type Information</span></span>](../../../docs/framework/reflection-and-codedom/viewing-type-information.md)|<span data-ttu-id="f09d6-199"><xref:System.Type> 클래스를 설명하고 <xref:System.Type>과 다양한 리플렉션 클래스를 함께 사용하여 생성자, 메서드, 필드, 속성, 이벤트에 대한 정보를 가져오는 방법을 보여 주는 코드 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f09d6-199">Describes the <xref:System.Type> class and provides code examples that illustrate how to use <xref:System.Type> with various reflection classes to obtain information about constructors, methods, fields, properties, and events.</span></span>|
