---
title: "Friend(Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Friend"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Friend 키워드"
  - "Friend 액세스 한정자"
  - "Friend 키워드, 구문"
  - "Protected Friend 키워드 조합"
  - "Friend 키워드, Protected"
ms.assetid: b664605e-1c79-4728-b996-aa59c50846bc
caps.latest.revision: 25
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 25
---
# Friend(Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

프로그래밍 요소를 선언한 어셈블리에서만 해당 프로그래밍 요소를 하나 이상 액세스할 수 있도록 지정합니다.  
  
## 설명  
 클래스와 구조체 같은 프로그래밍 요소를 해당 요소가 선언된 구성 요소만이 아닌 전체 어셈블리에서 사용하도록 해야 하는 경우가 많습니다.  그러나 \(예를 들어, 응용 프로그램 소유 경우\) 어셈블리 외부의 코드에서 사용할 수 할 수 있습니다지 않습니다.  이러한 방식으로 요소에 대 한 액세스를 제한 하려는 경우 사용 하 여 선언할 수 있는 `Friend` 한정자입니다.  
  
 같은 어셈블리로 컴파일되는 서로 다른 클래스, 구조체 및 모듈의 코드에서 해당 어셈블리의 모든 `Friend` 요소에 액세스할 수 있습니다.  
  
 `Friend`access 응용 프로그램의 프로그래밍 요소에 대 한 기본 설정된 수준인 경우가 및 `Friend` 는 기본 액세스 인터페이스, 모듈, 클래스 또는 구조체 수준입니다.  
  
 사용 하면 `Friend` 모듈, 인터페이스 또는 네임 스페이스 수준에서만.  따라서 대 한 선언 컨텍스트는 `Friend` 소스 파일, 네임 스페이스, 인터페이스, 모듈, 클래스 또는 구조체; 있어야 이 프로시저일 수는 없습니다.  
  
 하나의 선언에서 `Friend` 한정자를 [Protected](../../../visual-basic/language-reference/modifiers/protected.md) 한정자와 함께 사용할 수 있습니다.  이 조합은 둘 다 마시면 `Friend` 및 자체 클래스에서 및 파생된 클래스는 동일한 어셈블리의 모든 위치에서 액세스할 수 있으므로 선언 된 요소에 보호 된 액세스 합니다.  클래스의 멤버에만 `Protected Friend`를 지정할 수 있습니다.  
  
 비교 `Friend` 및 액세스 한정자를 참조 하십시오 기타 [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
> [!NOTE]
>  다른 어셈블리의 모든 형식 및로 표시 된 멤버에 액세스할 수 있도록 하는 friend 어셈블리 지를 지정할 수 있습니다 `Friend`.  자세한 내용은 [Friend 어셈블리](../Topic/Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)을 참조하십시오.  
  
## 예제  
 다음 클래스는 `Friend` 한정자를 사용하여 동일한 어셈블리 내의 다른 프로그래밍 요소가 특정 멤버에 액세스할 수 있도록 합니다.  
  
 [!code-vb[VbVbalrAccessModifiers#1](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/friend_1.vb)]  
  
## 용도  
 사용할 수 있는 `Friend` 이러한 컨텍스트 한정자:  
  
 [Class 문](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Const 문](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Delegate 문](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Enum 문](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Interface 문](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Module 문](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Structure 문](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## 참고 항목  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>   
 [Public](../../../visual-basic/language-reference/modifiers/public.md)   
 [Protected](../../../visual-basic/language-reference/modifiers/protected.md)   
 [Private](../../../visual-basic/language-reference/modifiers/private.md)   
 [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Procedures](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Structures](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)