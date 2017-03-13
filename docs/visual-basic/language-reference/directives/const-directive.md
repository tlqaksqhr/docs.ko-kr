---
title: "#Const Directive | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.#Const"
  - "#vb.Const"
  - "#Const"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "#Const directive"
  - "conditional compilation, directives"
  - "Const directive (#Const)"
  - "Visual Basic compiler, compiler directives"
  - "constants, Const directive"
  - "constants, declaring"
  - "Const statement [Visual Basic], directive (#Const)"
  - "declaring constants, #const directive"
ms.assetid: 707669e5-23f9-4f17-8622-a0d534429386
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# #Const Directive
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Visual Basic의 조건부 컴파일러 상수를 정의합니다.  
  
## 구문  
  
```  
#Const constname = expression  
```  
  
## 요소  
 `constname`  
 필수 요소.  정의되는 상수의 이름입니다.  
  
 `expression`  
 필수 요소.  리터럴, 다른 조건부 컴파일러 상수 또는 `Is`를 제외한 논리 연산자나 산술 연산자입니다.  
  
## 설명  
 조건부 컴파일러 상수는 이 상수가 사용된 파일에 대해 항상 Private입니다.  `#Const` 지시문을 사용하여 공용 컴파일러 상수를 만들 수 없으며 사용자 인터페이스 또는 `/define` 컴파일러 옵션을 통해서만 만들 수 있습니다.  
  
 `expression`에는 조건부 컴파일러 상수와 리터럴만 사용할 수 있습니다.  `Const`로 정의된 표준 상수를 사용하면 오류가 발생합니다.  반대로, `#Const` 키워드로 정의된 상수는 조건부 컴파일에만 사용할 수 있습니다.  상수를 정의하지 않을 경우 상수 값은 `Nothing`입니다.  
  
## 예제  
 다음 예제에서는 `#Const` 지시문을 사용합니다.  
  
 [!code-vb[VbVbalrConditionalComp#3](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/const-directive_1.vb)]  
  
## 참고 항목  
 [\/define](../../../visual-basic/reference/command-line-compiler/define.md)   
 [\#If...Then...\#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md)   
 [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md)   
 [Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)   
 [If...Then...Else Statement](../../../visual-basic/language-reference/statements/if-then-else-statement.md)