---
title: "기타 제어 구조 (Visual Basic) | Microsoft 문서"
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
- statements [Visual Basic], control flow
- control structures
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
caps.latest.revision: 19
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
ms.openlocfilehash: 639571b493037f26951bd8fbf140d7bce3244889
ms.lasthandoff: 03/13/2017

---
# <a name="other-control-structures-visual-basic"></a>기타 제어 구조(Visual Basic)
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]제어 구조 데 도움이 되는 리소스를 삭제 또는 개체 참조를 반복 해야 할 횟수를 줄이고 제공 합니다.  
  
## <a name="usingend-using-construction"></a>사용 하 여... 생성을 사용 하 여  
 `Using...End Using` 구문은 문 블록을 할 때 SQL 연결 같은 리소스를 사용 합니다. 사용 하 여 리소스를 선택적으로 가져올 수는 `Using` 문입니다. 종료 하는 경우는 `Using` 블록 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 사용 하 여 다른 코드에 사용할 수 있도록 리소스의 자동으로 삭제 합니다. 리소스는 로컬 이며 삭제할 이어야 합니다. 자세한 내용은 참조 [문을 사용 하 여](../../../../visual-basic/language-reference/statements/using-statement.md)합니다.  
  
## <a name="withend-with-construction"></a>와... 생성과 함께 종료 합니다.  
 `With...End With` 생성을 사용 하면 개체 참조를 한 번만 지정할 수 다음 일련의 해당 멤버에 액세스 하는 문 실행 합니다. 이 코드를 간소화할 수 있으며 때문에 성능이 향상 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 멤버에 액세스 하는 각 문에 대 한 참조를 다시 설정할 필요가 없습니다. 자세한 내용은 참조 [와... 문을 사용 하 여 종료](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [제어 흐름](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [판단 구조](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)   
 [루프 구조](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [중첩된 제어 구조](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [문을 사용 하 여](../../../../visual-basic/language-reference/statements/using-statement.md)   
 [With...End With 문](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
