---
title: 제네릭 형식 매개 변수(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], type parameters
- type parameters [C#]
ms.assetid: a03b0ab2-0606-4b41-b7bf-e64d5bb4d18f
ms.openlocfilehash: 35029b90fb7b905a87055596cf8dcd6a84ef9d36
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="generic-type-parameters-c-programming-guide"></a><span data-ttu-id="7546c-102">제네릭 형식 매개 변수(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="7546c-102">Generic Type Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="7546c-103">제네릭 형식 또는 메서드 정의에서 형식 매개 변수는 클라이언트가 제네릭 형식의 변수를 인스턴스화할 때 지정하는 특정 형식에 대한 자리 표시자입니다.</span><span class="sxs-lookup"><span data-stu-id="7546c-103">In a generic type or method definition, a type parameters is a placeholder for a specific type that a client specifies when they instantiate a variable of the generic type.</span></span> <span data-ttu-id="7546c-104">[제네릭 소개](../../../csharp/programming-guide/generics/introduction-to-generics.md)에 나열된 `GenericList<T>`와 같은 제네릭 클래스는 실제로 형식이 아니고 형식에 대한 청사진과 같으므로 있는 그대로 사용할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7546c-104">A generic class, such as `GenericList<T>` listed in [Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md), cannot be used as-is because it is not really a type; it is more like a blueprint for a type.</span></span> <span data-ttu-id="7546c-105">`GenericList<T>`를 사용하려면, 클라이언트 코드에서 꺾쇠 괄호 안에 형식 인수를 지정하여 생성된 형식을 선언하고 인스턴스화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7546c-105">To use `GenericList<T>`, client code must declare and instantiate a constructed type by specifying a type argument inside the angle brackets.</span></span> <span data-ttu-id="7546c-106">이 특정 클래스의 형식 인수는 컴파일러에서 인식하는 모든 형식이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7546c-106">The type argument for this particular class can be any type recognized by the compiler.</span></span> <span data-ttu-id="7546c-107">만들 수 있는 생성된 형식 인스턴스의 수에는 제한이 없고, 각 인스턴스에서는 다음과 같이 서로 다른 형식 인수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7546c-107">Any number of constructed type instances can be created, each one using a different type argument, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#7](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_1.cs)]  
  
 <span data-ttu-id="7546c-108">`GenericList<T>`의 각 인스턴스에서 클래스에 있는 모든 `T`는 런타임에 형식 인수로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="7546c-108">In each of these instances of `GenericList<T>`, every occurrence of `T` in the class will be substituted at run time with the type argument.</span></span> <span data-ttu-id="7546c-109">이러한 대체를 통해 단일 클래스 정의를 사용하여 세 개의 형식이 안전한 효율적인 개체를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="7546c-109">By means of this substitution, we have created three separate type-safe and efficient objects using a single class definition.</span></span> <span data-ttu-id="7546c-110">CLR에서 이러한 대체를 수행하는 방식에 대한 자세한 내용은 [런타임의 제네릭](../../../csharp/programming-guide/generics/generics-in-the-run-time.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7546c-110">For more information on how this substitution is performed by the CLR, see [Generics in the Run Time](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).</span></span>  
  
## <a name="type-parameter-naming-guidelines"></a><span data-ttu-id="7546c-111">형식 매개 변수 명명 지침</span><span class="sxs-lookup"><span data-stu-id="7546c-111">Type Parameter Naming Guidelines</span></span>  
  
-   <span data-ttu-id="7546c-112">**필수적** 단일 문자 이름으로도 자체 설명이 가능하여 설명적인 이름을 굳이 사용할 필요가 없는 경우가 아니면 제네릭 형식 매개 변수 이름을 설명적인 이름으로 지정하세요.</span><span class="sxs-lookup"><span data-stu-id="7546c-112">**Do** name generic type parameters with descriptive names, unless a single letter name is completely self explanatory and a descriptive name would not add value.</span></span>  
  
     [!code-csharp[csProgGuideGenerics#8](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_2.cs)]  
  
-   <span data-ttu-id="7546c-113">**선택적** 단일 문자 형식 매개 변수를 사용하는 형식에는 형식 매개 변수 이름으로 T를 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="7546c-113">**Consider** using T as the type parameter name for types with one single letter type parameter.</span></span>  
  
     [!code-csharp[csProgGuideGenerics#9](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_3.cs)]  
  
-   <span data-ttu-id="7546c-114">**필수적** 설명적인 형식 매개 변수 이름 앞에 “T”를 붙이세요.</span><span class="sxs-lookup"><span data-stu-id="7546c-114">**Do** prefix descriptive type parameter names with "T".</span></span>  
  
     [!code-csharp[csProgGuideGenerics#10](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_4.cs)]  
  
-   <span data-ttu-id="7546c-115">**선택적** 매개 변수 이름 안에 형식 매개 변수에 적용되는 제약 조건을 나타내 보세요.</span><span class="sxs-lookup"><span data-stu-id="7546c-115">**Consider** indicating constraints placed on a type parameter in the name of parameter.</span></span> <span data-ttu-id="7546c-116">예를 들어 `ISession`으로 제한되는 매개 변수의 이름은 `TSession`이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7546c-116">For example, a parameter constrained to `ISession` may be called `TSession`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7546c-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7546c-117">See Also</span></span>  
 <xref:System.Collections.Generic>  
 [<span data-ttu-id="7546c-118">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="7546c-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="7546c-119">제네릭</span><span class="sxs-lookup"><span data-stu-id="7546c-119">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)  
 [<span data-ttu-id="7546c-120">C++ 템플릿과 C# 제네릭의 차이점</span><span class="sxs-lookup"><span data-stu-id="7546c-120">Differences Between C++ Templates and C# Generics</span></span>](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)
