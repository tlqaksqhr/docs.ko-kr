---
title: "제네릭(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, generics
- generics [C#]
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
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
ms.sourcegitcommit: 1e548df4de2c07934313311a7ffcfae82be76000
ms.openlocfilehash: de81058173b0985577474e8601aa84d4e83336a5
ms.contentlocale: ko-kr
ms.lasthandoff: 08/29/2017

---
# <a name="generics-c-programming-guide"></a><span data-ttu-id="4fc57-102">제네릭(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="4fc57-102">Generics (C# Programming Guide)</span></span>
<span data-ttu-id="4fc57-103">제네릭이 C# 언어 및 CLR(공용 언어 런타임)의 버전 2.0에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc57-103">Generics were added to version 2.0 of the C# language and the common language runtime (CLR).</span></span> <span data-ttu-id="4fc57-104">제네릭은 .NET Framework에 클라이언트 코드에서 클래스 또는 메서드를 선언하고 인스턴스화할 때까지 하나 이상의 형식 사양을 따르는 클래스 및 메서드를 디자인할 수 있도록 만드는 형식 매개 변수 개념을 도입합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc57-104">Generics introduce to the .NET Framework the concept of type parameters, which make it possible to design classes and methods that defer the specification of one or more types until the class or method is declared and instantiated by client code.</span></span> <span data-ttu-id="4fc57-105">예를 들어 제네릭 형식 매개 변수 T를 사용하여 여기에 표시된 것처럼, 다른 클라이언트 코드에서 런타임 캐스팅 또는 boxing 작업에 대한 비용이나 위험을 발생하지 않고 사용할 수 있는 단일 클래스를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc57-105">For example, by using a generic type parameter T you can write a single class that other client code can use without incurring the cost or risk of runtime casts or boxing operations, as shown here:</span></span>  
  
 <span data-ttu-id="4fc57-106">[!code-cs[csProgGuideGenerics#1](../../../csharp/programming-guide/generics/codesnippet/CSharp/index_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="4fc57-106">[!code-cs[csProgGuideGenerics#1](../../../csharp/programming-guide/generics/codesnippet/CSharp/index_1.cs)]</span></span>  
  
## <a name="generics-overview"></a><span data-ttu-id="4fc57-107">제네릭 개요</span><span class="sxs-lookup"><span data-stu-id="4fc57-107">Generics Overview</span></span>  
  
-   <span data-ttu-id="4fc57-108">제네릭 형식을 사용하여 코드 재사용, 형식 안전성 및 성능을 최대화합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc57-108">Use generic types to maximize code reuse, type safety, and performance.</span></span>  
  
-   <span data-ttu-id="4fc57-109">가장 일반적으로 제네릭은 컬렉션 클래스를 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fc57-109">The most common use of generics is to create collection classes.</span></span>  
  
-   <span data-ttu-id="4fc57-110">.NET Framework 클래스 라이브러리에는 <xref:System.Collections.Generic> 네임스페이스에 여러 가지 새로운 제네릭 컬렉션 클래스가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fc57-110">The .NET Framework class library contains several new generic collection classes in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="4fc57-111">이러한 제네릭 컬렉션 클래스는 가능할 때마다 <xref:System.Collections> 네임스페이스의 <xref:System.Collections.ArrayList>처럼 클래스 대신 사용되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc57-111">These should be used whenever possible instead of classes such as <xref:System.Collections.ArrayList> in the <xref:System.Collections> namespace.</span></span>  
  
-   <span data-ttu-id="4fc57-112">사용자 고유의 제네릭 인터페이스, 클래스, 메서드, 이벤트 및 대리자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc57-112">You can create your own generic interfaces, classes, methods, events and delegates.</span></span>  
  
-   <span data-ttu-id="4fc57-113">제네릭 클래스는 특정 데이터 형식의 메서드에 액세스할 수 있도록 제한될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc57-113">Generic classes may be constrained to enable access to methods on particular data types.</span></span>  
  
-   <span data-ttu-id="4fc57-114">제네릭 데이터 형식에 사용되는 형식에 대한 정보는 리플렉션을 사용하여 런타임 시 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc57-114">Information on the types that are used in a generic data type may be obtained at run-time by using reflection.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4fc57-115">관련 단원</span><span class="sxs-lookup"><span data-stu-id="4fc57-115">Related Sections</span></span>  
 <span data-ttu-id="4fc57-116">추가 정보</span><span class="sxs-lookup"><span data-stu-id="4fc57-116">For more information:</span></span>  
  
-   [<span data-ttu-id="4fc57-117">제네릭 소개</span><span class="sxs-lookup"><span data-stu-id="4fc57-117">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
  
-   [<span data-ttu-id="4fc57-118">제네릭의 장점</span><span class="sxs-lookup"><span data-stu-id="4fc57-118">Benefits of Generics</span></span>](../../../csharp/programming-guide/generics/benefits-of-generics.md)  
  
-   [<span data-ttu-id="4fc57-119">제네릭 형식 매개 변수</span><span class="sxs-lookup"><span data-stu-id="4fc57-119">Generic Type Parameters</span></span>](../../../csharp/programming-guide/generics/generic-type-parameters.md)  
  
-   [<span data-ttu-id="4fc57-120">형식 매개 변수에 대한 제약 조건</span><span class="sxs-lookup"><span data-stu-id="4fc57-120">Constraints on Type Parameters</span></span>](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)  
  
-   [<span data-ttu-id="4fc57-121">제네릭 클래스</span><span class="sxs-lookup"><span data-stu-id="4fc57-121">Generic Classes</span></span>](../../../csharp/programming-guide/generics/generic-classes.md)  
  
-   [<span data-ttu-id="4fc57-122">제네릭 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4fc57-122">Generic Interfaces</span></span>](../../../csharp/programming-guide/generics/generic-interfaces.md)  
  
-   [<span data-ttu-id="4fc57-123">제네릭 메서드</span><span class="sxs-lookup"><span data-stu-id="4fc57-123">Generic Methods</span></span>](../../../csharp/programming-guide/generics/generic-methods.md)  
  
-   [<span data-ttu-id="4fc57-124">제네릭 대리자</span><span class="sxs-lookup"><span data-stu-id="4fc57-124">Generic Delegates</span></span>](../../../csharp/programming-guide/generics/generic-delegates.md)  
  
-   [<span data-ttu-id="4fc57-125">C++ 템플릿과 C# 제네릭의 차이점</span><span class="sxs-lookup"><span data-stu-id="4fc57-125">Differences Between C++ Templates and C# Generics</span></span>](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)  
  
-   [<span data-ttu-id="4fc57-126">제네릭 및 리플렉션</span><span class="sxs-lookup"><span data-stu-id="4fc57-126">Generics and Reflection</span></span>](../../../csharp/programming-guide/generics/generics-and-reflection.md)  
  
-   [<span data-ttu-id="4fc57-127">런타임의 제네릭</span><span class="sxs-lookup"><span data-stu-id="4fc57-127">Generics in the Run Time</span></span>](../../../csharp/programming-guide/generics/generics-in-the-run-time.md)  
  
-   [<span data-ttu-id="4fc57-128">.NET Framework 클래스 라이브러리의 제네릭</span><span class="sxs-lookup"><span data-stu-id="4fc57-128">Generics in the .NET Framework Class Library</span></span>](../../../csharp/programming-guide/generics/generics-in-the-net-framework-class-library.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="4fc57-129">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="4fc57-129">C# Language Specification</span></span>  
 <span data-ttu-id="4fc57-130">자세한 내용은 [C# 언어 사양](../../../csharp/language-reference/language-specification/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4fc57-130">For more information, see the [C# Language Specification](../../../csharp/language-reference/language-specification/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fc57-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4fc57-131">See Also</span></span>  
 <span data-ttu-id="4fc57-132"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="4fc57-132"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="4fc57-133">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="4fc57-133">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="4fc57-134">[형식](../../../csharp/programming-guide/types/index.md) </span><span class="sxs-lookup"><span data-stu-id="4fc57-134">[Types](../../../csharp/programming-guide/types/index.md) </span></span>  
 <span data-ttu-id="4fc57-135">[\<typeparam>](../../../csharp/programming-guide/xmldoc/typeparam.md) </span><span class="sxs-lookup"><span data-stu-id="4fc57-135">[\<typeparam>](../../../csharp/programming-guide/xmldoc/typeparam.md) </span></span>  
 [<span data-ttu-id="4fc57-136">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="4fc57-136">\<typeparamref></span></span>](../../../csharp/programming-guide/xmldoc/typeparamref.md)

