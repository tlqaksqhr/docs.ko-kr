---
title: "#If...Then...#Else Directives | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.#EndIf"
  - "#End If"
  - "#Then"
  - "#ElseIf"
  - "vb.#ElseIf"
  - "vb.#Else"
  - "vb.#If"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Visual Basic code, compiling"
  - "#If directive [Visual Basic]"
  - "conditional compilation, directives"
  - "#End if directive [Visual Basic]"
  - "selective compiling"
  - "else directive (#else)"
  - "#Else directive [Visual Basic]"
ms.assetid: 10bba104-e3fd-451b-b672-faa472530502
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# #If...Then...#Else Directives
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

선택한 Visual Basic 코드 블록을 조건부로 컴파일합니다.  
  
## 구문  
  
```  
#If expression Then  
   statements  
[ #ElseIf expression Then  
   [ statements ]  
...  
#ElseIf expression Then  
   [ statements ] ]  
[ #Else  
   [ statements ] ]  
#End If  
```  
  
## 요소  
 `expression`  
 `#If` 및 `#ElseIf` 문에서는 필수적 요소이고 그 외에는 선택적 요소입니다.  하나 이상의 조건부 컴파일러 상수, 리터럴 및 연산자로만 구성되는 모든 식으로, `True` 또는 `False`가 됩니다.  
  
 `statements`  
 `#If` 문 블록에서는 필수적 요소이고 그 외에는 선택적 요소입니다.  관련 식의 결과가 `True`일 경우 컴파일되는 Visual Basic 프로그램 줄 또는 컴파일러 지시문입니다.  
  
 `#End If`  
 `#If` 문 블록을 끝냅니다.  
  
## 설명  
 겉으로 보기에는 `#If...Then...#Else` 지시문의 동작과 `If...Then...Else` 문의 동작이 같습니다.   그러나 `#If...Then...#Else` 지시문은 컴파일러에서 컴파일되는 내용을 평가하고 `If...Then...Else` 문은 런타임에 조건을 평가합니다.  
  
 조건부 컴파일은 주로 동일한 프로그램을 여러 플랫폼에 대해 컴파일할 때 사용하거나  실행 파일에 디버깅 코드가 나타나지 않도록 하는 데 사용됩니다.  조건부 컴파일 타임에 제외된 코드는 최종 실행 파일에서 완전히 생략되기 때문에 최종 실행 파일의 크기나 성능에 영향을 주지 않습니다.  
  
 계산 결과에 상관없이 모든 식은 `Option Compare Binary`를 사용하여 계산됩니다.  `Option Compare` 문은 `#If` 문과 `#ElseIf` 문의 식에 영향을 주지 않습니다.  
  
> [!NOTE]
>  한 줄 형태의 `#If`, `#Else`, `#ElseIf` 및 `#End If` 지시문은 없습니다.  다른 코드는 동일한 줄에 지시문으로 표시될 수 없습니다.  
  
## 예제  
 다음 예제에서는 `#If...Then...#Else` 구문을 사용하여 특정 문의 컴파일 여부를 결정합니다.  
  
 [!CODE [VbVbalrConditionalComp#1](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrConditionalComp#1)]  
  
## 참고 항목  
 [\#Const Directive](../../../visual-basic/language-reference/directives/const-directive.md)   
 [If...Then...Else Statement](../../../visual-basic/language-reference/statements/if-then-else-statement.md)   
 [Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)