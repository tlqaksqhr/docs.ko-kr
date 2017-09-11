---
title: "이전 함수 실행 시간이 초과 되었으므로 함수를 실행할 수 없습니다 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30957
- vbc30957
dev_langs:
- VB
helpviewer_keywords:
- BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
caps.latest.revision: 7
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
ms.openlocfilehash: 127f89f4c7ddaf794f58707d8925731a511f3740
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a><span data-ttu-id="82d8e-102">이전 함수 실행 시간이 초과되었으므로 함수를 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="82d8e-102">Function evaluation is disabled because a previous function evaluation timed out</span></span>
<span data-ttu-id="82d8e-103">이전 함수 실행 시간이 초과 되었으므로 함수 실행 비활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82d8e-103">Function evaluation is disabled because a previous function evaluation timed out.</span></span> <span data-ttu-id="82d8e-104">함수 실행을 다시 활성화 하려면 다시 단계별로 실행 하거나 디버깅을 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="82d8e-104">To re-enable function evaluation, step again or restart debugging.</span></span>  
  
 <span data-ttu-id="82d8e-105">Visual Studio 디버거는 프로시저 호출을 지정 하는 식이 되지만 또 다른 평가 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="82d8e-105">In the Visual Studio debugger, an expression specifies a procedure call, but another evaluation has timed out.</span></span>  
  
 <span data-ttu-id="82d8e-106">무한 루프를 포함 하는 시간 제한 초과로 프로시저 호출에 대 한 가능한 원인 또는 *무한 루프*합니다.</span><span class="sxs-lookup"><span data-stu-id="82d8e-106">Possible causes for a procedure call to time out include an infinite loop or *endless loop*.</span></span> <span data-ttu-id="82d8e-107">자세한 내용은 참조 [에 대 한... 다음 문](../../../visual-basic/language-reference/statements/for-next-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="82d8e-107">For more information, see [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
 <span data-ttu-id="82d8e-108">무한 루프의 특수 한 경우는 *재귀*합니다.</span><span class="sxs-lookup"><span data-stu-id="82d8e-108">A special case of an infinite loop is *recursion*.</span></span> <span data-ttu-id="82d8e-109">자세한 내용은 참조 [재귀 프로시저](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="82d8e-109">For more information, see [Recursive Procedures](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).</span></span>  
  
 <span data-ttu-id="82d8e-110">**오류 ID:** BC30957</span><span class="sxs-lookup"><span data-stu-id="82d8e-110">**Error ID:** BC30957</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="82d8e-111">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="82d8e-111">To correct this error</span></span>  
  
1.  <span data-ttu-id="82d8e-112">가능 하면 이전 함수 실행 무슨 일 및 시간 제한 초과로 원인을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="82d8e-112">If possible, determine what the previous function evaluation was and what caused it to time out.</span></span> <span data-ttu-id="82d8e-113">그렇지 않은 경우이 오류가 다시 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82d8e-113">Otherwise, you might encounter this error again.</span></span>  
  
2.  <span data-ttu-id="82d8e-114">디버거를 다시 실행 하거나 종료 하 고 디버깅을 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="82d8e-114">Either step the debugger again, or terminate and restart debugging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82d8e-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="82d8e-115">See Also</span></span>  
 <span data-ttu-id="82d8e-116">[Visual Studio의 디버깅](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio) </span><span class="sxs-lookup"><span data-stu-id="82d8e-116">[Debugging in Visual Studio](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio) </span></span>  
<span data-ttu-id="82d8e-117"> [디버거로 코드 탐색](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)</span><span class="sxs-lookup"><span data-stu-id="82d8e-117"> [Navigating through Code with the Debugger](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)</span></span>
