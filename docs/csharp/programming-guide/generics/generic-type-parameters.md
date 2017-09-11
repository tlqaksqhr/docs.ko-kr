---
title: "제네릭 형식 매개 변수(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], type parameters
- type parameters [C#]
ms.assetid: a03b0ab2-0606-4b41-b7bf-e64d5bb4d18f
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ce1024215a381afb3a7b42f2127fe5e8c212d378
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="generic-type-parameters-c-programming-guide"></a><span data-ttu-id="9d62e-102">제네릭 형식 매개 변수(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="9d62e-102">Generic Type Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="9d62e-103">제네릭 형식 또는 메서드 정의에서 형식 매개 변수는 클라이언트가 제네릭 형식의 변수를 인스턴스화할 때 지정하는 특정 형식에 대한 자리 표시자입니다.</span><span class="sxs-lookup"><span data-stu-id="9d62e-103">In a generic type or method definition, a type parameters is a placeholder for a specific type that a client specifies when they instantiate a variable of the generic type.</span></span> <span data-ttu-id="9d62e-104">[제네릭 소개](../../../csharp/programming-guide/generics/introduction-to-generics.md)에 나열된 `GenericList<T>`와 같은 제네릭 클래스는 실제로 형식이 아니고 형식에 대한 청사진과 같으므로 있는 그대로 사용할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9d62e-104">A generic class, such as `GenericList<T>` listed in [Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md), cannot be used as-is because it is not really a type; it is more like a blueprint for a type.</span></span> <span data-ttu-id="9d62e-105">`GenericList<T>`를 사용하려면, 클라이언트 코드에서 꺾쇠 괄호 안에 형식 인수를 지정하여 생성된 형식을 선언하고 인스턴스화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d62e-105">To use `GenericList<T>`, client code must declare and instantiate a constructed type by specifying a type argument inside the angle brackets.</span></span> <span data-ttu-id="9d62e-106">이 특정 클래스의 형식 인수는 컴파일러에서 인식하는 모든 형식이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d62e-106">The type argument for this particular class can be any type recognized by the compiler.</span></span> <span data-ttu-id="9d62e-107">만들 수 있는 생성된 형식 인스턴스의 수에는 제한이 없고, 각 인스턴스에서는 다음과 같이 서로 다른 형식 인수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d62e-107">Any number of constructed type instances can be created, each one using a different type argument, as follows:</span></span>  
  
 <span data-ttu-id="9d62e-108">[!code-cs[csProgGuideGenerics#7](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9d62e-108">[!code-cs[csProgGuideGenerics#7](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_1.cs)]</span></span>  
  
 <span data-ttu-id="9d62e-109">`GenericList<T>`의 각 인스턴스에서 클래스에 있는 모든 `T`는 런타임에 형식 인수로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d62e-109">In each of these instances of `GenericList<T>`, every occurrence of `T` in the class will be substituted at run time with the type argument.</span></span> <span data-ttu-id="9d62e-110">이러한 대체를 통해 단일 클래스 정의를 사용하여 세 개의 형식이 안전한 효율적인 개체를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="9d62e-110">By means of this substitution, we have created three separate type-safe and efficient objects using a single class definition.</span></span> <span data-ttu-id="9d62e-111">CLR에서 이러한 대체를 수행하는 방식에 대한 자세한 내용은 [런타임의 제네릭](../../../csharp/programming-guide/generics/generics-in-the-run-time.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9d62e-111">For more information on how this substitution is performed by the CLR, see [Generics in the Run Time](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).</span></span>  
  
## <a name="type-parameter-naming-guidelines"></a><span data-ttu-id="9d62e-112">형식 매개 변수 명명 지침</span><span class="sxs-lookup"><span data-stu-id="9d62e-112">Type Parameter Naming Guidelines</span></span>  
  
-   <span data-ttu-id="9d62e-113">**필수적** 단일 문자 이름으로도 자체 설명이 가능하여 설명적인 이름을 굳이 사용할 필요가 없는 경우가 아니면 제네릭 형식 매개 변수 이름을 설명적인 이름으로 지정하세요.</span><span class="sxs-lookup"><span data-stu-id="9d62e-113">**Do** name generic type parameters with descriptive names, unless a single letter name is completely self explanatory and a descriptive name would not add value.</span></span>  
  
     <span data-ttu-id="9d62e-114">[!code-cs[csProgGuideGenerics#8](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="9d62e-114">[!code-cs[csProgGuideGenerics#8](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_2.cs)]</span></span>  
  
-   <span data-ttu-id="9d62e-115">**선택적** 단일 문자 형식 매개 변수를 사용하는 형식에는 형식 매개 변수 이름으로 T를 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="9d62e-115">**Consider** using T as the type parameter name for types with one single letter type parameter.</span></span>  
  
     <span data-ttu-id="9d62e-116">[!code-cs[csProgGuideGenerics#9](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="9d62e-116">[!code-cs[csProgGuideGenerics#9](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_3.cs)]</span></span>  
  
-   <span data-ttu-id="9d62e-117">**필수적** 설명적인 형식 매개 변수 이름 앞에 “T”를 붙이세요.</span><span class="sxs-lookup"><span data-stu-id="9d62e-117">**Do** prefix descriptive type parameter names with "T".</span></span>  
  
     <span data-ttu-id="9d62e-118">[!code-cs[csProgGuideGenerics#10](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="9d62e-118">[!code-cs[csProgGuideGenerics#10](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_4.cs)]</span></span>  
  
-   <span data-ttu-id="9d62e-119">**선택적** 매개 변수 이름 안에 형식 매개 변수에 적용되는 제약 조건을 나타내 보세요.</span><span class="sxs-lookup"><span data-stu-id="9d62e-119">**Consider** indicating constraints placed on a type parameter in the name of parameter.</span></span> <span data-ttu-id="9d62e-120">예를 들어 `ISession`으로 제한되는 매개 변수의 이름은 `TSession`이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d62e-120">For example, a parameter constrained to `ISession` may be called `TSession`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d62e-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9d62e-121">See Also</span></span>  
 <span data-ttu-id="9d62e-122"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="9d62e-122"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="9d62e-123">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9d62e-123">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="9d62e-124">[제네릭](../../../csharp/programming-guide/generics/index.md) </span><span class="sxs-lookup"><span data-stu-id="9d62e-124">[Generics](../../../csharp/programming-guide/generics/index.md) </span></span>  
 [<span data-ttu-id="9d62e-125">C++ 템플릿과 C# 제네릭의 차이점</span><span class="sxs-lookup"><span data-stu-id="9d62e-125">Differences Between C++ Templates and C# Generics</span></span>](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)

