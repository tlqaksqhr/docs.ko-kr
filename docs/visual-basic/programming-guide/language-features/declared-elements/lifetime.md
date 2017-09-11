---
title: "Visual Basic의 수명 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- static variables, lifetime
- static variables, Visual Basic
- declared elements, lifetime
- Shared variable lifetime
- lifetime, declared elements
- lifetime, Visual Basic
- lifetime
ms.assetid: bd91e390-690a-469a-9946-8dca70bc14e7
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4e183d1fa36c967facbb81ebd6917a8fb75d48cd
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="lifetime-in-visual-basic"></a><span data-ttu-id="61538-102">Visual Basic의 수명</span><span class="sxs-lookup"><span data-stu-id="61538-102">Lifetime in Visual Basic</span></span>
<span data-ttu-id="61538-103">*수명* 선언 요소의 시간 동안 어떤 용도로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61538-103">The *lifetime* of a declared element is the period of time during which it is available for use.</span></span> <span data-ttu-id="61538-104">변수는 수명이 있는 유일한 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="61538-104">Variables are the only elements that have lifetime.</span></span> <span data-ttu-id="61538-105">이 위해 컴파일러는 프로시저 매개 변수를 처리 및 변수의 특별 한 경우로 함수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="61538-105">For this purpose, the compiler treats procedure parameters and function returns as special cases of variables.</span></span> <span data-ttu-id="61538-106">변수의 수명 값을 저장할 수 있는 기간을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="61538-106">The lifetime of a variable represents the period of time during which it can hold a value.</span></span> <span data-ttu-id="61538-107">해당 값은 해당 수명 동안 변경 될 수 있지만 항상 어떤 값을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="61538-107">Its value can change over its lifetime, but it always holds some value.</span></span>  
  
## <a name="different-lifetimes"></a><span data-ttu-id="61538-108">다른 수명</span><span class="sxs-lookup"><span data-stu-id="61538-108">Different Lifetimes</span></span>  
 <span data-ttu-id="61538-109">A *멤버 변수* (다른 프로시저 외부의 모듈 수준에서 선언 됨) 일반적으로 수명이 같은 선언 된 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="61538-109">A *member variable* (declared at module level, outside any procedure) typically has the same lifetime as the element in which it is declared.</span></span> <span data-ttu-id="61538-110">클래스 또는 구조체에 선언 된 비공유 변수 선언 된 구조체의 각 인스턴스에 대해 별도 복사본으로 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="61538-110">A nonshared variable declared in a class or structure exists as a separate copy for each instance of the class or structure in which it is declared.</span></span> <span data-ttu-id="61538-111">각 변수는 해당 인스턴스로 수명이 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="61538-111">Each such variable has the same lifetime as its instance.</span></span> <span data-ttu-id="61538-112">그러나 한 `Shared` 변수는 응용 프로그램을 실행 하는 전체 기간 동안 지속 되는 단일 수명이 합니다.</span><span class="sxs-lookup"><span data-stu-id="61538-112">However, a `Shared` variable has only a single lifetime, which lasts for the entire time your application is running.</span></span>  
  
 <span data-ttu-id="61538-113">A *지역 변수* (프로시저 내에 선언 된) 선언 된 프로시저를 실행 하는 동안에 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="61538-113">A *local variable* (declared inside a procedure) exists only while the procedure in which it is declared is running.</span></span> <span data-ttu-id="61538-114">또한 모든 함수 반환 값 및 해당 프로시저의 매개 변수에 적용 됩니다이.</span><span class="sxs-lookup"><span data-stu-id="61538-114">This applies also to that procedure's parameters and to any function return.</span></span> <span data-ttu-id="61538-115">그러나 해당 프로시저가 다른 프로시저를 호출 하는 경우 지역 변수 값을 유지 호출된 프로시저를 실행 하는 동안.</span><span class="sxs-lookup"><span data-stu-id="61538-115">However, if that procedure calls other procedures, the local variables retain their values while the called procedures are running.</span></span>  
  
## <a name="beginning-of-lifetime"></a><span data-ttu-id="61538-116">수명의 시작</span><span class="sxs-lookup"><span data-stu-id="61538-116">Beginning of Lifetime</span></span>  
 <span data-ttu-id="61538-117">로컬 변수의 수명 제어가 선언 되는 프로시저를 입력할 때 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61538-117">A local variable's lifetime begins when control enters the procedure in which it is declared.</span></span> <span data-ttu-id="61538-118">프로시저를 시작 하는 즉시 모든 지역 변수 데이터 형식에 대 한 기본 값으로 초기화 됩니다를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="61538-118">Every local variable is initialized to the default value for its data type as soon as the procedure begins running.</span></span> <span data-ttu-id="61538-119">프로시저가 발견 하는 경우는 `Dim` 초기 값을 지정 하는 문을 해당 변수를 설정 하려면 이러한 값을 코드에 이미 다른 값을 할당 한 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="61538-119">When the procedure encounters a `Dim` statement that specifies initial values, it sets those variables to those values, even if your code had already assigned other values to them.</span></span>  
  
 <span data-ttu-id="61538-120">구조체 변수의 각 멤버는 마치는 별도 변수인 것 처럼 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61538-120">Each member of a structure variable is initialized as if it were a separate variable.</span></span> <span data-ttu-id="61538-121">마찬가지로, 배열 변수의 각 요소는 개별적으로 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61538-121">Similarly, each element of an array variable is initialized individually.</span></span>  
  
 <span data-ttu-id="61538-122">프로시저 내의 블록 내에서 선언 된 변수 (예:는 `For` 루프) 프로시저에는 항목에 대해 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61538-122">Variables declared within a block inside a procedure (such as a `For` loop) are initialized on entry to the procedure.</span></span> <span data-ttu-id="61538-123">이러한 초기화 코드 블록 실행 여부를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="61538-123">These initializations take effect whether or not your code ever executes the block.</span></span>  
  
## <a name="end-of-lifetime"></a><span data-ttu-id="61538-124">수명의 끝</span><span class="sxs-lookup"><span data-stu-id="61538-124">End of Lifetime</span></span>  
 <span data-ttu-id="61538-125">프로시저 종료 되 면 해당 지역 변수의 값 유지 되지 않습니다, 그리고 및 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 해당 메모리를 회수 합니다.</span><span class="sxs-lookup"><span data-stu-id="61538-125">When a procedure terminates, the values of its local variables are not preserved, and [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] reclaims their memory.</span></span> <span data-ttu-id="61538-126">다음에 프로시저를 호출할 때 모든 지역 변수가 다시 만들고 다시 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="61538-126">The next time you call the procedure, all its local variables are created afresh and reinitialized.</span></span>  
  
 <span data-ttu-id="61538-127">클래스 또는 구조체의 인스턴스를 종료 하는 경우의 메모리와 해당 값 비공유 변수의 손실 합니다.</span><span class="sxs-lookup"><span data-stu-id="61538-127">When an instance of a class or structure terminates, its nonshared variables lose their memory and their values.</span></span> <span data-ttu-id="61538-128">클래스 또는 구조체의 각 새 인스턴스를 만들고 비공유 변수의 다시 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="61538-128">Each new instance of the class or structure creates and reinitializes its nonshared variables.</span></span> <span data-ttu-id="61538-129">그러나 `Shared` 변수는 응용 프로그램의 실행이 중지 될 때까지 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61538-129">However, `Shared` variables are preserved until your application stops running.</span></span>  
  
## <a name="extension-of-lifetime"></a><span data-ttu-id="61538-130">수명의 연장</span><span class="sxs-lookup"><span data-stu-id="61538-130">Extension of Lifetime</span></span>  
 <span data-ttu-id="61538-131">사용 하 여 로컬 변수를 선언 하는 경우는 `Static` 키워드를 수명 보다 길면 해당 프로시저의 실행 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="61538-131">If you declare a local variable with the `Static` keyword, its lifetime is longer than the execution time of its procedure.</span></span> <span data-ttu-id="61538-132">다음 표에서 프로시저 선언 기간 결정 하는 방법을 보여 줍니다.는 `Static` 변수가 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="61538-132">The following table shows how the procedure declaration determines how long a `Static` variable exists.</span></span>  
  
|<span data-ttu-id="61538-133">프로시저 위치 및 공유</span><span class="sxs-lookup"><span data-stu-id="61538-133">Procedure location and sharing</span></span>|<span data-ttu-id="61538-134">정적 변수 수명을 시작합니다</span><span class="sxs-lookup"><span data-stu-id="61538-134">Static variable lifetime begins</span></span>|<span data-ttu-id="61538-135">정적 변수 수명 끝</span><span class="sxs-lookup"><span data-stu-id="61538-135">Static variable lifetime ends</span></span>|  
|------------------------------------|-------------------------------------|-----------------------------------|  
|<span data-ttu-id="61538-136">(기본적으로 공유) 모듈에서</span><span class="sxs-lookup"><span data-stu-id="61538-136">In a module (shared by default)</span></span>|<span data-ttu-id="61538-137">처음에 프로시저 호출 될 때</span><span class="sxs-lookup"><span data-stu-id="61538-137">The first time the procedure is called</span></span>|<span data-ttu-id="61538-138">응용 프로그램 실행이 중지 될 때</span><span class="sxs-lookup"><span data-stu-id="61538-138">When your application stops running</span></span>|  
|<span data-ttu-id="61538-139">클래스에서 `Shared` (절차는 인스턴스 멤버가 아님)</span><span class="sxs-lookup"><span data-stu-id="61538-139">In a class, `Shared` (procedure is not an instance member)</span></span>|<span data-ttu-id="61538-140">처음으로 프로시저를 호출할 특정 인스턴스 또는 자체 클래스 또는 구조체 이름</span><span class="sxs-lookup"><span data-stu-id="61538-140">The first time the procedure is called either on a specific instance or on the class or structure name itself</span></span>|<span data-ttu-id="61538-141">응용 프로그램 실행이 중지 될 때</span><span class="sxs-lookup"><span data-stu-id="61538-141">When your application stops running</span></span>|  
|<span data-ttu-id="61538-142">클래스의 인스턴스에 하지 `Shared` (절차는 인스턴스 멤버는)</span><span class="sxs-lookup"><span data-stu-id="61538-142">In an instance of a class, not `Shared` (procedure is an instance member)</span></span>|<span data-ttu-id="61538-143">프로시저 라고 하는 특정 인스턴스에 처음으로</span><span class="sxs-lookup"><span data-stu-id="61538-143">The first time the procedure is called on the specific instance</span></span>|<span data-ttu-id="61538-144">가비지 수집 (GC)에 인스턴스가 해제 되는 경우</span><span class="sxs-lookup"><span data-stu-id="61538-144">When the instance is released for garbage collection (GC)</span></span>|  
  
## <a name="static-variables-of-the-same-name"></a><span data-ttu-id="61538-145">이름이 같은 정적 변수</span><span class="sxs-lookup"><span data-stu-id="61538-145">Static Variables of the Same Name</span></span>  
 <span data-ttu-id="61538-146">둘 이상의 프로시저에 같은 이름의 정적 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61538-146">You can declare static variables with the same name in more than one procedure.</span></span> <span data-ttu-id="61538-147">이 작업을 수행 하는 경우는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러는 각 변수를 별도 요소로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="61538-147">If you do this, the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler considers each such variable to be a separate element.</span></span> <span data-ttu-id="61538-148">이러한 변수 중 하나를 초기화할 때 다른 값 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61538-148">The initialization of one of these variables does not affect the values of the others.</span></span> <span data-ttu-id="61538-149">오버 로드 집합이 있는 프로시저를 정의 하 고 각 오버 로드에 동일한 이름 가진 정적 변수를 선언 하는 경우에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61538-149">The same applies if you define a procedure with a set of overloads and declare a static variable with the same name in each overload.</span></span>  
  
## <a name="containing-elements-for-static-variables"></a><span data-ttu-id="61538-150">정적 변수에 대 한 요소가 포함 된</span><span class="sxs-lookup"><span data-stu-id="61538-150">Containing Elements for Static Variables</span></span>  
 <span data-ttu-id="61538-151">해당 클래스의 프로시저 즉, 클래스 내의 정적 지역 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61538-151">You can declare a static local variable within a class, that is, inside a procedure in that class.</span></span> <span data-ttu-id="61538-152">그러나 구조체 멤버 또는 해당 구조 내에서 프로시저의 지역 변수로 구조체에 정적 지역 변수를 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61538-152">However, you cannot declare a static local variable within a structure, either as a structure member or as a local variable of a procedure within that structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61538-153">예제</span><span class="sxs-lookup"><span data-stu-id="61538-153">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="61538-154">설명</span><span class="sxs-lookup"><span data-stu-id="61538-154">Description</span></span>  
 <span data-ttu-id="61538-155">다음 예제에서는 사용 하 여 변수를 선언 된 [정적](../../../../visual-basic/language-reference/modifiers/static.md) 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="61538-155">The following example declares a variable with the [Static](../../../../visual-basic/language-reference/modifiers/static.md) keyword.</span></span> <span data-ttu-id="61538-156">(참고 필요 하지 않은 `Dim` 키워드 때는 [Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) 와 같은 한정자를 사용 하 여 `Static`.)</span><span class="sxs-lookup"><span data-stu-id="61538-156">(Note that you do not need the `Dim` keyword when the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) uses a modifier such as `Static`.)</span></span>  
  
### <a name="code"></a><span data-ttu-id="61538-157">코드</span><span class="sxs-lookup"><span data-stu-id="61538-157">Code</span></span>  
 <span data-ttu-id="61538-158">[!code-vb[VbVbalrKeywords #&13;](../../../../visual-basic/language-reference/codesnippet/VisualBasic/lifetime_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="61538-158">[!code-vb[VbVbalrKeywords#13](../../../../visual-basic/language-reference/codesnippet/VisualBasic/lifetime_1.vb)]</span></span>  
  
### <a name="comments"></a><span data-ttu-id="61538-159">설명</span><span class="sxs-lookup"><span data-stu-id="61538-159">Comments</span></span>  
 <span data-ttu-id="61538-160">위의 예제에서는 변수에서에서 `applesSold` 계속 존재는 절차를 수행한 후 `runningTotal` 호출 코드로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="61538-160">In the preceding example, the variable `applesSold` continues to exist after the procedure `runningTotal` returns to the calling code.</span></span> <span data-ttu-id="61538-161">다음에 `runningTotal` 이라고 `applesSold` 는 이전에 계산 된 값을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="61538-161">The next time `runningTotal` is called, `applesSold` retains its previously calculated value.</span></span>  
  
 <span data-ttu-id="61538-162">경우 `applesSold` 선언 되었으면 네임 스페이스를 사용 하지 않고 `Static`, 이전의 누적된 값에 대 한 호출에서 유지 되지는 것 `runningTotal`합니다.</span><span class="sxs-lookup"><span data-stu-id="61538-162">If `applesSold` had been declared without using `Static`, the previous accumulated values would not be preserved across calls to `runningTotal`.</span></span> <span data-ttu-id="61538-163">다음에 `runningTotal` 를 호출 했지만 `applesSold` 다시 및 0으로 초기화 된 것 및 `runningTotal` 호출 된 동일한 값 단순히 반환는 합니다.</span><span class="sxs-lookup"><span data-stu-id="61538-163">The next time `runningTotal` was called, `applesSold` would have been recreated and initialized to 0, and `runningTotal` would have simply returned the same value with which it was called.</span></span>  
  
### <a name="compiling-the-code"></a><span data-ttu-id="61538-164">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="61538-164">Compiling the Code</span></span>  
 <span data-ttu-id="61538-165">정적 지역 변수 선언의 일부로 값을 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61538-165">You can initialize the value of a static local variable as part of its declaration.</span></span> <span data-ttu-id="61538-166">배열을 선언 하는 경우 `Static`, 해당 순위 (차원의 수), 각 차원의 길이 및 개별 요소의 값을 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61538-166">If you declare an array to be `Static`, you can initialize its rank (number of dimensions), the length of each dimension, and the values of the individual elements.</span></span>  
  
### <a name="security"></a><span data-ttu-id="61538-167">보안</span><span class="sxs-lookup"><span data-stu-id="61538-167">Security</span></span>  
 <span data-ttu-id="61538-168">앞의 예제에서 선언 하 여 동일한 수명 주기를 생성할 수 있습니다 `applesSold` 모듈 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="61538-168">In the preceding example, you can produce the same lifetime by declaring `applesSold` at module level.</span></span> <span data-ttu-id="61538-169">그러나 변수의 범위를 이러한 방식으로 변경 하면 프로시저가 더 이상 있을 경우 단독으로 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61538-169">If you changed the scope of a variable this way, however, the procedure would no longer have exclusive access to it.</span></span> <span data-ttu-id="61538-170">다른 프로시저에 액세스할 수 있으므로 `applesSold` 및 해당 값을 변경, 누적 합계를 신뢰할 수 및 코드를 유지 하기 위해 더욱 어려워질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61538-170">Because other procedures could access `applesSold` and change its value, the running total could be unreliable and the code could be more difficult to maintain.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61538-171">참고 항목</span><span class="sxs-lookup"><span data-stu-id="61538-171">See Also</span></span>  
 <span data-ttu-id="61538-172">[공유](../../../../visual-basic/language-reference/modifiers/shared.md) </span><span class="sxs-lookup"><span data-stu-id="61538-172">[Shared](../../../../visual-basic/language-reference/modifiers/shared.md) </span></span>  
<span data-ttu-id="61538-173"> [아무 것도](../../../../visual-basic/language-reference/nothing.md) </span><span class="sxs-lookup"><span data-stu-id="61538-173"> [Nothing](../../../../visual-basic/language-reference/nothing.md) </span></span>  
<span data-ttu-id="61538-174"> [선언된 요소 이름](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span><span class="sxs-lookup"><span data-stu-id="61538-174"> [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span></span>  
<span data-ttu-id="61538-175"> [선언 된 요소에 대 한 참조](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) </span><span class="sxs-lookup"><span data-stu-id="61538-175"> [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) </span></span>  
<span data-ttu-id="61538-176"> [Visual Basic의 범위](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md) </span><span class="sxs-lookup"><span data-stu-id="61538-176"> [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md) </span></span>  
<span data-ttu-id="61538-177"> [Visual Basic의 액세스 수준](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md) </span><span class="sxs-lookup"><span data-stu-id="61538-177"> [Access Levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md) </span></span>  
<span data-ttu-id="61538-178"> [변수](../../../../visual-basic/programming-guide/language-features/variables/index.md) </span><span class="sxs-lookup"><span data-stu-id="61538-178"> [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md) </span></span>  
<span data-ttu-id="61538-179"> [변수 선언](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="61538-179"> [Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span></span>  
<span data-ttu-id="61538-180"> [데이터 형식 문제 해결](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="61538-180"> [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
<span data-ttu-id="61538-181"> [정적](../../../../visual-basic/language-reference/modifiers/static.md)</span><span class="sxs-lookup"><span data-stu-id="61538-181"> [Static](../../../../visual-basic/language-reference/modifiers/static.md)</span></span>
