---
title: "Iterator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Iterator"
helpviewer_keywords: 
  - "Iterator keyword [Visual Basic]"
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Iterator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

지정 하는 함수 또는 `Get` 접근자는 반복기입니다.  
  
## 설명  
 *반복기* 컬렉션에서 사용자 지정 반복을 수행 합니다.  반복기를 사용 하 여  [산출](../../../visual-basic/language-reference/statements/yield-statement.md) 문 컬렉션에 있는 한 번에 각 요소를 반환 합니다.  경우는 `Yield` 문을 도달, 코드의 현재 위치를 유지 합니다.  실행 위치에서 다음 반복기 함수가 호출 될 때 다시 시작 됩니다.  
  
 함수 또는 반복기를 구현할 수 있는 `Get` 접근자는 속성 정의의.  `Iterator` 한정자의 반복기 함수 선언에 나타납니다 또는 `Get` 접근자입니다.  
  
 사용 하 여 클라이언트 코드에서 반복기를 호출을 [For Each...Next 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
 반복기 함수의 반환 형식 또는 `Get` 접근자를 사용할 수 있습니다 <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, 또는 <xref:System.Collections.Generic.IEnumerator%601>.  
  
 반복기를 사용할 수 없습니다 `ByRef` 매개 변수.  
  
 반복기는 이벤트, 인스턴스 생성자, 정적 생성자 또는 정적 소멸자에서 발생 하지 않습니다.  
  
 반복기는 익명 함수를 수 있습니다.  자세한 내용은 [반복기](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md)를 참조하십시오.  
  
 반복기에 대한 자세한 내용은 [반복기](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md)를 참조하십시오.  
  
## 용도  
 `Iterator` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
-   [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## 예제  
 다음 예제에서는 반복기 함수를 보여 줍니다.  반복기 함수는 `Yield` 문 안에  [For…다음](../../../visual-basic/language-reference/statements/for-next-statement.md) 루프.  반복할 때마다는  [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) 문의 본문에 `Main` 에 대 한 호출을 만듭니다는 `Power` 반복기 함수.  반복기 함수를 호출할 때마다 계속 해 서 다음을 실행 하는 `Yield` 다음 반복의 과정에서 발생 하는 문의 `For…Next` 루프.  
  
 [!code-vb[VbVbalrStatements#98](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/iterator_1.vb)]  
  
## 예제  
 다음 예제는 `Get` 되는 반복기 접근자입니다.  `Iterator` 한정자는 속성 선언에서입니다.  
  
 [!code-vb[VbVbalrStatements#99](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/iterator_2.vb)]  
  
 다른 예제를 보려면 [반복기](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>   
 [반복기](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md)   
 [Yield 문](../../../visual-basic/language-reference/statements/yield-statement.md)