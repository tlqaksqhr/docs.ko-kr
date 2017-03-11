---
title: "Namespace Statement | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Namespace"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "namespaces, root"
  - "Namespace statement"
  - "namespaces, nested"
  - "declaring namespaces, syntax"
  - "namespaces, declaring"
  - "root namespaces"
  - "declarations, namespaces"
ms.assetid: a31fbd95-9ace-4c3d-bbb1-51222a2272b2
caps.latest.revision: 39
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 39
---
# Namespace Statement
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

네임스페이스 이름을 선언하고 선언 뒤에 오는 소스 코드가 해당 네임스페이스 내에서 컴파일되도록 합니다.  
  
## 구문  
  
```  
Namespace [Global.] { name | name.name }  
    [ componenttypes ]  
End Namespace  
```  
  
## 요소  
 Global  
 선택적 요소.  프로젝트의 루트 네임 스페이스의 네임 스페이스를 정의할 수 있습니다.  자세한 내용은 [Visual Basic의 네임스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md)를 참조하십시오.  
  
 `name`  
 필수 요소.  네임스페이스를 식별하는 고유 이름입니다.  올바른 Visual Basic 식별자여야 합니다.  자세한 내용은 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)를 참조하십시오.  
  
 `componenttypes`  
 선택적 요소.  네임스페이스를 구성하는 요소입니다.  작업이 있지만 열거형, 구조체, 인터페이스, 클래스, 모듈, 대리자 및 다른 네임 스페이스를 제한 되지 않습니다.  
  
 `End Namespace`  
 `Namespace` 블록을 끝냅니다.  
  
## 설명  
 네임스페이스는 구성 체계로 사용됩니다.  네임스페이스는 다른 프로그램 및 응용 프로그램에 노출된 프로그래밍 요소를 분류 및 표시하는 방법을 제공합니다.  네임 스페이스를 하지 않습니다는  *형식* 클래스 또는 구조체와 같은 의미에서\-데이터 형식 네임 스페이스에 프로그래밍 요소를 선언할 수 없습니다.  
  
 `Namespace` 문 뒤에 오는 모든 선언된 프로그래밍 요소는 해당 네임스페이스에 속합니다.  Visual Basic에서는 마지막으로 선언된 네임스페이스가 `End Namespace` 문 또는 `Namespace` 문을 만날 때까지 마지막으로 선언된 네임스페이스로 요소를 컴파일합니다.  
  
 프로젝트 외부에서도 네임스페이스가 이미 정의되어 있는 경우 해당 네임스페이스에 프로그래밍 요소를 추가할 수 있습니다.  이 작업을 수행할 수는 `Namespace` 해당 네임 스페이스에 요소를 컴파일하려면 Visual Basic 문의 합니다.  
  
 `Namespace` 문은 파일 또는 네임스페이스 수준에서만 사용할 수 있습니다.  즉, 네임스페이스에 대한 *선언 컨텍스트*는 소스 파일 또는 다른 네임스페이스이어야 하며 클래스, 구조체, 모듈, 인터페이스 또는 프로시저일 수 없습니다.  자세한 내용은 [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하십시오.  
  
 네임스페이스 내에 다른 네임스페이스 한 개를 선언할 수 있습니다.  선언 가능한 중첩 수준에 대한 엄격한 제한은 없지만, 다른 코드에서 가장 안쪽에 있는 네임스페이스에서 선언된 요소에 액세스하는 경우 이 코드에서는 중첩 계층의 모든 네임스페이스 이름을 포함하는 한정 문자열을 사용해야 합니다.  
  
## 액세스 수준  
 가 있는 경우에 네임 스페이스 처리는 `Public` 액세스 수준입니다.  네임스페이스는 같은 프로젝트 내의 임의의 위치에 있는 코드, 해당 프로젝트를 참조하는 다른 프로젝트 및 해당 프로젝트에서 빌드된 어셈블리에서 액세스할 수 있습니다.  
  
 다른 요소의 내부가 아닌 네임스페이스 내부를 의미하는 네임스페이스 수준에서 선언된 프로그래밍 요소는 `Public` 또는 `Friend` 액세스를 가질 수 있습니다.  이러한 요소의 액세스 수준에는 별도로 지정하지 않은 경우 기본적으로 `Friend`가 사용됩니다.  네임스페이스 수준에서 선언할 수 있는 요소에는 클래스, 구조체, 모듈, 인터페이스, 열거형 및 대리자가 있습니다.  자세한 내용은 [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하십시오.  
  
## 루트 네임 스페이스  
 프로젝트의 모든 네임스페이스 이름은 *루트 네임스페이스*를 기반으로 합니다.  Visual Studio에서는 프로젝트 이름을 프로젝트의 모든 코드에 대한 기본 루트 네임스페이스로 할당합니다.  예를 들어, 프로젝트 이름이 `Payroll`인 경우 프로젝트의 프로그래밍 요소는 `Payroll` 네임스페이스에 속합니다.  `Namespace funding`을 선언하는 경우 해당 네임스페이스의 전체 이름은 `Payroll.funding`입니다.  
  
 제네릭 목록 클래스 예제와 같이 `Namespace` 문의 기존 네임스페이스를 지정하려면 루트 네임스페이스를 null 값으로 설정합니다.  이렇게 하려면 **프로젝트** 메뉴에서 **프로젝트 속성**을 클릭한 다음 **루트 네임스페이스** 항목을 제거하여 상자가 비어 있도록 합니다.  제네릭 목록 클래스 예제에서 이렇게 하지 않은 경우 Visual Basic 컴파일러는 `Payroll` 프로젝트 내에서 `System.Collections.Generic`을 새 네임스페이스로 사용하며 전체 이름은 `Payroll.System.Collections.Generic`입니다.  
  
 또는 `Global` 키워드를 사용하여 프로젝트 외부에서 정의된 네임스페이스의 요소를 참조할 수도 있습니다.  이렇게 하면 프로젝트 이름을 루트 네임스페이스로 유지할 수 있습니다.  그러면 본의 아니게 프로그래밍 요소를 기존 네임스페이스 요소와 병합할 가능성을 줄일 수 있습니다.  자세한 내용은 "글로벌 키워드에 완전 하 게 정규화 된 이름이" 섹션에서 [Visual Basic의 네임스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md).  
  
 `Global` 키워드 네임 스페이스 문에서 사용할 수 있습니다.  이 프로젝트의 루트 네임 스페이스의 네임 스페이스를 정의할 수 있습니다.  자세한 내용은 "글로벌 키워드에서 네임 스페이스 문" 섹션에서 [Visual Basic의 네임스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md).  
  
 **문제를 해결 합니다.** 루트 네임스페이스에서 예기치 않게 네임스페이스 이름을 연결할 수 있습니다.  프로젝트 외부에서 정의된 네임스페이스를 참조하는 경우 Visual Basic 컴파일러는 해당 네임스페이스를 루트 네임스페이스 내에서 중첩된 네임스페이스로 해석할 수 있습니다.  이러한 경우 컴파일러는 외부 네임스페이스에서 이미 정의된 형식을 인식하지 않습니다.  이 문제를 방지 하려면 루트 네임 스페이스를 "루트 네임 스페이스"에서 설명한 null 값으로 설정 하거나 사용을 `Global` 키워드 외부 네임 스페이스의 요소에 액세스 합니다.  
  
## 특성 및 한정자  
 특성을 네임스페이스에 적용할 수 없습니다.  특성은 정보를 어셈블리 메타데이터에 제공하므로 네임스페이스와 같은 소스 분류자에는 의미가 없습니다.  
  
 네임스페이스에는 액세스 한정자나 프로시저 한정자 또는 다른 한정자를 적용할 수 없습니다.  네임스페이스는 형식이 아니므로 이러한 한정자는 의미가 없습니다.  
  
## 예제  
 다음 예제에서는 네임스페이스 내에서 다른 네임스페이스 하나가 중첩되는 두 개의 네임스페이스를 선언합니다.  
  
 [!code-vb[VbVbalrStatements#43](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/namespace-statement_1.vb)]  
  
## 예제  
 다음 예제에서는 한 줄에 여러 개의 중첩된 네임스페이스를 선언하며 앞의 예제와 동일합니다.  
  
 [!code-vb[VbVbalrStatements#41](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/namespace-statement_2.vb)]  
  
## 예제  
 다음 예제에서는 앞의 예제에서 정의한 클래스에 액세스합니다.  
  
 [!code-vb[VbVbalrStatements#42](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/namespace-statement_3.vb)]  
  
## 예제  
 다음 예제에서는 새 제네릭 목록 클래스의 구조를 정의하여 <xref:System.Collections.Generic?displayProperty=fullName> 네임스페이스에 추가합니다.  
  
```vb  
Namespace System.Collections.Generic  
    Class specialSortedList(Of T)  
        Inherits List(Of T)  
        ' Insert code to define the special generic list class.  
    End Class  
End Namespace  
```  
  
## 참고 항목  
 [Imports Statement \(.NET Namespace and Type\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Visual Basic의 네임스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md)