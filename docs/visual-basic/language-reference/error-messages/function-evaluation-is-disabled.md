---
title: "이전 함수 실행 시간이 초과되었으므로 함수를 실행할 수 없습니다."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30957
- vbc30957
helpviewer_keywords: BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 05067e730486b443b7a508adb499f34c060d5093
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a><span data-ttu-id="ef1d2-102">이전 함수 실행 시간이 초과되었으므로 함수를 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ef1d2-102">Function evaluation is disabled because a previous function evaluation timed out</span></span>
<span data-ttu-id="ef1d2-103">함수 실행 사용할 수 없습니다. 이전 함수 실행 시간이 초과 되었습니다. 함수 실행을 다시 활성화 하려면 단계별로 다시 실행 하거나 디버깅을 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef1d2-103">Function evaluation is disabled because a previous function evaluation timed out. To re-enable function evaluation, step again or restart debugging.</span></span>  
  
 <span data-ttu-id="ef1d2-104">Visual Studio 디버거에서 식이 프로시저 호출을 지정 하지만 또 다른 평가 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ef1d2-104">In the Visual Studio debugger, an expression specifies a procedure call, but another evaluation has timed out.</span></span>  
  
 <span data-ttu-id="ef1d2-105">프로시저 호출 시간이 초과 원인일 무한 루프 또는 *무한 루프*합니다.</span><span class="sxs-lookup"><span data-stu-id="ef1d2-105">Possible causes for a procedure call to time out include an infinite loop or *endless loop*.</span></span> <span data-ttu-id="ef1d2-106">자세한 내용은 참조 [에 대 한... 다음 문](../../../visual-basic/language-reference/statements/for-next-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ef1d2-106">For more information, see [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
 <span data-ttu-id="ef1d2-107">무한 루프의 특수 한 경우는 *재귀*합니다.</span><span class="sxs-lookup"><span data-stu-id="ef1d2-107">A special case of an infinite loop is *recursion*.</span></span> <span data-ttu-id="ef1d2-108">자세한 내용은 참조 [재귀 프로시저](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ef1d2-108">For more information, see [Recursive Procedures](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).</span></span>  
  
 <span data-ttu-id="ef1d2-109">**오류 ID:** BC30957</span><span class="sxs-lookup"><span data-stu-id="ef1d2-109">**Error ID:** BC30957</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ef1d2-110">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="ef1d2-110">To correct this error</span></span>  
  
1.  <span data-ttu-id="ef1d2-111">가능 하면 이전 함수 실행 त ल ्와 제한 시간이 초과 원인을 결정 합니다. 그렇지 않은 경우이 오류가 다시 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef1d2-111">If possible, determine what the previous function evaluation was and what caused it to time out. Otherwise, you might encounter this error again.</span></span>  
  
2.  <span data-ttu-id="ef1d2-112">디버거를 다시 실행 하거나 종료 하 고 디버깅을 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef1d2-112">Either step the debugger again, or terminate and restart debugging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef1d2-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ef1d2-113">See Also</span></span>  
 [<span data-ttu-id="ef1d2-114">Visual Studio의 디버깅</span><span class="sxs-lookup"><span data-stu-id="ef1d2-114">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)  
 [<span data-ttu-id="ef1d2-115">디버거로 코드 탐색</span><span class="sxs-lookup"><span data-stu-id="ef1d2-115">Navigating through Code with the Debugger</span></span>](/visualstudio/debugger/navigating-through-code-with-the-debugger)
