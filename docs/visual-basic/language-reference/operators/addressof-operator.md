---
title: "AddressOf Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "AddressOf"
  - "vb.AddressOf"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "AddressOf operator"
  - "addresses, passing to API procedures"
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# AddressOf Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

특정 프로시저를 참조하는 프로시저 대리자 인스턴스를 만듭니다.  
  
## 구문  
  
```  
  
AddressOf procedurename  
```  
  
## 요소  
 `procedurename`  
 필수 요소.  새로 만든 프로시저 대리자에서 참조할 프로시저를 지정합니다.  
  
## 설명  
 `AddressOf` 연산자는 `procedurename`에 지정된 함수를 가리키는 함수 대리자를 생성합니다.  지정한 프로시저가 인스턴스 메서드이면 함수 대리자는 인스턴스와 메서드를 모두 참조합니다.  그런 다음 함수 대리자가 호출되면 지정한 인스턴스의 지정한 메서드가 호출됩니다.  
  
 `AddressOf` 연산자는 대리자 생성자의 피연산자로 사용되거나, 컴파일러가 대리자의 형식을 확인하는 컨텍스트에서 사용될 수 있습니다.  
  
## 예제  
 다음 예제에서는 `AddressOf` 연산자를 사용하여 단추의 `Click` 이벤트를 처리할 대리자를 지정합니다.  
  
 [!code-vb[VbVbalrDelegates#8](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_1.vb)]  
  
## 예제  
 다음 예제에서는 `AddressOf` 연산자를 사용하여 스레드에 대한 시작 함수를 지정합니다.  
  
 [!code-vb[VbVbalrDelegates#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_2.vb)]  
  
## 참고 항목  
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Delegates](../../../visual-basic/programming-guide/language-features/delegates/delegates.md)