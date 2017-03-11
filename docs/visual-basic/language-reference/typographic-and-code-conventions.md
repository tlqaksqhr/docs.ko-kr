---
title: "Typographic and Code Conventions (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "coding conventions, Visual Basic"
  - "best practices, coding conventions"
  - "conventions, Visual Basic coding"
  - "typographic conventions"
  - "document conventions"
  - "conventions, documentation"
  - "Visual Basic code, conventions"
ms.assetid: 1916cd81-ea9d-4faa-81f7-4a0d864b60f4
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Typographic and Code Conventions (Visual Basic)
[!INCLUDE[vs2017banner](../../visual-basic/developing-apps/includes/vs2017banner.md)]

Visual Basic 설명서는 다음과 같은 글꼴 표시 및 코드 규칙을 사용합니다.  
  
## 글꼴 표시 규칙  
  
|예제|설명|  
|--------|--------|  
|`Sub`, `If`, `ChDir`, `Print`, `True`, `Debug`|언어별 키워드 및 런타임 멤버는 첫 문자가 대문자이며 이 예제에서처럼 서식 지정됩니다.|  
|SmallProject, ButtonCollection|형식에 적용하는 단어 및 구는 이 예제에서처럼 서식 지정됩니다.|  
|[Module Statement](../../visual-basic/language-reference/statements/module-statement.md)|클릭하여 다른 도움말 페이지로 이동할 수 있는 링크는 이 예제에서처럼 서식 지정됩니다.|  
|*object*, *variableName*, `argumentList`|사용자가 제공하는 정보에 대한 자리 표시자는 이 예제에서처럼 서식 지정됩니다.|  
|\[ Shadows \], \[ *expressionList* \]|구문에서 선택적 항목은 대괄호 안에 들어갑니다.|  
|{ `Public` &#124; `Friend` &#124; `Private` }|구문에서 둘 이상의 항목 중에서 선택해야 하는 경우에는 항목이 중괄호로 묶이고 세로줄로 구분됩니다.<br /><br /> 항목이 여러 개 있는 경우 한 항목만 선택해야 합니다.|  
|\[ `Protected` &#124; `Friend` \]|구문에서 둘 이상의 항목 중에서 선택할 수 있는 경우에는 항목이 대괄호로 묶이고 세로줄로 구분됩니다.<br /><br /> 항목의 모든 조합을 선택하거나 항목을 선택하지 않을 수 있습니다.|  
|\[{ `ByVal` &#124; `ByRef` }\]|구문에서 둘 이상의 항목을 선택할 수 있지만 항목을 완전히 생략할 수도 있는 경우에는 항목이 대괄호와 중괄호로 묶이고 세로줄로 구분됩니다.|  
|*memberName* 1, *memberName*2, *memberName*3|같은 자리 표시자의 여러 인스턴스는 예제에서처럼 첨자로 구분됩니다.|  
|*memberName1*<br /><br /> ...<br /><br /> *memberNameN*|구문에서 줄임표\(...\)는 바로 앞에 불특정 개수의 항목이 있다는 것을 나타냅니다.<br /><br /> 코드에서 줄임표는 명확성을 기하기 위해 생략되는 코드를 의미합니다.|  
|Esc, Enter|키보드의 키 이름 및 키 시퀀스는 모두 대문자로 나타납니다.|  
|ALT\+F1|키 이름 사이에 더하기 기호\(\+\)가 있는 경우에는 한 키를 누른 상태에서 다른 키를 눌러야 합니다.  예를 들어, Alt\+F1은 Alt 키를 누른 채 F1 키를 누르는 것을 의미합니다.|  
  
## 코드 규칙  
  
|예제|설명|  
|--------|--------|  
|`sampleString = "Hello, world!"`|코드 샘플은 고정 폭 글꼴로 나타나며 이 예제에서처럼 서식 지정됩니다.|  
|앞의 문에서는 `sampleString`의 값을 "Hello, world\!"로 설정합니다.|설명 텍스트의 코드 요소는 이 예제에서처럼 고정 폭 글꼴로 나타납니다.|  
|`' This is a comment.`<br /><br /> `REM This is also a comment.`|코드 주석은 아포스트로피\('\) 또는 REM 키워드로 지정됩니다.|  
|`sampleVar = "This is an " _`<br /><br /> `& "example" _`<br /><br /> `& " of how to continue code."`|줄 끝의 공백과 밑줄\( \_\)은 다음 줄에서 문이 계속됨을 나타냅니다.|  
  
## 참고 항목  
 [Visual Basic Language Reference](../../visual-basic/language-reference/index.md)   
 [키워드](../../visual-basic/language-reference/keywords/index.md)   
 [Visual Basic Runtime Library Members](../../visual-basic/language-reference/runtime-library-members.md)   
 [Visual Basic Naming Conventions](../../visual-basic/programming-guide/program-structure/naming-conventions.md)   
 [방법: 코드에서 문 분리 및 결합](../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)   
 [Comments in Code](../../visual-basic/programming-guide/program-structure/comments-in-code.md)