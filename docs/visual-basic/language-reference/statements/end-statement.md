---
title: "End 문"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.End
- End
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- End keyword [Visual Basic], End statements
- programs [Visual Basic], quitting
- code, exiting
- program termination
- End statement [Visual Basic]
- execution [Visual Basic], stopping
ms.assetid: 0e64467c-0f34-4aab-9ddd-43f8b9d55d90
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b692409f2895f5e9b713c57fc35ff2def40bce75
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="end-statement"></a><span data-ttu-id="dea52-102">End 문</span><span class="sxs-lookup"><span data-stu-id="dea52-102">End Statement</span></span>
<span data-ttu-id="dea52-103">즉시 실행을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="dea52-103">Terminates execution immediately.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dea52-104">구문</span><span class="sxs-lookup"><span data-stu-id="dea52-104">Syntax</span></span>  
  
```  
End  
```  
  
## <a name="remarks"></a><span data-ttu-id="dea52-105">설명</span><span class="sxs-lookup"><span data-stu-id="dea52-105">Remarks</span></span>  
 <span data-ttu-id="dea52-106">배치할 수 있습니다는 `End` 전체 응용 프로그램에서 실행을 중지 하려면 프로시저의 아무 곳 이나 문입니다.</span><span class="sxs-lookup"><span data-stu-id="dea52-106">You can place the `End` statement anywhere in a procedure to force the entire application to stop running.</span></span> <span data-ttu-id="dea52-107">`End`사용 하 여 열린 파일을 닫고 프로그램 `Open` 문을 응용 프로그램의 모든 변수를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="dea52-107">`End` closes any files opened with an `Open` statement and clears all the application's variables.</span></span> <span data-ttu-id="dea52-108">응용 프로그램을 해당 개체에 대 한 참조를 보유 하는 다른 프로그램 있으며 실행 중인 코드의 항목이 즉시 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea52-108">The application closes as soon as there are no other programs holding references to its objects and none of its code is running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dea52-109">`End` 문을 갑자기 코드 실행이 중지 되 고 호출 하지 않습니다는 `Dispose` 또는 `Finalize` 메서드 또는 Visual Basic 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="dea52-109">The `End` statement stops code execution abruptly, and does not invoke the `Dispose` or `Finalize` method, or any other Visual Basic code.</span></span> <span data-ttu-id="dea52-110">다른 프로그램에서의 개체 참조를 무효화 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea52-110">Object references held by other programs are invalidated.</span></span> <span data-ttu-id="dea52-111">경우는 `End` 내에서 문이 `Try` 또는 `Catch` 제어 블록에 해당 요소에 통과 하지 못하는 `Finally` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="dea52-111">If an `End` statement is encountered within a `Try` or `Catch` block, control does not pass to the corresponding `Finally` block.</span></span>  
  
 <span data-ttu-id="dea52-112">`Stop` 문을 달리 하지만 실행을 일시 중단 `End`, 파일을 모두 닫고 하거나 컴파일된 실행 파일 (.exe) 파일에서 발생 하지 않는 모든 변수를 선택 취소 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dea52-112">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
 <span data-ttu-id="dea52-113">때문에 `End` 처리 하지 않고 응용 프로그램을 종료 열려 있는 모든 리소스를 사용 하기 전에 완전히을 닫기 하려고 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea52-113">Because `End` terminates your application without attending to any resources that might be open, you should try to close down cleanly before using it.</span></span> <span data-ttu-id="dea52-114">예를 들어 경우 응용 프로그램에 모든 양식을 열고 닫아야 합니다 제어가 전달 되기 전에 `End` 문.</span><span class="sxs-lookup"><span data-stu-id="dea52-114">For example, if your application has any forms open, you should close them before control reaches the `End` statement.</span></span>  
  
 <span data-ttu-id="dea52-115">사용 해야 `End` 만 최소화 해야 즉시 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea52-115">You should use `End` sparingly, and only when you need to stop immediately.</span></span> <span data-ttu-id="dea52-116">프로시저를 종료 하는 일반적인 방법 ([Return 문을](../../../visual-basic/language-reference/statements/return-statement.md) 및 [Exit 문은](../../../visual-basic/language-reference/statements/exit-statement.md)) 뿐 아니라 프로시저를 완전히 종료 되지만 호출 코드에서 완전히 종료를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea52-116">The normal ways to terminate a procedure ([Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) and [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)) not only close down the procedure cleanly but also give the calling code the opportunity to close down cleanly.</span></span> <span data-ttu-id="dea52-117">콘솔 응용 프로그램, 예를 들어 하기만 하면 `Return` 에서 `Main` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="dea52-117">A console application, for example, can simply `Return` from the `Main` procedure.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dea52-118">`End` 문 호출은 <xref:System.Environment.Exit%2A> 의 메서드는 <xref:System.Environment> 클래스에 <xref:System> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="dea52-118">The `End` statement calls the <xref:System.Environment.Exit%2A> method of the <xref:System.Environment> class in the <xref:System> namespace.</span></span> <span data-ttu-id="dea52-119"><xref:System.Environment.Exit%2A>해야 `UnmanagedCode` 권한.</span><span class="sxs-lookup"><span data-stu-id="dea52-119"><xref:System.Environment.Exit%2A> requires that you have `UnmanagedCode` permission.</span></span> <span data-ttu-id="dea52-120">그렇지 않고 하는 경우는 <xref:System.Security.SecurityException> 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea52-120">If you do not, a <xref:System.Security.SecurityException> error occurs.</span></span>  
  
 <span data-ttu-id="dea52-121">뒤에 키워드를 추가 하는 경우 [끝 \<키워드 > 문을](../../../visual-basic/language-reference/statements/end-keyword-statement.md) 적절 한 프로시저 또는 블록의 정의의 끝을 나타낼 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea52-121">When followed by an additional keyword, [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) delineates the end of the definition of the appropriate procedure or block.</span></span> <span data-ttu-id="dea52-122">예를 들어 `End Function` 의 정의 종료 한 `Function` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="dea52-122">For example, `End Function` terminates the definition of a `Function` procedure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dea52-123">예제</span><span class="sxs-lookup"><span data-stu-id="dea52-123">Example</span></span>  
 <span data-ttu-id="dea52-124">다음 예제에서는 `End` 문을 사용자가 요청할 경우 코드 실행을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea52-124">The following example uses the `End` statement to terminate code execution if the user requests it.</span></span>  
  
 [!code-vb[VbVersHelp60Controls#64](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/end-statement_1.vb)]  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="dea52-125">스마트 장치 개발자 노트</span><span class="sxs-lookup"><span data-stu-id="dea52-125">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="dea52-126">이 문은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dea52-126">This statement is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dea52-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dea52-127">See Also</span></span>  
 <xref:System.Security.Permissions.SecurityPermissionFlag>  
 [<span data-ttu-id="dea52-128">Stop 문</span><span class="sxs-lookup"><span data-stu-id="dea52-128">Stop Statement</span></span>](../../../visual-basic/language-reference/statements/stop-statement.md)  
 [<span data-ttu-id="dea52-129">최종 \<키워드 > 문</span><span class="sxs-lookup"><span data-stu-id="dea52-129">End \<keyword> Statement</span></span>](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
