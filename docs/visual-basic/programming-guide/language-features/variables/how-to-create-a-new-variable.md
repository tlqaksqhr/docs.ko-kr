---
title: "How to: Create a New Variable (Visual Basic) | Microsoft Docs"
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
  - "Dim statement"
  - "variables [Visual Basic], creating"
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
caps.latest.revision: 29
caps.handback.revision: 29
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Create a New Variable (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

[Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)을 사용하여 변수를 만들 수 있습니다.  
  
### 새 변수를 만들려면  
  
1.  `Dim` 문을 사용하여 변수를 선언합니다.  
  
    ```  
  
    Dim newCustomer  
    ```  
  
2.  [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Static](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) 또는 [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md)와 같은 변수 특징에 대한 사양을 포함합니다.  자세한 내용은 [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)을 참조하십시오.  
  
    ```  
    Public Static newCustomer  
    ```  
  
     선언에 다른 키워드를 사용하는 경우 `Dim` 키워드는 사용하지 않아도 됩니다.  
  
3.  사양 다음에 변수의 이름을 지정합니다. 변수 이름은 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 규칙을 따라야 합니다.  자세한 내용은 [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하십시오.  
  
    ```  
    Public Static newCustomer  
    ```  
  
4.  이름 다음에 [As](../../../../visual-basic/language-reference/statements/as-clause.md) 절을 사용하여 변수의 데이터 형식을 지정합니다.  
  
    ```  
    Public Static newCustomer As Customer   
    ```  
  
     데이터 형식을 지정하지 않으면 기본값으로 `Object`가 사용됩니다.  
  
5.  `As` 절 다음에 등호\(`=`\)를 사용하고 등호 다음에 변수의 초기 값을 지정합니다.  
  
     [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 `Dim` 문을 실행할 때마다 해당 변수에 지정된 값을 할당합니다.  초기 값을 지정하지 않으면 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 `Dim` 문이 들어 있는 코드가 처음 실행될 때 해당 변수의 데이터 형식에 맞는 기본 초기 값을 할당합니다.  
  
     변수가 참조 형식인 경우 `As` 절에 [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) 키워드를 포함하여 클래스의 인스턴스를 만들 수 있습니다.  `New`를 사용하지 않은 경우 변수의 초기 값은 [Nothing](../../../../visual-basic/language-reference/nothing.md)이 됩니다.  
  
    ```  
    Public Static newCustomer As New Customer  
    ```  
  
## 참고 항목  
 [Variables](../../../../visual-basic/reference/command-line-compiler/index.md)   
 [변수 선언](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)   
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Statements](../../../../visual-basic/language-reference/statements/index.md)   
 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md)