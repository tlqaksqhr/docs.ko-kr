---
title: "How to: Hold More Than One Value in a Variable (Visual Basic) | Microsoft Docs"
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
  - "classes [Visual Basic], composite data types"
  - "composite types"
  - "composite data types"
  - "data types [Visual Basic], composite"
  - "arrays [Visual Basic], composite data types"
  - "structures, composite data types"
  - "arrays [Visual Basic], compilation errors"
  - "types [Visual Basic], composite"
ms.assetid: 5fe0e558-aac2-4a40-b7f2-7cfea7336917
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# How to: Hold More Than One Value in a Variable (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

변수를 *복합 데이터 형식*으로 선언하면 변수에 값을 두 개 이상 사용할 수 있습니다.  
  
 [Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)에는 구조체, 배열 및 클래스가 포함됩니다.  복합 데이터 형식의 변수에는 기본 데이터 형식과 다른 복합 형식의 조합을 사용할 수 있습니다.  구조체와 클래스에는 코드와 데이터를 사용할 수 있습니다.  
  
### 변수에 값을 두 개 이상 사용하려면  
  
1.  변수에 사용할 복합 데이터 형식을 결정합니다.  
  
2.  복합 데이터 형식이 아직 정의되지 않았으면 변수에서 사용할 수 있도록 복합 데이터 형식을 정의합니다.  
  
    -   [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md)을 사용하여 구조체를 정의합니다.  
  
    -   [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)을 사용하여 배열을 정의합니다.  
  
    -   [Class Statement](../../../../visual-basic/language-reference/statements/class-statement.md)을 사용하여 클래스를 정의합니다.  
  
3.  `Dim`을 사용하여 변수를 선언합니다.  
  
4.  변수 이름 뒤에 `As` 절을 붙입니다.  
  
5.  `As` 키워드 뒤에 해당 복합 데이터 형식의 이름을 붙입니다.  
  
## 참고 항목  
 [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Type Characters](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)   
 [Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)   
 [Structures](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [배열](../../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)