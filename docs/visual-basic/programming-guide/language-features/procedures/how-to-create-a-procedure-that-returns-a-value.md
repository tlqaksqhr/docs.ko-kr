---
title: "방법: 값을 반환하는 프로시저 만들기(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 787eddc1fd1cdb9dd6b655a8556b75044b2a49dc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a>방법: 값을 반환하는 프로시저 만들기(Visual Basic)
사용 된 `Function` 프로시저를 호출 하는 코드에 값을 반환 합니다.  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a>값을 반환 하는 프로시저를 만들려면  
  
1.  다른 프로시저 밖에 서 사용 하 여 한 `Function` 문 다음에 `End Function` 문.  
  
2.  에 `Function` 문을 수행는 `Function` 키워드는 프로시저 및 매개 변수 목록 괄호 안에 이름으로 합니다.  
  
3.  괄호 다음에 `As` 절 반환된 된 값의 데이터 형식을 지정 합니다.  
  
4.  프로시저의 코드 문을 사이 `Function` 및 `End Function` 문.  
  
5.  사용 하 여 한 `Return` 호출 코드에 값을 반환 하는 문입니다.  
  
     다음 `Function` 프로시저 가장 긴 면 또는 다른 두 변에 대 한 값을 지정 하는 직각 삼각형의 빗변을 계산 합니다.  
  
     [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-create-a-procedure-that-returns-a-value_1.vb)]  
  
     다음 예제에서는 호출을 `hypotenuse`합니다.  
  
     [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/how-to-create-a-procedure-that-returns-a-value_2.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [절차](./index.md)  
 [Sub 프로시저](./sub-procedures.md)  
 [속성 프로시저](./property-procedures.md)  
 [연산자 프로시저](./operator-procedures.md)  
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)  
 [Function 문](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [방법: 프로시저에서 값 반환](./how-to-return-a-value-from-a-procedure.md)  
 [방법: 값을 반환하는 프로시저 호출](./how-to-call-a-procedure-that-returns-a-value.md)
