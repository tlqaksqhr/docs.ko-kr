---
title: "인덱서(C# 프로그래밍 가이드)"
ms.date: 03/10/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.indexers
helpviewer_keywords:
- indexers [C#]
- C# language, indexers
ms.assetid: 022cd27d-d5e0-4cfe-8b97-dc018cc3355d
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: db49a602b83940cab3f87dea17accb92a2be825d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="indexers-c-programming-guide"></a><span data-ttu-id="34300-102">인덱서(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="34300-102">Indexers (C# Programming Guide)</span></span>

<span data-ttu-id="34300-103">인덱서에서는 클래스나 구조체의 인스턴스를 배열처럼 인덱싱할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34300-103">Indexers allow instances of a class or struct to be indexed just like arrays.</span></span> <span data-ttu-id="34300-104">인덱싱 값은 형식이나 인스턴스 멤버를 명시적으로 지정하지 않고도 설정하거나 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34300-104">The indexed value can be set or retrieved without explicitly specifying a type or instance member.</span></span> <span data-ttu-id="34300-105">인덱서는 해당 접근자가 매개 변수를 사용한다는 점을 제외하면 [속성](../../../csharp/programming-guide/classes-and-structs/properties.md)과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="34300-105">Indexers resemble [properties](../../../csharp/programming-guide/classes-and-structs/properties.md) except that their accessors take parameters.</span></span>  
 
 <span data-ttu-id="34300-106">다음 예제에서는 간단한 [get](../../../csharp/language-reference/keywords/get.md) 및 [set](../../../csharp/language-reference/keywords/set.md) 접근자 메서드를 사용해서 값을 할당하거나 검색하는 제네릭 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="34300-106">The following example defines a generic class with simple [get](../../../csharp/language-reference/keywords/get.md) and [set](../../../csharp/language-reference/keywords/set.md) accessor methods to assign and retrieve values.</span></span> <span data-ttu-id="34300-107">`Program` 클래스는 이 클래스의 인스턴스를 만들어 문자열을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="34300-107">The `Program` class creates an instance of this class for storing strings.</span></span>  
  
 [!code-csharp[indexers#1](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-1.cs)]  
  
> [!NOTE]
>  <span data-ttu-id="34300-108">추가 예제는 [관련 섹션](../../../csharp/programming-guide/indexers/index.md#BKMK_RelatedSections)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34300-108">For more examples, see [Related Sections](../../../csharp/programming-guide/indexers/index.md#BKMK_RelatedSections).</span></span>  
  
## <a name="expression-body-definitions"></a><span data-ttu-id="34300-109">식 본문 정의</span><span class="sxs-lookup"><span data-stu-id="34300-109">Expression Body Definitions</span></span>  
 
<span data-ttu-id="34300-110">인덱서의 get 또는 set 접근자는 값을 반환하거나 설정하는 단일 문으로 구성되는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="34300-110">It is common for an indexer's get or set accessor to consist of a single statement that either returns or sets a value.</span></span> <span data-ttu-id="34300-111">식 본문이 있는 멤버는 이 시나리오를 지원하기 위해 간단한 구문을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="34300-111">Expression-bodied members provide a simplified syntax to support this scenario.</span></span> <span data-ttu-id="34300-112">C# 6부터 읽기 전용 인덱서는 다음 예제와 같이 식 본문이 있는 멤버로 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34300-112">Starting with C# 6, a read-only indexer can be implemented as an expression-bodied member, as the following example shows.</span></span>

[!code-csharp[indexers#2](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-2.cs)]  

<span data-ttu-id="34300-113">`=>`에서 식 본문을 도입하며 `get` 키워드는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="34300-113">Note that `=>` introduces the expression body, and that the `get` keyword is not used.</span></span> 

<span data-ttu-id="34300-114">C# 7부터 get 및 set 접근자 모두를 식 본문 멤버로 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34300-114">Starting with C# 7, both the get and set accessor can be an implemented as expression-bodied members.</span></span> <span data-ttu-id="34300-115">이 경우 `get` 및 `set` 키워드를 둘 다 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34300-115">In this case, both `get` and `set` keywords must be used.</span></span> <span data-ttu-id="34300-116">예:</span><span class="sxs-lookup"><span data-stu-id="34300-116">For example:</span></span>

[!code-csharp[indexers#3](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-3.cs)]  
  
## <a name="indexers-overview"></a><span data-ttu-id="34300-117">인덱서 개요</span><span class="sxs-lookup"><span data-stu-id="34300-117">Indexers Overview</span></span>  
  
-   <span data-ttu-id="34300-118">인덱서를 사용하면 배열과 유사한 방식으로 개체를 인덱싱할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34300-118">Indexers enable objects to be indexed in a similar manner to arrays.</span></span>  
  
-   <span data-ttu-id="34300-119">`get` 접근자는 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="34300-119">A `get` accessor returns a value.</span></span> <span data-ttu-id="34300-120">`set` 접근자는 값을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="34300-120">A `set` accessor assigns a value.</span></span>  
  
-   <span data-ttu-id="34300-121">[this](../../../csharp/language-reference/keywords/this.md) 키워드는 인덱서를 정의하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="34300-121">The [this](../../../csharp/language-reference/keywords/this.md) keyword is used to define the indexer.</span></span>  
  
-   <span data-ttu-id="34300-122">[value](../../../csharp/language-reference/keywords/value.md) 키워드는 `set` 인덱서에서 할당하는 값을 정의하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="34300-122">The [value](../../../csharp/language-reference/keywords/value.md) keyword is used to define the value being assigned by the `set` indexer.</span></span>  
  
-   <span data-ttu-id="34300-123">인덱서는 정수 값으로 인덱싱될 필요가 없으며, 특정 조회 메커니즘을 정의하는 방법을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34300-123">Indexers do not have to be indexed by an integer value; it is up to you how to define the specific look-up mechanism.</span></span>  
  
-   <span data-ttu-id="34300-124">인덱서는 오버로드될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34300-124">Indexers can be overloaded.</span></span>  
  
-   <span data-ttu-id="34300-125">예를 들어 인덱서는 2차원 배열에 액세스하는 경우 둘 이상의 정식 매개 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34300-125">Indexers can have more than one formal parameter, for example, when accessing a two-dimensional array.</span></span>  
  
##  <a name="BKMK_RelatedSections"></a> <span data-ttu-id="34300-126">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="34300-126">Related Sections</span></span>  
  
-   [<span data-ttu-id="34300-127">인덱서 사용</span><span class="sxs-lookup"><span data-stu-id="34300-127">Using Indexers</span></span>](../../../csharp/programming-guide/indexers/using-indexers.md)  
  
-   [<span data-ttu-id="34300-128">인터페이스의 인덱서</span><span class="sxs-lookup"><span data-stu-id="34300-128">Indexers in Interfaces</span></span>](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md)  
  
-   [<span data-ttu-id="34300-129">속성 및 인덱서 비교</span><span class="sxs-lookup"><span data-stu-id="34300-129">Comparison Between Properties and Indexers</span></span>](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
  
-   [<span data-ttu-id="34300-130">접근자 접근성 제한</span><span class="sxs-lookup"><span data-stu-id="34300-130">Restricting Accessor Accessibility</span></span>](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="34300-131">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="34300-131">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="34300-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="34300-132">See Also</span></span>  
 [<span data-ttu-id="34300-133">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="34300-133">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="34300-134">속성</span><span class="sxs-lookup"><span data-stu-id="34300-134">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)
