---
title: Resume 문 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Resume
- vb.ResumeNext
helpviewer_keywords:
- Next statement [Visual Basic], Resume
- Resume Next statement [Visual Basic]
- execution [Visual Basic], resuming
- run-time errors [Visual Basic], resuming after
- Resume statement [Visual Basic], syntax
- errors [Visual Basic], resuming after
- Error statement [Visual Basic], and Resume statement
- execution
- Resume statement [Visual Basic]
ms.assetid: e24d058b-1a5c-4274-acb9-7d295d3ea537
ms.openlocfilehash: 853f3fe060b70c8a43957d3c843fb95539981679
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2018
ms.locfileid: "39296158"
---
# <a name="resume-statement"></a><span data-ttu-id="7d63d-102">Resume 문</span><span class="sxs-lookup"><span data-stu-id="7d63d-102">Resume Statement</span></span>
<span data-ttu-id="7d63d-103">오류 처리 루틴을 완료 된 후 실행을 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d63d-103">Resumes execution after an error-handling routine is finished.</span></span>  
  
 <span data-ttu-id="7d63d-104">구조화 되지 않은 예외 처리를 사용 하기 보다는 가능 하면 코드에서 구조적된 예외 처리를 사용 하는 것이 좋습니다 하며 `On Error` 고 `Resume` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="7d63d-104">We suggest that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="7d63d-105">자세한 내용은 [Try...Catch...Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d63d-105">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d63d-106">구문</span><span class="sxs-lookup"><span data-stu-id="7d63d-106">Syntax</span></span>  
  
```  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a><span data-ttu-id="7d63d-107">요소</span><span class="sxs-lookup"><span data-stu-id="7d63d-107">Parts</span></span>  
 `Resume`  
 <span data-ttu-id="7d63d-108">필수.</span><span class="sxs-lookup"><span data-stu-id="7d63d-108">Required.</span></span> <span data-ttu-id="7d63d-109">오류 처리기로 동일한 프로시저에 오류가 발생 한 경우 오류를 발생 시킨 문을 사용 하 여 실행을 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d63d-109">If the error occurred in the same procedure as the error handler, execution resumes with the statement that caused the error.</span></span> <span data-ttu-id="7d63d-110">호출된 된 프로시저에서 오류가 발생 한 경우 오류 처리 루틴을 포함 하는 프로시저에서 마지막으로 호출한 문에서 실행을 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d63d-110">If the error occurred in a called procedure, execution resumes at the statement that last called out of the procedure containing the error-handling routine.</span></span>  
  
 `Next`  
 <span data-ttu-id="7d63d-111">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7d63d-111">Optional.</span></span> <span data-ttu-id="7d63d-112">오류 처리기로 동일한 프로시저에 오류가 발생 한 경우 오류를 발생 시킨 문 바로 다음 문으로 실행을 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d63d-112">If the error occurred in the same procedure as the error handler, execution resumes with the statement immediately following the statement that caused the error.</span></span> <span data-ttu-id="7d63d-113">오류 처리 루틴을 포함 하는 프로시저에서 마지막으로 호출 하는 문 바로 다음 문으로 실행을 다시 시작 호출된 된 프로시저에서 오류가 발생 하는 경우 (또는 `On Error Resume Next` 문).</span><span class="sxs-lookup"><span data-stu-id="7d63d-113">If the error occurred in a called procedure, execution resumes with the statement immediately following the statement that last called out of the procedure containing the error-handling routine (or `On Error Resume Next` statement).</span></span>  
  
 `line`  
 <span data-ttu-id="7d63d-114">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7d63d-114">Optional.</span></span> <span data-ttu-id="7d63d-115">에 필요한 지정 된 줄에서 실행을 다시 시작할 `line` 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="7d63d-115">Execution resumes at the line specified in the required `line` argument.</span></span> <span data-ttu-id="7d63d-116">`line` 인수 줄 레이블 또는 줄 번호 및 오류 처리기와 동일한 절차에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d63d-116">The `line` argument is a line label or line number and must be in the same procedure as the error handler.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d63d-117">설명</span><span class="sxs-lookup"><span data-stu-id="7d63d-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7d63d-118">구조화 되지 않은 예외 처리를 사용 하기 보다는 가능 하면 코드에서 구조적된 예외 처리를 사용 하는 것이 좋습니다 하며 `On Error` 고 `Resume` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="7d63d-118">We recommend that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="7d63d-119">자세한 내용은 [Try...Catch...Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d63d-119">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
 <span data-ttu-id="7d63d-120">사용 하는 경우는 `Resume` 문을 아무 곳 이나 이외의 다른 오류 처리 루틴에서 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d63d-120">If you use a `Resume` statement anywhere other than in an error-handling routine, an error occurs.</span></span>  
  
 <span data-ttu-id="7d63d-121">합니다 `Resume` 문을 포함 하는 모든 프로시저에 사용할 수 없습니다는 `Try...Catch...Finally` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="7d63d-121">The `Resume` statement cannot be used in any procedure that contains a `Try...Catch...Finally` statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d63d-122">예</span><span class="sxs-lookup"><span data-stu-id="7d63d-122">Example</span></span>  
 <span data-ttu-id="7d63d-123">이 예제에서는 `Resume` 문을 프로시저의 오류 처리를 종료 하 고 오류를 발생 시킨 문 사용 하 여 실행을 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d63d-123">This example uses the `Resume` statement to end error handling in a procedure and then resume execution with the statement that caused the error.</span></span> <span data-ttu-id="7d63d-124">오류 번호 55 사용을 설명 하기 위해 생성 되는 `Resume` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="7d63d-124">Error number 55 is generated to illustrate use of the `Resume` statement.</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#16](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/resume-statement_1.vb)]  
  
## <a name="requirements"></a><span data-ttu-id="7d63d-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7d63d-125">Requirements</span></span>  
 <span data-ttu-id="7d63d-126">**: Namespace** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="7d63d-126">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="7d63d-127">**어셈블리:** Visual Basic 런타임 라이브러리 (Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="7d63d-127">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d63d-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7d63d-128">See Also</span></span>  
 [<span data-ttu-id="7d63d-129">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="7d63d-129">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="7d63d-130">Error 문</span><span class="sxs-lookup"><span data-stu-id="7d63d-130">Error Statement</span></span>](../../../visual-basic/language-reference/statements/error-statement.md)  
 [<span data-ttu-id="7d63d-131">On Error 문</span><span class="sxs-lookup"><span data-stu-id="7d63d-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
