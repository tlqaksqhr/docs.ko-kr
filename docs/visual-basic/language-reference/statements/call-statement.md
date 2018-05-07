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
ms.openlocfilehash: 2074f44aedf59f1570e73c898a9bf64e57034923
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="call-statement-visual-basic"></a>Call 문(Visual Basic)
컨트롤을 전송 하는 `Function`, `Sub`, 또는 동적 연결 라이브러리 (DLL) 프로시저입니다.  
  
## <a name="syntax"></a>구문  
  
```  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a>요소  
 `procedureName`  
 필수. 호출할 프로시저의 이름입니다.  
  
 `argumentList`  
 선택 사항입니다. 변수 또는 호출 될 때 프로시저에 전달 되는 인수를 나타내는 식의 목록입니다. 인수가 여러 개이면 쉼표로 구분 됩니다. 포함 하는 경우 `argumentList`를 괄호로 묶어야 합니다.  
  
## <a name="remarks"></a>설명  
 사용할 수는 `Call` 키워드 프로시저를 호출 합니다. 대부분의 프로시저 호출에 대 한이 키워드를 사용 하도록 요구 하지 않음.  
  
 일반적으로 사용 된 `Call` 키워드를 식별자로 호출된 식을 시작 하지 않습니다. 사용은 `Call` 키워드를 다른 곳에 권장 되지 않습니다.  
  
 프로시저는 값을 반환 하는 경우는 `Call` 문을 무시 합니다.  
  
## <a name="example"></a>예제  
 다음 코드는 두 가지 예를 보여 줍니다. 여기서는 `Call` 키워드는 프로시저를 호출 해야 합니다. 두 예제에서는 호출된 식을 식별자 문자로 시작 하지 않습니다.  
  
 [!code-vb[VbVbalrStatements#97](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/call-statement_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [람다 식](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
