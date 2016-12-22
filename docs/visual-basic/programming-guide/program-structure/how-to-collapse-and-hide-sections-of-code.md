---
title: "How to: Collapse and Hide Sections of Code (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Visual Basic, code collapsing"
  - "Visual Basic, code hiding"
  - "Visual Basic code, collapsing and hiding"
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Collapse and Hide Sections of Code (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`#Region` 지시문을 사용하면 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 파일의 코드 섹션을 축소하고 숨길 수 있습니다.  또한 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] 코드 편집기를 사용하는 경우 `#Region` 지시문을 사용하면 확장하거나 축소할 수 있는 코드 블록을 지정할 수 있습니다.  필요에 따라 코드를 숨기면 읽기 쉽고 관리하기 쉬운 파일을 만들 수 있습니다.  자세한 내용은 [개요](/visual-studio/ide/outlining)를 참조하십시오.  
  
 `#Region` 지시문은 `#If...#End If`와 같은 코드 블록의 의미를 지원합니다.  즉, 지시문은 어느 한 블록에서 시작하여 다른 블록에서 끝나는 것이 아니라 그 시작과 끝이 같은 블록에 있어야 합니다.  `#Region` 지시문은 함수 내에서는 지원되지 않습니다.  
  
### 코드 섹션을 축소하고 숨기려면  
  
-   다음 예제에서처럼 `#Region` 문과 `#End Region` 문 사이에 코드 섹션을 놓습니다.  
  
     [!CODE [VbVbalrConditionalComp#6](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrConditionalComp#6)]  
  
     `#Region` 블록은 한 코드 파일에서 여러 번 사용할 수 있습니다. 즉, 차례로 축소할 수 있는 사용자 고유의 프로시저 및 클래스 블록을 정의할 수 있습니다.  또한 `#Region` 블록은 다른 `#Region` 블록에 중첩될 수 있습니다.  
  
    > [!NOTE]
    >  코드를 숨겨도 컴파일하는 데 아무런 지장이 없으며 `#If...#End If` 문에도 영향을 주지 않습니다.  
  
## 참고 항목  
 [Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)   
 [\#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md)   
 [\#If...Then...\#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md)   
 [개요](/visual-studio/ide/outlining)