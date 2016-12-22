---
title: "How to: Declare an Object Variable and Assign an Object to It in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "object variables, declaring"
  - "declaring object variables"
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Declare an Object Variable and Assign an Object to It in Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

[Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)에 `As Object`를 지정하여 [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)의 변수를 선언할 수 있습니다.  개체 변수에 개체를 할당할 때는 대입문이나 초기화 절에서 등호\(`=`\) 뒤에 개체를 지정합니다.  
  
## 예제  
 다음 예제에서는 `Object` 변수를 선언하고 이 변수에 현재 인스턴스를 할당합니다.  
  
```  
  
      Dim thisObject As Object  
thisObject = "This is an Object"  
```  
  
 변수를 선언의 일부로 초기화하여 선언과 할당을 결합할 수 있습니다.  다음 예제는 위의 예제와 동일합니다.  
  
```  
Dim thisObject As Object = "This is an Object"  
```  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   <xref:System> 네임스페이스에 대한 참조  
  
-   `Dim` 문에 지정할 클래스, 구조체 또는 모듈  
  
-   대입문에 지정할 프로시저  
  
## 참고 항목  
 [변수 선언](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Object Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)   
 [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)   
 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)