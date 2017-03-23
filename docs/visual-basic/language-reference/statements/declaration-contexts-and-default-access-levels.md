---
title: "Declaration Contexts and Default Access Levels (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "module level, defined"
  - "declaration contexts, Visual Basic"
  - "procedure level, defined"
  - "namespace level, defined"
  - "access levels, Visual Basic"
  - "access levels, default levels"
ms.assetid: bf63b96e-e825-4745-88c8-5dae222728db
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Declaration Contexts and Default Access Levels (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 항목에서는 다른 형식 안에 선언할 수 있는 Visual Basic 형식과 해당 형식의 액세스 수준을 지정하지 않을 경우의 기본값에 대해 설명합니다.  
  
## 선언 컨텍스트 수준  
 프로그래밍 요소의 *선언 컨텍스트*는 해당 요소가 선언되는 코드의 영역입니다.  *포함 요소*라고도 하는 다른 프로그래밍 요소를 가리키는 경우도 많습니다.  
  
 선언 컨텍스트의 수준은 다음과 같습니다.  
  
-   *네임스페이스 수준* — 클래스, 구조체, 모듈 또는 인터페이스를 제외한 소스 파일 또는 네임스페이스 내  
  
-   *모듈 수준* — 프로시저나 블록을 제외한 클래스, 구조체, 모듈 또는 인터페이스 내  
  
-   *프로시저 수준* — 프로시저 또는 블록\(`If` 또는 `For`\) 내  
  
 다음 표에서는 선언된 여러 가지 프로그래밍 요소에 대한 기본 액세스 수준을 해당 선언 컨텍스트에 따라 보여 줍니다.  
  
|선언 요소|네임스페이스 수준|모듈 수준|프로시저 수준|  
|-----------|---------------|-----------|-------------|  
|변수\([Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)\)|허용되지 않음|`Private`\(`Structure`에서는 `Public`, `Interface`에서는 허용되지 않음\)|`Public`|  
|상수\([Const Statement](../../../visual-basic/language-reference/statements/const-statement.md)\)|허용되지 않음|`Private`\(`Structure`에서는 `Public`, `Interface`에서는 허용되지 않음\)|`Public`|  
|열거형\([Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md)\)|`Friend`|`Public`|허용되지 않음|  
|클래스\([Class Statement](../../../visual-basic/language-reference/statements/class-statement.md)\)|`Friend`|`Public`|허용되지 않음|  
|구조체\([Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md)\)|`Friend`|`Public`|허용되지 않음|  
|모듈\([Module Statement](../../../visual-basic/language-reference/statements/module-statement.md)\)|`Friend`|허용되지 않음|허용되지 않음|  
|인터페이스\([Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md)\)|`Friend`|`Public`|허용되지 않음|  
|프로시저\([Function Statement](../../../visual-basic/language-reference/statements/function-statement.md), [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)\)|허용되지 않음|`Public`|허용되지 않음|  
|외부 참조\([Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)\)|허용되지 않음|`Public`\(`Interface`에서는 허용되지 않음\)|허용되지 않음|  
|연산자\([Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)\)|허용되지 않음|`Public`\(`Interface` 또는 `Module`에서는 허용되지 않음\)|허용되지 않음|  
|속성\([Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)\)|허용되지 않음|`Public`|허용되지 않음|  
|기본 속성\([Default](../../../visual-basic/language-reference/modifiers/default.md)\)|허용되지 않음|`Public`\(`Module`에서는 허용되지 않음\)|허용되지 않음|  
|이벤트\([Event Statement](../../../visual-basic/language-reference/statements/event-statement.md)\)|허용되지 않음|`Public`|허용되지 않음|  
|대리자\([Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md)\)|`Friend`|`Public`|허용되지 않음|  
  
 자세한 내용은 [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조하십시오.  
  
## 참고 항목  
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)   
 [Private](../../../visual-basic/language-reference/modifiers/private.md)   
 [Public](../../../visual-basic/language-reference/modifiers/public.md)