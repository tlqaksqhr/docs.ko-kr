---
title: "Determining Object Type (Visual Basic) | Microsoft Docs"
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
  - "classes [Visual Basic], discovering which an object belongs to"
  - "types [Visual Basic], determining Visual Basic object types"
  - "object variables, testing values"
  - "TypeOf...Is expression, object type at run time"
  - "TypeName function"
  - "objects [Visual Basic], type determining"
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Determining Object Type (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

일반 개체 변수, 즉 `Object`로 선언하는 변수는 모든 클래스의 개체를 보유할 수 있습니다.  `Object` 형식의 변수를 사용할 경우 개체의 클래스에 따라 서로 다른 작업을 수행해야 할 수도 있습니다. 예를 들어, 일부 개체에서 특정 속성 또는 메서드를 지원하지 않을 수 있습니다.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 개체 변수에 어떤 형식의 개체가 저장되는지 확인할 수 있는 방법으로 `TypeName` 함수와 `TypeOf...Is` 연산자 두 가지를 제공합니다.  
  
## TypeName 및 TypeOf…Is  
 `TypeName` 함수는 문자열을 반환하며 다음 코드 조각과 같이 개체의 클래스 이름을 저장하거나 표시해야 할 때 사용됩니다.  
  
 [!code-vb[VbVbalrOOP#92](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_1.vb)]  
  
 `TypeOf...Is` 연산자는 `TypeName`을 사용한 동일 문자열 비교보다 수행 속도가 빠르므로 개체 형식을 테스트하는 데 가장 좋은 방법입니다.  다음은 `If...Then...Else` 문 내에 `TypeOf...Is`를 사용한 코드 조각입니다.  
  
 [!code-vb[VbVbalrOOP#93](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_2.vb)]  
  
 여기서 주의할 사항은  개체가 특정 형식이거나 특정 형식에서 파생된 경우 `TypeOf...Is` 연산자는 `True`를 반환한다는 것입니다.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 수행하는 거의 모든 작업에 개체가 사용되며, 개체에는 문자열 및 정수와 같이 일반적으로 개체로 간주되지 않는 요소도 포함됩니다.  이러한 개체는 <xref:System.Object>에서 파생되며 해당 메서드를 상속합니다.  `TypeOf...Is` 연산자는 `Integer`를 전달 받아 연산을 수행한 결과가 `Object`가 되면 `True`를 반환합니다.  다음 예제에서 매개 변수 `InParam`은 `Object`이면서 `Integer`입니다.  
  
 [!code-vb[VbVbalrOOP#94](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_3.vb)]  
  
 다음 예제에서는 `TypeOf...Is`와 `TypeName`을 모두 사용하여 `Ctrl` 인수에서 전달된 개체 형식을 확인합니다.  `TestObject` 프로시저는 서로 다른 세 가지 컨트롤을 사용하여 `ShowType`을 호출합니다.  
  
#### 예제를 실행하려면  
  
1.  Windows 응용 프로그램 프로젝트를 새로 만든 다음 <xref:System.Windows.Forms.Button> 컨트롤, <xref:System.Windows.Forms.CheckBox> 컨트롤 및 <xref:System.Windows.Forms.RadioButton> 컨트롤을 폼에 추가합니다.  
  
2.  폼의 단추에서 `TestObject` 프로시저를 호출합니다.  
  
3.  폼에 다음 코드를 추가합니다.  
  
     [!code-vb[VbVbalrOOP#95](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_4.vb)]  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Information.TypeName%2A>   
 [Calling a Property or Method Using a String Name](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md)   
 [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [If...Then...Else Statement](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)   
 [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md)   
 [Integer Data Type](../../../../visual-basic/language-reference/data-types/integer-data-type.md)