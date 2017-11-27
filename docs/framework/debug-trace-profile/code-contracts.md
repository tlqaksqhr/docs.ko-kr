---
title: "코드 계약"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: Code contracts
ms.assetid: 84526045-496f-489d-8517-a258cf76f040
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ce74cfb9c4e0eb759fb8160ab06fa6fbde60081b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="code-contracts"></a><span data-ttu-id="76dba-102">코드 계약</span><span class="sxs-lookup"><span data-stu-id="76dba-102">Code Contracts</span></span>
<span data-ttu-id="76dba-103">코드 계약을 통해 코드에서 사전 조건, 사후 조건 및 개체 고정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-103">Code contracts provide a way to specify preconditions, postconditions, and object invariants in your code.</span></span> <span data-ttu-id="76dba-104">사전 조건은 메서드 또는 속성을 입력할 때 충족해야 하는 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-104">Preconditions are requirements that must be met when entering a method or property.</span></span> <span data-ttu-id="76dba-105">사후 조건은 메서드 또는 속성 코드가 종료될 때의 예상을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-105">Postconditions describe expectations at the time the method or property code exits.</span></span> <span data-ttu-id="76dba-106">개체 고정은 양호한 상태인 클래스의 예상 상태를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-106">Object invariants describe the expected state for a class that is in a good state.</span></span>  
  
 <span data-ttu-id="76dba-107">코드 계약에는 코드 표시를 위한 클래스, 컴파일 타임 분석을 위한 정적 분석기 및 런타임 분석기가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-107">Code contracts include classes for marking your code, a static analyzer for compile-time analysis, and a runtime analyzer.</span></span> <span data-ttu-id="76dba-108">코드 계약에 대한 클래스는 <xref:System.Diagnostics.Contracts> 네임스페이스에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-108">The classes for code contracts can be found in the <xref:System.Diagnostics.Contracts> namespace.</span></span>  
  
 <span data-ttu-id="76dba-109">코드 계약의 이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-109">The benefits of code contracts include the following:</span></span>  
  
-   <span data-ttu-id="76dba-110">테스트 향상: 코드 계약은 정적 계약 검증, 런타임 검사 및 설명서 생성 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-110">Improved testing: Code contracts provide static contract verification, runtime checking, and documentation generation.</span></span>  
  
-   <span data-ttu-id="76dba-111">자동 테스트 도구: 코드 계약을 통해 사전 조건을 충족하지 않는 의미 없는 테스트 인수를 필터링하여 보다 의미 있는 단위 테스트를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-111">Automatic testing tools: You can use code contracts to generate more meaningful unit tests by filtering out meaningless test arguments that do not satisfy preconditions.</span></span>  
  
-   <span data-ttu-id="76dba-112">정적 검증: 정적 검사기는 프로그램을 실행하지 않고 계약 위반이 있는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-112">Static verification: The static checker can decide whether there are any contract violations without running the program.</span></span> <span data-ttu-id="76dba-113">null 역참조 및 배열 범위와 같은 암시적 계약 및 명시적 계약을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-113">It checks for implicit contracts, such as null dereferences and array bounds, and explicit contracts.</span></span>  
  
-   <span data-ttu-id="76dba-114">참조 설명서: 설명서 생성기는 기존 XML 설명서 파일을 계약 정보로 증대시킵니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-114">Reference documentation: The documentation generator augments existing XML documentation files with contract information.</span></span> <span data-ttu-id="76dba-115">생성된 설명서 페이지에 계약 섹션이 포함되도록 [Sandcastle](https://github.com/EWSoftware/SHFB)과 함께 사용할 수 있는 스타일시트도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-115">There are also style sheets that can be used with [Sandcastle](https://github.com/EWSoftware/SHFB) so that the generated documentation pages have contract sections.</span></span>  
  
 <span data-ttu-id="76dba-116">모든 .NET Framework 언어는 계약을 즉시 활용할 수 있습니다. 특별한 파서 또는 컴파일러를 작성할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-116">All .NET Framework languages can immediately take advantage of contracts; you do not have to write a special parser or compiler.</span></span> <span data-ttu-id="76dba-117">Visual Studio 추가 기능을 통해 수행할 코드 계약 분석 수준을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-117">A Visual Studio add-in lets you specify the level of code contract analysis to be performed.</span></span> <span data-ttu-id="76dba-118">분석기는 계약이 제대로 구성되었는지 확인할 수 있으며(형식 검사 및 이름 확인) 컴파일된 계약 형태를 MSIL(Microsoft Intermediate Language) 형식으로 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-118">The analyzers can confirm that the contracts are well-formed (type checking and name resolution) and can produce a compiled form of the contracts in Microsoft intermediate language (MSIL) format.</span></span> <span data-ttu-id="76dba-119">Visual Studio에서 계약을 작성하는 경우 도구에서 제공하는 표준 IntelliSense를 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-119">Authoring contracts in Visual Studio lets you take advantage of the standard IntelliSense provided by the tool.</span></span>  
  
 <span data-ttu-id="76dba-120">계약 클래스에 있는 대부분의 메서드는 조건부로 컴파일됩니다. 즉, `#define` 지시문을 사용하여 특수 기호 CONTRACTS_FULL을 정의하는 경우에만 컴파일러가 이러한 메서드 호출을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-120">Most methods in the contract class are conditionally compiled; that is, the compiler emits calls to these methods only when  you define a special symbol, CONTRACTS_FULL, by using the `#define` directive.</span></span> <span data-ttu-id="76dba-121">CONTRACTS_FULL을 사용하면 `#ifdef` 지시문을 사용하지 않고 코드에서 계약을 작성할 수 있습니다. 일부는 계약을 포함하고 일부는 계약을 포함하지 않는 다양한 빌드를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-121">CONTRACTS_FULL lets you write contracts in your code without using `#ifdef` directives; you can produce different builds, some with contracts, and some without.</span></span>  
  
 <span data-ttu-id="76dba-122">코드 계약을 사용하기 위한 도구 및 자세한 지침은 MSDN DevLabs 웹 사이트의 [코드 계약](http://go.microsoft.com/fwlink/?LinkId=152461)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76dba-122">For tools and detailed instructions for using code contracts, see [Code Contracts](http://go.microsoft.com/fwlink/?LinkId=152461) on the MSDN DevLabs Web site.</span></span>  
  
## <a name="preconditions"></a><span data-ttu-id="76dba-123">사전 조건</span><span class="sxs-lookup"><span data-stu-id="76dba-123">Preconditions</span></span>  
 <span data-ttu-id="76dba-124"><xref:System.Diagnostics.Contracts.Contract.Requires%2A?displayProperty=nameWithType> 메서드를 사용하여 사전 조건을 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-124">You can express preconditions by using the <xref:System.Diagnostics.Contracts.Contract.Requires%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="76dba-125">사전 조건은 메서드가 호출될 때의 상태를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-125">Preconditions specify state when a method is invoked.</span></span> <span data-ttu-id="76dba-126">일반적으로 유효한 매개 변수 값을 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-126">They are generally used to specify valid parameter values.</span></span> <span data-ttu-id="76dba-127">사전 조건에 언급된 모든 멤버는 최소한 메서드 자체만큼 액세스 가능해야 합니다. 그러지 않으면 메서드의 일부 호출자가 사전 조건을 이해하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-127">All members that are mentioned in preconditions must be at least as accessible as the method itself; otherwise, the precondition might not be understood by all callers of a method.</span></span> <span data-ttu-id="76dba-128">조건에 파생 작업이 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-128">The condition must have no side-effects.</span></span> <span data-ttu-id="76dba-129">실패한 사전 조건의 런타임 동작은 런타임 분석기에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-129">The run-time behavior of failed preconditions is determined by the runtime analyzer.</span></span>  
  
 <span data-ttu-id="76dba-130">예를 들어 다음 사전 조건은 `x` 매개 변수가 null이 아니어야 한다고 표현합니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-130">For example, the following precondition expresses that parameter `x` must be non-null.</span></span>  
  
 `Contract.Requires( x != null );`  
  
 <span data-ttu-id="76dba-131">사전 조건이 실패할 때 코드에서 특정 예외를 발생시켜야 하는 경우 다음과 같이 <xref:System.Diagnostics.Contracts.Contract.Requires%2A>의 제네릭 오버로드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-131">If your code must throw a particular exception on failure of a precondition, you can use the generic overload of <xref:System.Diagnostics.Contracts.Contract.Requires%2A> as follows.</span></span>  
  
 `Contract.Requires<ArgumentNullException>( x != null, "x" );`  
  
### <a name="legacy-requires-statements"></a><span data-ttu-id="76dba-132">레거시 Requires 문</span><span class="sxs-lookup"><span data-stu-id="76dba-132">Legacy Requires Statements</span></span>  
 <span data-ttu-id="76dba-133">대부분의 코드에는 `if`-`then`-`throw` 코드 형태의 일부 매개 변수 유효성 검사가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-133">Most code contains some parameter validation in the form of `if`-`then`-`throw` code.</span></span> <span data-ttu-id="76dba-134">다음과 같은 경우 계약 도구는 이러한 문을 사전 조건으로 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-134">The contract tools recognize these statements as preconditions in the following cases:</span></span>  
  
-   <span data-ttu-id="76dba-135">문이 메서드에서 다른 문 앞에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-135">The statements appear before any other statements in a method.</span></span>  
  
-   <span data-ttu-id="76dba-136">이러한 문의 전체 집합 뒤에는 <xref:System.Diagnostics.Contracts.Contract.Requires%2A>, <xref:System.Diagnostics.Contracts.Contract.Ensures%2A>, <xref:System.Diagnostics.Contracts.Contract.EnsuresOnThrow%2A> 또는 <xref:System.Diagnostics.Contracts.Contract.EndContractBlock%2A> 메서드 호출과 같은 명시적 <xref:System.Diagnostics.Contracts.Contract> 메서드 호출이 나옵니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-136">The entire set of such statements is followed by an explicit <xref:System.Diagnostics.Contracts.Contract> method call, such as a call to the <xref:System.Diagnostics.Contracts.Contract.Requires%2A>, <xref:System.Diagnostics.Contracts.Contract.Ensures%2A>, <xref:System.Diagnostics.Contracts.Contract.EnsuresOnThrow%2A>, or <xref:System.Diagnostics.Contracts.Contract.EndContractBlock%2A> method.</span></span>  
  
 <span data-ttu-id="76dba-137">`if`-`then`-`throw` 문이 이 형태로 나타나는 경우 도구에서 레거시 `requires` 문으로 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-137">When `if`-`then`-`throw` statements appear in this form, the tools recognize them as legacy `requires` statements.</span></span> <span data-ttu-id="76dba-138">`if`-`then`-`throw` 시퀀스 뒤에 나오는 다른 계약이 없는 경우 <xref:System.Diagnostics.Contracts.Contract.EndContractBlock%2A?displayProperty=nameWithType> 메서드를 사용하여 코드를 끝냅니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-138">If no other contracts follow the `if`-`then`-`throw` sequence, end the code with the <xref:System.Diagnostics.Contracts.Contract.EndContractBlock%2A?displayProperty=nameWithType> method.</span></span>  
  
```  
if ( x == null ) throw new ...  
Contract.EndContractBlock(); // All previous "if" checks are preconditions  
```  
  
 <span data-ttu-id="76dba-139">앞의 테스트에 있는 조건은 부정된 사전 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-139">Note that the condition in the preceding test is a negated precondition.</span></span> <span data-ttu-id="76dba-140">실제 사전 조건은 `x != null`입니다. 부정된 사전 조건은 매우 제한적입니다. 앞의 예제와 같이 작성해야 합니다. 즉, `else`을 포함하지 않아야 하며 `then` 절의 본문은 단일 `throw` 문이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-140">(The actual precondition would be `x != null`.) A negated precondition is highly restricted: It must be written as shown in the previous example; that is, it should contain no `else` clauses, and the body of the `then` clause must be a single `throw` statement.</span></span> <span data-ttu-id="76dba-141">`if` 테스트에는 순수성 및 표시 유형 규칙이 둘 다 적용되지만([사용 지침](#usage_guidelines) 참조) `throw` 식에는 순수성 규칙만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-141">The `if` test is subject to both purity and visibility rules (see [Usage Guidelines](#usage_guidelines)), but the `throw` expression is subject only to purity rules.</span></span> <span data-ttu-id="76dba-142">그러나 발생한 예외 형식은 계약이 발생하는 메서드와 동일한 표시 유형이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-142">However, the type of the exception thrown must be as visible as the method in which the contract occurs.</span></span>  
  
## <a name="postconditions"></a><span data-ttu-id="76dba-143">사후 조건</span><span class="sxs-lookup"><span data-stu-id="76dba-143">Postconditions</span></span>  
 <span data-ttu-id="76dba-144">사후 조건은 종료될 때의 메서드 상태에 대한 계약입니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-144">Postconditions are contracts for the state of a method when it terminates.</span></span> <span data-ttu-id="76dba-145">사후 조건은 메서드를 종료하기 직전에 검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-145">The postcondition is checked just before exiting a method.</span></span> <span data-ttu-id="76dba-146">실패한 사후 조건의 런타임 동작은 런타임 분석기에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-146">The run-time behavior of failed postconditions is determined by the runtime analyzer.</span></span>  
  
 <span data-ttu-id="76dba-147">사전 조건과 달리 사후 조건은 표시 수준이 낮은 멤버를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-147">Unlike preconditions, postconditions may reference members with less visibility.</span></span> <span data-ttu-id="76dba-148">클라이언트가 전용 상태를 사용하여 사후 조건에서 표현된 일부 정보를 이해 또는 사용하지 못할 수도 있지만 메서드를 올바르게 사용할 수 있는 클라이언트의 기능에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-148">A client may not be able to understand or make use of some of the information expressed by a postcondition using private state, but this does not affect the client's ability to use the method correctly.</span></span>  
  
### <a name="standard-postconditions"></a><span data-ttu-id="76dba-149">표준 사후 조건</span><span class="sxs-lookup"><span data-stu-id="76dba-149">Standard Postconditions</span></span>  
 <span data-ttu-id="76dba-150"><xref:System.Diagnostics.Contracts.Contract.Ensures%2A> 메서드를 사용하여 표준 사후 조건을 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-150">You can express standard postconditions by using the <xref:System.Diagnostics.Contracts.Contract.Ensures%2A> method.</span></span> <span data-ttu-id="76dba-151">사후 조건은 메서드가 정상 종료될 때 `true`여야 하는 조건을 표현합니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-151">Postconditions express a condition that must be `true` upon normal termination of the method.</span></span>  
  
 `Contract.Ensures( this.F > 0 );`  
  
### <a name="exceptional-postconditions"></a><span data-ttu-id="76dba-152">예외 사후 조건</span><span class="sxs-lookup"><span data-stu-id="76dba-152">Exceptional Postconditions</span></span>  
 <span data-ttu-id="76dba-153">예외 사후 조건은 메서드에서 특정 예외가 발생할 때 `true`여야 하는 사후 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-153">Exceptional postconditions are postconditions that should be `true` when a particular exception is thrown by a method.</span></span> <span data-ttu-id="76dba-154">다음 예제에 같이 <xref:System.Diagnostics.Contracts.Contract.EnsuresOnThrow%2A?displayProperty=nameWithType> 메서드를 사용하여 이러한 사후 조건을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-154">You can specify these postconditions by using the <xref:System.Diagnostics.Contracts.Contract.EnsuresOnThrow%2A?displayProperty=nameWithType> method, as the following example shows.</span></span>  
  
 `Contract.EnsuresOnThrow<T>( this.F > 0 );`  
  
 <span data-ttu-id="76dba-155">인수는 `T`의 하위 형식인 예외가 발생할 때마다 `true`여야 하는 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-155">The argument is the condition that must be `true` whenever an exception that is a subtype of `T` is thrown.</span></span>  
  
 <span data-ttu-id="76dba-156">예외 사후 조건에서 사용하기 어려운 일부 예외 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-156">There are some exception types that are difficult to use in an exceptional postcondition.</span></span> <span data-ttu-id="76dba-157">예를 들어 `T`에 대해 <xref:System.Exception> 형식을 사용하면 스택 오버플로 또는 제어하기 어려운 다른 예외인 경우에도 발생한 예외 형식에 관계없이 메서드가 조건을 보장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-157">For example, using the type <xref:System.Exception> for `T` requires the method to guarantee the condition regardless of the type of exception that is thrown, even if it is a stack overflow or other impossible-to-control exception.</span></span> <span data-ttu-id="76dba-158">예외 사후 조건은 멤버 호출 시 발생할 수 있는 특정 예외(예: <xref:System.TimeZoneInfo> 메서드 호출에 대해 <xref:System.InvalidTimeZoneException>이 발생하는 경우)에 대해서만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-158">You should use exceptional postconditions only for specific exceptions that might be thrown when a member is called, for example, when an <xref:System.InvalidTimeZoneException> is thrown for a <xref:System.TimeZoneInfo> method call.</span></span>  
  
### <a name="special-postconditions"></a><span data-ttu-id="76dba-159">특수 사후 조건</span><span class="sxs-lookup"><span data-stu-id="76dba-159">Special Postconditions</span></span>  
 <span data-ttu-id="76dba-160">다음 메서드는 사후 조건 내에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-160">The following methods may be used only within postconditions:</span></span>  
  
-   <span data-ttu-id="76dba-161">`T`가 메서드의 반환 형식으로 대체되는 `Contract.Result<T>()` 식을 사용하여 사후 조건에서 메서드 반환 값을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-161">You can refer to method return values in postconditions by using the expression `Contract.Result<T>()`, where `T` is replaced by the return type of the method.</span></span> <span data-ttu-id="76dba-162">컴파일러가 형식을 유추할 수 없는 경우 명시적으로 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-162">When the compiler is unable to infer the type, you must explicitly provide it.</span></span> <span data-ttu-id="76dba-163">예를 들어 C# 컴파일러는 인수를 사용하지 않는 메서드에 대한 형식을 유추할 수 없으므로 다음과 같은 사후 조건이 필요합니다. `Contract.Ensures(0 <Contract.Result<int>())` 반환 형식이 `void`인 메서드는 사후 조건에서 `Contract.Result<T>()`를 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-163">For example, the C# compiler is unable to infer types for methods that do not take any arguments, so it requires the following postcondition: `Contract.Ensures(0 <Contract.Result<int>())` Methods with a return type of `void` cannot refer to `Contract.Result<T>()` in their postconditions.</span></span>  
  
-   <span data-ttu-id="76dba-164">사후 조건의 사전 상태 값은 메서드 또는 속성의 시작 부분에 있는 식의 값을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-164">A prestate value in a postcondition refers to the value of an expression at the start of a method or property.</span></span> <span data-ttu-id="76dba-165">`Contract.OldValue<T>(e)` 식을 사용합니다. 여기서 `T`는 `e`의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-165">It uses the expression `Contract.OldValue<T>(e)`, where `T` is the type of `e`.</span></span> <span data-ttu-id="76dba-166">컴파일러가 형식을 유추할 수 있는 경우 언제든지 제네릭 형식 인수를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-166">You can omit the generic type argument whenever the compiler is able to infer its type.</span></span> <span data-ttu-id="76dba-167">예를 들어 C# 컴파일러는 인수를 사용하기 때문에 항상 형식을 유추합니다. `e`에서 발생할 수 있는 사항 및 이전 식이 나타날 수 있는 컨텍스트에 대한 몇 가지 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-167">(For example, the C# compiler always infers the type because it takes an argument.) There are several restrictions on what can occur in `e` and the contexts in which an old expression may appear.</span></span> <span data-ttu-id="76dba-168">이전 식은 다른 이전 식을 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-168">An old expression cannot contain another old expression.</span></span> <span data-ttu-id="76dba-169">무엇보다도 이전 식은 메서드의 사전 조건 상태에 있던 값을 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-169">Most importantly, an old expression must refer to a value that existed in the method's precondition state.</span></span> <span data-ttu-id="76dba-170">즉, 메서드의 사전 조건이 `true`이기만 하면 평가할 수 있는 식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-170">In other words, it must be an expression that can be evaluated as long as the method's precondition is `true`.</span></span> <span data-ttu-id="76dba-171">다음은 해당 규칙의 여러 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-171">Here are several instances of that rule.</span></span>  
  
    -   <span data-ttu-id="76dba-172">값은 메서드의 사전 조건 상태에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-172">The value must exist in the method's precondition state.</span></span> <span data-ttu-id="76dba-173">개체의 필드를 참조하려면 사전 조건에서 해당 개체가 항상 null이 아니도록 보장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-173">In order to reference a field on an object, the preconditions must guarantee that that object is always non-null.</span></span>  
  
    -   <span data-ttu-id="76dba-174">이전 식에서는 메서드의 반환 값을 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-174">You cannot refer to the method's return value in an old expression:</span></span>  
  
        ```  
        Contract.OldValue(Contract.Result<int>() + x) // ERROR  
        ```  
  
    -   <span data-ttu-id="76dba-175">이전 식에서는 `out` 매개 변수를 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-175">You cannot refer to `out` parameters in an old expression.</span></span>  
  
    -   <span data-ttu-id="76dba-176">수량자 범위가 메서드의 반환 값에 종속된 경우 이전 식은 수량자의 바인딩된 변수에 종속될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-176">An old expression cannot depend on the bound variable of a quantifier if the range of the quantifier depends on the return value of the method:</span></span>  
  
        ```  
        Contract. ForAll (0,Contract. Result<int>(),  
        i => Contract.OldValue(xs[i]) > 3); // ERROR  
        ```  
  
    -   <span data-ttu-id="76dba-177">이전 식이 메서드 호출의 인덱서 또는 인수로 사용되지 않는 한 <xref:System.Diagnostics.Contracts.Contract.ForAll%2A> 또는 <xref:System.Diagnostics.Contracts.Contract.Exists%2A> 호출에서 익명 대리자의 매개 변수를 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-177">An old expression cannot refer to the parameter of the anonymous delegate in a <xref:System.Diagnostics.Contracts.Contract.ForAll%2A> or <xref:System.Diagnostics.Contracts.Contract.Exists%2A> call unless it is used as an indexer or argument to a method call:</span></span>  
  
        ```  
        Contract. ForAll (0, xs .Length, i => Contract.OldValue(xs[i]) > 3); // OK  
        Contract. ForAll (0, xs .Length, i => Contract.OldValue(i) > 3); // ERROR  
        ```  
  
    -   <span data-ttu-id="76dba-178">익명 대리자가 <xref:System.Diagnostics.Contracts.Contract.ForAll%2A> 또는 <xref:System.Diagnostics.Contracts.Contract.Exists%2A> 메서드에 대한 인수가 아니면 이전 식의 값이 익명 대리자의 매개 변수 중 하나에 종속된 경우 익명 대리자의 본문에서 이전 식이 발생할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-178">An old expression cannot occur in the body of an anonymous delegate if the value of the old expression depends on any of the parameters of the anonymous delegate, unless the anonymous delegate is an argument to the <xref:System.Diagnostics.Contracts.Contract.ForAll%2A> or <xref:System.Diagnostics.Contracts.Contract.Exists%2A> method:</span></span>  
  
        ```  
        Method( ... (T t) => Contract.OldValue(... t ...) ... ); // ERROR  
        ```  
  
    -   <span data-ttu-id="76dba-179">계약이 메서드 본문 앞에 나타나고 대부분의 컴파일러가 사후 조건에서 `out` 매개 변수를 허용하지 않으므로 `Out` 매개 변수는 문제를 일으킵니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-179">`Out` parameters present a problem because contracts appear before the body of the method, and most compilers do not allow references to `out` parameters in postconditions.</span></span> <span data-ttu-id="76dba-180">이 문제를 해결하기 위해 <xref:System.Diagnostics.Contracts.Contract> 클래스는 `out` 매개 변수를 기준으로 사후 조건을 허용하는 <xref:System.Diagnostics.Contracts.Contract.ValueAtReturn%2A> 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-180">To solve this problem, the <xref:System.Diagnostics.Contracts.Contract> class provides the <xref:System.Diagnostics.Contracts.Contract.ValueAtReturn%2A> method, which allows a postcondition based on an `out` parameter.</span></span>  
  
        ```  
        public void OutParam(out int x) f  
        Contract.Ensures(Contract.ValueAtReturn(out x) == 3);  
        x = 3;  
        ```  
  
         <span data-ttu-id="76dba-181"><xref:System.Diagnostics.Contracts.Contract.OldValue%2A> 메서드와 마찬가지로, 컴파일러가 형식을 유추할 수 있는 경우 언제든지 제네릭 형식 매개 변수를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-181">As with the <xref:System.Diagnostics.Contracts.Contract.OldValue%2A> method, you can omit the generic type parameter whenever the compiler is able to infer its type.</span></span> <span data-ttu-id="76dba-182">계약 재작성기는 메서드 호출을 `out` 매개 변수의 값으로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-182">The contract rewriter replaces the method call with the value of the `out` parameter.</span></span> <span data-ttu-id="76dba-183"><xref:System.Diagnostics.Contracts.Contract.ValueAtReturn%2A> 메서드는 사후 조건에서만 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-183">The <xref:System.Diagnostics.Contracts.Contract.ValueAtReturn%2A> method may appear only in postconditions.</span></span> <span data-ttu-id="76dba-184">메서드에 대한 인수는 `out` 매개 변수 또는 구조체 필드 `out` 매개 변수여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-184">The argument to the method must be an `out` parameter or a field of a structure `out` parameter.</span></span> <span data-ttu-id="76dba-185">후자는 구조체 생성자의 사후 조건에서 필드를 참조할 때에도 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-185">The latter is also useful when referring to fields in the postcondition of a structure constructor.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="76dba-186">코드 계약 분석 도구는 현재 `out` 매개 변수가 올바르게 초기화되었는지 여부를 확인하지 않으며 사후 조건에서 해당 내용을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-186">Currently, the code contract analysis tools do not check whether `out` parameters are initialized properly and disregard their mention in the postcondition.</span></span> <span data-ttu-id="76dba-187">따라서 앞의 예제에서 계약 뒤의 줄이 정수를 할당하는 대신 `x`의 값을 사용한 경우 컴파일러가 올바른 오류를 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-187">Therefore, in the previous example, if the line after the contract had used the value of `x` instead of assigning an integer to it, a compiler would not issue the correct error.</span></span> <span data-ttu-id="76dba-188">그러나 CONTRACTS_FULL 전처리기 기호가 정의되지 않은 빌드(예: 릴리스 빌드)에서는 컴파일러가 오류를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-188">However, on a build where the CONTRACTS_FULL preprocessor symbol is not defined (such asa release build), the compiler will issue an error.</span></span>  
  
## <a name="invariants"></a><span data-ttu-id="76dba-189">고정</span><span class="sxs-lookup"><span data-stu-id="76dba-189">Invariants</span></span>  
 <span data-ttu-id="76dba-190">개체 고정은 해당 개체가 클라이언트에 표시될 때마다 클래스의 각 인스턴스에 대해 true여야 하는 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-190">Object invariants are conditions that should be true for each instance of a class whenever that object is visible to a client.</span></span> <span data-ttu-id="76dba-191">개체가 올바른 것으로 간주되는 조건을 표현합니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-191">They express the conditions under which the object is considered to be correct.</span></span>  
  
 <span data-ttu-id="76dba-192">고정 메서드는 <xref:System.Diagnostics.Contracts.ContractInvariantMethodAttribute> 특성 표시로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-192">The invariant methods are identified by being marked with the <xref:System.Diagnostics.Contracts.ContractInvariantMethodAttribute> attribute.</span></span> <span data-ttu-id="76dba-193">고정 메서드는 다음 예제와 같이 각각 개별 고정을 지정하는 <xref:System.Diagnostics.Contracts.Contract.Invariant%2A> 메서드 호출 시퀀스를 제외하고 코드를 포함하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-193">The invariant methods must contain no code except for a sequence of calls to the <xref:System.Diagnostics.Contracts.Contract.Invariant%2A> method, each of which specifies an individual invariant, as shown in the following example.</span></span>  
  
```  
[ContractInvariantMethod]  
protected void ObjectInvariant ()   
{  
Contract.Invariant(this.y >= 0);  
Contract.Invariant(this.x > this.y);  
...  
}  
```  
  
 <span data-ttu-id="76dba-194">고정은 CONTRACTS_FULL 전처리기 기호에 의해 조건부로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-194">Invariants are conditionally defined by the CONTRACTS_FULL preprocessor symbol.</span></span> <span data-ttu-id="76dba-195">런타임 검사 중에 고정은 각 public 메서드의 끝에서 검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-195">During run-time checking, invariants are checked at the end of each public method.</span></span> <span data-ttu-id="76dba-196">고정이 동일한 클래스의 public 메서드를 언급하는 경우 일반적으로 해당 public 메서드의 끝에서 발생하는 고정 검사를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-196">If an invariant mentions a public method in the same class, the invariant check that would normally happen at the end of that public method is disabled.</span></span> <span data-ttu-id="76dba-197">대신, 해당 클래스에 대한 가장 바깥쪽 메서드 호출의 끝에서만 검사가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-197">Instead, the check occurs only at the end of the outermost method call to that class.</span></span> <span data-ttu-id="76dba-198">이 검사는 다른 클래스의 메서드 호출로 인해 클래스에 재진입하는 경우에도 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-198">This also happens if the class is re-entered because of a call to a method on another class.</span></span> <span data-ttu-id="76dba-199">개체 종료자나 <xref:System.IDisposable.Dispose%2A> 메서드를 구현하는 모든 메서드에 대해서는 고정이 검사되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-199">Invariants are not checked for object finalizers or for any methods that implement the <xref:System.IDisposable.Dispose%2A> method.</span></span>  
  
<a name="usage_guidelines"></a>   
## <a name="usage-guidelines"></a><span data-ttu-id="76dba-200">사용 지침</span><span class="sxs-lookup"><span data-stu-id="76dba-200">Usage Guidelines</span></span>  
  
### <a name="contract-ordering"></a><span data-ttu-id="76dba-201">계약 순서 지정</span><span class="sxs-lookup"><span data-stu-id="76dba-201">Contract Ordering</span></span>  
 <span data-ttu-id="76dba-202">다음 표에서는 메서드 계약을 쓸 때 사용해야 하는 요소의 순서를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-202">The following table shows the order of elements you should use when you write method contracts.</span></span>  
  
|`If-then-throw statements`|<span data-ttu-id="76dba-203">이전 버전과 호환되는 공용 사전 조건</span><span class="sxs-lookup"><span data-stu-id="76dba-203">Backward-compatible public preconditions</span></span>|  
|-|-|  
|<xref:System.Diagnostics.Contracts.Contract.Requires%2A>|<span data-ttu-id="76dba-204">모든 공용 사전 조건</span><span class="sxs-lookup"><span data-stu-id="76dba-204">All public preconditions.</span></span>|  
|<xref:System.Diagnostics.Contracts.Contract.Ensures%2A>|<span data-ttu-id="76dba-205">모든 공용(일반) 사후 조건</span><span class="sxs-lookup"><span data-stu-id="76dba-205">All public (normal) postconditions.</span></span>|  
|<xref:System.Diagnostics.Contracts.Contract.EnsuresOnThrow%2A>|<span data-ttu-id="76dba-206">모든 공용 예외 사후 조건</span><span class="sxs-lookup"><span data-stu-id="76dba-206">All public exceptional postconditions.</span></span>|  
|<xref:System.Diagnostics.Contracts.Contract.Ensures%2A>|<span data-ttu-id="76dba-207">모든 전용/내부(일반) 사후 조건</span><span class="sxs-lookup"><span data-stu-id="76dba-207">All private/internal (normal) postconditions.</span></span>|  
|<xref:System.Diagnostics.Contracts.Contract.EnsuresOnThrow%2A>|<span data-ttu-id="76dba-208">모든 전용/내부 예외 사후 조건</span><span class="sxs-lookup"><span data-stu-id="76dba-208">All private/internal exceptional postconditions.</span></span>|  
|<xref:System.Diagnostics.Contracts.Contract.EndContractBlock%2A>|<span data-ttu-id="76dba-209">다른 계약 없이 `if`-`then`-`throw` 스타일 사전 조건을 사용하는 경우 <xref:System.Diagnostics.Contracts.Contract.EndContractBlock%2A> 호출을 배치하여 이전의 모든 if 검사가 사전 조건임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-209">If using `if`-`then`-`throw` style preconditions without any other contracts, place a call to <xref:System.Diagnostics.Contracts.Contract.EndContractBlock%2A> to indicate that all previous if checks are preconditions.</span></span>|  
  
<a name="purity"></a>   
### <a name="purity"></a><span data-ttu-id="76dba-210">순수성</span><span class="sxs-lookup"><span data-stu-id="76dba-210">Purity</span></span>  
 <span data-ttu-id="76dba-211">계약 내에서 호출되는 모든 메서드는 순수해야 합니다. 즉, 기존 상태를 업데이트하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-211">All methods that are called within a contract must be pure; that is, they must not update any preexisting state.</span></span> <span data-ttu-id="76dba-212">순수 메서드는 순수 메서드에 진입한 후 생성된 개체를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-212">A pure method is allowed to modify objects that have been created after entry into the pure method.</span></span>  
  
 <span data-ttu-id="76dba-213">코드 계약 도구는 현재 다음과 같은 코드 요소를 순수하다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-213">Code contract tools currently assume that the following code elements are pure:</span></span>  
  
-   <span data-ttu-id="76dba-214"><xref:System.Diagnostics.Contracts.PureAttribute>로 표시된 메서드</span><span class="sxs-lookup"><span data-stu-id="76dba-214">Methods that are marked with the <xref:System.Diagnostics.Contracts.PureAttribute>.</span></span>  
  
-   <span data-ttu-id="76dba-215"><xref:System.Diagnostics.Contracts.PureAttribute>로 표시된 형식(형식의 모든 메서드에 특성이 적용됨)</span><span class="sxs-lookup"><span data-stu-id="76dba-215">Types that are marked with the <xref:System.Diagnostics.Contracts.PureAttribute> (the attribute applies to all the type's methods).</span></span>  
  
-   <span data-ttu-id="76dba-216">속성 get 접근자</span><span class="sxs-lookup"><span data-stu-id="76dba-216">Property get accessors.</span></span>  
  
-   <span data-ttu-id="76dba-217">연산자(이름이 "op"로 시작하고 한두 개의 매개 변수와 void가 아닌 반환 형식을 가진 static 메서드)</span><span class="sxs-lookup"><span data-stu-id="76dba-217">Operators (static methods whose names start with "op", and that have one or two parameters and a non-void return type).</span></span>  
  
-   <span data-ttu-id="76dba-218">정규화된 이름이 "System.Diagnostics.Contracts.Contract", "System.String", "System.IO.Path" 또는 "System.Type"으로 시작하는 모든 메서드</span><span class="sxs-lookup"><span data-stu-id="76dba-218">Any method whose fully qualified name begins with "System.Diagnostics.Contracts.Contract", "System.String", "System.IO.Path", or "System.Type".</span></span>  
  
-   <span data-ttu-id="76dba-219">호출된 대리자(대리자 형식 자체가 <xref:System.Diagnostics.Contracts.PureAttribute> 특성을 가진 경우)</span><span class="sxs-lookup"><span data-stu-id="76dba-219">Any invoked delegate, provided that the delegate type itself is attributed with the <xref:System.Diagnostics.Contracts.PureAttribute>.</span></span> <span data-ttu-id="76dba-220">대리자 형식 <xref:System.Predicate%601?displayProperty=nameWithType> 및 <xref:System.Comparison%601?displayProperty=nameWithType>은 순수하다고 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-220">The delegate types <xref:System.Predicate%601?displayProperty=nameWithType> and <xref:System.Comparison%601?displayProperty=nameWithType> are considered pure.</span></span>  
  
<a name="visibility"></a>   
### <a name="visibility"></a><span data-ttu-id="76dba-221">표시 유형</span><span class="sxs-lookup"><span data-stu-id="76dba-221">Visibility</span></span>  
 <span data-ttu-id="76dba-222">계약에 언급된 모든 멤버는 최소한 멤버가 표시되는 메서드와 동일한 표시 유형이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-222">All members mentioned in a contract must be at least as visible as the method in which they appear.</span></span> <span data-ttu-id="76dba-223">예를 들어 전용 필드는 public 메서드에 대한 사전 조건에서 언급할 수 없습니다. 클라이언트가 메서드를 호출하기 전에 이러한 계약의 유효성을 검사할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-223">For example, a private field cannot be mentioned in a precondition for a public method; clients cannot validate such a contract before they call the method.</span></span> <span data-ttu-id="76dba-224">그러나 필드가 <xref:System.Diagnostics.Contracts.ContractPublicPropertyNameAttribute>로 표시된 경우에는 이러한 규칙에서 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-224">However, if the field is marked with the <xref:System.Diagnostics.Contracts.ContractPublicPropertyNameAttribute>, it is exempt from these rules.</span></span>  
  
## <a name="example"></a><span data-ttu-id="76dba-225">예제</span><span class="sxs-lookup"><span data-stu-id="76dba-225">Example</span></span>  
 <span data-ttu-id="76dba-226">다음 예제에서는 코드 계약을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="76dba-226">The following example shows the use of code contracts.</span></span>  
  
 [!code-csharp[ContractExample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/contractexample/cs/program.cs#1)]
 [!code-vb[ContractExample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/contractexample/vb/program.vb#1)]
