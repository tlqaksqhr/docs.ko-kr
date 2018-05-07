---
title: '방법: 프로시저에서 값 반환(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
ms.openlocfilehash: 62e8a52e488247d4dfcde2a560920447abe1c182
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a>방법: 프로시저에서 값 반환(Visual Basic)
A `Function` 프로시저가 반환 값을 호출 하는 코드 실행 하거나 한 `Return` 문 또는 발생 하 여는 `Exit Function` 또는 `End Function` 문.  
  
### <a name="to-return-a-value-using-the-return-statement"></a>Return 문을 사용 하 여 값을 반환 하려면  
  
1.  배치는 `Return` 프로시저의 작업이 완료 되는 지점에 문의 합니다.  
  
2.  에 따라는 `Return` 호출 코드에 반환 하려는 값을 생성 하는 식으로 키워드입니다.  
  
3.  동일한 프로시저에 `Return` 문을 둘 이상 사용할 수 있습니다.  
  
     다음 `Function` 프로시저가 가장 긴 측 또는 직각 삼각형의 빗변 계산 하 고 호출 코드에 반환 합니다.  
  
     [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_1.vb)]  
  
     다음 예제에서는 호출을 `hypotenuse`, 반환된 된 값을 저장 하는 합니다.  
  
     [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_2.vb)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a>Exit 함수 또는 최종 함수를 사용 하 여 값을 반환 하려면  
  
1.  적어도 한 위치에 `Function` 프로시저를 프로시저의 이름에 값 할당 합니다.  
  
2.  실행 하는 동안는 `Exit Function` 또는 `End Function` 문, Visual Basic 프로시저의 이름에 가장 최근에 할당 된 값을 반환 합니다.  
  
3.  동일한 프로시저에 `Exit Function` 문을 둘 이상 사용할 수 있으며, `Return` 및 `Exit Function` 문을 혼합할 수도 있습니다.  
  
4.  하나만 사용할 수 있습니다 `End Function` 의 문에서 `Function` 프로시저입니다.  
  
     자세한 내용 및 예제에 대 한 "반환 값이"의 참조 [Function 문](../../../../visual-basic/language-reference/statements/function-statement.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [절차](./index.md)  
 [Sub 프로시저](./sub-procedures.md)  
 [속성 프로시저](./property-procedures.md)  
 [연산자 프로시저](./operator-procedures.md)  
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)  
 [Function 문](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [Return 문](../../../../visual-basic/language-reference/statements/return-statement.md)  
 [방법: 값을 반환하는 프로시저 만들기](./how-to-create-a-procedure-that-returns-a-value.md)  
 [방법: 값을 반환하는 프로시저 호출](./how-to-call-a-procedure-that-returns-a-value.md)
