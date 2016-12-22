---
title: "Visual Basic의 데이터 형식 | Microsoft Docs"
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
  - "데이터 형식[Visual Basic], 선언"
  - "형식화"
  - "데이터 형식[Visual Basic]"
  - "Visual Basic 코드, 데이터 형식"
  - "데이터 형식[Visual Basic], 속도 향상"
ms.assetid: 5e1b9aaf-c7ca-4b29-9b22-0e82ed8e85e2
caps.latest.revision: 28
caps.handback.revision: 28
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Visual Basic의 데이터 형식
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

프로그래밍 요소의 *데이터 형식*은 사용할 수 있는 데이터의 종류 및 데이터를 저장하는 방식을 의미합니다.  데이터 형식은 컴퓨터 메모리에 저장할 수 있거나 식의 계산에 사용되는 모든 값에 적용됩니다.  모든 변수, 리터럴, 상수, 열거형, 속성, 프로시저 매개 변수, 프로시저 인수 및 프로시저 반환 값은 데이터 형식을 가집니다.  
  
## 선언된 데이터 형식  
 선언문을 사용하여 프로그래밍 요소를 정의하고 `As` 절을 사용하여 데이터 형식을 지정합니다.  다음 표에서는 다양한 요소를 선언하기 위해 사용하는 문을 보여 줍니다.  
  
|프로그래밍 요소|데이터 형식 선언|  
|--------------|---------------|  
|변수|[Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)에서 지정합니다.<br /><br /> `Dim`   `amount As Double`<br /><br /> `Static`   `yourName As String`<br /><br /> `Public`   `billsPaid As Decimal = 0`|  
|Literal|리터럴 형식 문자에 지정합니다. [Type Characters](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)의 " 리터럴 형식 문자"를 참조하십시오.<br /><br /> `Dim searchChar As Char = "."`  `C`|  
|상수|[Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md)에서 지정합니다.<br /><br /> `Const`   `modulus As Single = 4.17825F`|  
|열거형|[Enum Statement](../../../../visual-basic/language-reference/statements/enum-statement.md)에서 지정합니다.<br /><br /> `Public`   `Enum`   `colors`|  
|속성|[Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md)에서 지정합니다.<br /><br /> `Property`   `region() As String`|  
|프로시저 매개 변수|[Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md), [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md) 또는 [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)에서 지정합니다.<br /><br /> `Sub addSale(ByVal`   `amount`   `As Double)`|  
|프로시저 인수|호출 코드에서 지정합니다. 각 인수는 이미 선언된 프로그래밍 요소이거나 선언된 요소를 포함하는 식입니다.<br /><br /> `subString = Left(`  `inputString`  `,`   `5`  `)`|  
|프로시저 반환 값|[Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md) 또는 [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)에서 지정합니다.<br /><br /> `Function convert(ByVal b As Byte)`   `As String`|  
  
 Visual Basic 데이터 형식 목록을 보려면 참조 하십시오 [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
## 참고 항목  
 [Type Characters](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)   
 [Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)   
 [Visual Basic의 제네릭 형식](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Structures](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Efficient Use of Data Types](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)