---
title: "Variable &#39;&lt;variablename&gt;&#39; is used before it has been assigned a value | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc42104"
  - "BC42104"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42104"
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Variable &#39;&lt;variablename&gt;&#39; is used before it has been assigned a value
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

값이 할당되기 전에 '\<variablename\>' 변수를 사용했습니다.런타임에 null 참조 예외가 발생할 수 있습니다.  
  
 임의의 값이 변수에 할당되기 전에 변수를 읽는 해당 코드를 통한 하나 이상의 경로가 응용 프로그램에 있어야 합니다.  
  
 변수에 값이 할당되지 않으면 해당 데이터 형식에 대한 기본값을 저장합니다.  참조 데이터 형식의 경우 기본값은 [Nothing](../../../visual-basic/language-reference/nothing.md)입니다.  `Nothing` 값을 가진 참조 변수를 읽으면 일부 환경에서는 <xref:System.NullReferenceException>이 발생할 수 있습니다.  
  
 기본적으로 이 메시지는 경고입니다.  경고를 숨기거나 경고를 오류로 처리하는 방법은 [Visual Basic에서 경고 구성](/visual-studio/ide/configuring-warnings-in-visual-basic)을 참조하십시오.  
  
 **오류 ID:** BC42104  
  
### 이 오류를 해결하려면  
  
-   제어 흐름 로직을 확인하고 변수를 읽는 모든 문에 제어를 전달하기 전에 변수가 올바른 값을 가지고 있는지 확인합니다.  
  
-   변수가 항상 올바른 값을 가지도록 하려면 변수를 변수 선언의 일부로 초기화해야 합니다.  자세한 내용은 [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)에서 "초기화"를 참조하십시오.  
  
## 참고 항목  
 [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)   
 [변수 선언](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [변수 문제 해결](../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)