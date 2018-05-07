---
title: Continue 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: eb8596c43bf6232eec4bcb844e6202c5de373404
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="continue-statement-visual-basic"></a>Continue 문(Visual Basic)
루프의 다음 반복으로 즉시 제어를 전송 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a>설명  
 전송할 수 내부는 `Do`, `For`, 또는 `While` 해당 루프의 다음 반복으로 루프입니다. 제어를 전송 하는 것과 같은 루프 조건 테스트를 즉시 전달은 `For` 또는 `While` 문, 또는 `Do` 또는 `Loop` 문을 포함 하는 `Until` 또는 `While` 절.  
  
 사용할 수 있습니다 `Continue` 이동이 허용 되는 루프 내의 모든 위치에서 합니다. 컨트롤을 전송할 수 있도록 하는 규칙은와 동일 하 게는 [GoTo 문](../../../visual-basic/language-reference/statements/goto-statement.md)합니다.  
  
 예를 들어, 루프 내에 완전히 포함 되어는 `Try` 블록은 `Catch` 블록 또는 `Finally` 블록을 사용할 수 있습니다 `Continue` 루프 밖으로 전송할 수 있습니다. 반대로, if는 `Try`... `End Try` 구조 루프 내에 포함 된, 사용할 수 없습니다 `Continue` 밖으로 제어를 전송 하는 `Finally` 블록 및 있습니다 사용할 수의 전송 하는 `Try` 또는 `Catch` 부재 중 완전히 전송 하는 경우에 차단는 `Try`... `End Try` 구조입니다.  
  
 동일한 형식의 중첩 된 루프 예를 들어 있으면는 `Do` 루프 내에 다른 `Do` 루프는 `Continue Do` 가장 안쪽의 다음 반복으로 문을 건너뜁니다 `Do` 포함 된 루프입니다. 사용할 수 없습니다 `Continue` 같은 유형의 포함 하는 루프의 다음 반복 이동 합니다.  
  
 다양 한 유형의 중첩 된 루프 예를 들어 있으면는 `Do` 내에서 반복을 `For` 루프를 사용 하 여 두 루프의 다음 반복으로 건너뛸 수 없다 `Continue Do` 또는 `Continue For`합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 `Continue While` 문을 제수가 0 인 경우 배열의 다음 열을 이동 합니다. `Continue While` 내는 `For` 루프입니다. 전송 하는 `While col < lastcol` 가장 안쪽의 다음 반복 문을 `While` 루프를 포함 하는 `For` 루프입니다.  
  
 [!code-vb[VbVbalrStatements#14](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/continue-statement_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Do...Loop 문](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [For...Next 문](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [While...End While 문](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [Try...Catch...Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
