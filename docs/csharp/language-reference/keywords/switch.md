---
title: switch 키워드(C# 참조)
ms.date: 03/07/2017
f1_keywords:
- switch_CSharpKeyword
- switch
- case
- case_CSharpKeyword
helpviewer_keywords:
- switch statement [C#]
- switch keyword [C#]
- case statement [C#]
- default keyword [C#]
ms.assetid: 44bae8b8-8841-4d85-826b-8a94277daecb
ms.openlocfilehash: 4e21700b36437bf9bd60bb4f33e2833819333f1e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33288894"
---
# <a name="switch-c-reference"></a><span data-ttu-id="bb011-102">switch(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="bb011-102">switch (C# Reference)</span></span>
<span data-ttu-id="bb011-103">`switch`는 *일치 식*을 사용한 패턴 일치를 기반으로 하여 후보 목록에서 실행할 *switch 섹션* 하나를 선택하는 선택 문입니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-103">`switch` is a selection statement that chooses a single *switch section* to execute from a list of candidates based on a pattern match with the *match expression*.</span></span> 
  
 [!code-csharp[switch#1](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch1.cs#1)]  

<span data-ttu-id="bb011-104">단일 식을 3개 이상의 조건에 대해 테스트하는 경우 `switch` 문이 [if-else](if-else.md) 구문 대신 사용되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-104">The `switch` statement is often used as an alternative to an [if-else](if-else.md) construct if a single expression is tested against three or more conditions.</span></span> <span data-ttu-id="bb011-105">예를 들어 다음 `switch` 문은 `Color` 형식의 변수에 다음 세 가지 값 중 하나가 있는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-105">For example, the following `switch` statement determines whether a variable of type `Color` has one of three values:</span></span> 

[!code-csharp[switch#3](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch3.cs#1)] 

<span data-ttu-id="bb011-106">이 문은 `if`-`else` 구문을 사용하는 다음 예제와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-106">It is equivalent to the following example that uses an `if`-`else` construct.</span></span> 

[!code-csharp[switch#3a](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch3a.cs#1)] 

## <a name="the-match-expression"></a><span data-ttu-id="bb011-107">일치 식</span><span class="sxs-lookup"><span data-stu-id="bb011-107">The match expression</span></span>

<span data-ttu-id="bb011-108">일치 식은 `case` 레이블의 패턴과 일치시킬 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-108">The match expression provides the value to match against the patterns in `case` labels.</span></span> <span data-ttu-id="bb011-109">사용되는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-109">Its syntax is:</span></span>

```csharp
   switch (expr)
```

<span data-ttu-id="bb011-110">C# 6에서 일치 식은 다음 형식의 값을 반환하는 식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-110">In C# 6, the match expression must be an expression that returns a value of the following types:</span></span>

- <span data-ttu-id="bb011-111">[char](char.md)</span><span class="sxs-lookup"><span data-stu-id="bb011-111">a [char](char.md).</span></span>
- <span data-ttu-id="bb011-112">[string](string.md)</span><span class="sxs-lookup"><span data-stu-id="bb011-112">a [string](string.md).</span></span>
- <span data-ttu-id="bb011-113">[bool](bool.md)</span><span class="sxs-lookup"><span data-stu-id="bb011-113">a [bool](bool.md).</span></span> 
- <span data-ttu-id="bb011-114">[int](int.md) 또는 [long](long.md)과 같은 정수 계열 값</span><span class="sxs-lookup"><span data-stu-id="bb011-114">an integral value, such as an [int](int.md) or a [long](long.md).</span></span>
- <span data-ttu-id="bb011-115">[enum](enum.md) 값</span><span class="sxs-lookup"><span data-stu-id="bb011-115">an [enum](enum.md) value.</span></span>

<span data-ttu-id="bb011-116">C# 7.0부터 일치 식은 null이 아닌 모든 식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-116">Starting with C# 7.0, the match expression can be any non-null expression.</span></span>
 
## <a name="the-switch-section"></a><span data-ttu-id="bb011-117">switch 섹션</span><span class="sxs-lookup"><span data-stu-id="bb011-117">The switch section</span></span>
 
 <span data-ttu-id="bb011-118">`switch` 문에는 스위치 섹션이 하나 이상 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-118">A `switch` statement includes one or more switch sections.</span></span> <span data-ttu-id="bb011-119">각 switch 섹션에는 하나 이상의 *case 레이블* 및 하나 이상의 문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-119">Each switch section contains one or more *case labels* followed by one or more statements.</span></span> <span data-ttu-id="bb011-120">다음 예제에서는 세 개의 스위치 섹션이 있는 간단한 `switch` 문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-120">The following example shows a simple `switch` statement that has three switch sections.</span></span> <span data-ttu-id="bb011-121">각 스위치 섹션에는 `case 1:`과 같은 하나의 case 레이블과 두 개의 문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-121">Each switch section has one case label, such as `case 1:`, and two statements.</span></span>
 
  <span data-ttu-id="bb011-122">`switch` 문에 포함할 수 있는 switch 섹션 수에는 제한이 없으며 각 섹션에 하나 이상의 case 레이블을 포함할 수 있습니다(다음 예제 참조).</span><span class="sxs-lookup"><span data-stu-id="bb011-122">A `switch` statement can include any number of switch sections, and each section can have one or more case labels, as shown in the following example.</span></span> <span data-ttu-id="bb011-123">하지만 두 case 레이블에 동일한 식을 포함할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-123">However, no two case labels may contain the same expression.</span></span>  

 [!code-csharp[switch#2](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch2.cs#1)]  

 <span data-ttu-id="bb011-124">switch 문에서 하나의 switch 섹션만 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-124">Only one switch section in a switch statement executes.</span></span> <span data-ttu-id="bb011-125">C#은 한 switch 섹션에서 다음 switch 섹션으로 계속 실행하도록 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-125">C# does not allow execution to continue from one switch section to the next.</span></span> <span data-ttu-id="bb011-126">이 때문에 다음 코드는 컴파일러 오류 CS0163: "한 case 레이블(<case label>)에서 다른 case 레이블로 제어를 이동할 수 없습니다."를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-126">Because of this, the following code generates a compiler error, CS0163: "Control cannot fall through from one case label (<case label>) to another."</span></span>  

```csharp  
switch (caseSwitch)  
{  
    // The following switch section causes an error.  
    case 1:  
        Console.WriteLine("Case 1...");  
        // Add a break or other jump statement here.  
    case 2:  
        Console.WriteLine("... and/or Case 2");  
        break;  
}  
```  
<span data-ttu-id="bb011-127">이 요구 사항은 일반적으로 [break](break.md), [goto](goto.md) 또는 [return](return.md) 문을 통해 switch 섹션을 명시적으로 종료하여 충족됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-127">This requirement is usually met by explicitly exiting the switch section by using a [break](break.md), [goto](goto.md), or [return](return.md) statement.</span></span> <span data-ttu-id="bb011-128">그러나 다음 코드는 프로그램 제어가 `default` switch 섹션으로 이동할 수 없도록 하기 때문에 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-128">However, the following code is also valid, because it ensures that program control cannot fall through to the `default` switch section.</span></span>
  
 [!code-csharp[switch#4](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch4.cs#1)]    
  
 <span data-ttu-id="bb011-129">case 레이블이 일치 식과 일치하는 switch 섹션에서 문 목록의 실행은 첫 번째 문으로 시작하고 일반적으로 `break`, `goto case`, `goto label`, `return` 또는 `throw` 같은 점프 문에 도달할 때까지 문 목록 전체를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-129">Execution of the statement list in the switch section with a case label that matches the match expression begins with the first statement and proceeds through the statement list, typically until a jump statement, such as a `break`, `goto case`, `goto label`, `return`, or `throw`, is reached.</span></span> <span data-ttu-id="bb011-130">이 경우 `switch` 문 외부 또는 다른 case 레이블로 제어를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-130">At that point, control is transferred outside the `switch` statement or to another case label.</span></span> <span data-ttu-id="bb011-131">사용되는 경우 `goto` 문은 constant 레이블에 컨트롤을 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-131">A `goto` statement, if it is used, must transfer control to a constant label.</span></span> <span data-ttu-id="bb011-132">이 제한 사항이 필요합니다. constant가 아닌 레이블에 컨트롤을 전달하려고 하면 코드의 의도치 않은 위치에 컨트롤을 전달하거나 무한 루프를 만드는 것과 같은 원치 않는 부작용이 발생할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-132">This restriction is necessary, since attempting to transfer control to a non-constant label can have undesirable side-effects, such transferring control to an unintended location in code or creating an endless loop.</span></span>

## <a name="case-labels"></a><span data-ttu-id="bb011-133">case 레이블</span><span class="sxs-lookup"><span data-stu-id="bb011-133">Case labels</span></span>

 <span data-ttu-id="bb011-134">각 case 레이블은 일치 식과 비교할 패턴(이전 예제의 `caseSwitch` 변수)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-134">Each case label specifies a pattern to compare to the match expression (the `caseSwitch` variable in the previous examples).</span></span> <span data-ttu-id="bb011-135">일치하는 경우 제어가 일치하는 **첫 번째** case 레이블을 포함하는 switch 섹션으로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-135">If they match, control is transferred to the switch section that contains the **first** matching case label.</span></span> <span data-ttu-id="bb011-136">일치 식과 일치하는 case 레이블 패턴이 없는 경우 제어가 `default` case 레이블을 포함하는 섹션으로 전송됩니다(있는 경우).</span><span class="sxs-lookup"><span data-stu-id="bb011-136">If no case label pattern matches the match expression, control is transferred to the section with the `default` case label, if there is one.</span></span> <span data-ttu-id="bb011-137">`default` case가 없는 경우 switch 섹션의 문이 실행되지 않으며, 제어가 `switch` 문 외부로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-137">If there is no `default` case, no statements in any switch section are executed, and control is transferred outside the `switch` statement.</span></span>

 <span data-ttu-id="bb011-138">`switch` 문과 패턴 일치에 대한 자세한 내용은 [`switch` 문을 사용한 패턴 일치](#pattern) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb011-138">For information on the `switch` statement and pattern matching, see the [Pattern matching with the `switch` statement](#pattern) section.</span></span>

 <span data-ttu-id="bb011-139">C# 6에서 상수 패턴만 지원하고 상수 값의 반복을 허용하지 않는 경우 case 레이블은 상호 배타적인 값을 정의하며 하나의 패턴만 일치 식과 일치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-139">Because C# 6 supports only the constant pattern and does not allow the repetition of constant values, case labels define mutually exclusive values, and only one pattern can match the match expression.</span></span> <span data-ttu-id="bb011-140">따라서 `case` 문이 표시되는 순서는 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-140">As a result, the order in which `case` statements appear is unimportant.</span></span>

 <span data-ttu-id="bb011-141">그러나 C# 7.0에서는 다른 패턴도 지원되므로 case 레이블에서 상호 배타적인 값을 정의할 필요가 없으며 여러 패턴이 일치 식과 일치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-141">In C# 7.0, however, because other patterns are supported, case labels need not define mutually exclusive values, and multiple patterns can match the match expression.</span></span> <span data-ttu-id="bb011-142">첫 번째 일치 패턴을 포함하는 switch 섹션의 문만 실행되기 때문에 이제 `case` 문이 나타나는 순서가 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-142">Because only the statements in the switch section that contains the first matching pattern are executed, the order in which `case` statements appear is now important.</span></span> <span data-ttu-id="bb011-143">C#에서 case 문이 이전 문과 같거나 이전 문의 하위 집합인 switch 섹션을 검색할 경우 컴파일러 오류, CS8120, "Switch case가 이전 case에서 이미 처리되었습니다."를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-143">If C# detects a switch section whose case statement or statements are equivalent to or are subsets of previous statements, it generates a compiler error, CS8120, "The switch case has already been handled by a previous case."</span></span> 

 <span data-ttu-id="bb011-144">다음 예제에서는 상호 배타적이 아닌 다양한 패턴을 사용하는 `switch` 문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-144">The following example illustrates a `switch` statement that uses a variety of non-mutually exclusive patterns.</span></span> <span data-ttu-id="bb011-145">더 이상 `switch` 문의 첫 번째 섹션이 아니도록 `case 0:` switch 섹션을 이동하는 경우 해당 값이 0인 정수는 `case int val` 문에 정의된 패턴인 모든 정수의 하위 집합이므로 C#에서 컴파일러 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-145">If you move the `case 0:` switch section so that it is no longer the first section in the `switch` statement, C# generates a compiler error because an integer whose value is zero is a subset of all integers, which is the pattern defined by the `case int val` statement.</span></span>

 [!code-csharp[switch#5](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch5.cs#1)]    

<span data-ttu-id="bb011-146">이 문제를 해결하고 다음 두 가지 방법 중 하나로 컴파일러 경고를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-146">You can correct this issue and eliminate the compiler warning in one of two ways:</span></span>

- <span data-ttu-id="bb011-147">switch 섹션의 순서 변경</span><span class="sxs-lookup"><span data-stu-id="bb011-147">By changing the order of the switch sections.</span></span> 
 
- <span data-ttu-id="bb011-148">`case` 레이블에 </a name="when">when clause</a> 사용</span><span class="sxs-lookup"><span data-stu-id="bb011-148">By using a </a name="when">when clause</a> in the `case` label.</span></span>
 
## <a name="the-default-case"></a><span data-ttu-id="bb011-149">`default` case</span><span class="sxs-lookup"><span data-stu-id="bb011-149">The `default` case</span></span>

<span data-ttu-id="bb011-150">`default` case는 일치 식이 다른 `case` 레이블과 일치하지 않는 경우 실행할 switch 섹션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-150">The `default` case specifies the switch section to execute if the match expression does not match any other `case` label.</span></span> <span data-ttu-id="bb011-151">`default` case가 없고 일치 식이 다른 `case` 레이블과 일치하지 않는 경우 프로그램 제어가 `switch` 문으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-151">If a `default` case is not present and the match expression does not match any other `case` label, program flow falls through the `switch` statement.</span></span>

<span data-ttu-id="bb011-152">`default` case는 `switch` 문에 임의 순서로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-152">The `default` case can appear in any order in the `switch` statement.</span></span> <span data-ttu-id="bb011-153">소스 코드에서의 해당 순서에 관계없이 항상 모든 `case` 레이블이 평가된 후 마지막에 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-153">Regardless of its order in the source code, it is always evaluated last, after all `case` labels have been evaluated.</span></span>

## <a name="a-namepattern--pattern-matching-with-the-switch-statement"></a><span data-ttu-id="bb011-154">`switch` 문을 사용한 <a name="pattern" /> 패턴 일치</span><span class="sxs-lookup"><span data-stu-id="bb011-154"><a name="pattern" /> Pattern matching with the `switch` statement</span></span>
  
<span data-ttu-id="bb011-155">각 `case` 문은 일치 식과 일치할 경우 포함하는 switch 섹션이 실행되는 패턴을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-155">Each `case` statement defines a pattern that, if it matches the match expression, causes its  containing switch section to be executed.</span></span> <span data-ttu-id="bb011-156">상수 패턴은 모든 버전의 C#에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-156">All versions of C# support the constant pattern.</span></span> <span data-ttu-id="bb011-157">나머지 패턴은 C# 7.0부터 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-157">The remaining patterns are supported beginning with C# 7.0.</span></span> 
  
### <a name="constant-pattern"></a><span data-ttu-id="bb011-158">상수 패턴</span><span class="sxs-lookup"><span data-stu-id="bb011-158">Constant pattern</span></span> 

<span data-ttu-id="bb011-159">상수 패턴은 일치 식이 지정된 상수와 같은지 여부를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-159">The constant pattern tests whether the match expression equals a specified constant.</span></span> <span data-ttu-id="bb011-160">사용되는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-160">Its syntax is:</span></span>

```csharp
   case constant:
```

<span data-ttu-id="bb011-161">여기서 *constant*는 테스트할 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-161">where *constant* is the value to test for.</span></span> <span data-ttu-id="bb011-162">*constant*는 다음 상수 식 중 하나가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-162">*constant* can be any of the following constant expressions:</span></span> 

- <span data-ttu-id="bb011-163">[bool](bool.md) 리터럴(`true` 또는 `false`)</span><span class="sxs-lookup"><span data-stu-id="bb011-163">A [bool](bool.md) literal, either `true` or `false`.</span></span>
- <span data-ttu-id="bb011-164">[int](int.md), [long](long.md) 또는 [byte](byte.md)와 같은 모든 정수 계열 상수</span><span class="sxs-lookup"><span data-stu-id="bb011-164">Any integral constant, such as an [int](int.md), a [long](long.md), or a [byte](byte.md).</span></span> 
- <span data-ttu-id="bb011-165">선언된 `const` 변수의 이름</span><span class="sxs-lookup"><span data-stu-id="bb011-165">The name of a declared `const` variable.</span></span>
- <span data-ttu-id="bb011-166">열거형 상수</span><span class="sxs-lookup"><span data-stu-id="bb011-166">An enumeration constant.</span></span>
- <span data-ttu-id="bb011-167">[char](char.md) 리터럴</span><span class="sxs-lookup"><span data-stu-id="bb011-167">A [char](char.md) literal.</span></span>
- <span data-ttu-id="bb011-168">[string](string.md) 리터럴</span><span class="sxs-lookup"><span data-stu-id="bb011-168">A [string](string.md) literal.</span></span>

<span data-ttu-id="bb011-169">상수 식은 다음과 같이 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-169">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="bb011-170">*expr* 및 *constant*가 정수 형식인 경우 C# 같음 연산자는 식에서 `true`를 반환하는지 여부 즉, `expr == constant`인지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-170">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="bb011-171">정수 형식이 아니면 static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) 메서드 호출을 통해 식의 값이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-171">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>  

<span data-ttu-id="bb011-172">다음 예제에서는 상수 패턴을 사용하여 특정 날짜가 주말인지, 작업 주의 첫째 날인지, 작업 주의 마지막 날인지 또는 작업 주의 중간인지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-172">The following example uses the constant pattern to determine whether a particular date is a weekend, the first day of the work week, the last day of the work week, or the middle of the work week.</span></span> <span data-ttu-id="bb011-173">현재 날짜의 <xref:System.DateTime.DayOfWeek?displayProperty=nameWithType> 속성을 <xref:System.DayOfWeek> 열거형의 멤버와 비교해서 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-173">It evaluates the <xref:System.DateTime.DayOfWeek?displayProperty=nameWithType> property of the current day against the members of the <xref:System.DayOfWeek> enumeration.</span></span> 

[!code-csharp[switch#7](../../../../samples/snippets/csharp/language-reference/keywords/switch/const-pattern.cs#1)]

<span data-ttu-id="bb011-174">다음 예제에서는 상수 패턴을 사용하여 자동 커피 머신을 시뮬레이트하는 콘솔 응용 프로그램의 사용자 입력을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-174">The following example uses the constant pattern to handle user input in a console application that simulates an automatic coffee machine.</span></span>
  
 [!code-csharp[switch#6](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch6.cs)]  

### <a name="type-pattern"></a><span data-ttu-id="bb011-175">형식 패턴</span><span class="sxs-lookup"><span data-stu-id="bb011-175">Type pattern</span></span>

<span data-ttu-id="bb011-176">형식 패턴은 간결한 형식 평가 및 변환을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-176">The type pattern enables concise type evaluation and conversion.</span></span> <span data-ttu-id="bb011-177">`switch` 문과 함께 사용하여 패턴 일치를 수행하는 경우 식을 지정된 형식으로 변환할 수 있는지 여부를 테스트하고, 변환할 수 있으면 해당 형식의 변수로 캐스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-177">When used with the `switch` statement to perform pattern matching, it tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="bb011-178">사용되는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-178">Its syntax is:</span></span>

```csharp
   case type varname 
```
<span data-ttu-id="bb011-179">여기서 *type*은 *expr*의 결과가 변환되는 형식의 이름이고, *varname*은 일치에 성공할 경우 *expr*의 결과가 변환되는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-179">where *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the match succeeds.</span></span> 

<span data-ttu-id="bb011-180">다음 중 하나가 true일 경우 `case` 식은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-180">The `case` expression is `true` if any of the following is true:</span></span>

- <span data-ttu-id="bb011-181">*expr*이 *type*과 동일한 형식의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-181">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="bb011-182">*expr*이 *type*에서 파생된 형식의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-182">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="bb011-183">즉, *expr*의 결과를 *type*의 인스턴스로 업캐스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-183">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="bb011-184">*expr*의 컴파일 시간 형식은 *type*의 기본 클래스이고 *expr*의 런타임 형식은 *type*이거나 *type*에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-184">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="bb011-185">변수의 *컴파일 시간 형식*은 해당 형식 선언에 정의된 변수의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-185">The *compile-time type* of a variable is the variable's type as defined in its type declaration.</span></span> <span data-ttu-id="bb011-186">변수의 *런타임 형식*은 해당 변수에 할당된 인스턴스의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-186">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="bb011-187">*expr*이 *type* 인터페이스를 구현하는 형식의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-187">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="bb011-188">case 식이 true이면 *varname*이 한정적으로 할당되고 switch 섹션 내의 로컬 범위만 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-188">If the case expression is true, *varname* is definitely assigned and has local scope within the switch section only.</span></span>

<span data-ttu-id="bb011-189">`null`은 형식과 일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-189">Note that `null` does not match a type.</span></span> <span data-ttu-id="bb011-190">`null`과 일치하려면 다음 `case` 레이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-190">To match a `null`, you use the following `case` label:</span></span>

```csharp
case null:
```
 
<span data-ttu-id="bb011-191">다음 예제에서는 형식 패턴을 사용하여 다양한 종류의 컬렉션 형식에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-191">The following example uses the type pattern to provide information about various kinds of collection types.</span></span>

[!code-csharp[switch#5](../../../../samples/snippets/csharp/language-reference/keywords/switch/type-pattern.cs#1)]

<span data-ttu-id="bb011-192">패턴 일치를 사용하지 않을 경우 이 코드를 다음과 같이 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-192">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="bb011-193">형식 패턴 일치를 사용하면 변환 결과가 `null`인지 여부를 테스트하거나 반복된 캐스트를 수행할 필요가 없으므로 더욱 단순하고 읽기 쉬운 코드가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-193">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null` or to perform repeated casts.</span></span>  

[!code-csharp[switch#6](../../../../samples/snippets/csharp/language-reference/keywords/switch/type-pattern2.cs#1)]

## <a name="the-case-statement-and-the-when-clause"></a><span data-ttu-id="bb011-194">`case` 문과 `when` 절</span><span class="sxs-lookup"><span data-stu-id="bb011-194">The `case` statement and the `when` clause</span></span>

<span data-ttu-id="bb011-195">C# 7.0부터 case 문이 상호 배타적일 필요가 없으므로 `when` 절을 사용하여 case 문이 true로 평가되기 위해 충족해야 하는 추가 조건을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-195">Starting with C# 7.0, because case statements need not be mutually exclusive, you can use add a `when` clause to specify an additional condition that must be satisfied for the case statement to evaluate to true.</span></span> <span data-ttu-id="bb011-196">`when` 절은 부울 값을 반환하는 모든 식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-196">The `when` clause can be any expression that returns a Boolean value.</span></span> <span data-ttu-id="bb011-197">`when` 절의 보다 일반적인 사용 중 하나는 일치 식의 값이 `null`일 때 switch 섹션이 실행되지 않도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-197">One of the more common uses for the `when` clause is used to prevent a switch section from executing when the value of a match expression is `null`.</span></span> 

 <span data-ttu-id="bb011-198">다음 예제에서는 기본 `Shape` 클래스, `Shape`에서 파생된 `Rectangle` 클래스 및 `Rectangle`에서 파생된 `Square` 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-198">The following example defines a base `Shape` class, a `Rectangle` class that derives from `Shape`, and a `Square` class that derives from `Rectangle`.</span></span> <span data-ttu-id="bb011-199">`when` 절을 사용하여 `ShowShapeInfo`에서 `Square` 개체로 인스턴스화되지 않은 경우에도 동일한 길이 및 너비가 할당된 `Rectangle` 개체를 `Square`로 처리하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-199">It uses the `when` clause to ensure that the `ShowShapeInfo` treats a `Rectangle` object that has been assigned equal lengths and widths as a `Square` even if is has not been instantiated as a `Square` object.</span></span> <span data-ttu-id="bb011-200">이 메서드는 `null`인 개체나 면적이 0인 도형에 대한 정보를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-200">The method does not attempt to display information either about an object that is `null` or a shape whose area is zero.</span></span> 

[!code-csharp[switch#8](../../../../samples/snippets/csharp/language-reference/keywords/switch/when-clause.cs#1)]
  
<span data-ttu-id="bb011-201">`Shape` 개체가 `null`인지 여부를 테스트하는 예제의 `when` 절은 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-201">Note that the `when` clause in the example that attempts to test whether a `Shape` object is `null` does not execute.</span></span> <span data-ttu-id="bb011-202">`null`인지 테스트하는 올바른 형식 패턴은 `case null:`입니다.</span><span class="sxs-lookup"><span data-stu-id="bb011-202">The correct type pattern to test for a `null` is `case null:`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="bb011-203">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="bb011-203">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](../../../../includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bb011-204">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bb011-204">See Also</span></span>  

 [<span data-ttu-id="bb011-205">C# 참조</span><span class="sxs-lookup"><span data-stu-id="bb011-205">C# Reference</span></span>](../index.md)  
 [<span data-ttu-id="bb011-206">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="bb011-206">C# Programming Guide</span></span>](../../programming-guide/index.md)  
 [<span data-ttu-id="bb011-207">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="bb011-207">C# Keywords</span></span>](index.md)  
 [<span data-ttu-id="bb011-208">if-else</span><span class="sxs-lookup"><span data-stu-id="bb011-208">if-else</span></span>](if-else.md)  
 [<span data-ttu-id="bb011-209">패턴 일치</span><span class="sxs-lookup"><span data-stu-id="bb011-209">Pattern Matching</span></span>](../../pattern-matching.md)  
 

 
