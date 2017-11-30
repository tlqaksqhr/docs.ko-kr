---
title: "방법: 액세스 수준이 혼합된 속성 선언(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- access levels [Visual Basic], properties
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- mixed access levels
- Visual Basic code, properties
- properties [Visual Basic], access levels
- Property statement [Visual Basic], declaring mixed access levels
ms.assetid: fdbb2d97-279a-4956-b26c-cbdfbc34915a
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 90fe20303f6f2ed692e54e44ee8cc65897531543
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-a-property-with-mixed-access-levels-visual-basic"></a>방법: 액세스 수준이 혼합된 속성 선언(Visual Basic)
원하는 경우는 `Get` 및 `Set` 액세스 수준이 서로 속성에 프로시저에서 더 수준을 사용할 수 있습니다는 `Property` 문과 더 제한적인 수준 중 하나에 `Get` 또는 `Set` 문입니다. 일부 속성의 값을 가져올 수 있게 되기를 코드와 값을 변경 하려면 코드의 다른 구성 요소 속성에 액세스 수준이 혼합된를 사용 합니다.  
  
 액세스 수준에 대 한 자세한 내용은 참조 하십시오. [액세스 수준을 Visual Basic의](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.  
  
### <a name="to-declare-a-property-with-mixed-access-levels"></a>액세스 수준이 혼합된 된 속성을 선언 하려면  
  
1.  일반적인 방법으로 속성을 선언 하 고 덜 제한적인 액세스 수준을 지정할 (같은 `Public`)에 `Property` 문.  
  
2.  선언 중 하나는 `Get` 또는 `Set` 더 제한적인 액세스 수준을 지정 하는 프로시저 (같은 `Friend`).  
  
3.  다른 속성 프로시저에 대 한 액세스 수준을 지정 하지 마십시오. 액세스 수준에 선언 된 것으로 가정은 `Property` 문. 속성 프로시저 중 하나 에서만 액세스를 제한할 수 있습니다.  
  
     [!code-vb[VbVbcnProcedures#10](./codesnippet/VisualBasic/how-to-declare-a-property-with-mixed-access-levels_1.vb)]  
  
     앞의 예제에는 `Get` 프로시저에 동일한 `Protected` 자체를 속성으로 액세스 하는 동안는 `Set` 프로시저에 `Private` 액세스 합니다. 클래스에서 파생 `employee` 읽을 수는 `salary` 값만 `employee` 클래스에서 설정할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [절차](./index.md)  
 [속성 프로시저](./property-procedures.md)  
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)  
 [Property 문](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [Visual Basic에서 속성과 변수의 차이점](./differences-between-properties-and-variables.md)  
 [방법: 속성 만들기](./how-to-create-a-property.md)  
 [방법: 속성 프로시저 호출](./how-to-call-a-property-procedure.md)  
 [방법: 선언 하 고 Visual Basic의 기본 속성 호출](./how-to-declare-and-call-a-default-property.md)  
 [방법: 속성 값 입력](./how-to-put-a-value-in-a-property.md)  
 [방법: 속성에서 값 가져오기](./how-to-get-a-value-from-a-property.md)
