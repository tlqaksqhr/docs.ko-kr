---
title: "Continue 문(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4a47819600a6c1d58f09c2f8ed3443632e9dab68
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="continue-statement-visual-basic"></a><span data-ttu-id="7bc67-102">Continue 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7bc67-102">Continue Statement (Visual Basic)</span></span>
<span data-ttu-id="7bc67-103">루프의 다음 반복으로 즉시 제어를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bc67-103">Transfers control immediately to the next iteration of a loop.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bc67-104">구문</span><span class="sxs-lookup"><span data-stu-id="7bc67-104">Syntax</span></span>  
  
```  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a><span data-ttu-id="7bc67-105">설명</span><span class="sxs-lookup"><span data-stu-id="7bc67-105">Remarks</span></span>  
 <span data-ttu-id="7bc67-106">전송할 수 내부는 `Do`, `For`, 또는 `While` 해당 루프의 다음 반복으로 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="7bc67-106">You can transfer from inside a `Do`, `For`, or `While` loop to the next iteration of that loop.</span></span> <span data-ttu-id="7bc67-107">제어를 전송 하는 것과 같은 루프 조건 테스트를 즉시 전달은 `For` 또는 `While` 문, 또는 `Do` 또는 `Loop` 문을 포함 하는 `Until` 또는 `While` 절.</span><span class="sxs-lookup"><span data-stu-id="7bc67-107">Control passes immediately to the loop condition test, which is equivalent to transferring to the `For` or `While` statement, or to the `Do` or `Loop` statement that contains the `Until` or `While` clause.</span></span>  
  
 <span data-ttu-id="7bc67-108">사용할 수 있습니다 `Continue` 이동이 허용 되는 루프 내의 모든 위치에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bc67-108">You can use `Continue` at any location in the loop that allows transfers.</span></span> <span data-ttu-id="7bc67-109">컨트롤을 전송할 수 있도록 하는 규칙은와 동일 하 게는 [GoTo 문](../../../visual-basic/language-reference/statements/goto-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7bc67-109">The rules allowing transfer of control are the same as with the [GoTo Statement](../../../visual-basic/language-reference/statements/goto-statement.md).</span></span>  
  
 <span data-ttu-id="7bc67-110">예를 들어, 루프 내에 완전히 포함 되어는 `Try` 블록은 `Catch` 블록 또는 `Finally` 블록을 사용할 수 있습니다 `Continue` 루프 밖으로 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bc67-110">For example, if a loop is totally contained within a `Try` block, a `Catch` block, or a `Finally` block, you can use `Continue` to transfer out of the loop.</span></span> <span data-ttu-id="7bc67-111">반대로, if는 `Try`... `End Try` 구조 루프 내에 포함 된, 사용할 수 없습니다 `Continue` 밖으로 제어를 전송 하는 `Finally` 블록 및 있습니다 사용할 수의 전송 하는 `Try` 또는 `Catch` 부재 중 완전히 전송 하는 경우에 차단는 `Try`... `End Try` 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="7bc67-111">If, on the other hand, the `Try`...`End Try` structure is contained within the loop, you cannot use `Continue` to transfer control out of the `Finally` block, and you can use it to transfer out of a `Try` or `Catch` block only if you transfer completely out of the `Try`...`End Try` structure.</span></span>  
  
 <span data-ttu-id="7bc67-112">동일한 형식의 중첩 된 루프 예를 들어 있으면는 `Do` 루프 내에 다른 `Do` 루프는 `Continue Do` 가장 안쪽의 다음 반복으로 문을 건너뜁니다 `Do` 포함 된 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="7bc67-112">If you have nested loops of the same type, for example a `Do` loop within another `Do` loop, a `Continue Do` statement skips to the next iteration of the innermost `Do` loop that contains it.</span></span> <span data-ttu-id="7bc67-113">사용할 수 없습니다 `Continue` 같은 유형의 포함 하는 루프의 다음 반복 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bc67-113">You cannot use `Continue` to skip to the next iteration of a containing loop of the same type.</span></span>  
  
 <span data-ttu-id="7bc67-114">다양 한 유형의 중첩 된 루프 예를 들어 있으면는 `Do` 내에서 반복을 `For` 루프를 사용 하 여 두 루프의 다음 반복으로 건너뛸 수 없다 `Continue Do` 또는 `Continue For`합니다.</span><span class="sxs-lookup"><span data-stu-id="7bc67-114">If you have nested loops of different types, for example a `Do` loop within a `For` loop, you can skip to the next iteration of either loop by using either `Continue Do` or `Continue For`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7bc67-115">예제</span><span class="sxs-lookup"><span data-stu-id="7bc67-115">Example</span></span>  
 <span data-ttu-id="7bc67-116">다음 코드 예제에서는 `Continue While` 문을 제수가 0 인 경우 배열의 다음 열을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bc67-116">The following code example uses the `Continue While` statement to skip to the next column of an array if a divisor is zero.</span></span> <span data-ttu-id="7bc67-117">`Continue While` 내는 `For` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="7bc67-117">The `Continue While` is inside a `For` loop.</span></span> <span data-ttu-id="7bc67-118">전송 하는 `While col < lastcol` 가장 안쪽의 다음 반복 문을 `While` 루프를 포함 하는 `For` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="7bc67-118">It transfers to the `While col < lastcol` statement, which is the next iteration of the innermost `While` loop that contains the `For` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#14](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/continue-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7bc67-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7bc67-119">See Also</span></span>  
 [<span data-ttu-id="7bc67-120">Do...Loop 문</span><span class="sxs-lookup"><span data-stu-id="7bc67-120">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [<span data-ttu-id="7bc67-121">For...Next 문</span><span class="sxs-lookup"><span data-stu-id="7bc67-121">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="7bc67-122">While...End While 문</span><span class="sxs-lookup"><span data-stu-id="7bc67-122">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [<span data-ttu-id="7bc67-123">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="7bc67-123">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
