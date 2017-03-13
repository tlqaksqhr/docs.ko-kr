---
title: "#Region Directive | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Region"
  - "vb.#Region"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Visual Basic compiler, compiler directives"
  - "#region directive"
  - "region directive (#region)"
  - "#Region keyword"
ms.assetid: 90a6a104-3cbf-47d0-bdc4-b585d0921b87
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# #Region Directive
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Visual Basic 파일에서 코드 섹션을 축소하고 숨깁니다.  
  
## 구문  
  
```  
  
        #Region "identifier_string"  
#End Region  
```  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`identifier_string`|필수.  축소된 경우 영역의 제목 역할을 하는 문자열입니다.  영역은 기본적으로 축소되어 있습니다.|  
|`#End Region`|`#Region` 블록을 종료합니다.|  
  
## 설명  
 `#Region` 지시문을 사용하면 Visual Studio 코드 편집기의 개요 기능을 사용할 때 확장하거나 축소할 코드 블록을 지정할 수 있습니다.  영역을 다른 영역들 내에 배치하거나 *중첩*하여 비슷한 영역을 함께 그룹화할 수 있습니다.  
  
## 예제  
 이 예제에서는 `#Region` 지시문을 사용합니다.  
  
 [!code-vb[VbVbalrConditionalComp#4](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/region-directive_1.vb)]  
  
## 참고 항목  
 [\#If...Then...\#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md)   
 [개요](/visual-studio/ide/outlining)   
 [How to: Collapse and Hide Sections of Code](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)