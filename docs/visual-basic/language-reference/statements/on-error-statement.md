---
title: "On Error 문(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.OnError
helpviewer_keywords:
- Visual Basic code, control flow
- Resume Next statement [Visual Basic]
- errors [Visual Basic], trapping
- error handling, On Error statement
- Next statement [Visual Basic], On Error
- control flow [Visual Basic], branching
- Error keyword [Visual Basic]
- execution [Visual Basic], conditional
- Resume statement [Visual Basic], and On Error statement
- Error statement [Visual Basic], and On Error statement
- GoTo statement [Visual Basic], and On Error statement
- branching [Visual Basic], on error
- conditional statements [Visual Basic], On Error
- On Error statement [Visual Basic], syntax
- On keyword [Visual Basic]
- run-time errors [Visual Basic], handling
- On Error statement [Visual Basic]
ms.assetid: ff947930-fb84-40cf-bd66-1ea219561d5c
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 96baa5d91d0a600b84ed832fb1e3b1ed71a9d89d
ms.sourcegitcommit: 2142a4732bb4ff519b9817db4c24a237b9810d4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2018
---
# <a name="on-error-statement-visual-basic"></a><span data-ttu-id="1eae3-102">On Error 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1eae3-102">On Error Statement (Visual Basic)</span></span>
<span data-ttu-id="1eae3-103">오류 처리 루틴을 사용 하 고 프로시저;에서 루틴의 위치 지정 오류 처리 루틴을 사용 하지 않도록 설정 하 여 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-103">Enables an error-handling routine and specifies the location of the routine within a procedure; can also be used to disable an error-handling routine.</span></span>  
  
 <span data-ttu-id="1eae3-104">모든 런타임 오류가 발생 하는 심각한 오류를 처리 하지: 오류 메시지가 표시 되 고 실행이 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-104">Without error handling, any run-time error that occurs is fatal: an error message is displayed, and execution stops.</span></span>  
  
 <span data-ttu-id="1eae3-105">가능 하면 항상 비구조적된 예외 처리를 사용 하지 않고 코드에서 처리 하는 구조화 된 예외를 사용 하는 것이 좋습니다 및 `On Error` 문.</span><span class="sxs-lookup"><span data-stu-id="1eae3-105">Whenever possible, we suggest you use structured exception handling in your code, rather than using unstructured exception handling and the `On Error` statement.</span></span> <span data-ttu-id="1eae3-106">자세한 내용은 [Try...Catch...Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1eae3-106">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1eae3-107">`Error` 키워드는 또한는 [Error 문](../../../visual-basic/language-reference/statements/error-statement.md), 이전 버전과 호환성을 위해 지원 되는 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-107">The `Error` keyword is also used in the [Error Statement](../../../visual-basic/language-reference/statements/error-statement.md), which is supported for backward compatibility.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1eae3-108">구문</span><span class="sxs-lookup"><span data-stu-id="1eae3-108">Syntax</span></span>  
  
```  
On Error { GoTo [ line | 0 | -1 ] | Resume Next }  
```  
  
## <a name="parts"></a><span data-ttu-id="1eae3-109">요소</span><span class="sxs-lookup"><span data-stu-id="1eae3-109">Parts</span></span>  
  
|<span data-ttu-id="1eae3-110">용어</span><span class="sxs-lookup"><span data-stu-id="1eae3-110">Term</span></span>|<span data-ttu-id="1eae3-111">정의</span><span class="sxs-lookup"><span data-stu-id="1eae3-111">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="1eae3-112">`GoTo` `line`</span><span class="sxs-lookup"><span data-stu-id="1eae3-112">`GoTo` `line`</span></span>|<span data-ttu-id="1eae3-113">필요한에 지정 된 줄에서 시작 하는 오류 처리 루틴을 사용 `line` 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-113">Enables the error-handling routine that starts at the line specified in the required `line` argument.</span></span> <span data-ttu-id="1eae3-114">`line` 인수는 모든 줄 레이블 또는 줄 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-114">The `line` argument is any line label or line number.</span></span> <span data-ttu-id="1eae3-115">런타임 오류가 발생 하는 경우 오류 처리기 활성화 될 때 지정된 된 줄에 분기를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-115">If a run-time error occurs, control branches to the specified line, making the error handler active.</span></span> <span data-ttu-id="1eae3-116">지정 된 줄에서와 동일한 절차에 있어야는 `On Error` 문 또는 컴파일 타임 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-116">The specified line must be in the same procedure as the `On Error` statement, or a compile-time error will occur.</span></span>|  
|<span data-ttu-id="1eae3-117">`GoTo` 0</span><span class="sxs-lookup"><span data-stu-id="1eae3-117">`GoTo` 0</span></span>|<span data-ttu-id="1eae3-118">현재 프로시저에서 사용 가능한 오류 처리기를 사용 하지 않도록 설정 하 고 다시 설정 하려면 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-118">Disables enabled error handler in the current procedure and resets it to `Nothing`.</span></span>|  
|<span data-ttu-id="1eae3-119">`GoTo` -1</span><span class="sxs-lookup"><span data-stu-id="1eae3-119">`GoTo` -1</span></span>|<span data-ttu-id="1eae3-120">현재 프로시저에서 사용 가능한 예외를 사용 하지 않도록 설정 하 고 다시 설정 하려면 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-120">Disables enabled exception in the current procedure and resets it to `Nothing`.</span></span>|  
|`Resume Next`|<span data-ttu-id="1eae3-121">런타임 오류가 발생 하는 제어 오류가 발생 한 장소와 해당 지점에서 실행이 계속 문 바로 다음 문으로 이동 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-121">Specifies that when a run-time error occurs, control goes to the statement immediately following the statement where the error occurred, and execution continues from that point.</span></span> <span data-ttu-id="1eae3-122">이 양식을 사용 하지 않고 `On Error GoTo` 개체에 액세스할 때.</span><span class="sxs-lookup"><span data-stu-id="1eae3-122">Use this form rather than `On Error GoTo` when accessing objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1eae3-123">설명</span><span class="sxs-lookup"><span data-stu-id="1eae3-123">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1eae3-124">비구조적된 예외 처리를 사용 하 여 보다는 가능한 경우 코드에서 구조적된 예외 처리를 사용 하는 것이 좋습니다 및 `On Error` 문.</span><span class="sxs-lookup"><span data-stu-id="1eae3-124">We recommend that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` statement.</span></span> <span data-ttu-id="1eae3-125">자세한 내용은 [Try...Catch...Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1eae3-125">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
 <span data-ttu-id="1eae3-126">"enabled" 오류 처리기를가 하 여 설정 하는 `On Error` 문.</span><span class="sxs-lookup"><span data-stu-id="1eae3-126">An "enabled" error handler is one that is turned on by an `On Error` statement.</span></span> <span data-ttu-id="1eae3-127">"활성" 오류 처리기가 오류를 처리 하는 사용 가능한 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-127">An "active" error handler is an enabled handler that is in the process of handling an error.</span></span>  
  
 <span data-ttu-id="1eae3-128">오류 처리 하는 동안 오류가 발생 하는 경우 (오류 발생 사이 및 `Resume`, `Exit Sub`, `Exit Function`, 또는 `Exit Property` 문), 현재 프로시저의 오류 처리기는 오류를 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-128">If an error occurs while an error handler is active (between the occurrence of the error and a `Resume`, `Exit Sub`, `Exit Function`, or `Exit Property` statement), the current procedure's error handler cannot handle the error.</span></span> <span data-ttu-id="1eae3-129">호출 하는 프로시저 제어가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-129">Control returns to the calling procedure.</span></span>  
  
 <span data-ttu-id="1eae3-130">호출 프로시저가 활성화 된 오류 처리기를 갖는 경우 오류 처리에 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-130">If the calling procedure has an enabled error handler, it is activated to handle the error.</span></span> <span data-ttu-id="1eae3-131">호출 하는 프로시저의 오류 처리기 활성 상태인 경우, 사용할 수 있지만, 비활성 상태 오류 처리기를 찾을 때까지 호출 앞의 절차를 통해 다시 제어가 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-131">If the calling procedure's error handler is also active, control passes back through previous calling procedures until an enabled, but inactive, error handler is found.</span></span> <span data-ttu-id="1eae3-132">이러한 오류 처리기가 있으면 실제로 발생 되는 시점의 수도 있는 오류가입니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-132">If no such error handler is found, the error is fatal at the point at which it actually occurred.</span></span>  
  
 <span data-ttu-id="1eae3-133">오류 처리기를 호출 하는 프로시저에 제어를 전달 될 때마다 해당 프로시저는 현재 프로시저가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-133">Each time the error handler passes control back to a calling procedure, that procedure becomes the current procedure.</span></span> <span data-ttu-id="1eae3-134">모든 프로시저에 오류 처리기가 오류 처리를 실행 하 여 지정 된 지점 현재 프로시저에서 재개는 `Resume` 문.</span><span class="sxs-lookup"><span data-stu-id="1eae3-134">Once an error is handled by an error handler in any procedure, execution resumes in the current procedure at the point designated by the `Resume` statement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1eae3-135">오류 처리 루틴 않습니다는 `Sub` 프로시저 또는 `Function` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-135">An error-handling routine is not a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="1eae3-136">줄 레이블 또는 줄 번호를 표시 된 코드의 섹션은</span><span class="sxs-lookup"><span data-stu-id="1eae3-136">It is a section of code marked by a line label or a line number.</span></span>  
  
## <a name="number-property"></a><span data-ttu-id="1eae3-137">Number 속성</span><span class="sxs-lookup"><span data-stu-id="1eae3-137">Number Property</span></span>  
 <span data-ttu-id="1eae3-138">오류 처리 루틴에 있는 값에 따라는 `Number` 의 속성은 `Err` 오류의 원인을 파악 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-138">Error-handling routines rely on the value in the `Number` property of the `Err` object to determine the cause of the error.</span></span> <span data-ttu-id="1eae3-139">루틴을 테스트 하거나 관련 속성 값을 저장 해야는 `Err` 개체 다른 오류가 발생 하기 전이나 오류가 발생할 수 있는 절차 전에 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-139">The routine should test or save relevant property values in the `Err` object before any other error can occur or before a procedure that might cause an error is called.</span></span> <span data-ttu-id="1eae3-140">속성 값에 `Err` 개체는 가장 최근의 오류만을 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-140">The property values in the `Err` object reflect only the most recent error.</span></span> <span data-ttu-id="1eae3-141">오류 메시지와 관련 된 `Err.Number` 에 포함 된 `Err.Description`합니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-141">The error message associated with `Err.Number` is contained in `Err.Description`.</span></span>  
  
## <a name="throw-statement"></a><span data-ttu-id="1eae3-142">Throw 문</span><span class="sxs-lookup"><span data-stu-id="1eae3-142">Throw Statement</span></span>  
 <span data-ttu-id="1eae3-143">발생 하는 오류는 `Err.Raise` 메서드 설정은 `Exception` 의 새로 만든된 인스턴스에 대 한 속성은 <xref:System.Exception> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-143">An error that is raised with the `Err.Raise` method sets the `Exception` property to a newly created instance of the <xref:System.Exception> class.</span></span> <span data-ttu-id="1eae3-144">파생 된 예외 형식의 예외를 발생 한 `Throw` 언어에서 문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-144">In order to support the raising of exceptions of derived exception types, a `Throw` statement is supported in the language.</span></span> <span data-ttu-id="1eae3-145">예외 인스턴스가 throw 되 게 하는 단일 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-145">This takes a single parameter that is the exception instance to be thrown.</span></span> <span data-ttu-id="1eae3-146">다음 예제에서는 처리를 지 원하는 기존 예외와 함께 이러한 기능은 사용할 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-146">The following example shows how these features can be used with the existing exception handling support:</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/on-error-statement_1.vb)]  
  
 <span data-ttu-id="1eae3-147">에 `On Error GoTo` 문은 예외 클래스에 관계 없이 모든 오류를 트래핑 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-147">Notice that the `On Error GoTo` statement traps all errors, regardless of the exception class.</span></span>  
  
## <a name="on-error-resume-next"></a><span data-ttu-id="1eae3-148">On Error Resume Next</span><span class="sxs-lookup"><span data-stu-id="1eae3-148">On Error Resume Next</span></span>  
 <span data-ttu-id="1eae3-149">`On Error Resume Next`실행이 런타임 오류를 발생 시킨 문 바로 다음 문을 사용 하 여 계속 하거나 포함 하는 프로시저에서 호출 바로 다음에 가장 최근의 문으로 `On Error Resume Next` 문.</span><span class="sxs-lookup"><span data-stu-id="1eae3-149">`On Error Resume Next` causes execution to continue with the statement immediately following the statement that caused the run-time error, or with the statement immediately following the most recent call out of the procedure containing the `On Error Resume Next` statement.</span></span> <span data-ttu-id="1eae3-150">이 문은 실행 시간 오류가 발생 해도 계속 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-150">This statement allows execution to continue despite a run-time error.</span></span> <span data-ttu-id="1eae3-151">프로시저 내의 다른 위치로 제어를 전송 하지 않고 오류 발생 오류 처리 루틴을 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-151">You can place the error-handling routine where the error would occur rather than transferring control to another location within the procedure.</span></span> <span data-ttu-id="1eae3-152">`On Error Resume Next` 문은 비활성화 됩니다 다른 프로시저를 호출할 때 실행 해야 하므로 `On Error Resume Next` 각 문이 인라인 내의 오류 처리 루틴을 원하는 경우 루틴을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-152">An `On Error Resume Next` statement becomes inactive when another procedure is called, so you should execute an `On Error Resume Next` statement in each called routine if you want inline error handling within that routine.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1eae3-153">`On Error Resume Next` 구문에 더 적합할 수 있습니다 `On Error GoTo` 다른 개체에 액세스 하는 동안 발생 한 오류를 처리 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="1eae3-153">The `On Error Resume Next` construct may be preferable to `On Error GoTo` when handling errors generated during access to other objects.</span></span> <span data-ttu-id="1eae3-154">검사 `Err` 개체와 함께 각 상호 작용 개체는 코드에서 액세스 된 후입니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-154">Checking `Err` after each interaction with an object removes ambiguity about which object was accessed by the code.</span></span> <span data-ttu-id="1eae3-155">확인할 수 있는 개체의 오류 코드에 배치 `Err.Number`, 개체가 원래 오류를 생성 뿐만 아니라 (에 지정 된 개체가 `Err.Source`).</span><span class="sxs-lookup"><span data-stu-id="1eae3-155">You can be sure which object placed the error code in `Err.Number`, as well as which object originally generated the error (the object specified in `Err.Source`).</span></span>  
  
## <a name="on-error-goto-0"></a><span data-ttu-id="1eae3-156">On Error GoTo 0</span><span class="sxs-lookup"><span data-stu-id="1eae3-156">On Error GoTo 0</span></span>  
 <span data-ttu-id="1eae3-157">`On Error GoTo 0`현재 프로시저의 오류 처리를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-157">`On Error GoTo 0` disables error handling in the current procedure.</span></span> <span data-ttu-id="1eae3-158">라인 0 프로시저 0 번 줄에 있는 경우에 오류 처리 코드의 시작으로 지정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-158">It doesn't specify line 0 as the start of the error-handling code, even if the procedure contains a line numbered 0.</span></span> <span data-ttu-id="1eae3-159">없이 `On Error GoTo 0` 문, 오류 처리기가 프로시저 종료 될 때 자동으로 비활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-159">Without an `On Error GoTo 0` statement, an error handler is automatically disabled when a procedure is exited.</span></span>  
  
## <a name="on-error-goto--1"></a><span data-ttu-id="1eae3-160">On Error GoTo-1</span><span class="sxs-lookup"><span data-stu-id="1eae3-160">On Error GoTo -1</span></span>  
 <span data-ttu-id="1eae3-161">`On Error GoTo -1`현재 프로시저에서 예외를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-161">`On Error GoTo -1` disables the exception in the current procedure.</span></span> <span data-ttu-id="1eae3-162">프로시저에이 문이 있는 경우에-1 번 줄 오류 처리 코드의 시작으로 지정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-162">It does not specify line -1 as the start of the error-handling code, even if the procedure contains a line numbered -1.</span></span> <span data-ttu-id="1eae3-163">없이 `On Error GoTo -1` 프로시저 종료 문, 예외가 자동으로 비활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-163">Without an `On Error GoTo -1` statement, an exception is automatically disabled when a procedure is exited.</span></span>  
  
 <span data-ttu-id="1eae3-164">오류 처리 코드 오류가 발생 하지 않은 경우 실행 되지 않도록 하려면 배치는 `Exit Sub`, `Exit Function`, 또는 `Exit Property` 문은 다음과 같이 오류 처리 루틴에 바로 앞:</span><span class="sxs-lookup"><span data-stu-id="1eae3-164">To prevent error-handling code from running when no error has occurred, place an `Exit Sub`, `Exit Function`, or `Exit Property` statement immediately before the error-handling routine, as in the following fragment:</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#18](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/on-error-statement_2.vb)]  
  
 <span data-ttu-id="1eae3-165">여기에서 오류 처리 코드가 다음과 `Exit Sub` 문 앞에 오는 및는 `End Sub` 문을 프로시저 흐름을 구분 하기 위해.</span><span class="sxs-lookup"><span data-stu-id="1eae3-165">Here, the error-handling code follows the `Exit Sub` statement and precedes the `End Sub` statement to separate it from the procedure flow.</span></span> <span data-ttu-id="1eae3-166">프로시저에서 아무 곳 이나 오류 처리 코드를 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-166">You can place error-handling code anywhere in a procedure.</span></span>  
  
## <a name="untrapped-errors"></a><span data-ttu-id="1eae3-167">포착된 되지 않은 오류</span><span class="sxs-lookup"><span data-stu-id="1eae3-167">Untrapped Errors</span></span>  
 <span data-ttu-id="1eae3-168">개체가 실행 파일로 실행 되는 경우 개체에서 포착된 되지 않은 오류 제어 응용 프로그램에 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-168">Untrapped errors in objects are returned to the controlling application when the object is running as an executable file.</span></span> <span data-ttu-id="1eae3-169">개발 환경에서 적절 한 옵션을 설정 하는 경우에 포착된 되지 않은 오류 제어 응용 프로그램에 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-169">Within the development environment, untrapped errors are returned to the controlling application only if the proper options are set.</span></span> <span data-ttu-id="1eae3-170">옵션을 디버깅 하는 동안 집합,를 설정 하는 방법 및 호스트 클래스를 만들 수 있는지 여부 수 설명에 대 한 호스트 응용 프로그램의 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1eae3-170">See your host application's documentation for a description of which options should be set during debugging, how to set them, and whether the host can create classes.</span></span>  
  
 <span data-ttu-id="1eae3-171">다른 개체에 액세스 하는 개체를 만드는 경우에 다시 전달 하는 처리 되지 않은 오류를 처리 하려고 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-171">If you create an object that accesses other objects, you should try to handle any unhandled errors they pass back.</span></span> <span data-ttu-id="1eae3-172">오류 코드에 매핑하면 열 수는 없습니다 `Err.Number` 개체의 호출자에 게 다시 사용자 고유의 오류와 다음 단계 중 하나에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-172">If you cannot, map the error codes in `Err.Number` to one of your own errors and then pass them back to the caller of your object.</span></span> <span data-ttu-id="1eae3-173">오류 코드를 추가 하 여 오류를 지정 해야는 `VbObjectError` 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-173">You should specify your error by adding your error code to the `VbObjectError` constant.</span></span> <span data-ttu-id="1eae3-174">예를 들어 오류 코드가 1052 이면 다음과 같이 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-174">For example, if your error code is 1052, assign it as follows:</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#19](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/on-error-statement_3.vb)]  
  
> [!CAUTION]
>  <span data-ttu-id="1eae3-175">Windows 동적 연결 라이브러리 (Dll)를 호출 하는 동안 시스템 오류 예외를 발생 시 키 지 않는 및 Visual Basic 오류 트래핑 함께 트랩 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-175">System errors during calls to Windows dynamic-link libraries (DLLs) do not raise exceptions and cannot be trapped with Visual Basic error trapping.</span></span> <span data-ttu-id="1eae3-176">성공 또는 실패 (에 따라 API 사양)에 대 한 각 반환 값을 확인 해야 DLL 함수를 호출할 때 오류가 발생 한 값을 확인 하 고는 `Err` 개체의 `LastDLLError` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-176">When calling DLL functions, you should check each return value for success or failure (according to the API specifications), and in the event of a failure, check the value in the `Err` object's `LastDLLError` property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1eae3-177">예</span><span class="sxs-lookup"><span data-stu-id="1eae3-177">Example</span></span>  
 <span data-ttu-id="1eae3-178">이 예에서는 먼저 사용 하 여는 `On Error GoTo` 문을 프로시저 내에서 오류 처리 루틴의 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-178">This example first uses the `On Error GoTo` statement to specify the location of an error-handling routine within a procedure.</span></span> <span data-ttu-id="1eae3-179">예제에서는 0으로 나누려 할 6 오류 번호를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-179">In the example, an attempt to divide by zero generates error number 6.</span></span> <span data-ttu-id="1eae3-180">오류 처리 루틴에는 오류를 처리 하 고 제어 오류를 발생 시킨 명령문에 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-180">The error is handled in the error-handling routine, and control is then returned to the statement that caused the error.</span></span> <span data-ttu-id="1eae3-181">`On Error GoTo 0` 문이 오류 트래핑을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-181">The `On Error GoTo 0` statement turns off error trapping.</span></span> <span data-ttu-id="1eae3-182">그런 다음 `On Error Resume Next` 문을 다음 문으로 생성 된 오류에 대 한 컨텍스트를 특정 알 수 있도록 오류 트래핑을 지연 시키려면 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-182">Then the `On Error Resume Next` statement is used to defer error trapping so that the context for the error generated by the next statement can be known for certain.</span></span> <span data-ttu-id="1eae3-183">`Err.Clear` 선택을 취소 하는 데 사용 되는 `Err` 는 오류를 처리 한 후 개체의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-183">Note that `Err.Clear` is used to clear the `Err` object's properties after the error is handled.</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#20](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/on-error-statement_4.vb)]  
  
## <a name="requirements"></a><span data-ttu-id="1eae3-184">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1eae3-184">Requirements</span></span>  
 <span data-ttu-id="1eae3-185">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="1eae3-185">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="1eae3-186">**어셈블리:** Visual Basic 런타임 라이브러리 (Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="1eae3-186">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eae3-187">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1eae3-187">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Information.Err%2A>  
 <xref:Microsoft.VisualBasic.ErrObject.Number%2A>  
 <xref:Microsoft.VisualBasic.ErrObject.Description%2A>  
 <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>  
 [<span data-ttu-id="1eae3-188">End 문</span><span class="sxs-lookup"><span data-stu-id="1eae3-188">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)  
 [<span data-ttu-id="1eae3-189">Exit 문</span><span class="sxs-lookup"><span data-stu-id="1eae3-189">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [<span data-ttu-id="1eae3-190">Resume 문</span><span class="sxs-lookup"><span data-stu-id="1eae3-190">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)  
 [<span data-ttu-id="1eae3-191">오류 메시지</span><span class="sxs-lookup"><span data-stu-id="1eae3-191">Error Messages</span></span>](../../../visual-basic/language-reference/error-messages/index.md)  
 [<span data-ttu-id="1eae3-192">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="1eae3-192">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
