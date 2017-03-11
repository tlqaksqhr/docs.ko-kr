---
title: "Directives (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "directives, Visual Basic compiler"
  - "Visual Basic code, directives"
  - "directives"
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Directives (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 섹션의 항목에서는 Visual Basic 소스 코드 컴파일러 지시문을 문서화합니다.  
  
## 단원 내용  
 [\#Const Directive](../../../visual-basic/language-reference/directives/const-directive.md) \-\- 컴파일러 상수를 정의합니다.  
  
 [\#ExternalSource Directive](../../../visual-basic/language-reference/directives/externalsource-directive.md) \-\- 소스 줄과 소스 외부에 있는 텍스트 간의 매핑을 나타냅니다.  
  
 [\#If...Then...\#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md) \-\- 선택한 코드 블록을 컴파일합니다.  
  
 [\#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md) \-\- Visual Studio 편집기에서 코드의 섹션을 축소하고 숨깁니다.  
  
 **\#Disable, \#Enable** \-\- 코드의 영역에 대한 특정 경고를 사용하거나 사용하지 않도록 설정합니다.  
  
```vb  
#Disable Warning BC42356 ' suppress warning about no awaits in this method  
    Async Function TestAsync() As Task  
        Console.WriteLine("testing")  
    End Function  
#Enable Warning BC42356  
  
```  
  
 쉼표로 구분된 경고 코드 목록도 사용하거나 사용하지 않도록 설정할 수 있습니다.  
  
## 관련 단원  
 [Visual Basic Language Reference](../../../visual-basic/language-reference/index.md)  
  
 [Visual Basic](../../../visual-basic/index.md)