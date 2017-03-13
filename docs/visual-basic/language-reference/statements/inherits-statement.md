---
title: "Inherits Statement | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Inherits"
  - "Inherits"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Inherits statement"
  - "Inherits statement, syntax"
ms.assetid: 9e6fe042-9af3-4341-8093-fc3537770cf2
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Inherits Statement
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

현재 클래스나 인터페이스가 다른 클래스나 인터페이스 집합에서 특성, 변수, 속성, 프로시저 및 이벤트를 상속하도록 합니다.  
  
## 구문  
  
```  
Inherits basetypenames  
```  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`basetypenames`|필수 요소.  이 클래스가 파생되는 클래스의 이름입니다.<br /><br /> 또는<br /><br /> 이 인터페이스가 파생되는 인터페이스의 이름입니다.  여러 이름을 구분하려면 쉼표를 사용합니다.|  
  
## 설명  
 `Inherits` 문을 사용하는 경우 이 문은 클래스 또는 인터페이스 정의에서 공백 또는 주석이 없는 첫 번째 줄이어야 합니다.  또한 `Class` 문이나 `Interface` 문 바로 다음에 나와야 합니다.  
  
 `Inherits`는 클래스나 인터페이스에만 사용할 수 있습니다.  즉, 상속의 선언 컨텍스트는 소스 파일, 네임스페이스, 구조체, 모듈, 프로시저 또는 블록일 수 없습니다.  
  
## 규칙  
  
-   **클래스 상속.** 클래스가 `Inherits` 문을 사용하는 경우에는 하나의 기본 클래스만 지정할 수 있습니다.  
  
     클래스는 해당 클래스 내에 중첩된 클래스에서 상속될 수 없습니다.  
  
-   **인터페이스 상속.** 인터페이스가 `Inherits` 문을 사용하는 경우 하나 이상의 기본 인터페이스를 지정할 수 있습니다.  두 인터페이스가 동일한 이름의 멤버를 각각 정의해도 이러한 두 인터페이스에서 상속할 수 있습니다.  상속할 경우 구현하는 코드는 이름 한정을 사용하여 구현하는 멤버를 지정해야 합니다.  
  
     인터페이스는 액세스 수준이 보다 제한적인 다른 인터페이스에서 상속할 수 없습니다.  예를 들어 `Public` 인터페이스는 `Friend` 인터페이스에서 상속할 수 없습니다.  
  
     인터페이스는 해당 인터페이스 내에 중첩된 인터페이스에서 상속할 수 없습니다.  
  
 .NET Framework 클래스 상속의 예로 <xref:System.SystemException> 클래스에서 상속하는 <xref:System.ArgumentException> 클래스를 들 수 있습니다.  이 클래스는 <xref:System.Exception.Message%2A> 속성 및 <xref:System.Exception.ToString%2A> 메서드와 같이 시스템 예외에 필요한 미리 정의된 모든 속성과 프로시저를 <xref:System.ArgumentException>에 제공합니다.  
  
 .NET Framework 인터페이스 상속의 예로 <xref:System.Collections.IEnumerable> 인터페이스에서 상속하는 <xref:System.Collections.ICollection> 인터페이스를 들 수 있습니다.  이 인터페이스는 <xref:System.Collections.ICollection>이 컬렉션을 이동하는 데 필요한 열거자 정의를 상속하도록 합니다.  
  
## 예제  
 다음 예제에서는 `Inherits` 문을 사용하여 `thisClass`라는 클래스가 `anotherClass`라는 기본 클래스의 모든 멤버를 상속하는 방법을 보여 줍니다.  
  
 [!code-vb[VbVbalrStatements#37](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/inherits-statement_1.vb)]  
  
## 예제  
 다음 예제에서는 여러 인스턴스의 상속을 보여 줍니다.  
  
 [!code-vb[VbVbalrStatements#38](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/inherits-statement_2.vb)]  
  
 `thisInterface`라는 인터페이스는 이제 <xref:System.IComparable>, <xref:System.IDisposable> 및 <xref:System.IFormattable> 인터페이스의 모든 정의를 포함합니다. 상속된 멤버는 두 개체의 형식 관련 비교를 각각 제공하여 할당된 리소스를 해제하고 개체의 값을 `String`으로 나타냅니다.  `thisInterface`를 구현하는 클래스는 모든 기본 인터페이스의 모든 멤버를 구현해야 합니다.  
  
## 참고 항목  
 [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)   
 [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)   
 [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)   
 [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)