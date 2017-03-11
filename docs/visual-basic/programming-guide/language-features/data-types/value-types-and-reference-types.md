---
title: "Value Types and Reference Types | Microsoft Docs"
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
  - "reference data types"
  - "reference types"
  - "value types"
  - "value data types"
  - "types [Visual Basic]"
  - "data types [Visual Basic], value types"
  - "data types [Visual Basic], reference types"
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Value Types and Reference Types
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Visual Basic 자신의 등급을 기준으로 데이터 형식 구현 됩니다.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 데이터 형식은 특정 형식의 변수가 자신의 데이터를 저장하는지 또는 데이터에 대한 포인터를 저장하는지에 따라 분류할 수 있습니다.  데이터 형식이 자신의 데이터를 저장하는 경우에는 *값 형식*이고 데이터에 대한 포인터를 메모리에 저장하는 경우에는 *참조 형식*입니다.  
  
## 값 형식  
 *값 형식*은 자신의 메모리 할당 영역에 데이터를 가지는 데이터 형식입니다.  값 형식에는 다음 항목이 포함됩니다.  
  
-   모든 숫자 데이터 형식  
  
-   `Boolean`, `Char` 및 `Date`  
  
-   모든 구조체\(구조체의 멤버가 참조 형식인 경우도 포함\)  
  
-   열거형\(내부 형식이 항상 `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger` 또는 `ULong`이기 때문\)  
  
 참조 형식 멤버를 포함 하는 경우에 모든 구조체는 값 형식입니다.  이러한 이유로, 값 형식 등 `Char` 및 `Integer` 에 의해 구현 됩니다.NET Framework 구조체입니다.  
  
 `Decimal` 등의 예약 키워드를 사용하여 값 형식을 선언할 수 있습니다.  `New` 키워드를 사용하여 값 형식을 초기화할 수도 있습니다.  이 기능은 형식이 매개 변수를 가진 생성자인 경우에 특히 유용합니다.  이러한 예로는 지정된 부분에서 새 `Decimal` 값을 만드는 <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> 생성자가 있습니다.  
  
## 참조 형식  
 *참조 형식*은 데이터가 저장된 다른 메모리 위치에 대한 포인터를 가집니다.  참조 형식에는 다음 항목이 포함됩니다.  
  
-   `String`  
  
-   배열의 요소가 값 형식인 경우까지 포함한 모든 배열  
  
-   클래스 형식\(예: <xref:System.Windows.Forms.Form>\)  
  
-   대리자  
  
 클래스는 *참조 형식*입니다.  따라서 `Object` 및 `String`과 같은 참조 형식이 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)] 클래스에서 지원됩니다.  모든 배열은 해당 멤버가 값 형식인 경우에도 항상 참조 형식입니다.  
  
 모든 참조 형식은 내부 있기 때문입니다.NET Framework 클래스를 사용 해야 해당 [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) 초기화할 때는 키워드입니다.  다음 문은 배열을 초기화합니다.  
  
```  
Dim totals() As Single = New Single(8) {}  
```  
  
## 형식이 아닌 요소  
 다음 프로그래밍 요소는 선언된 요소의 데이터 형식으로 지정할 수 없으므로 형식이 될 수 없습니다.  
  
-   네임스페이스  
  
-   모듈  
  
-   이벤트  
  
-   속성 및 프로시저  
  
-   변수, 상수 및 필드  
  
## Object 데이터 형식에 대한 작업  
 참조 형식이나 값 형식을 `Object` 데이터 형식의 변수에 할당할 수 있습니다.  `Object` 변수는 항상 데이터 자체를 가지는 것이 아니라 데이터에 대한 포인터를 가집니다.  그러나 값 형식을 `Object` 변수에 할당할 경우 이 변수는 자체 데이터를 가지는 것처럼 동작합니다.  자세한 내용은 [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)을 참조하십시오.  
  
 있는지 찾을 수 있습니다는 `Object` 변수는 역할 참조 형식 또는 값 형식에 전달 하 여는 <xref:Microsoft.VisualBasic.Information.IsReference%2A> 메서드에서 <xref:Microsoft.VisualBasic.Information> 클래스의의 <xref:Microsoft.VisualBasic?displayProperty=fullName> 네임 스페이스.  <xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=fullName>는 `Object` 변수의 내용이 참조 형식을 나타낼 경우 `True`를 반환합니다.  
  
## 참고 항목  
 [Nullable Value Types](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)   
 [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Efficient Use of Data Types](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)   
 [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)