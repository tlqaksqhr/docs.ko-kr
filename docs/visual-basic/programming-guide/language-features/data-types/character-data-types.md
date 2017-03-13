---
title: "Character Data Types (Visual Basic) | Microsoft Docs"
ms.custom: ""
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
  - "data types [Visual Basic], character"
  - "String data type, character data types"
  - "character data types [Visual Basic]"
  - "Char data type, character data types"
  - "data types [Visual Basic], choosing"
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 23
---
# Character Data Types (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 인쇄하거나 표시할 수 있는 문자를 다루는 데 사용되는 *문자 데이터 형식*을 제공합니다.  이 형식은 모두 유니코드 문자를 다루지만 `Char`은 문자를 하나만 포함하고 `String`은 문자를 무한대로 포함합니다.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 데이터 형식을 비교한 표를 보려면 [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md)을 참조하십시오.  
  
## Char 형식  
 `Char` 데이터 형식은 단일 2바이트\(16비트\) 유니코드 문자입니다.  변수가 항상 정확히 한 문자만 포함하는 경우 변수를 `Char`로 선언합니다.  예를 들면 다음과 같습니다.  
  
 [!code-vb[VbVbalrCharTypes#1](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_1.vb)]  
  
 `Char` 또는 `String` 변수에 사용할 수 있는 각 값은 유니코드 문자 집합의 *코드 포인트*\(문자 코드\)입니다.  유니코드 문자에는 기본 ASCII 문자 집합, 그 밖의 다양한 영문자, 악센트 부호, 통화 기호, 분수, 분음 부호 및 수학\/기술 기호가 포함됩니다.  
  
> [!NOTE]
>  유니코드 문자 집합에서 십진수 55296~55551에 해당하는 코드 포인트 D800~DFFF는 두 개의 16비트 값을 사용하여 단일 코드 포인트를 나타내는 *서로게이트 쌍*에 사용하기 위해 예약되어 있습니다.  `Char` 변수에는 서로게이트 쌍을 사용할 수 없으며 `String` 변수에서는 두 개의 위치에 이러한 쌍을 보유합니다.  
  
 자세한 내용은 [Char Data Type](../../../../visual-basic/language-reference/data-types/char-data-type.md)을 참조하십시오.  
  
## String 형식  
 `String` 데이터 형식은 0개 이상의 2바이트\(16비트\) 유니코드 문자 시퀀스입니다.  변수가 문자를 무한대로 포함할 수 있으면 변수를 `String`으로 선언합니다.  예를 들면 다음과 같습니다.  
  
 [!code-vb[VbVbalrCharTypes#2](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_2.vb)]  
  
 자세한 내용은 [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md)을 참조하십시오.  
  
## 참고 항목  
 [Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)   
 [Visual Basic의 제네릭 형식](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Type Characters](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)