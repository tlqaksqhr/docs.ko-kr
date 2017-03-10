---
title: "How to: Determine What Type an Object Variable Refers To (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "TypeOf operator [Visual Basic], determining object variable type"
  - "variables [Visual Basic], object"
  - "object variables, determining type"
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# How to: Determine What Type an Object Variable Refers To (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

개체 변수에는 다른 위치에 저장된 데이터에 대한 포인터가 들어 있습니다.  해당 데이터의 형식은 런타임 동안 변경될 수 있습니다.  언제든지 <xref:System.Type.GetTypeCode%2A> 메서드를 사용하여 현재 런타임 형식을 확인하거나, [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md)를 사용하여 현재 런타임 형식이 지정된 형식과 호환되는지 여부를 확인할 수 있습니다.  
  
### 개체 변수가 현재 참조하고 있는 정확한 형식을 확인하려면  
  
1.  개체 변수에 대해 <xref:System.Object.GetType%2A> 메서드를 호출하여 <xref:System.Type?displayProperty=fullName> 개체를 가져옵니다.  
  
    ```  
    Dim myObject As Object  
    myObject.GetType()  
    ```  
  
2.  <xref:System.Type?displayProperty=fullName> 클래스에서 공유 메서드 <xref:System.Type.GetTypeCode%2A> 메서드를 호출하여 개체 형식에 대한 <xref:System.TypeCode> 열거형 값을 가져옵니다.  
  
    ```  
    Dim myObject As Object  
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())  
    MsgBox("myObject currently has type code " & CStr(datTyp))  
    ```  
  
     `Double` 등의 원하는 모든 열거형 멤버에 대해 <xref:System.TypeCode> 열거형 값을 테스트할 수 있습니다.  
  
### 개체 변수 형식이 지정된 형식과 호환되는지 확인하려면  
  
-   `TypeOf` 연산자와 [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md)를 함께 사용하여 `TypeOf`...`Is` 식으로 개체를 테스트합니다.  
  
    ```  
    If TypeOf objA Is System.Windows.Forms.Control Then  
        MsgBox("objA is compatible with the Control class")  
    End If  
    ```  
  
     `TypeOf`...`Is` 식은 개체의 런타임 형식이 지정된 형식과 호환되는 경우 `True`를 반환합니다.  
  
     호환성 기준은 지정된 형식이 클래스, 구조체 또는 인터페이스 중 무엇인지에 따라 달라집니다.  일반적으로 개체가 지정된 형식과 동일한 형식이거나 지정된 형식에서 상속되거나 지정된 형식을 구현하면 해당 개체의 형식은 호환된다고 합니다.  자세한 내용은 [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md)를 참조하십시오.  
  
## 코드 컴파일  
 지정된 형식은 변수나 식일 수 없으며,  클래스, 구조체 또는 인터페이스 같이 정의된 형식의 이름이어야 합니다.  여기에는 `Integer` 및 `String` 등의 내장 형식이 포함됩니다.  
  
## 참고 항목  
 <xref:System.Object.GetType%2A>   
 <xref:System.Type?displayProperty=fullName>   
 <xref:System.Type.GetTypeCode%2A>   
 <xref:System.TypeCode>   
 [Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Object Variable Values](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)   
 [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)