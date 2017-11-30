---
title: "방법: 값을 반환하는 프로시저 호출(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f6d408eed67fa417f42252bb49ecea28d4458382
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a>방법: 값을 반환하는 프로시저 호출(Visual Basic)
A `Function` 프로시저가 호출 코드에 값을 반환 합니다. 식 또는 대입문의 오른쪽의 이름 및 인수를 포함 하 여 프로시저를 호출 합니다.  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a>식 내에서 Function 프로시저를 호출 하려면  
  
1.  사용 하 여는 `Function` 프로시저 변수를 사용할 때 동일한 방식으로 이름을 지정 합니다. 사용할 수는 `Function` 프로시저 호출 원하는 위치에 식에서 변수 또는 상수를 사용할 수 있습니다.  
  
2.  프로시저 이름으로 인수 목록을 묶는 괄호를 따릅니다. 인수가 없는 경우에 필요에 따라 괄호를 생략할 수 있습니다. 그러나 괄호를 사용 하는 코드 보다 쉽게 읽을 수 있습니다.  
  
3.  쉼표로 구분 하 여는 괄호 안에 인수 목록에서 인수를 배치 합니다. 와 같은 순서로 인수를 지정 해야 하는 `Function` 프로시저가 해당 매개 변수를 정의 합니다.  
  
     또는 이름으로 하나 이상의 인수를 전달할 수 있습니다. 자세한 내용은 참조 [이름 및 위치도 인수 전달](./passing-arguments-by-position-and-by-name.md)합니다.  
  
4.  변수의 값과 마찬가지로 식에 참여 하는 프로시저에서 반환 되는 값 또는 상수입니다.  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a>대입문에서 Function 프로시저를 호출 하려면  
  
1.  사용 하 여는 `Function` 프로시저 이름 다음에 오는 (`=`) 대입문에 로그인 합니다.  
  
2.  프로시저 이름으로 인수 목록을 묶는 괄호를 따릅니다. 인수가 없는 경우에 필요에 따라 괄호를 생략할 수 있습니다. 그러나 괄호를 사용 하는 코드 보다 쉽게 읽을 수 있습니다.  
  
3.  쉼표로 구분 하 여는 괄호 안에 인수 목록에서 인수를 배치 합니다. 와 같은 순서로 인수를 지정 해야 하는 `Function` 으로 전달 하는 이름으로 하지 않는 한 프로시저에서 해당 매개 변수를 정의 합니다.  
  
4.  프로시저에서 반환 되는 값은 변수 또는 속성 대입문의 왼쪽에 저장 됩니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] <xref:Microsoft.VisualBasic.Interaction.Environ%2A> 운영 체제 환경 변수의 값을 검색 합니다. 첫 번째 줄에서는 `Environ` 식 내에서 두 번째 줄에서에서 호출 할당 문의 합니다. `Environ`변수 이름에는 유일한 인수로 사용 합니다. 호출 코드에 변수 값을 반환 합니다.  
  
 [!code-vb[VbVbcnProcedures#7](./codesnippet/VisualBasic/how-to-call-a-procedure-that-returns-a-value_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Function 프로시저](./function-procedures.md)  
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)  
 [Function 문](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [방법: 값을 반환하는 프로시저 만들기](./how-to-create-a-procedure-that-returns-a-value.md)  
 [방법: 프로시저에서 값 반환](./how-to-return-a-value-from-a-procedure.md)  
 [방법: 값을 반환하지 않는 프로시저 호출](./how-to-call-a-procedure-that-does-not-return-a-value.md)
