---
title: 최종 &lt;키워드&gt; 문 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.EndDefinition
helpviewer_keywords:
- End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
ms.openlocfilehash: 8137434bfd8c26144d78b1761b784cdba4894eaf
ms.sourcegitcommit: 7fe772c6c05a982153655d618c826e9839d39cac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/03/2018
ms.locfileid: "33605266"
---
# <a name="end-ltkeywordgt-statement-visual-basic"></a><span data-ttu-id="b29f3-102">최종 &lt;키워드&gt; 문 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b29f3-102">End &lt;keyword&gt; Statement (Visual Basic)</span></span>

<span data-ttu-id="b29f3-103">추가 키워드 뒤에, 해당 키워드 뒤에 문 블록의 정의가 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-103">When followed by an additional keyword, terminates the definition of the statement block introduced by that keyword.</span></span>

## <a name="syntax"></a><span data-ttu-id="b29f3-104">구문</span><span class="sxs-lookup"><span data-stu-id="b29f3-104">Syntax</span></span>

```vb
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
  
## <a name="parts"></a><span data-ttu-id="b29f3-105">요소</span><span class="sxs-lookup"><span data-stu-id="b29f3-105">Parts</span></span>

|<span data-ttu-id="b29f3-106">파트</span><span class="sxs-lookup"><span data-stu-id="b29f3-106">Part</span></span>|<span data-ttu-id="b29f3-107">설명</span><span class="sxs-lookup"><span data-stu-id="b29f3-107">Description</span></span>|
|---|---|
|`End`|<span data-ttu-id="b29f3-108">필수.</span><span class="sxs-lookup"><span data-stu-id="b29f3-108">Required.</span></span> <span data-ttu-id="b29f3-109">프로그래밍 요소의 정의 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-109">Terminates the definition of the programming element.</span></span>|
|`AddHandler`|<span data-ttu-id="b29f3-110">종료 하는 데 필요한를 `AddHandler` 일치 하는 시작 하는 접근자 `AddHandler` 사용자 지정에서 문을 [이벤트 연결 문으로](event-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-110">Required to terminate an `AddHandler` accessor begun by a matching `AddHandler` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`Class`|<span data-ttu-id="b29f3-111">일치 하는 시작 클래스 정의 종료 하는 데 필요한 [Class 문](class-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-111">Required to terminate a class definition begun by a matching [Class Statement](class-statement.md).</span></span>|
|`Enum`|<span data-ttu-id="b29f3-112">일치 하는 시작 된 열거형 정의 종료 하는 데 필요한 [Enum 문](enum-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-112">Required to terminate an enumeration definition begun by a matching [Enum Statement](enum-statement.md).</span></span>|
|`Event`|<span data-ttu-id="b29f3-113">종료 하는 데 필요한를 `Custom` 일치 하는 시작 하는 이벤트 정의 [이벤트 연결 문으로](event-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-113">Required to terminate a `Custom` event definition begun by a matching [Event Statement](event-statement.md).</span></span>|  
|`Function`|<span data-ttu-id="b29f3-114">종료 하는 데 필요한를 `Function` 일치 하는 시작 하는 프로시저 정의 [Function 문](function-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-114">Required to terminate a `Function` procedure definition begun by a matching [Function Statement](function-statement.md).</span></span> <span data-ttu-id="b29f3-115">실행 하는 경우는 `End Function` 문을 컨트롤이 호출 코드에 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-115">If execution encounters an `End Function` statement, control returns to the calling code.</span></span>|
|`Get`|<span data-ttu-id="b29f3-116">종료 하는 데 필요한를 `Property` 일치 하는 시작 하는 프로시저 정의 [Get 문은](get-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-116">Required to terminate a `Property` procedure definition begun by a matching [Get Statement](get-statement.md).</span></span> <span data-ttu-id="b29f3-117">실행 하는 경우는 `End Get` 문을 컨트롤 속성의 값을 요청 하는 문으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-117">If execution encounters an `End Get` statement, control returns to the statement requesting the property's value.</span></span>|
|`If`|<span data-ttu-id="b29f3-118">종료 하는 데 필요한는 `If`... `Then`... `Else` 일치 하는 시작 된 정의 차단 `If` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-118">Required to terminate an `If`...`Then`...`Else` block definition begun by a matching `If` statement.</span></span> <span data-ttu-id="b29f3-119">참조 [경우... 다음 중... Else 문](if-then-else-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-119">See [If...Then...Else Statement](if-then-else-statement.md).</span></span>|
|`Interface`|<span data-ttu-id="b29f3-120">일치 하는 시작 된 인터페이스 정의 종료 하는 데 필요한 [Interface 문](interface-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-120">Required to terminate an interface definition begun by a matching [Interface Statement](interface-statement.md).</span></span>|
|`Module`|<span data-ttu-id="b29f3-121">일치 하는 시작 모듈 정의 종료 하는 데 필요한 [Module 문](module-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-121">Required to terminate a module definition begun by a matching [Module Statement](module-statement.md).</span></span>|
|`Namespace`|<span data-ttu-id="b29f3-122">일치 하는 시작 된 네임 스페이스 정의 종료 하는 데 필요한 [Namespace 문](namespace-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-122">Required to terminate a namespace definition begun by a matching [Namespace Statement](namespace-statement.md).</span></span>|
|`Operator`|<span data-ttu-id="b29f3-123">일치 하는 시작 하는 연산자 정의 종료 하는 데 필요한 [Operator 문](operator-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-123">Required to terminate an operator definition begun by a matching [Operator Statement](operator-statement.md).</span></span>|
|`Property`|<span data-ttu-id="b29f3-124">일치 하는 시작 속성 정의 종료 하는 데 필요한 [Property 문](property-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-124">Required to terminate a property definition begun by a matching [Property Statement](property-statement.md).</span></span>|
|`RaiseEvent`|<span data-ttu-id="b29f3-125">종료 하는 데 필요한를 `RaiseEvent` 일치 하는 시작 하는 접근자 `RaiseEvent` 사용자 지정에서 문을 [이벤트 연결 문으로](event-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-125">Required to terminate a `RaiseEvent` accessor begun by a matching `RaiseEvent` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`RemoveHandler`|<span data-ttu-id="b29f3-126">종료 하는 데 필요한를 `RemoveHandler` 일치 하는 시작 하는 접근자 `RemoveHandler` 사용자 지정에서 문을 [이벤트 연결 문으로](event-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-126">Required to terminate a `RemoveHandler` accessor begun by a matching `RemoveHandler` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`Select`|<span data-ttu-id="b29f3-127">종료 하는 데 필요한를 `Select`... `Case` 일치 하는 시작 된 정의 차단 `Select` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-127">Required to terminate a `Select`...`Case` block definition begun by a matching `Select` statement.</span></span> <span data-ttu-id="b29f3-128">참조 [선택... Case 문](select-case-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-128">See [Select...Case Statement](select-case-statement.md).</span></span>  
|`Set`|<span data-ttu-id="b29f3-129">종료 하는 데 필요한를 `Property` 일치 하는 시작 하는 프로시저 정의 [Set 문을](set-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-129">Required to terminate a `Property` procedure definition begun by a matching [Set Statement](set-statement.md).</span></span> <span data-ttu-id="b29f3-130">실행 하는 경우는 `End Set` 문을 컨트롤 속성의 값을 설정 하는 문으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-130">If execution encounters an `End Set` statement, control returns to the statement setting the property's value.</span></span>  
|`Structure`|<span data-ttu-id="b29f3-131">일치 하는 시작 된 구조 정의 종료 하는 데 필요한 [Structure 문을](structure-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-131">Required to terminate a structure definition begun by a matching [Structure Statement](structure-statement.md).</span></span>  
|`Sub`|<span data-ttu-id="b29f3-132">종료 하는 데 필요한를 `Sub` 일치 하는 시작 하는 프로시저 정의 [Sub 문](sub-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-132">Required to terminate a `Sub` procedure definition begun by a matching [Sub Statement](sub-statement.md).</span></span> <span data-ttu-id="b29f3-133">실행 하는 경우는 `End Sub` 문을 컨트롤이 호출 코드에 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-133">If execution encounters an `End Sub` statement, control returns to the calling code.</span></span>  
|`SyncLock`|<span data-ttu-id="b29f3-134">종료 하는 데 필요한를 `SyncLock` 일치 하는 시작 된 정의 차단 `SyncLock` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-134">Required to terminate a `SyncLock` block definition begun by a matching `SyncLock` statement.</span></span> <span data-ttu-id="b29f3-135">참조 [SyncLock 문](synclock-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-135">See [SyncLock Statement](synclock-statement.md).</span></span>  
|`Try`|<span data-ttu-id="b29f3-136">종료 하는 데 필요한를 `Try`... `Catch`... `Finally` 일치 하는 시작 된 정의 차단 `Try` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-136">Required to terminate a `Try`...`Catch`...`Finally` block definition begun by a matching `Try` statement.</span></span> <span data-ttu-id="b29f3-137">참조 [시도 하는 중... Catch 하는 중... Finally 문](try-catch-finally-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-137">See [Try...Catch...Finally Statement](try-catch-finally-statement.md).</span></span>  
|`While`|<span data-ttu-id="b29f3-138">종료 하는 데 필요한를 `While` 일치 하는 시작 된 정의 루프 `While` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-138">Required to terminate a `While` loop definition begun by a matching `While` statement.</span></span> <span data-ttu-id="b29f3-139">참조 [하는 동안... While 문 종료](while-end-while-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-139">See [While...End While Statement](while-end-while-statement.md).</span></span>  
|`With`| <span data-ttu-id="b29f3-140">종료 하는 데 필요한를 `With` 일치 하는 시작 된 정의 차단 `With` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-140">Required to terminate a `With` block definition begun by a matching `With` statement.</span></span> <span data-ttu-id="b29f3-141">참조 [사용 하 여는 중... 문을 사용 하 여 종료](with-end-with-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-141">See [With...End With Statement](with-end-with-statement.md).</span></span>  
|||
  
## <a name="directives"></a><span data-ttu-id="b29f3-142">지시문</span><span class="sxs-lookup"><span data-stu-id="b29f3-142">Directives</span></span>

<span data-ttu-id="b29f3-143">앞에 숫자 기호 (`#`), `End` 키워드는 해당 지시문에 도입 된 전처리 블록을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-143">When preceded by a number sign (`#`), the `End` keyword terminates a preprocessing block introduced by the corresponding directive.</span></span>  

```vb
#End ExternalSource
#End If
#End Region
```

|<span data-ttu-id="b29f3-144">파트</span><span class="sxs-lookup"><span data-stu-id="b29f3-144">Part</span></span>|<span data-ttu-id="b29f3-145">설명</span><span class="sxs-lookup"><span data-stu-id="b29f3-145">Description</span></span>|
|---|---|
|`#End`|<span data-ttu-id="b29f3-146">필수.</span><span class="sxs-lookup"><span data-stu-id="b29f3-146">Required.</span></span> <span data-ttu-id="b29f3-147">전처리 블록의 정의 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-147">Terminates the definition of the preprocessing block.</span></span>|
|`ExternalSource`|<span data-ttu-id="b29f3-148">일치 하는 시작 하는 외부 소스 블록을 종료 하는 데 필요한 [#ExternalSource 지시문](../directives/externalsource-directive.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-148">Required to terminate an external source block begun by a matching [#ExternalSource Directive](../directives/externalsource-directive.md).</span></span>|
|`If`|<span data-ttu-id="b29f3-149">일치 하는 시작 된 조건부 컴파일 블록을 종료 하는 데 필요한 `#If` 지시문입니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-149">Required to terminate a conditional compilation block begun by a matching `#If` directive.</span></span> <span data-ttu-id="b29f3-150">참조 [#If... Then... #Else 지시문](../directives/if-then-else-directives.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-150">See [#If...Then...#Else Directives](../directives/if-then-else-directives.md).</span></span>|
|`Region`|<span data-ttu-id="b29f3-151">일치 하는 시작 된 소스 영역 블록을 종료 하는 데 필요한 [#Region 지시문](../directives/region-directive.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-151">Required to terminate a source region block begun by a matching [#Region Directive](../directives/region-directive.md).</span></span>|
|||

## <a name="remarks"></a><span data-ttu-id="b29f3-152">설명</span><span class="sxs-lookup"><span data-stu-id="b29f3-152">Remarks</span></span>

<span data-ttu-id="b29f3-153">합니다 [End 문](end-statement.md), 추가 키워드, 실행을 즉시 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-153">The [End Statement](end-statement.md), without an additional keyword, terminates execution immediately.</span></span>

## <a name="smart-device-developer-notes"></a><span data-ttu-id="b29f3-154">스마트 장치 개발자 노트</span><span class="sxs-lookup"><span data-stu-id="b29f3-154">Smart Device Developer Notes</span></span>  

<span data-ttu-id="b29f3-155">`End` 추가 키워드, 문이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b29f3-155">The `End` statement, without an additional keyword, is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b29f3-156">참고자료</span><span class="sxs-lookup"><span data-stu-id="b29f3-156">See also</span></span>

[<span data-ttu-id="b29f3-157">End 문</span><span class="sxs-lookup"><span data-stu-id="b29f3-157">End Statement</span></span>](end-statement.md)
