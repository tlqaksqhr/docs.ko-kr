---
title: "Composite Data Types (Visual Basic) | Microsoft Docs"
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
  - "classes [Visual Basic], composite data types"
  - "composite types"
  - "composite data types"
  - "data types [Visual Basic], composite"
  - "arrays [Visual Basic], composite data types"
  - "structures, composite data types"
  - "classes [Visual Basic], composite types"
  - "types [Visual Basic], composite"
ms.assetid: 62970f2e-52c0-4369-8963-613820f1f434
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Composite Data Types (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 제공하는 기본 데이터 형식과 별도로 다른 형식의 항목을 조합하여 구조체, 배열 및 클래스와 같은 *복합 데이터 형식*을 만들 수 있습니다.  기본 데이터 형식과 다른 복합 데이터 형식으로부터 복합 데이터 형식을 빌드할 수 있습니다.  예를 들어, 구조체 요소의 배열이나 배열 멤버를 가진 구조체를 정의할 수 있습니다.  
  
## 데이터 형식  
 복합 형식은 각 구성 요소의 데이터 형식과 다릅니다.  예를 들어, `Integer` 요소의 배열은 `Integer` 데이터 형식의 배열이 아닙니다.  
  
 일반적으로 배열 데이터 형식을 나타내는 데는 요소 형식, 괄호 및 쉼표가 필요에 따라 사용됩니다.  예를 들어, `String` 요소의 1차원 배열은 `String()`으로 나타내고 `Boolean` 요소의 2차원 배열은 `Boolean(,)`으로 나타냅니다.  
  
## 구조체 형식  
 모든 구조체를 포함하는 단일 데이터 형식은 없습니다.  각 구조체 정의는 고유한 데이터 형식을 나타냅니다. 이는 두 개의 구조체가 같은 요소를 동일한 순서로 정의하는 경우에도 해당됩니다.  그러나 같은 구조체의 인스턴스를 둘 이상 만들 경우 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 모든 인스턴스가 동일한 데이터 형식인 것으로 간주합니다.  
  
## 배열 형식  
 모든 배열을 포함하는 단일 데이터 형식은 없습니다.  배열의 특정 인스턴스의 데이터 형식을 결정하는 요소는 다음과 같습니다.  
  
-   배열이라는 사실  
  
-   배열의 차수\(차원 수\)  
  
-   배열의 요소 형식  
  
 특히 특정 차원의 길이는 해당 인스턴스의 데이터 형식의 일부가 아닙니다.  다음은 이에 대한 예입니다.  
  
```  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 위 예제에서 배열 변수 `arrayA`와 `arrayB`는 다른 길이로 초기화되더라도 동일한 데이터 형식\(`Byte()`\)으로 간주됩니다.  변수 `arrayB`와 `arrayC`는 해당 요소 형식이 다르므로 동일한 형식이 아닙니다.  변수 `arrayC`와 `arrayD`는 차수가 다르므로 동일한 형식이 아닙니다.  변수 `arrayD`와 `arrayE`는 `arrayD`가 아직 초기화되지는 않았지만 차수와 요소 형식이 같으므로 동일한 데이터 형식\(`Short(,)`\)입니다.  
  
 배열에 대한 자세한 내용은 [배열](../../../../visual-basic/programming-guide/language-features/arrays/index.md)을 참조하십시오.  
  
## 클래스 형식  
 모든 클래스를 포함하는 단일 데이터 형식은 없습니다.  한 클래스가 다른 클래스에서 상속할 수는 있지만 각 클래스는 개별 데이터 형식입니다.  같은 클래스의 여러 인스턴스는 동일한 데이터 형식입니다.  한 클래스 인스턴스의 변수를 다른 인스턴스에 할당하면 두 인스턴스는 데이터 형식이 동일할 뿐 아니라 메모리에서 동일한 클래스 인스턴스를 가리킵니다.  
  
 클래스에 대한 자세한 내용은 [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)를 참조하십시오.  
  
## 참고 항목  
 [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Visual Basic의 제네릭 형식](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Structures](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [How to: Hold More Than One Value in a Variable](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)