---
title: "런타임의 제네릭(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- generics [C#], at run time
ms.assetid: 119df7e6-9ceb-49df-af36-24f8f8c0747f
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5ef0b63b293ec277ebf9331e8f282ce2c1692d31
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="generics-in-the-run-time-c-programming-guide"></a><span data-ttu-id="fa593-102">런타임의 제네릭(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="fa593-102">Generics in the Run Time (C# Programming Guide)</span></span>
<span data-ttu-id="fa593-103">제네릭 형식 또는 메서드가 MSIL(Microsoft Intermediate Language)로 컴파일되면 자체적으로 형식 매개 변수를 갖는 것으로 식별하는 메타데이터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa593-103">When a generic type or method is compiled into Microsoft intermediate language (MSIL), it contains metadata that identifies it as having type parameters.</span></span> <span data-ttu-id="fa593-104">제네릭 형식의 MSIL이 사용되는 방식은 제공된 형식 매개 변수가 값 형식인지 참조 형식인지에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="fa593-104">How the MSIL for a generic type is used differs based on whether the supplied type parameter is a value type or reference type.</span></span>  
  
 <span data-ttu-id="fa593-105">값 형식을 매개 변수로 사용하여 제네릭 형식을 처음 생성할 경우 런타임에서는 제공된 매개 변수를 MSIL의 해당 위치에 대체하여 특수화된 제네릭 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa593-105">When a generic type is first constructed with a value type as a parameter, the runtime creates a specialized generic type with the supplied parameter or parameters substituted in the appropriate locations in the MSIL.</span></span> <span data-ttu-id="fa593-106">고유한 값 형식이 매개 변수로 사용될 때마다 특수화된 제네릭 형식이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="fa593-106">Specialized generic types are created one time for each unique value type that is used as a parameter.</span></span>  
  
 <span data-ttu-id="fa593-107">예를 들어 프로그램 코드에서 다음과 같이 정수로 구성된 스택을 선언한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa593-107">For example, suppose your program code declared a stack that is constructed of integers:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#42](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_1.cs)]  
  
 <span data-ttu-id="fa593-108">이 시점에서 런타임은 매개 변수를 정수로 적절히 대체하여 특수화된 버전의 <xref:System.Collections.Generic.Stack%601> 클래스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="fa593-108">At this point, the runtime generates a specialized version of the <xref:System.Collections.Generic.Stack%601> class that has the integer substituted appropriately for its parameter.</span></span> <span data-ttu-id="fa593-109">이제부터 프로그램 코드에서 정수 스택을 사용하면 런타임은 생성된 특수화 <xref:System.Collections.Generic.Stack%601> 클래스를 다시 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa593-109">Now, whenever your program code uses a stack of integers, the runtime reuses the generated specialized <xref:System.Collections.Generic.Stack%601> class.</span></span> <span data-ttu-id="fa593-110">다음 예제에서는 `Stack<int>` 코드의 단일 인스턴스를 공유하는 정수 스택의 두 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa593-110">In the following example, two instances of a stack of integers are created, and they share a single instance of the `Stack<int>` code:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#43](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_2.cs)]  
  
 <span data-ttu-id="fa593-111">그러나 코드의 다른 지점에서 `long`과 같이 값 형식이 다르거나, 사용자 정의된 구조체를 매개 변수로 사용하는 다른 <xref:System.Collections.Generic.Stack%601> 클래스를 만들었다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="fa593-111">However, suppose that another <xref:System.Collections.Generic.Stack%601> class with a different value type such as a `long` or a user-defined structure as its parameter is created at another point in your code.</span></span> <span data-ttu-id="fa593-112">이 경우 런타임에서는 제네릭 형식의 다른 버전을 생성하여 MSIL의 적절한 위치에 `long`을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="fa593-112">As a result, the runtime generates another version of the generic type and substitutes a `long` in the appropriate locations in MSIL.</span></span> <span data-ttu-id="fa593-113">특수화된 각 제네릭 클래스에는 기본적으로 값 형식이 포함되므로 변환은 더 이상 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa593-113">Conversions are no longer necessary because each specialized generic class natively contains the value type.</span></span>  
  
 <span data-ttu-id="fa593-114">참조 형식에 대해서는 제네릭의 작동 방식이 조금 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="fa593-114">Generics work somewhat differently for reference types.</span></span> <span data-ttu-id="fa593-115">참조 형식을 사용하여 제네릭 형식이 처음 생성될 때 런타임에서는 MSIL의 매개 변수를 개체 참조로 대체하여 특수화된 제네릭 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa593-115">The first time a generic type is constructed with any reference type, the runtime creates a specialized generic type with object references substituted for the parameters in the MSIL.</span></span> <span data-ttu-id="fa593-116">이후 참조 형식과 관계없이 참조 형식을 매개 변수로 사용하여 생성된 형식이 인스턴스화될 때마다 런타임에서는 이전에 만든 특수화된 버전의 제네릭 형식을 다시 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa593-116">Then, every time that a constructed type is instantiated with a reference type as its parameter, regardless of what type it is, the runtime reuses the previously created specialized version of the generic type.</span></span> <span data-ttu-id="fa593-117">이는 모든 참조의 크기가 동일하기 때문에 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="fa593-117">This is possible because all references are the same size.</span></span>  
  
 <span data-ttu-id="fa593-118">예를 들어 `Customer` 클래스와 `Order` 클래스라는 두 참조 형식이 있고 `Customer` 형식의 스택을 만들었다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa593-118">For example, suppose you had two reference types, a `Customer` class and an `Order` class, and also suppose that you created a stack of `Customer` types:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#47](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_3.cs)]  
  
 [!code-csharp[csProgGuideGenerics#44](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_4.cs)]  
  
 <span data-ttu-id="fa593-119">이 시점에서 런타임은 데이터를 저장하는 대신 이후에 채워질 개체 참조를 저장하는 특수화된 버전의 <xref:System.Collections.Generic.Stack%601> 클래스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="fa593-119">At this point, the runtime generates a specialized version of the <xref:System.Collections.Generic.Stack%601> class that stores object references that will be filled in later instead of storing data.</span></span> <span data-ttu-id="fa593-120">다음 코드 줄에서 `Order`라는 다른 참조 형식의 스택을 만든다고 가정해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="fa593-120">Suppose the next line of code creates a stack of another reference type, which is named `Order`:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#45](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_5.cs)]  
  
 <span data-ttu-id="fa593-121">값 형식과는 달리 `Order` 형식에 대한 또 다른 특수화된 버전의 <xref:System.Collections.Generic.Stack%601> 클래스는 만들어지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa593-121">Unlike with value types, another specialized version of the <xref:System.Collections.Generic.Stack%601> class is not created for the `Order` type.</span></span> <span data-ttu-id="fa593-122">대신 특수화된 버전의 <xref:System.Collections.Generic.Stack%601> 클래스 인스턴스가 만들어지고 `orders` 변수가 이 인스턴스를 참조하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa593-122">Instead, an instance of the specialized version of the <xref:System.Collections.Generic.Stack%601> class is created and the `orders` variable is set to reference it.</span></span> <span data-ttu-id="fa593-123">이후에 `Customer` 형식의 스택을 만드는 코드 줄이 나타난다고 가정해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="fa593-123">Suppose that you then encountered a line of code to create a stack of a `Customer` type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#46](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_6.cs)]  
  
 <span data-ttu-id="fa593-124">`Order` 형식을 사용하여 만든 <xref:System.Collections.Generic.Stack%601> 클래스를 사용한 경우와 마찬가지로 특수화된 <xref:System.Collections.Generic.Stack%601> 클래스의 다른 인스턴스가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa593-124">As with the previous use of the <xref:System.Collections.Generic.Stack%601> class created by using the `Order` type, another instance of the specialized <xref:System.Collections.Generic.Stack%601> class is created.</span></span> <span data-ttu-id="fa593-125">여기에 포함된 포인터는 `Customer` 형식과 크기가 같은 메모리 영역을 참조하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa593-125">The pointers that are contained therein are set to reference an area of memory the size of a `Customer` type.</span></span> <span data-ttu-id="fa593-126">참조 형식의 수는 프로그램마다 크게 다를 수 있으므로, 제네릭을 C# 방식으로 구현하면 컴파일러가 참조 형식의 제네릭 클래스에 대해 만드는 특수화된 클래스의 수가 1개로 줄어들어 코드가 매우 간결해집니다.</span><span class="sxs-lookup"><span data-stu-id="fa593-126">Because the number of reference types can vary wildly from program to program, the C# implementation of generics greatly reduces the amount of code by reducing to one the number of specialized classes created by the compiler for generic classes of reference types.</span></span>  
  
 <span data-ttu-id="fa593-127">그뿐만 아니라, 값 형식 또는 참조 형식 매개 변수를 사용하여 제네릭 C# 클래스가 인스턴스화되면 런타임에 리플렉션을 통해 쿼리할 수 있고 실제 형식과 형식 매개 변수를 모두 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa593-127">Moreover, when a generic C# class is instantiated by using a value type or reference type parameter, reflection can query it at runtime and both its actual type and its type parameter can be ascertained.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa593-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fa593-128">See Also</span></span>  
 <xref:System.Collections.Generic>  
 [<span data-ttu-id="fa593-129">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="fa593-129">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="fa593-130">제네릭 소개</span><span class="sxs-lookup"><span data-stu-id="fa593-130">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
 [<span data-ttu-id="fa593-131">제네릭</span><span class="sxs-lookup"><span data-stu-id="fa593-131">Generics</span></span>](~/docs/standard/generics/index.md)
