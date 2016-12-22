---
title: "Array Conversions (Visual Basic) | Microsoft Docs"
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
  - "arrays [Visual Basic], converting type"
  - "type conversion, arrays"
  - "conversions, type"
  - "arrays [Visual Basic], data types"
  - "conversions, data type"
  - "object arrays, converting type"
  - "data type conversion, array conversions"
  - "conversions, array types"
  - "object arrays"
ms.assetid: fceff7d2-a1b7-44c7-b9aa-8bd831d8a444
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Array Conversions (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

다음 조건이 충족되면 특정 배열 형식을 서로 다른 배열 형식으로 변환할 수 있습니다.  
  
-   **동일한 차수.** 두 배열의 차수가 동일해야 합니다. 즉, 동일한 개수의 차수를 가지고 있어야 합니다.  그러나 각 차원의 길이는 동일하지 않아도 됩니다.  
  
-   **요소 데이터 형식.** 두 배열의 요소 데이터 형식이 참조 형식이어야 합니다.  `Integer` 배열은 최소한 하나의 값 형식이 포함되어 있기 때문에 `Long` 배열이나 `Object` 배열로도 변환할 수 없습니다.  자세한 내용은 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)를 참조하십시오.  
  
-   **변환 가능성.** 두 배열의 요소 형식 사이에서 확대 변환이나 축소 변환이 가능해야 합니다.  `String` 배열과 <xref:System.Attribute?displayProperty=fullName>에서 파생된 클래스의 배열 사이에 변환을 시도하는 경우가 이 요구 사항을 충족하지 않는 예입니다.  이 두 형식은 공통적인 요소가 전혀 없으므로 서로 간에 어떤 종류의 변환도 존재하지 않습니다.  
  
 배열 형식 간의 변환이 축소인지 확대인지 여부는 각 요소의 변환이 확대인지 축소인지에 따라 결정됩니다.  자세한 내용은 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)을 참조하십시오.  
  
## Object 배열로 변환  
 `Object` 배열을 초기화하지 않고 선언한 경우 배열의 요소 형식은 초기화되지 않는 동안은 `Object`입니다.  배열을 특정 클래스의 배열로 설정하면 해당 클래스 형식을 갖게 됩니다.  그러나 내부 형식은 여전히 `Object`이며 나중에 해당 배열을 관련이 없는 다른 클래스 배열로 설정할 수 있습니다.  모든 클래스는 `Object`에서 파생되므로 배열의 요소 형식을 한 클래스에서 다른 클래스로 자유롭게 변경할 수 있습니다.  
  
 다음 예제에서 형식 `student`와 `String` 간에 변환은 발생하지 않지만 둘 모두 `Object`에서 파생되므로 모든 할당이 올바릅니다.  
  
```  
' Assume student has already been defined as a class.  
Dim testArray() As Object  
' testArray is still an Object array at this point.  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
testArray = New student(3) {}  
' testArray is now of type student().  
testArray = names  
' testArray is now a String array.  
```  
  
### 배열의 내부 형식  
 처음부터 배열을 특정 클래스로 선언하면 배열의 내부 요소 형식은 해당 클래스가 됩니다.  나중에 배열을 다른 클래스의 배열로 설정하는 경우에는 두 클래스 간에 변환이 수행되어야 합니다.  
  
 다음 예제에서 `students`는 `student` 배열입니다.  `String`과 `student` 사이에 어떠한 변환도 수행되지 않기 때문에 마지막 문은 실패합니다.  
  
```  
Dim students() As student  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
students = New Student(3) {}  
' The following statement fails at compile time.  
students = names  
```  
  
## 참고 항목  
 [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Implicit and Explicit Conversions](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Conversions Between Strings and Other Types](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)   
 [How to: Convert an Object to Another Type in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)   
 [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [배열](../../../../visual-basic/programming-guide/language-features/arrays/index.md)