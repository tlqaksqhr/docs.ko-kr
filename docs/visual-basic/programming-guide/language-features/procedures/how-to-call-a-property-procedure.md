---
title: "방법: 속성 프로시저 호출(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], property procedures
- procedure calls [Visual Basic], property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cf9080e3c2b23302257499f13e734231f3614495
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a>방법: 속성 프로시저 호출(Visual Basic)
속성에 값을 저장 하거나 값을 검색 하는 속성 프로시저를 호출 합니다. 속성 변수에 액세스 하는 동일한 방식으로 액세스 합니다.  
  
 속성의 `Set` 프로시저 값을 저장 및 해당 `Get` 값을 검색 하는 프로시저입니다. 그러나 호출 하지 않으면 명시적으로 이러한 프로시저 이름으로 합니다. 저장 하거나 변수 값을 검색할 것 처럼 대입문 이나 하나의 식에서 속성을 사용 합니다. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]에서는 속성의 프로시저를 호출 합니다.  
  
### <a name="to-call-a-propertys-get-procedure"></a>속성의 Get 프로시저를 호출 하려면  
  
1.  변수 이름을 사용할 것 같은 방법으로 식에서 속성 이름을 사용 합니다. 속성을 사용 하 여 아무 곳 이나 변수 또는 상수를 사용할 수 있습니다.  
  
     또는  
  
     다음에 오는 속성 이름을 사용 하 여 (`=`) 대입문에 로그인 합니다.  
  
     다음 예제에서는 값을 읽었습니다는 <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> 속성을 호출 하는 암시적으로 해당 `Get` 프로시저입니다.  
  
     [!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-call-a-property-procedure_1.vb)]  
  
2.  인수를 사용 하는 속성, 속성 이름으로를 인수 목록을 묶는 괄호를 따릅니다. 인수가 없는 경우에 필요에 따라 괄호를 생략할 수 있습니다.  
  
3.  쉼표로 구분 하 여는 괄호 안에 인수 목록에서 인수를 배치 합니다. 속성은 해당 매개 변수를 정의 하는 동일한 순서로 인수를 지정 해야 합니다.  
  
 방금 변수로 식에 참여 하는 속성의 값 또는 상수 또는 변수 또는 속성 대입문의 왼쪽에 저장 됩니다.  
  
### <a name="to-call-a-propertys-set-procedure"></a>프로시저의 Set 속성을 호출 하려면  
  
1.  대입문의 왼쪽에 속성 이름을 사용 합니다.  
  
     값을 설정 하는 다음 예제는 <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> 속성을 암시적으로 호출 하는 `Set` 프로시저입니다.  
  
     [!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-call-a-property-procedure_2.vb)]  
  
2.  인수를 사용 하는 속성, 속성 이름으로를 인수 목록을 묶는 괄호를 따릅니다. 인수가 없는 경우에 필요에 따라 괄호를 생략할 수 있습니다.  
  
3.  쉼표로 구분 하 여는 괄호 안에 인수 목록에서 인수를 배치 합니다. 속성은 해당 매개 변수를 정의 하는 동일한 순서로 인수를 지정 해야 합니다.  
  
 대입문의 오른쪽에 생성 된 값은 속성에 저장 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [속성 프로시저](./property-procedures.md)  
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)  
 [Property 문](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [Visual Basic에서 속성과 변수의 차이점](./differences-between-properties-and-variables.md)  
 [방법: 속성 만들기](./how-to-create-a-property.md)  
 [방법: 액세스 수준이 혼합된 속성 선언](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [방법: 선언 하 고 Visual Basic의 기본 속성 호출](./how-to-declare-and-call-a-default-property.md)  
 [방법: 속성 값 입력](./how-to-put-a-value-in-a-property.md)  
 [방법: 속성에서 값 가져오기](./how-to-get-a-value-from-a-property.md)  
 [Get 문](../../../../visual-basic/language-reference/statements/get-statement.md)  
 [Set 문](../../../../visual-basic/language-reference/statements/set-statement.md)
