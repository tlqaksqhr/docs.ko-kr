---
title: Alias 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: 62b34f5860b35104b6a8caa82c359383999dd61b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33599176"
---
# <a name="alias-clause-visual-basic"></a><span data-ttu-id="f1896-102">Alias 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f1896-102">Alias Clause (Visual Basic)</span></span>
<span data-ttu-id="f1896-103">외부 프로시저의 DLL에 다른 이름이 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f1896-103">Indicates that an external procedure has another name in its DLL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1896-104">설명</span><span class="sxs-lookup"><span data-stu-id="f1896-104">Remarks</span></span>  
 <span data-ttu-id="f1896-105">`Alias` 키워드는이 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1896-105">The `Alias` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="f1896-106">Declare 문</span><span class="sxs-lookup"><span data-stu-id="f1896-106">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 <span data-ttu-id="f1896-107">다음 예제에서는 `Alias` 키워드 advapi32.dll에서이 함수의 이름을 제공 하는 데 사용 됩니다 `GetUserNameA`, 해당 `getUserName` 대신에이 예에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1896-107">In the following example, the `Alias` keyword is used to provide the name of the function in advapi32.dll, `GetUserNameA`, that `getUserName` is used in place of in this example.</span></span> <span data-ttu-id="f1896-108">함수 `getUserName` sub에서 호출 되 `getUser`, 현재 사용자의 이름을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1896-108">Function `getUserName` is called in sub `getUser`, which displays the name of the current user.</span></span>  
  
 [!code-vb[VbVbalrStatements#15](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/alias-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="f1896-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f1896-109">See Also</span></span>  
 [<span data-ttu-id="f1896-110">키워드</span><span class="sxs-lookup"><span data-stu-id="f1896-110">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
