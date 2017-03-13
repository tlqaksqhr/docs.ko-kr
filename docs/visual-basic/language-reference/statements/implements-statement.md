---
title: "Implements Statement | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Implements"
  - "Implements"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Implements statement, syntax"
  - "Implements statement"
  - "interface implementation, Implements statement"
ms.assetid: 1fafb83f-f55a-4215-8ea9-681e8622613d
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Implements Statement
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

하나 이상의 인터페이스를 지정하거나, 해당 인터페이스가 있는 클래스 또는 구조체 정의에서 구현될 인터페이스 멤버를 지정합니다.  
  
## 구문  
  
```  
Implements interfacename [, ...]  
-or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## 요소  
 `interfacename`  
 필수 요소.  포함된 속성, 프로시저 및 이벤트가 클래스나 구조체의 해당 멤버에 의해 구현되는 인터페이스입니다.  
  
 `interfacemember`  
 필수 요소.  구현될 인터페이스의 멤버입니다.  
  
## 설명  
 인터페이스는 포함된 멤버\(속성, 프로시저, 이벤트\)를 나타내는 프로토타입의 컬렉션입니다.  인터페이스에는 멤버에 대한 선언만 포함되어 있으며, 클래스와 구조체는 이 멤버를 구현합니다.  자세한 내용은 [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)를 참조하십시오.  
  
 `Implements` 문이 `Class` 또는 `Structure` 문 바로 뒤에 있어야 합니다.  
  
 인터페이스를 구현하는 경우 해당 인터페이스에 선언된 모든 멤버를 구현해야 합니다.  멤버를 생략하면 구문 오류가 발생합니다.  개별 멤버를 구현하려면 클래스나 구조체에서 멤버를 선언할 때 [Implements](../../../visual-basic/language-reference/statements/implements-clause.md) 키워드를 `Implements` 문과 별도로 지정합니다.  자세한 내용은 [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)를 참조하십시오.  
  
 클래스는 속성과 프로시저를 [Private](../../../visual-basic/language-reference/modifiers/private.md)으로 구현할 수 있지만 구현하는 클래스의 인스턴스를 인터페이스의 형식으로 선언된 변수로 캐스팅해야 이들 멤버에 액세스할 수 있습니다.  
  
## 예제  
 다음 예제에서는 `Implements` 문을 사용하여 인터페이스의 멤버를 구현하는 방법을 보여 줍니다.  또한 이벤트, 속성 및 프로시저를 사용하여 `ICustomerInfo`라는 인터페이스를 정의합니다.  `customerInfo` 클래스는 인터페이스에 정의된 모든 멤버를 구현합니다.  
  
 [!code-vb[VbVbalrStatements#33](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_1.vb)]  
  
 `customerInfo` 클래스는 개별 소스 코드 줄에서 `Implements` 문을 사용하여 `ICustomerInfo` 인터페이스의 모든 멤버를 구현하는 클래스를 나타냅니다.  그러면 클래스의 각 멤버는 멤버 선언 과정에서 `Implements` 키워드를 사용하여 해당 인터페이스 멤버를 구현함을 나타냅니다.  
  
## 예제  
 다음 두 프로시저는 이전 예제에서 구현된 인터페이스를 사용하는 방법을 보여 줍니다.  구현을 테스트하려면 해당 프로젝트에 이러한 프로시저를 추가하고 `testImplements` 프로시저를 호출합니다.  
  
 [!code-vb[VbVbalrStatements#34](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_2.vb)]  
  
## 참고 항목  
 [Implements](../../../visual-basic/language-reference/statements/implements-clause.md)   
 [Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)