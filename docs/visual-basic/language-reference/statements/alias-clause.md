---
title: "Alias 절(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Alias
helpviewer_keywords: Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f61e738434ea616d751576ef21669545afc41397
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="alias-clause-visual-basic"></a><span data-ttu-id="65d02-102">Alias 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65d02-102">Alias Clause (Visual Basic)</span></span>
<span data-ttu-id="65d02-103">외부 프로시저의 DLL에 다른 이름이 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="65d02-103">Indicates that an external procedure has another name in its DLL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65d02-104">설명</span><span class="sxs-lookup"><span data-stu-id="65d02-104">Remarks</span></span>  
 <span data-ttu-id="65d02-105">`Alias` 키워드는이 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65d02-105">The `Alias` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="65d02-106">Declare 문</span><span class="sxs-lookup"><span data-stu-id="65d02-106">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 <span data-ttu-id="65d02-107">다음 예제에서는 `Alias` 키워드 advapi32.dll에서이 함수의 이름을 제공 하는 데 사용 됩니다 `GetUserNameA`, 해당 `getUserName` 대신에이 예에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65d02-107">In the following example, the `Alias` keyword is used to provide the name of the function in advapi32.dll, `GetUserNameA`, that `getUserName` is used in place of in this example.</span></span> <span data-ttu-id="65d02-108">함수 `getUserName` sub에서 호출 되 `getUser`, 현재 사용자의 이름을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="65d02-108">Function `getUserName` is called in sub `getUser`, which displays the name of the current user.</span></span>  
  
 [!code-vb[VbVbalrStatements#15](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/alias-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="65d02-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="65d02-109">See Also</span></span>  
 [<span data-ttu-id="65d02-110">키워드</span><span class="sxs-lookup"><span data-stu-id="65d02-110">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
