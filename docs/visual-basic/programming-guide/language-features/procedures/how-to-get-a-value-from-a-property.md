---
title: "방법: 속성 (Visual Basic)에서 값 가져오기 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- property values
- Visual Basic code, procedures
- values, properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
caps.latest.revision: 11
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7487e4cde724c46a193639f2ad116d25e4ff834c
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a>방법: 속성에서 값 가져오기(Visual Basic)
식에서 속성 이름을 포함 하 여 속성의 값을 검색 합니다.  
  
 속성의 `Get` 프로시저는 값을 검색 하지만 호출 하지 않으면 명시적으로 그 이름으로 합니다. 변수를 사용할 때와 마찬가지로 속성을 사용 합니다. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 속성의 프로시저를 호출 합니다.  
  
### <a name="to-retrieve-a-value-from-a-property"></a>속성에서 값을 검색 하려면  
  
1.  변수 이름을 사용할 것 같은 방법으로 식에서 속성 이름을 사용 합니다. 속성을 사용 하 여 어디서 나 변수 또는 상수를 사용할 수 있습니다.  
  
     또는  
  
     다음에 오는 속성 이름을 사용 하 여 (`=`) 대입문에 로그인 합니다.  
  
     다음 예제에서는 값을 읽었습니다는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] `Now` 암시적으로 호출 하는 속성을 해당 `Get` 프로시저입니다.  
  
     [!code-vb[VbVbalrDateProperties #&4;](./codesnippet/VisualBasic/how-to-get-a-value-from-a-property_1.vb)]  
  
2.  인수를 사용 하는 속성을 괄호로 묶어 인수 목록 속성 이름 뒤에. 필요에 따라 인수가 있을 경우 괄호를 생략할 수 있습니다.  
  
3.  인수를 괄호로 묶고 쉼표로 구분 된 인수 목록에 배치 합니다. 속성은 해당 매개 변수를 정의 하는 동일한 순서 대로 인수를 지정 해야 합니다.  
  
 변수 처럼 식에 참여 하는 속성의 값 또는 상수 또는 변수 또는 대입문의 왼쪽에는 속성에 저장 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로시저](./index.md)   
 [속성 프로시저](./property-procedures.md)   
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)   
 [Property 문](../../../../visual-basic/language-reference/statements/property-statement.md)   
 [Visual Basic에서 속성과 변수의 차이점](./differences-between-properties-and-variables.md)   
 [방법: 속성 만들기](./how-to-create-a-property.md)   
 [방법: 액세스 수준이 혼합된 된 속성 선언](./how-to-declare-a-property-with-mixed-access-levels.md)   
 [방법: 속성 프로시저 호출](./how-to-call-a-property-procedure.md)   
 [방법: 선언 하 고 Visual Basic의 기본 속성 호출](./how-to-declare-and-call-a-default-property.md)   
 [방법: 속성 값 입력](./how-to-put-a-value-in-a-property.md)
