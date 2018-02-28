---
title: "제네릭의 장점(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- generics [C#], benefits
ms.assetid: 80f037cd-9ea7-48be-bfc1-219bfb2d4277
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2eb4aad3d23e459af738045b37ae3f1e8f33da06
ms.sourcegitcommit: 96cc82cac4650adfb65ba351506d8a8fbcd17b5c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2018
---
# <a name="benefits-of-generics-c-programming-guide"></a><span data-ttu-id="278d8-102">제네릭의 장점(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="278d8-102">Benefits of Generics (C# Programming Guide)</span></span>
<span data-ttu-id="278d8-103">제네릭은 형식을 유니버설 기본 형식 <xref:System.Object>으로/에서 캐스팅하여 일반화가 수행되는 이전 버전의 공용 언어 런타임 및 C# 언어의 제한 사항에 대한 솔루션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="278d8-103">Generics provide the solution to a limitation in earlier versions of the common language runtime and the C# language in which generalization is accomplished by casting types to and from the universal base type <xref:System.Object>.</span></span> <span data-ttu-id="278d8-104">제네릭 클래스를 만들면 컴파일 시간에 형식이 안전한 컬렉션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="278d8-104">By creating a generic class, you can create a collection that is type-safe at compile-time.</span></span>  
  
 <span data-ttu-id="278d8-105">.NET 클래스 라이브러리의 <xref:System.Collections.ArrayList> 컬렉션 클래스를 사용하는 간단한 프로그램을 작성하면 제네릭이 아닌 컬렉션 클래스를 사용할 경우의 제한 사항을 보여 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="278d8-105">The limitations of using non-generic collection classes can be demonstrated by writing a short program that uses the <xref:System.Collections.ArrayList> collection class from the .NET class library.</span></span> <span data-ttu-id="278d8-106"><xref:System.Collections.ArrayList> 클래스의 인스턴스는 모든 참조 또는 값 형식을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="278d8-106">An instance of the <xref:System.Collections.ArrayList> class can store any reference or value type.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#4](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_1.cs)]  
  
 <span data-ttu-id="278d8-107">하지만 이 편리함에는 대가가 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="278d8-107">But this convenience comes at a cost.</span></span> <span data-ttu-id="278d8-108"><xref:System.Collections.ArrayList>에 추가된 모든 참조 형식이나 값 형식이 암시적으로 <xref:System.Object>로 업캐스팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="278d8-108">Any reference or value type that is added to an <xref:System.Collections.ArrayList> is implicitly upcast to <xref:System.Object>.</span></span> <span data-ttu-id="278d8-109">항목이 값 형식이면 목록에 추가될 때 boxing하고 검색될 때 unboxing해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="278d8-109">If the items are value types, they must be boxed when they are added to the list, and unboxed when they are retrieved.</span></span> <span data-ttu-id="278d8-110">캐스팅과 boxing 및 unboxing 작업은 모두 성능을 저하시키므로 큰 컬렉션을 반복해야 하는 시나리오에서는 boxing 및 unboxing이 큰 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="278d8-110">Both the casting and the boxing and unboxing operations decrease performance; the effect of boxing and unboxing can be very significant in scenarios where you must iterate over large collections.</span></span>  
  
 <span data-ttu-id="278d8-111">다른 제한 사항은 컴파일 시간 형식 검사가 없다는 것입니다. <xref:System.Collections.ArrayList>가 모든 항목을 <xref:System.Object>로 캐스팅하기 때문에 컴파일 시간에는 클라이언트 코드에서 다음과 같은 작업을 수행하지 않도록 차단할 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="278d8-111">The other limitation is lack of compile-time type checking; because an <xref:System.Collections.ArrayList> casts everything to <xref:System.Object>, there is no way at compile-time to prevent client code from doing something such as this:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#5](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_2.cs)]  
  
 <span data-ttu-id="278d8-112">완벽하게 허용되고, 다른 유형의 컬렉션을 만드는 경우 의도적일 때도 있지만 단일 <xref:System.Collections.ArrayList>에 문자열과 `ints`를 함께 사용하면 프로그래밍 오류가 발생할 가능성이 크며 이 오류는 런타임 시까지 검색되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="278d8-112">Although perfectly acceptable and sometimes intentional if you are creating a heterogeneous collection, combining strings and `ints` in a single <xref:System.Collections.ArrayList> is more likely to be a programming error, and this error will not be detected until runtime.</span></span>  
  
 <span data-ttu-id="278d8-113">C# 언어의 버전 1.0 및 1.1에서는 사용자 고유의 형식별 컬렉션을 작성해야만 .NET Framework 기본 클래스 라이브러리 컬렉션 클래스에 일반화된 코드가 포함될 위험을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="278d8-113">In versions 1.0 and 1.1 of the C# language, you could avoid the dangers of generalized code in the .NET Framework base class library collection classes only by writing your own type specific collections.</span></span> <span data-ttu-id="278d8-114">물론, 이러한 클래스는 둘 이상의 데이터 형식에 다시 사용할 수 없기 때문에 일반화의 이점이 손실되며 저장할 각 형식에 대한 클래스를 다시 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="278d8-114">Of course, because such a class is not reusable for more than one data type, you lose the benefits of generalization, and you have to rewrite the class for each type that will be stored.</span></span>  
  
 <span data-ttu-id="278d8-115"><xref:System.Collections.ArrayList> 및 다른 유사한 클래스에 실제로 필요한 것은 클라이언트 코드에서 사용할 특정 데이터 형식을 인스턴스 단위로 지정할 수 있는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="278d8-115">What <xref:System.Collections.ArrayList> and other similar classes really need is a way for client code to specify, on a per-instance basis, the particular data type that they intend to use.</span></span> <span data-ttu-id="278d8-116">그러면 <xref:System.Object>로 업캐스팅할 필요가 없으며 컴파일러가 형식을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="278d8-116">That would eliminate the need for the upcast to <xref:System.Object> and would also make it possible for the compiler to do type checking.</span></span> <span data-ttu-id="278d8-117">즉, <xref:System.Collections.ArrayList>에 형식 매개 변수가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="278d8-117">In other words, <xref:System.Collections.ArrayList> needs a type parameter.</span></span> <span data-ttu-id="278d8-118">제네릭은 바로 이것을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="278d8-118">That is exactly what generics provide.</span></span> <span data-ttu-id="278d8-119">제네릭 <xref:System.Collections.Generic.List%601> 컬렉션의 <xref:System.Collections.Generic> 네임스페이스에서 컬렉션에 항목을 추가하는 동일한 작업은 다음과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="278d8-119">In the generic <xref:System.Collections.Generic.List%601> collection, in the <xref:System.Collections.Generic> namespace, the same operation of adding items to the collection resembles this:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#6](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_3.cs)]  
  
 <span data-ttu-id="278d8-120">클라이언트 코드의 경우 <xref:System.Collections.ArrayList>에 해당하는 <xref:System.Collections.Generic.List%601>로 추가된 유일한 구문은 선언 및 인스턴스화의 형식 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="278d8-120">For client code, the only added syntax with <xref:System.Collections.Generic.List%601> compared to <xref:System.Collections.ArrayList> is the type argument in the declaration and instantiation.</span></span> <span data-ttu-id="278d8-121">코딩이 약간 더 복잡하지만 <xref:System.Collections.ArrayList>보다 안전할 뿐 아니라 특히 목록 항목이 값 형식인 경우 훨씬 더 빠른 목록을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="278d8-121">In return for this slightly more coding complexity, you can create a list that is not only safer than <xref:System.Collections.ArrayList>, but also significantly faster, especially when the list items are value types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="278d8-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="278d8-122">See Also</span></span>  
 <xref:System.Collections.Generic>  
 [<span data-ttu-id="278d8-123">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="278d8-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="278d8-124">제네릭 소개</span><span class="sxs-lookup"><span data-stu-id="278d8-124">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
 [<span data-ttu-id="278d8-125">boxing 및 unboxing</span><span class="sxs-lookup"><span data-stu-id="278d8-125">Boxing and Unboxing</span></span>](../../../csharp/programming-guide/types/boxing-and-unboxing.md)  
 [<span data-ttu-id="278d8-126">제네릭 컬렉션 사용 기준</span><span class="sxs-lookup"><span data-stu-id="278d8-126">When to Use Generic Collections</span></span>](../../../standard/collections/when-to-use-generic-collections.md)  
 [<span data-ttu-id="278d8-127">컬렉션에 대한 지침</span><span class="sxs-lookup"><span data-stu-id="278d8-127">Guidelines for Collections</span></span>](../../../standard/design-guidelines/guidelines-for-collections.md)   
