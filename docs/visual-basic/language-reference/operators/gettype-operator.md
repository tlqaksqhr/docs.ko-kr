---
title: "GetType Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.GetType"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "GetType operator"
  - "GetType keyword"
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# GetType Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

지정한 형식의 <xref:System.Type> 개체를 반환합니다.  <xref:System.Type> 개체는 해당 속성, 메서드 및 이벤트와 같은 형식에 대한 정보를 제공합니다.  
  
## 구문  
  
```  
GetType(typename)  
```  
  
#### 매개 변수  
  
|||  
|-|-|  
|Parameter|설명|  
|`typename`|정보가 필요한 형식의 이름입니다.|  
  
## 설명  
 `GetType` 연산자는 지정한 `typename`에 대한 <xref:System.Type> 개체를 반환합니다.  `typename`에 정의된 다음과 같은 형식의  예를 들면 다음과 같은 요소입니다.  
  
-   `Boolean` 또는 `Date` 같은 Visual Basic 데이터 형식  
  
-   <xref:System.ArgumentException?displayProperty=fullName> 또는 <xref:System.Double?displayProperty=fullName> 같은 .NET Framework 클래스, 구조체, 모듈 또는 인터페이스  
  
-   응용 프로그램에서 정의된 클래스, 구조체 모듈 또는 인터페이스  
  
-   응용 프로그램에서 정의된 배열  
  
-   응용 프로그램에서 정의된 대리자  
  
-   Visual Basic, .NET Framework 또는 응용 프로그램에서 정의된 열거형  
  
 개체 변수의 형식 개체를 가져오려면 <xref:System.Type.GetType%2A?displayProperty=fullName> 메서드를 사용하십시오.  
  
 다음과 같은 경우에 `GetType` 연산자를 사용하면 유용합니다.  
  
-   런타임에 형식에 대한 메타데이터에 액세스해야 하는 경우.  <xref:System.Type> 개체는 형식 멤버와 배포 정보 같은 메타데이터를 제공합니다.  이 메타데이터는 어셈블리에 리플렉션하는 경우 등에 필요합니다.  자세한 내용은 <xref:System.Reflection?displayProperty=fullName>를 참조하십시오.  
  
-   두 개체 참조를 비교하여 둘 다 동일한 형식의 인스턴스를 참조하는지 확인할 수 있습니다.  동일한 형식의 인스턴스를 참조할 경우 `GetType`은 동일한 <xref:System.Type> 개체에 대한 참조를 반환합니다.  
  
## 예제  
 다음 예제에서는 사용 중인 `GetType` 연산자를 보여 줍니다.  
  
 [!code-vb[VbVbalrOperators#26](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/gettype-operator_1.vb)]  
  
## 참고 항목  
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Operators and Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)