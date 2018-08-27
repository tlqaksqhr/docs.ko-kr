---
title: Return 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Return
helpviewer_keywords:
- Return statement [Visual Basic], syntax
- control flow [Visual Basic], returning control to expressions
- Return statement [Visual Basic]
- expressions [Visual Basic], returning control to
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
ms.openlocfilehash: fe200add4e29fe4bbe0fdf335dcd94107b8ff1eb
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932594"
---
# <a name="return-statement-visual-basic"></a>Return 문(Visual Basic)
호출한 코드로 제어가 되돌아갑니다를 `Function`, `Sub`를 `Get`를 `Set`, 또는 `Operator` 프로시저입니다.  
  
## <a name="syntax"></a>구문  
  
```  
Return  
-or-  
Return expression  
```  
  
## <a name="part"></a>파트  
 `expression`  
 필요는 `Function`, `Get`, 또는 `Operator` 프로시저입니다. 호출 코드에 반환 될 값을 나타내는 식입니다.  
  
## <a name="remarks"></a>설명  
 에 `Sub` 또는 `Set` 프로시저를 `Return` 문과 동일는 `Exit Sub` 또는 `Exit Property` 문 및 `expression` 제공 하지 않아야 합니다.  
  
 에 `Function`, `Get`, 또는 `Operator` 절차는 `Return` 문에 포함 되어야 합니다 `expression`, 및 `expression` 프로시저의 반환 형식으로 변환 될 수 있는 데이터 형식으로 계산 되어야 합니다. 에 `Function` 또는 `Get` 프로시저 있습니다 식을 반환 값으로 처리 하는 프로시저 이름에 할당 한 다음 실행 하는 대안을 `Exit Function` 또는 `Exit Property` 문을. 에 `Operator` 를 사용 해야 프로시저 `Return expression`합니다.  
  
 만큼 포함할 수 있습니다 `Return` 문을 동일한 프로시저에 적절 하 게 합니다.  
  
> [!NOTE]
>  코드를 `Finally` 블록 실행를 `Return` 문에서 `Try` 또는 `Catch` 만난 전에 블록은 `Return` 문을 실행 합니다. A `Return` 에 문의 포함할 수 없습니다는 `Finally` 블록입니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 `Return` 문을 여러 번 절차는 다른 작업을 수행 하지 않아도 되는 경우 호출 코드에 반환 합니다.  
  
 [!code-vb[VbVbalrStatements#53](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/return-statement_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Get 문](../../../visual-basic/language-reference/statements/get-statement.md)  
 [Set 문](../../../visual-basic/language-reference/statements/set-statement.md)  
 [Operator 문](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Exit 문](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [Try...Catch...Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
