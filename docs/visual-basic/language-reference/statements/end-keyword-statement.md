---
title: "최종 &lt;키워드&gt; 문 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.EndDefinition
helpviewer_keywords: End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cf0ac1221f8a85a8a43599d9c5ec210884205e5e
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="end-ltkeywordgt-statement-visual-basic"></a><span data-ttu-id="3b25f-102">최종 &lt;키워드&gt; 문 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3b25f-102">End &lt;keyword&gt; Statement (Visual Basic)</span></span>
<span data-ttu-id="3b25f-103">추가 키워드 뒤에 나올, 해당 키워드 뒤에 문 블록의 정의 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-103">When followed by an additional keyword, terminates the definition of the statement block introduced by that keyword.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b25f-104">구문</span><span class="sxs-lookup"><span data-stu-id="3b25f-104">Syntax</span></span>  
  
```  
End AddHandler  
End Class   
End Enum   
End Event   
End Function   
End Get   
End If   
End Interface   
End Module   
End Namespace   
End Operator   
End Property   
End RaiseEvent  
End RemoveHandler  
End Select   
End Set   
End Structure   
End Sub   
End SyncLock   
End Try   
End While   
End With  
```  
  
## <a name="parts"></a><span data-ttu-id="3b25f-105">요소</span><span class="sxs-lookup"><span data-stu-id="3b25f-105">Parts</span></span>  
 `End`  
 <span data-ttu-id="3b25f-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="3b25f-106">Required.</span></span> <span data-ttu-id="3b25f-107">프로그래밍 요소의 정의 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-107">Terminates the definition of the programming element.</span></span>  
  
 `AddHandler`  
 <span data-ttu-id="3b25f-108">종료 하는 데 필요한 프로그램 `AddHandler` 접근자는 일치 하는 시작 `AddHandler` 문을 사용자 지정에서 [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-108">Required to terminate an `AddHandler` accessor begun by a matching `AddHandler` statement in a custom [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
 `Class`  
 <span data-ttu-id="3b25f-109">일치 하는 시작 되었습니다. 클래스 정의 종료 하는 데 필요한 [Class 문](../../../visual-basic/language-reference/statements/class-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-109">Required to terminate a class definition begun by a matching [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md).</span></span>  
  
 `Enum`  
 <span data-ttu-id="3b25f-110">일치 하는 시작 된 열거형 정의 종료 하는 데 필요한 [Enum 문](../../../visual-basic/language-reference/statements/enum-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-110">Required to terminate an enumeration definition begun by a matching [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md).</span></span>  
  
 `Event`  
 <span data-ttu-id="3b25f-111">종료 하는 데 필요한는 `Custom` 는 일치 하는 시작 된 이벤트 정의 [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-111">Required to terminate a `Custom` event definition begun by a matching [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
 `Function`  
 <span data-ttu-id="3b25f-112">종료 하는 데 필요한는 `Function` 는 일치 하는 시작 된 프로시저 정의 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-112">Required to terminate a `Function` procedure definition begun by a matching [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span> <span data-ttu-id="3b25f-113">실행 발생 한 경우는 `End``Function` 문, 컨트롤이 호출 코드에 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-113">If execution encounters an `End``Function` statement, control returns to the calling code.</span></span>  
  
 `Get`  
 <span data-ttu-id="3b25f-114">종료 하는 데 필요한는 `Property` 는 일치 하는 시작 된 프로시저 정의 [Get 문을](../../../visual-basic/language-reference/statements/get-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-114">Required to terminate a `Property` procedure definition begun by a matching [Get Statement](../../../visual-basic/language-reference/statements/get-statement.md).</span></span> <span data-ttu-id="3b25f-115">실행 발생 한 경우는 `End``Get` 속성의 값을 요청 하는 문으로 문에 제어가 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-115">If execution encounters an `End``Get` statement, control returns to the statement requesting the property's value.</span></span>  
  
 `If`  
 <span data-ttu-id="3b25f-116">종료 하는 데 필요한 프로그램 `If`... `Then`... `Else` 블록으로 일치 하는 시작 된 정의 `If` 문.</span><span class="sxs-lookup"><span data-stu-id="3b25f-116">Required to terminate an `If`...`Then`...`Else` block definition begun by a matching `If` statement.</span></span> <span data-ttu-id="3b25f-117">참조 [경우... 다음 중... Else 문](../../../visual-basic/language-reference/statements/if-then-else-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-117">See [If...Then...Else Statement](../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span></span>  
  
 `Interface`  
 <span data-ttu-id="3b25f-118">일치 하는 시작 된 인터페이스 정의 종료 하는 데 필요한 [Interface 문](../../../visual-basic/language-reference/statements/interface-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-118">Required to terminate an interface definition begun by a matching [Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md).</span></span>  
  
 `Module`  
 <span data-ttu-id="3b25f-119">일치 하는 시작 된 모듈 정의 종료 하는 데 필요한 [Module 문](../../../visual-basic/language-reference/statements/module-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-119">Required to terminate a module definition begun by a matching [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md).</span></span>  
  
 `Namespace`  
 <span data-ttu-id="3b25f-120">일치 하는 시작 된 네임 스페이스 정의 종료 하는 데 필요한 [Namespace 문](../../../visual-basic/language-reference/statements/namespace-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-120">Required to terminate a namespace definition begun by a matching [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md).</span></span>  
  
 `Operator`  
 <span data-ttu-id="3b25f-121">일치 하는 시작 된 연산자 정의 종료 하는 데 필요한 [Operator 문](../../../visual-basic/language-reference/statements/operator-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-121">Required to terminate an operator definition begun by a matching [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
 `Property`  
 <span data-ttu-id="3b25f-122">일치 하는 시작 된 속성 정의 종료 하는 데 필요한 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-122">Required to terminate a property definition begun by a matching [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md).</span></span>  
  
 `RaiseEvent`  
 <span data-ttu-id="3b25f-123">종료 하는 데 필요한는 `RaiseEvent` 접근자는 일치 하는 시작 `RaiseEvent` 문을 사용자 지정에서 [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-123">Required to terminate a `RaiseEvent` accessor begun by a matching `RaiseEvent` statement in a custom [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
 `RemoveHandler`  
 <span data-ttu-id="3b25f-124">종료 하는 데 필요한는 `RemoveHandler` 접근자는 일치 하는 시작 `RemoveHandler` 문을 사용자 지정에서 [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-124">Required to terminate a `RemoveHandler` accessor begun by a matching `RemoveHandler` statement in a custom [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
 `Select`  
 <span data-ttu-id="3b25f-125">종료 하는 데 필요한는 `Select`... `Case` 블록으로 일치 하는 시작 된 정의 `Select` 문.</span><span class="sxs-lookup"><span data-stu-id="3b25f-125">Required to terminate a `Select`...`Case` block definition begun by a matching `Select` statement.</span></span> <span data-ttu-id="3b25f-126">참조 [선택... Case 문](../../../visual-basic/language-reference/statements/select-case-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-126">See [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
 `Set`  
 <span data-ttu-id="3b25f-127">종료 하는 데 필요한는 `Property` 는 일치 하는 시작 된 프로시저 정의 [Set 문을](../../../visual-basic/language-reference/statements/set-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-127">Required to terminate a `Property` procedure definition begun by a matching [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md).</span></span> <span data-ttu-id="3b25f-128">실행 발생 한 경우는 `End``Set` 속성의 값을 설정 하는 문으로 문에 제어가 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-128">If execution encounters an `End``Set` statement, control returns to the statement setting the property's value.</span></span>  
  
 `Structure`  
 <span data-ttu-id="3b25f-129">일치 하는 시작 된 구조 정의 종료 하는 데 필요한 [Structure 문을](../../../visual-basic/language-reference/statements/structure-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-129">Required to terminate a structure definition begun by a matching [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md).</span></span>  
  
 `Sub`  
 <span data-ttu-id="3b25f-130">종료 하는 데 필요한는 `Sub` 는 일치 하는 시작 된 프로시저 정의 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-130">Required to terminate a `Sub` procedure definition begun by a matching [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md).</span></span> <span data-ttu-id="3b25f-131">실행 발생 한 경우는 `End``Sub` 문, 컨트롤이 호출 코드에 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-131">If execution encounters an `End``Sub` statement, control returns to the calling code.</span></span>  
  
 `SyncLock`  
 <span data-ttu-id="3b25f-132">종료 하는 데 필요한는 `SyncLock` 블록으로 일치 하는 시작 된 정의 `SyncLock` 문.</span><span class="sxs-lookup"><span data-stu-id="3b25f-132">Required to terminate a `SyncLock` block definition begun by a matching `SyncLock` statement.</span></span> <span data-ttu-id="3b25f-133">참조 [SyncLock 문](../../../visual-basic/language-reference/statements/synclock-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-133">See [SyncLock Statement](../../../visual-basic/language-reference/statements/synclock-statement.md).</span></span>  
  
 `Try`  
 <span data-ttu-id="3b25f-134">종료 하는 데 필요한는 `Try`... `Catch`... `Finally` 블록으로 일치 하는 시작 된 정의 `Try` 문.</span><span class="sxs-lookup"><span data-stu-id="3b25f-134">Required to terminate a `Try`...`Catch`...`Finally` block definition begun by a matching `Try` statement.</span></span> <span data-ttu-id="3b25f-135">참조 [시도 중... Catch 하는 중... Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-135">See [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
 `While`  
 <span data-ttu-id="3b25f-136">종료 하는 데 필요한는 `While` 는 일치 하는 시작 된 정의 루프 `While` 문.</span><span class="sxs-lookup"><span data-stu-id="3b25f-136">Required to terminate a `While` loop definition begun by a matching `While` statement.</span></span> <span data-ttu-id="3b25f-137">참조 [동안... While 문 종료](../../../visual-basic/language-reference/statements/while-end-while-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-137">See [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span></span>  
  
 `With`  
 <span data-ttu-id="3b25f-138">종료 하는 데 필요한는 `With` 블록으로 일치 하는 시작 된 정의 `With` 문.</span><span class="sxs-lookup"><span data-stu-id="3b25f-138">Required to terminate a `With` block definition begun by a matching `With` statement.</span></span> <span data-ttu-id="3b25f-139">참조 [와... 문을 사용 하 여 종료](../../../visual-basic/language-reference/statements/with-end-with-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-139">See [With...End With Statement](../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b25f-140">설명</span><span class="sxs-lookup"><span data-stu-id="3b25f-140">Remarks</span></span>  
 <span data-ttu-id="3b25f-141">[End 문](../../../visual-basic/language-reference/statements/end-statement.md), 추가 키워드, 실행을 즉시 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-141">The [End Statement](../../../visual-basic/language-reference/statements/end-statement.md), without an additional keyword, terminates execution immediately.</span></span>  
  
 <span data-ttu-id="3b25f-142">앞에 숫자 기호 (`#`), `End` 키워드는 해당 지시문에 의해 도입 된 전처리 블록을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-142">When preceded by a number sign (`#`), the `End` keyword terminates a preprocessing block introduced by the corresponding directive.</span></span>  
  
 `#End`  
 <span data-ttu-id="3b25f-143">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="3b25f-143">Required.</span></span> <span data-ttu-id="3b25f-144">전처리 블록의 정의 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-144">Terminates the definition of the preprocessing block.</span></span>  
  
 `#ExternalSource`  
 <span data-ttu-id="3b25f-145">일치 하는 시작 된 외부 소스 블록을 종료 하는 데 필요한 [#ExternalSource 지시문](../../../visual-basic/language-reference/directives/externalsource-directive.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-145">Required to terminate an external source block begun by a matching [#ExternalSource Directive](../../../visual-basic/language-reference/directives/externalsource-directive.md).</span></span>  
  
 `#If`  
 <span data-ttu-id="3b25f-146">일치 하는 시작 된 조건부 컴파일 블록을 종료 하는 데 필요한 `#If` 지시문입니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-146">Required to terminate a conditional compilation block begun by a matching `#If` directive.</span></span> <span data-ttu-id="3b25f-147">참조 [#If... Then... #Else 지시문](../../../visual-basic/language-reference/directives/if-then-else-directives.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-147">See [#If...Then...#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md).</span></span>  
  
 `#Region`  
 <span data-ttu-id="3b25f-148">일치 하는 시작 된 소스 영역 블록을 종료 하는 데 필요한 [#Region 지시문](../../../visual-basic/language-reference/directives/region-directive.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-148">Required to terminate a source region block begun by a matching [#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md).</span></span>  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="3b25f-149">스마트 장치 개발자 노트</span><span class="sxs-lookup"><span data-stu-id="3b25f-149">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="3b25f-150">`End` 추가 키워드 문이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b25f-150">The `End` statement, without an additional keyword, is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b25f-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3b25f-151">See Also</span></span>  
 [<span data-ttu-id="3b25f-152">End 문</span><span class="sxs-lookup"><span data-stu-id="3b25f-152">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
