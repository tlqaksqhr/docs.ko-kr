---
title: "Of Clause (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "Of"
  - "vb.Of"
  - "vb.of"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Of keyword"
  - "arguments [Visual Basic], data types"
  - "constraints, Visual Basic generic types"
  - "generic parameters"
  - "generics [Visual Basic], constraints"
  - "parameters, type"
  - "types [Visual Basic], generic"
  - "parameters, generic"
  - "type parameters"
  - "data type arguments"
ms.assetid: 0db8f65c-65af-4089-ab7f-6fcfecb60444
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Of Clause (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

*제네릭* 클래스, 구조체, 인터페이스, 대리자 또는 프로시저에서 *형식 매개 변수*를 식별하는 `Of` 절을 정의합니다.  제네릭 형식에 대한 자세한 내용은 [Visual Basic의 제네릭 형식](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)을 참조하십시오.  
  
## Of 키워드 사용  
 다음 코드 예제에서는 `Of` 키워드를 사용하여 두 형식 매개 변수가 사용되는 클래스의 개요를 정의합니다.  <xref:System.IComparable> 인터페이스를 통해 `keyType` 매개 변수를 *제한*합니다. 즉, 사용하는 코드는 <xref:System.IComparable>을 구현하는 형식 인수를 제공해야 합니다.  이러한 작업은 `add` 프로시저에서 <xref:System.IComparable.CompareTo%2A?displayProperty=fullName> 메서드를 호출하는 데 필요합니다.  제약 조건에 대한 자세한 내용은 [Type List](../../../visual-basic/language-reference/statements/type-list.md)을 참조하십시오.  
  
```  
Public Class Dictionary(Of entryType, keyType As IComparable)  
    Public Sub add(ByVal e As entryType, ByVal k As keyType)  
        Dim dk As keyType  
        If k.CompareTo(dk) = 0 Then  
        End If  
    End Sub  
    Public Function find(ByVal k As keyType) As entryType  
    End Function  
End Class  
```  
  
 위의 클래스 정의를 완료한 경우 해당 클래스 정의로부터 다양한 `dictionary` 클래스를 생성할 수 있습니다.  `entryType` 및 `keyType`에 제공한 형식에 따라 클래스에 저장되는 항목의 형식과 각 항목에 연결되는 키의 형식이 결정됩니다.  이 제약 조건 때문에 `keyType`에 <xref:System.IComparable>을 구현하는 형식을 제공해야 합니다.  
  
 다음 코드 예제에서는 `String` 항목을 저장하고 `Integer` 키를 각 항목에 연결하는 개체를 만듭니다.  `Integer`는 <xref:System.IComparable>을 구현하므로 `keyType` 대한 제약 조건을 만족합니다.  
  
```  
Dim d As New dictionary(Of String, Integer)  
```  
  
 `Of` 키워드는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Class 문](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Delegate 문](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Interface 문](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Structure 문](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## 참고 항목  
 <xref:System.IComparable>   
 [Type List](../../../visual-basic/language-reference/statements/type-list.md)   
 [Visual Basic의 제네릭 형식](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)   
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)