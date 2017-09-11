---
title: "생성자(C# 프로그래밍 가이드)"
ms.date: 2017-05-05
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- constructors [C#]
- classes [C#], constructors
- C# language, constructors
ms.assetid: df2e2e9d-7998-418b-8e7d-890c17ff6c95
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 400afcda2fe30bf0e3621ee4c4247486e01d3ee4
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="constructors-c-programming-guide"></a><span data-ttu-id="c1a50-102">생성자(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="c1a50-102">Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="c1a50-103">[class](../../../csharp/language-reference/keywords/class.md) 또는 [struct](../../../csharp/language-reference/keywords/struct.md)를 만들 때마다 해당 생성자가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1a50-103">Whenever a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md) is created, its constructor is called.</span></span> <span data-ttu-id="c1a50-104">클래스 또는 구조체에는 서로 다른 인수를 사용하는 여러 생성자가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a50-104">A class or struct may have multiple constructors that take different arguments.</span></span> <span data-ttu-id="c1a50-105">프로그래머는 생성자를 통해 기본값을 설정하고, 인스턴스화를 제한하며, 유연하고 읽기 쉬운 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a50-105">Constructors enable the programmer to set default values, limit instantiation, and write code that is flexible and easy to read.</span></span> <span data-ttu-id="c1a50-106">자세한 내용 및 예제는 [생성자 사용](../../../csharp/programming-guide/classes-and-structs/using-constructors.md) 및 [인스턴스 생성자](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c1a50-106">For more information and examples, see [Using Constructors](../../../csharp/programming-guide/classes-and-structs/using-constructors.md) and [Instance Constructors](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span></span>  

## <a name="default-constructors"></a><span data-ttu-id="c1a50-107">기본 생성자</span><span class="sxs-lookup"><span data-stu-id="c1a50-107">Default constructors</span></span>
  
<span data-ttu-id="c1a50-108">클래스에 대한 생성자를 제공하지 않으면 C#이 기본적으로 개체를 인스턴스화하고 멤버 변수를 [기본값 표](../../../csharp/language-reference/keywords/default-values-table.md)에 나열된 기본값으로 설정하는 생성자를 새로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c1a50-108">If you don't provide a constructor for your class, C# creates one by default that instantiates the object and sets member variables to the default values as listed in the [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="c1a50-109">구조체에 대한 생성자를 제공하지 않으면 C#이 *암시적 기본 생성자*에서 응답하여 값 형식의 각 필드를 [기본값 표](../../../csharp/language-reference/keywords/default-values-table.md)에 나열된 기본값으로 자동으로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a50-109">If you don't provide a constructor for your struct, C# relies on an *implicit default constructor* to automatically initialize each field of a value type to its default value as listed in the [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="c1a50-110">자세한 내용 및 예제는 [인스턴스 생성자](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c1a50-110">For more information and examples, see [Instance Constructors](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span></span>  

## <a name="constructor-syntax"></a><span data-ttu-id="c1a50-111">생성자 구문</span><span class="sxs-lookup"><span data-stu-id="c1a50-111">Constructor syntax</span></span>

<span data-ttu-id="c1a50-112">생성자는 이름이 해당 형식의 이름과 동일한 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="c1a50-112">A constructor is a method whose name is the same as the name of its type.</span></span> <span data-ttu-id="c1a50-113">해당 메서드 시그니처에는 메서드 이름과 매개 변수 목록만 포함되고 반환 형식은 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a50-113">Its method signature includes only the method name and its parameter list; it does not include a return type.</span></span> <span data-ttu-id="c1a50-114">다음 예제에서는 `Person`이라는 클래스에 대한 생성자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c1a50-114">The following example shows the constructor for a class named `Person`.</span></span>

<span data-ttu-id="c1a50-115">[!code-cs[생성자](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="c1a50-115">[!code-cs[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#1)]</span></span>  

<span data-ttu-id="c1a50-116">생성자를 단일 문으로 구현할 수 있는 경우 [식 본문 정의](../statements-expressions-operators/expression-bodied-members.md)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a50-116">If a constructor can be implemented as a single statement, you can use an [expression body definition](../statements-expressions-operators/expression-bodied-members.md).</span></span> <span data-ttu-id="c1a50-117">다음 예제에서는 생성자에 *name*이라는 단일 문자열 매개 변수가 있는 `Location` 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a50-117">The following example defines a `Location` class whose constructor has a single string parameter named *name*.</span></span> <span data-ttu-id="c1a50-118">식 본문 정의에서 `locationName` 필드에 인수를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a50-118">The expression body definition assigns the argument to the `locationName` field.</span></span>

<span data-ttu-id="c1a50-119">[!code-cs[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="c1a50-119">[!code-cs[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]</span></span>  

## <a name="static-constructors"></a><span data-ttu-id="c1a50-120">정적 생성자</span><span class="sxs-lookup"><span data-stu-id="c1a50-120">Static constructors</span></span>

<span data-ttu-id="c1a50-121">앞의 예제에서는 새 개체를 만드는 인스턴스 생성자를 모두 보여 주었습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a50-121">The previous examples have all shown instance constructors, which create a new object.</span></span> <span data-ttu-id="c1a50-122">클래스 또는 구조체에 형식의 정적 멤버를 초기화하는 정적 생성자도 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a50-122">A class or struct can also have a static constructor, which initializes static members of the type.</span></span>  <span data-ttu-id="c1a50-123">정적 생성자에는 매개 변수가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a50-123">Static constructors are parameterless.</span></span> <span data-ttu-id="c1a50-124">정적 필드를 초기화하는 정적 생성자를 제공하지 않으면 C# 컴파일러가 정적 필드를 [기본값 표](../../../csharp/language-reference/keywords/default-values-table.md)에 나열된 기본값으로 초기화하는 기본 정적 생성자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a50-124">If you don't provide a static constructor to initialize static fields, the C# compiler will supply a default static constructor that initializes static fields to their default value as listed in the [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> 

<span data-ttu-id="c1a50-125">다음 예제에서는 정적 생성자를 사용하여 정적 필드를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a50-125">The following example uses a static constructor to initialize a static field.</span></span>

<span data-ttu-id="c1a50-126">[!code-cs[생성자](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#2)]</span><span class="sxs-lookup"><span data-stu-id="c1a50-126">[!code-cs[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#2)]</span></span>  

<span data-ttu-id="c1a50-127">다음 예제와 같이 식 본문 정의를 사용하여 정적 생성자를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a50-127">You can also define a static constructor with an expression body definition, as the following example shows.</span></span> 

<span data-ttu-id="c1a50-128">[!code-cs[생성자](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#3)]</span><span class="sxs-lookup"><span data-stu-id="c1a50-128">[!code-cs[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#3)]</span></span>  

<span data-ttu-id="c1a50-129">자세한 내용 및 예제는 [정적 생성자](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c1a50-129">For more information and examples, see [Static Constructors](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c1a50-130">단원 내용</span><span class="sxs-lookup"><span data-stu-id="c1a50-130">In This Section</span></span>  
 [<span data-ttu-id="c1a50-131">생성자 사용</span><span class="sxs-lookup"><span data-stu-id="c1a50-131">Using Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)  
  
 [<span data-ttu-id="c1a50-132">인스턴스 생성자</span><span class="sxs-lookup"><span data-stu-id="c1a50-132">Instance Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)  
  
 [<span data-ttu-id="c1a50-133">전용 생성자</span><span class="sxs-lookup"><span data-stu-id="c1a50-133">Private Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/private-constructors.md)  
  
 [<span data-ttu-id="c1a50-134">정적 생성자</span><span class="sxs-lookup"><span data-stu-id="c1a50-134">Static Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)  
  
 [<span data-ttu-id="c1a50-135">방법: 복사 생성자 작성</span><span class="sxs-lookup"><span data-stu-id="c1a50-135">How to: Write a Copy Constructor</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-write-a-copy-constructor.md)  
  
## <a name="see-also"></a><span data-ttu-id="c1a50-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c1a50-136">See Also</span></span>  
 <span data-ttu-id="c1a50-137">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c1a50-137">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="c1a50-138">[클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="c1a50-138">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="c1a50-139">[종료자](../../../csharp/programming-guide/classes-and-structs/destructors.md) </span><span class="sxs-lookup"><span data-stu-id="c1a50-139">[Finalizers](../../../csharp/programming-guide/classes-and-structs/destructors.md) </span></span>  
 <span data-ttu-id="c1a50-140">[static](../../../csharp/language-reference/keywords/static.md) </span><span class="sxs-lookup"><span data-stu-id="c1a50-140">[static](../../../csharp/language-reference/keywords/static.md) </span></span>  
 [<span data-ttu-id="c1a50-141">이니셜라이저가 생성자와 반대 순서로 실행되는 이유는 무엇인가요? 1부</span><span class="sxs-lookup"><span data-stu-id="c1a50-141">Why Do Initializers Run In The Opposite Order As Constructors? Part One</span></span>](http://go.microsoft.com/fwlink/?LinkId=112374)

