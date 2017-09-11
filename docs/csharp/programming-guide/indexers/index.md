---
title: "인덱서(C# 프로그래밍 가이드)"
ms.date: 2017-03-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.indexers
dev_langs:
- CSharp
helpviewer_keywords:
- indexers [C#]
- C# language, indexers
ms.assetid: 022cd27d-d5e0-4cfe-8b97-dc018cc3355d
caps.latest.revision: 29
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
ms.openlocfilehash: 784308f3073114cd0c07cf15edae527a2654edec
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="indexers-c-programming-guide"></a><span data-ttu-id="b367b-102">인덱서(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="b367b-102">Indexers (C# Programming Guide)</span></span>

<span data-ttu-id="b367b-103">인덱서에서는 클래스나 구조체의 인스턴스를 배열처럼 인덱싱할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b367b-103">Indexers allow instances of a class or struct to be indexed just like arrays.</span></span> <span data-ttu-id="b367b-104">인덱싱 값은 형식이나 인스턴스 멤버를 명시적으로 지정하지 않고도 설정하거나 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b367b-104">The indexed value can be set or retrieved without explicitly specifying a type or instance member.</span></span> <span data-ttu-id="b367b-105">인덱서는 해당 접근자가 매개 변수를 사용한다는 점을 제외하면 [속성](../../../csharp/programming-guide/classes-and-structs/properties.md)과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="b367b-105">Indexers resemble [properties](../../../csharp/programming-guide/classes-and-structs/properties.md) except that their accessors take parameters.</span></span>  
 
 <span data-ttu-id="b367b-106">다음 예제에서는 간단한 [get](../../../csharp/language-reference/keywords/get.md) 및 [set](../../../csharp/language-reference/keywords/set.md) 접근자 메서드를 사용해서 값을 할당하거나 검색하는 제네릭 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b367b-106">The following example defines a generic class with simple [get](../../../csharp/language-reference/keywords/get.md) and [set](../../../csharp/language-reference/keywords/set.md) accessor methods to assign and retrieve values.</span></span> <span data-ttu-id="b367b-107">`Program` 클래스는 이 클래스의 인스턴스를 만들어 문자열을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="b367b-107">The `Program` class creates an instance of this class for storing strings.</span></span>  
  
 <span data-ttu-id="b367b-108">[!code-cs[indexers#1](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b367b-108">[!code-cs[indexers#1](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-1.cs)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b367b-109">추가 예제는 [관련 섹션](../../../csharp/programming-guide/indexers/index.md#BKMK_RelatedSections)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b367b-109">For more examples, see [Related Sections](../../../csharp/programming-guide/indexers/index.md#BKMK_RelatedSections).</span></span>  
  
## <a name="expression-body-definitions"></a><span data-ttu-id="b367b-110">식 본문 정의</span><span class="sxs-lookup"><span data-stu-id="b367b-110">Expression Body Definitions</span></span>  
 
<span data-ttu-id="b367b-111">인덱서의 get 또는 set 접근자는 값을 반환하거나 설정하는 단일 문으로 구성되는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="b367b-111">It is common for an indexer's get or set accessor to consist of a single statement that either returns or sets a value.</span></span> <span data-ttu-id="b367b-112">식 본문이 있는 멤버는 이 시나리오를 지원하기 위해 간단한 구문을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b367b-112">Expression-bodied members provide a simplified syntax to support this scenario.</span></span> <span data-ttu-id="b367b-113">C# 6부터 읽기 전용 인덱서는 다음 예제와 같이 식 본문이 있는 멤버로 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b367b-113">Starting with C# 6, a read-only indexer can be implemented as an expression-bodied member, as the following example shows.</span></span>

<span data-ttu-id="b367b-114">[!code-cs[indexers#2](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-2.cs)]</span><span class="sxs-lookup"><span data-stu-id="b367b-114">[!code-cs[indexers#2](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-2.cs)]</span></span>  

<span data-ttu-id="b367b-115">`=>`에서 식 본문을 도입하며 `get` 키워드는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b367b-115">Note that `=>` introduces the expression body, and that the `get` keyword is not used.</span></span> 

<span data-ttu-id="b367b-116">C# 7부터 get 및 set 접근자 모두를 식 본문 멤버로 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b367b-116">Starting with C# 7, both the get and set accessor can be an implemented as expression-bodied members.</span></span> <span data-ttu-id="b367b-117">이 경우 `get` 및 `set` 키워드를 둘 다 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b367b-117">In this case, both `get` and `set` keywords must be used.</span></span> <span data-ttu-id="b367b-118">예:</span><span class="sxs-lookup"><span data-stu-id="b367b-118">For example:</span></span>

<span data-ttu-id="b367b-119">[!code-cs[indexers#3](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-3.cs)]</span><span class="sxs-lookup"><span data-stu-id="b367b-119">[!code-cs[indexers#3](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-3.cs)]</span></span>  
  
## <a name="indexers-overview"></a><span data-ttu-id="b367b-120">인덱서 개요</span><span class="sxs-lookup"><span data-stu-id="b367b-120">Indexers Overview</span></span>  
  
-   <span data-ttu-id="b367b-121">인덱서를 사용하면 배열과 유사한 방식으로 개체를 인덱싱할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b367b-121">Indexers enable objects to be indexed in a similar manner to arrays.</span></span>  
  
-   <span data-ttu-id="b367b-122">`get` 접근자는 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b367b-122">A `get` accessor returns a value.</span></span> <span data-ttu-id="b367b-123">`set` 접근자는 값을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="b367b-123">A `set` accessor assigns a value.</span></span>  
  
-   <span data-ttu-id="b367b-124">[this](../../../csharp/language-reference/keywords/this.md) 키워드는 인덱서를 정의하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b367b-124">The [this](../../../csharp/language-reference/keywords/this.md) keyword is used to define the indexer.</span></span>  
  
-   <span data-ttu-id="b367b-125">[value](../../../csharp/language-reference/keywords/value.md) 키워드는 `set` 인덱서에서 할당하는 값을 정의하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b367b-125">The [value](../../../csharp/language-reference/keywords/value.md) keyword is used to define the value being assigned by the `set` indexer.</span></span>  
  
-   <span data-ttu-id="b367b-126">인덱서는 정수 값으로 인덱싱될 필요가 없으며, 특정 조회 메커니즘을 정의하는 방법을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b367b-126">Indexers do not have to be indexed by an integer value; it is up to you how to define the specific look-up mechanism.</span></span>  
  
-   <span data-ttu-id="b367b-127">인덱서는 오버로드될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b367b-127">Indexers can be overloaded.</span></span>  
  
-   <span data-ttu-id="b367b-128">예를 들어 인덱서는 2차원 배열에 액세스하는 경우 둘 이상의 정식 매개 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b367b-128">Indexers can have more than one formal parameter, for example, when accessing a two-dimensional array.</span></span>  
  
##  <span data-ttu-id="b367b-129"><a name="BKMK_RelatedSections"></a> 관련 섹션</span><span class="sxs-lookup"><span data-stu-id="b367b-129"><a name="BKMK_RelatedSections"></a> Related Sections</span></span>  
  
-   [<span data-ttu-id="b367b-130">인덱서 사용</span><span class="sxs-lookup"><span data-stu-id="b367b-130">Using Indexers</span></span>](../../../csharp/programming-guide/indexers/using-indexers.md)  
  
-   [<span data-ttu-id="b367b-131">인터페이스의 인덱서</span><span class="sxs-lookup"><span data-stu-id="b367b-131">Indexers in Interfaces</span></span>](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md)  
  
-   [<span data-ttu-id="b367b-132">속성 및 인덱서 비교</span><span class="sxs-lookup"><span data-stu-id="b367b-132">Comparison Between Properties and Indexers</span></span>](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
  
-   [<span data-ttu-id="b367b-133">접근자 접근성 제한</span><span class="sxs-lookup"><span data-stu-id="b367b-133">Restricting Accessor Accessibility</span></span>](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="b367b-134">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="b367b-134">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b367b-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b367b-135">See Also</span></span>  
 <span data-ttu-id="b367b-136">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b367b-136">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="b367b-137">속성</span><span class="sxs-lookup"><span data-stu-id="b367b-137">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)

