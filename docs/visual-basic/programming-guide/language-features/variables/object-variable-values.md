---
title: "Object Variable Values (Visual Basic) | Microsoft Docs"
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
  - "object variables, values"
  - "values, of object variables"
  - "data types [Visual Basic], object variable"
  - "variables [Visual Basic], object"
ms.assetid: 31555704-58a3-49f1-9a0a-6421f605664f
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Object Variable Values (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

[Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)의 변수는 모든 형식의 데이터를 참조할 수 있습니다.  `Object` 변수에 저장되는 값은 메모리의 특정 위치에 보관되며 변수는 데이터에 대한 포인터를 유지합니다.  
  
## 개체 분류자 함수  
 다음 표에 표시된 것처럼 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 `Object` 변수가 참조하는 내용에 대한 정보를 반환하는 함수를 제공합니다.  
  
|Function|개체 변수가 참조하면 True가 반환되는 항목|  
|--------------|-------------------------------|  
|<xref:Microsoft.VisualBasic.Information.IsArray%2A>|단일 값이 아닌 값의 배열|  
|<xref:Microsoft.VisualBasic.Information.IsDate%2A>|[Date Data Type](../../../../visual-basic/language-reference/data-types/date-data-type.md) 값, 또는 날짜 및 시간 값으로 해석할 수 있는 문자열|  
|<xref:Microsoft.VisualBasic.Information.IsDBNull%2A>|없거나 존재하지 않는 데이터를 나타내는 <xref:System.DBNull> 형식의 개체|  
|<xref:Microsoft.VisualBasic.Information.IsError%2A>|<xref:System.Exception>에서 파생된 예외 개체|  
|<xref:Microsoft.VisualBasic.Information.IsNothing%2A>|[Nothing](../../../../visual-basic/language-reference/nothing.md)\(변수에 현재 할당된 개체가 없음을 의미\)|  
|<xref:Microsoft.VisualBasic.Information.IsNumeric%2A>|숫자, 또는 숫자로 해석할 수 있는 문자열|  
|<xref:Microsoft.VisualBasic.Information.IsReference%2A>|참조 형식\(예: 문자열, 배열, 대리자 또는 클래스 형식\)|  
  
 이러한 함수를 사용하면 연산이나 프로시저에 잘못된 값을 전달하는 것을 피할 수 있습니다.  
  
## TypeOf 연산자  
 또한 [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md)를 사용하여 개체 변수가 현재 특정 데이터 형식을 참조하고 있는지 여부를 확인할 수 있습니다.  피연산자의 런타임 형식이 지정된 형식에서 파생되거나 지정된 형식을 구현하는 경우 `TypeOf`...`Is` 식의 값은 `True`가 됩니다.  
  
 다음 예제에서는 값 및 참조 형식을 참조하는 개체 변수에 `TypeOf`가 사용됩니다.  
  
```  
' The following statement puts a value type (Integer) in an Object variable.  
Dim num As Object = 10  
' The following statement puts a reference type (Form) in an Object variable.  
Dim frm As Object = New Form()  
If TypeOf num Is Long Then Debug.WriteLine("num is Long")  
If TypeOf num Is Integer Then Debug.WriteLine("num is Integer")  
If TypeOf num Is Short Then Debug.WriteLine("num is Short")  
If TypeOf num Is Object Then Debug.WriteLine("num is Object")  
If TypeOf frm Is Form Then Debug.WriteLine("frm is Form")  
If TypeOf frm Is Label Then Debug.WriteLine("frm is Label")  
If TypeOf frm Is Object Then Debug.WriteLine("frm is Object")  
```  
  
 위 예제의 결과로 **디버그** 창에 다음 줄이 표시됩니다.  
  
 `num is Integer`  
  
 `num is Object`  
  
 `frm is Form`  
  
 `frm is Object`  
  
 개체 변수 `num`은 `Integer` 형식의 데이터를 참조하며 `frm`은 <xref:System.Windows.Forms.Form> 클래스의 개체를 참조합니다.  
  
## 개체 배열  
 또한 `Object` 변수의 배열을 선언하고 사용할 수 있습니다.  이렇게 하면 다양한 데이터 형식과 개체 클래스를 처리할 수 있습니다.  배열의 모든 요소에는 동일한 데이터 형식을 선언해야 합니다.  데이터 형식을 `Object`로 선언하면 개체와 클래스 인스턴스를 배열의 다른 데이터 형식과 함께 저장할 수 있습니다.  
  
## 참고 항목  
 [Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Object Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)   
 [Object Variable Assignment](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)   
 [How to: Refer to the Current Instance of an Object](../../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)   
 [How to: Determine What Type an Object Variable Refers To](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md)   
 [How to: Determine Whether Two Objects Are Related](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)   
 [How to: Determine Whether Two Objects Are Identical](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)   
 [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)