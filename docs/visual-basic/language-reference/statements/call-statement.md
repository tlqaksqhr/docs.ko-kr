---
title: Call 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
ms.openlocfilehash: 259fcc6f1c59df09e768a08204df81aa8105de53
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37936791"
---
# <a name="call-statement-visual-basic"></a>Call 문(Visual Basic)
컨트롤을 전송 하는 `Function`, `Sub`, 또는 동적 연결 라이브러리 (DLL) 프로시저.  
  
## <a name="syntax"></a>구문  
  
```  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a>요소  
|||
|---|---|
|`procedureName`|필수. 호출 프로시저의 이름입니다.|
|`argumentList`|선택 사항입니다. 변수 또는 호출 될 때 프로시저에 전달 되는 인수를 나타내는 식의 목록입니다. 여러 인수는 쉼표로 구분 됩니다. 포함 하는 경우 `argumentList`를 괄호로 묶어야 합니다.|
|||
  
## <a name="remarks"></a>설명  
 사용할 수는 `Call` 키워드 프로시저를 호출 합니다. 대부분의 프로시저 호출에이 키워드를 사용할 필요가 없습니다.  
  
 일반적으로 사용 하 여 `Call` 키워드 호출된 식 식별자로 시작 하지 않습니다. 사용 된 `Call` 키워드 다른 용도로 권장 되지 않습니다.  
  
 프로시저는 값을 반환 하는 경우는 `Call` 문을 무시 합니다.  
  
## <a name="example"></a>예  
 다음 코드는 두 가지 예제를 보여 줍니다. 여기서는 `Call` 키워드는 프로시저를 호출 하는 데 필요한 합니다. 두 예제에서는 호출된 식 식별자를 사용 하 여 시작 되지 않습니다.  
  
 [!code-vb[VbVbalrStatements#97](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/call-statement_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [람다 식](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
