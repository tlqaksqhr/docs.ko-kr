---
title: "Call Statement (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Call"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "procedures, Call statement"
  - "Call statement"
  - "procedures, calling"
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Call Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`Function`, `Sub` 또는 DLL\(동적 연결 라이브러리\) 프로시저로 제어를 전달합니다.  
  
## 구문  
  
```  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## 요소  
 `procedureName`  
 필수 요소.  호출할 프로시저의 이름입니다.  
  
 `argumentList`  
 선택적 요소.  호출될 때 프로시저로 전달되는 인수를 나타내는 변수나 식의 목록입니다.  인수가 여러 개 있으면 쉼표로 구분됩니다.  `argumentList`를 포함하는 경우 괄호로 묶어야 합니다.  
  
## 설명  
 사용할 수 있는 `Call` 프로시저를 호출할 때 키워드.  대부분의 프로시저 호출의 경우에이 키워드를 사용할 필요가 없습니다.  
  
 일반적으로 사용 하는 `Call` 키워드 식 이라는 식별자로 시작 되지 않는 경우.  사용은 `Call` 없는 기타 사용에 대 한 키워드를 권장 합니다.  
  
 프로시저가 값을 반환하는 경우 `Call` 문은 반환되는 값을 무시합니다.  
  
## 예제  
 코드는 다음 두 가지 예를 보여 줍니다. 여기서는 `Call` 키워드 프로시저를 호출할 필요가 없습니다.  두 예제 모두 식 이라는 식별자로 시작 되지 않습니다.  
  
 [!code-vb[VbVbalrStatements#97](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/call-statement_1.vb)]  
  
## 참고 항목  
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)