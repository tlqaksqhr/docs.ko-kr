---
title: "&#39;AddressOf&#39; operand must be the name of a method (without parentheses) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30577"
  - "bc30577"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30577"
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# &#39;AddressOf&#39; operand must be the name of a method (without parentheses)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`AddressOf` 연산자는 특정 프로시저를 참조하는 프로시저 대리자 인스턴스를 만드므로  구문은 다음과 같습니다.  
  
 `AddressOf` `procedurename`  
  
 `AddressOf` 뒤의 인수에 불필요한 괄호를 삽입했습니다.  
  
 **오류 ID:** BC30577  
  
### 이 오류를 해결하려면  
  
1.  `AddressOf` 뒤의 인수를 묶은 괄호를 제거합니다.  
  
2.  인수가 메서드 이름인지 확인합니다.  
  
## 참고 항목  
 [AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Delegates](../../../visual-basic/programming-guide/language-features/delegates/delegates.md)