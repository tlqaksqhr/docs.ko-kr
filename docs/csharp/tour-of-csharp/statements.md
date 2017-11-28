---
title: "C# 문 - C# 언어 둘러보기"
description: "문을 사용하여 C# 프로그램 동작 만들기"
keywords: ".NET, c샵, 문, 구문"
author: BillWagner
ms.author: wiwagn
ms.date: 11/06/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 5409c379-5622-4fae-88b5-1654276ea8d4
ms.openlocfilehash: 99ec2489daf89926da9b8c4e148965412826a8a6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="statements"></a><span data-ttu-id="acab9-104">문</span><span class="sxs-lookup"><span data-stu-id="acab9-104">Statements</span></span>

<span data-ttu-id="acab9-105">프로그램의 동작은 *문*을 사용하여 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="acab9-105">The actions of a program are expressed using *statements*.</span></span> <span data-ttu-id="acab9-106">C#은 여러 다른 종류의 문을 지원하며 이중 많은 문이 포함 문에 대해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="acab9-106">C# supports several different kinds of statements, a number of which are defined in terms of embedded statements.</span></span>

<span data-ttu-id="acab9-107">*블록*은 단일 문이 허용되는 컨텍스트에서 여러 문을 쓸 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="acab9-107">A *block* permits multiple statements to be written in contexts where a single statement is allowed.</span></span> <span data-ttu-id="acab9-108">블록은 구분 기호 `{`와 `}` 사이에 쓴 문 목록으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="acab9-108">A block consists of a list of statements written between the delimiters `{` and `}`.</span></span>

<span data-ttu-id="acab9-109">*선언 문*은 지역 변수 및 상수를 선언하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="acab9-109">*Declaration statements* are used to declare local variables and constants.</span></span>

<span data-ttu-id="acab9-110">*식 문*은 식을 평가하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="acab9-110">*Expression statements* are used to evaluate expressions.</span></span> <span data-ttu-id="acab9-111">문으로 사용할 수 있는 식에는 메서드 호출, `new` 연산자를 사용하는 개체 할당, `=` 및 복합 할당 연산자를 사용하는 대입, `++` 및 `--` 연산자를 사용하는 증가 및 감소 연산, `await` 식이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="acab9-111">Expressions that can be used as statements include method invocations, object allocations using the `new` operator, assignments using `=` and the compound assignment operators, increment and decrement operations using the `++` and `--` operators and `await` expressions.</span></span>

<span data-ttu-id="acab9-112">*선택 문*은 일부 식 값에 따라 실행할 수 있는 다양한 문 중에서 하나를 선택하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="acab9-112">*Selection statements* are used to select one of a number of possible statements for execution based on the value of some expression.</span></span> <span data-ttu-id="acab9-113">이 그룹에는 `if` 및 `switch` 문이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="acab9-113">In this group are the `if` and `switch` statements.</span></span>

<span data-ttu-id="acab9-114">*반복 문*은 포함 문을 반복해서 실행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="acab9-114">*Iteration statements* are used to execute repeatedly an embedded statement.</span></span> <span data-ttu-id="acab9-115">이 그룹에는 `while`, `do`, `for` 및 `foreach` 문이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="acab9-115">In this group are the `while`, `do`, `for`, and `foreach` statements.</span></span>

<span data-ttu-id="acab9-116">*점프 문*은 제어를 전달하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="acab9-116">*Jump statements* are used to transfer control.</span></span> <span data-ttu-id="acab9-117">이 그룹에는 `break`, `continue`, `goto`, `throw`, `return` 및 `yield` 문이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="acab9-117">In this group are the `break`, `continue`, `goto`, `throw`, `return`, and `yield` statements.</span></span>

<span data-ttu-id="acab9-118">`try`... `catch` 문은 블록 실행 중에 발생하는 예외를 catch하는 데 사용되고 `try`... `finally` 문은 예외 발생 여부에 관계 없이 항상 실행되는 종료 코드를 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="acab9-118">The `try`...`catch` statement is used to catch exceptions that occur during execution of a block, and the `try`...`finally` statement is used to specify finalization code that is always executed, whether an exception occurred or not.</span></span>

<span data-ttu-id="acab9-119">`checked` 및 `unchecked` 문은 정수 계열 형식 산술 연산 및 변환에 대한 오버플로 검사 컨텍스트를 제어하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="acab9-119">The `checked` and `unchecked` statements are used to control the overflow-checking context for integral-type arithmetic operations and conversions.</span></span>

<span data-ttu-id="acab9-120">`lock` 문은 지정된 개체에 대한 상호 배타적 잠금을 획득하고, 문을 실행한 후 잠금을 해제하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="acab9-120">The `lock` statement is used to obtain the mutual-exclusion lock for a given object, execute a statement, and then release the lock.</span></span>

<span data-ttu-id="acab9-121">`using` 문은 리소스를 획득하고, 문을 실행한 후 해당 리소스를 삭제하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="acab9-121">The `using` statement is used to obtain a resource, execute a statement, and then dispose of that resource.</span></span>

<span data-ttu-id="acab9-122">다음은 사용할 수 있는 문 종류와 각각에 대한 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="acab9-122">The following lists the kinds of statements that can be used, and provides an example for each.</span></span>

* <span data-ttu-id="acab9-123">지역 변수 선언:</span><span class="sxs-lookup"><span data-stu-id="acab9-123">Local variable declaration:</span></span>

 [!code-csharp[Declarations](../../../samples/snippets/csharp/tour/statements/Program.cs#L9-L15)]

* <span data-ttu-id="acab9-124">지역 상수 선언:</span><span class="sxs-lookup"><span data-stu-id="acab9-124">Local constant declaration:</span></span>

 [!code-csharp[ConstantDeclarations](../../../samples/snippets/csharp/tour/statements/Program.cs#L17-L22)]

* <span data-ttu-id="acab9-125">식 문</span><span class="sxs-lookup"><span data-stu-id="acab9-125">Expression statement:</span></span>

 [!code-csharp[Expressions](../../../samples/snippets/csharp/tour/statements/Program.cs#L24-L31)]

* <span data-ttu-id="acab9-126">`if` 문:</span><span class="sxs-lookup"><span data-stu-id="acab9-126">`if` statement:</span></span>

 [!code-csharp[IfStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L33-L43)]

* <span data-ttu-id="acab9-127">`switch` 문:</span><span class="sxs-lookup"><span data-stu-id="acab9-127">`switch` statement:</span></span>

 [!code-csharp[SwitchStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L45-L60)]

* <span data-ttu-id="acab9-128">`while` 문:</span><span class="sxs-lookup"><span data-stu-id="acab9-128">`while` statement:</span></span>

 [!code-csharp[WhileStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L62-L70)]

* <span data-ttu-id="acab9-129">`do` 문:</span><span class="sxs-lookup"><span data-stu-id="acab9-129">`do` statement:</span></span>

 [!code-csharp[DoStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L72-L81)]

* <span data-ttu-id="acab9-130">`for` 문:</span><span class="sxs-lookup"><span data-stu-id="acab9-130">`for` statement:</span></span>

 [!code-csharp[ForStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L83-L89)]

* <span data-ttu-id="acab9-131">`foreach` 문:</span><span class="sxs-lookup"><span data-stu-id="acab9-131">`foreach` statement:</span></span>

 [!code-csharp[ForEachStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L91-L97)]

* <span data-ttu-id="acab9-132">`break` 문:</span><span class="sxs-lookup"><span data-stu-id="acab9-132">`break` statement:</span></span>

 [!code-csharp[BreakStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L99-L108)]

* <span data-ttu-id="acab9-133">`continue` 문:</span><span class="sxs-lookup"><span data-stu-id="acab9-133">`continue` statement:</span></span>

 [!code-csharp[ContinueStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L110-L118)]

* <span data-ttu-id="acab9-134">`goto` 문:</span><span class="sxs-lookup"><span data-stu-id="acab9-134">`goto` statement:</span></span>

 [!code-csharp[GotoStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L120-L129)]

* <span data-ttu-id="acab9-135">`return` 문:</span><span class="sxs-lookup"><span data-stu-id="acab9-135">`return` statement:</span></span>

 [!code-csharp[ReturnStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L131-L139)]

* <span data-ttu-id="acab9-136">`yield` 문:</span><span class="sxs-lookup"><span data-stu-id="acab9-136">`yield` statement:</span></span>

 [!code-csharp[YieldStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L141-L155)]

* <span data-ttu-id="acab9-137">`throw`문 및 `try` 문:</span><span class="sxs-lookup"><span data-stu-id="acab9-137">`throw` statements and `try` statements:</span></span>

 [!code-csharp[TryThrow](../../../samples/snippets/csharp/tour/statements/Program.cs#L157-L183)]

* <span data-ttu-id="acab9-138">`checked` 및 `unchecked` 문:</span><span class="sxs-lookup"><span data-stu-id="acab9-138">`checked` and `unchecked` statements:</span></span>

 [!code-csharp[CheckedUncheckedStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L185-L196)]

* <span data-ttu-id="acab9-139">`lock` 문:</span><span class="sxs-lookup"><span data-stu-id="acab9-139">`lock` statement:</span></span>

 [!code-csharp[LockStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L257-L273)]

* <span data-ttu-id="acab9-140">`using` 문:</span><span class="sxs-lookup"><span data-stu-id="acab9-140">`using` statement:</span></span>

 [!code-csharp[UsingStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L198-L206)]

>[!div class="step-by-step"]
<span data-ttu-id="acab9-141">[이전](expressions.md)
[다음](classes-and-objects.md)</span><span class="sxs-lookup"><span data-stu-id="acab9-141">[Previous](expressions.md)
[Next](classes-and-objects.md)</span></span>
