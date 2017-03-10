---
title: "Object Variable Declaration (Visual Basic) | Microsoft Docs"
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
  - "early binding"
  - "declarations, class"
  - "classes [Visual Basic], declaring"
  - "binding, late and early"
  - "object variables, declaring"
  - "variables [Visual Basic], object"
  - "declaring variables, object variables"
  - "declaring classes"
  - "late binding"
ms.assetid: 2a5a41a3-1aa8-4236-b1f0-2382af7bf715
caps.latest.revision: 33
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 33
---
# Object Variable Declaration (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

개체 변수를 선언하는 데는 일반 선언문을 사용합니다.  데이터 형식에는 `Object`\([Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)\) 또는 개체를 만들 특정 클래스를 지정합니다.  
  
 변수를 `Object`로 선언하는 것은 변수를 <xref:System.Object?displayProperty=fullName>로 선언하는 것과 같습니다.  
  
 특정 개체 클래스를 사용하여 변수를 선언하면 이 변수는 해당 클래스와 해당 클래스가 상속하는 클래스에서 노출하는 모든 메서드와 속성에 액세스할 수 있습니다.  <xref:System.Object>를 사용하여 변수를 선언할 경우 런타임에 바인딩할 수 있도록 `Option Strict Off`로 설정하지 않으면 이 변수는 <xref:System.Object> 클래스의 멤버에만 액세스할 수 있습니다.  
  
## 선언 구문  
 다음 구문을 사용하여 개체 변수를 선언합니다.  
  
```  
Dim variablename As [New] { objectclass | Object }  
```  
  
 선언에 [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), `Protected Friend`, [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) 또는 [Static](../../../../visual-basic/language-reference/modifiers/static.md)을 지정할 수도 있습니다.  다음은 유효한 선언의 예입니다.  
  
```  
Private objA As Object  
Static objB As System.Windows.Forms.Label  
Dim objC As System.OperatingSystem  
```  
  
## 런타임에 바인딩 및 초기 바인딩  
 코드가 실행되기 전까지 클래스를 구체적으로 알 수 없는 경우가 있습니다.  이런 경우에는 `Object` 데이터 형식을 사용하여 개체 변수를 선언해야 합니다.  이렇게 하면 모든 개체 형식에 대한 일반적인 참조가 만들어지고 런타임에 특정 클래스가 할당됩니다.  이러한 방식을 *런타임에 바인딩*이라고 합니다.  런타임에 바인딩을 수행하려면 추가 실행 시간이 필요합니다.  또한 코드에서 액세스할 수 있는 항목은 가장 최근에 할당된 클래스의 메서드 및 속성으로 제한됩니다.  따라서 코드에서 다른 클래스의 멤버에 액세스하려고 하면 런타임 오류가 발생할 수 있습니다.  
  
 컴파일 타임에 클래스를 구체적으로 알고 있으면 해당 클래스로 개체 변수를 선언해야 합니다.  이러한 방식을 *초기 바인딩*이라고 합니다.  초기 바인딩을 사용하면 성능이 향상되고 코드에서 특정 클래스의 모든 메서드 및 속성에 액세스할 수 있습니다.  앞의 예제 선언에 있는 `objA` 변수가 <xref:System.Windows.Forms.Label?displayProperty=fullName> 클래스의 개체만 사용할 경우에는 선언에 `As System.Windows.Forms.Label`을 지정해야 합니다.  
  
### 초기 바인딩의 장점  
 개체 변수를 특정 클래스로 선언하면 다음과 같은 장점이 있습니다.  
  
-   자동 형식 검사  
  
-   특정 클래스의 모든 멤버에 대한 액세스 보장  
  
-   코드 편집기에서 Microsoft IntelliSense 지원  
  
-   코드의 가독성 향상  
  
-   코드 오류 감소  
  
-   런타임 대신 컴파일 타임에 오류 catch  
  
-   빠른 코드 실행  
  
## 개체 변수 멤버에 대한 액세스  
 `Option Strict`가 `On`으로 설정된 경우 개체 변수는 해당 변수가 선언된 클래스의 메서드 및 속성에만 액세스할 수 있습니다.  다음은 이에 대한 예입니다.  
  
```  
' Option statements must precede all other source file lines.  
Option Strict On  
' Imports statement must precede all declarations in the source file.  
Imports System.Windows.Forms  
Public Sub accessMembers()  
    Dim p As Object  
    Dim q As System.Windows.Forms.Label  
    p = New System.Windows.Forms.Label  
    q = New System.Windows.Forms.Label  
    Dim j, k As Integer  
    ' The following statement generates a compiler ERROR.  
    j = p.Left  
    ' The following statement retrieves the left edge of the label in pixels.  
    k = q.Left  
End Sub  
```  
  
 이 예제에서 `p`는 <xref:System.Object> 클래스 자체의 멤버만 사용할 수 있으므로 `Left` 속성을 포함하지 않습니다.  반면, <xref:System.Windows.Forms.Label> 형식으로 선언된 `q`는 <xref:System.Windows.Forms> 네임스페이스에 있는 <xref:System.Windows.Forms.Label> 클래스의 모든 메서드와 속성을 사용할 수 있습니다.  
  
## 개체 변수의 융통성  
 상속 계층 구조에서 개체를 사용하는 경우 개체 변수를 선언하는 데 사용할 클래스를 선택할 수 있습니다.  클래스를 선택하는 경우 개체를 할당할 때의 융통성과 클래스 멤버에 대한 액세스를 모두 고려해야 합니다.  예를 들어, <xref:System.Windows.Forms.Form?displayProperty=fullName> 클래스까지 이어지는 상속 계층 구조를 고려해 봅니다.  
  
 <xref:System.Object>  
  
 `` <xref:System.ComponentModel.Component>  
  
 `` <xref:System.Windows.Forms.Control>  
  
 `` <xref:System.Windows.Forms.ScrollableControl>  
  
 `` <xref:System.Windows.Forms.ContainerControl>  
  
 `` <xref:System.Windows.Forms.Form>  
  
 응용 프로그램이 <xref:System.Windows.Forms.Form> 클래스에서 상속하는 `specialForm`이라는 폼 클래스를 정의할 경우  다음 예제와 같이 참조 대상을 `specialForm`으로 지정하여 개체 변수를 선언할 수 있습니다.  
  
<CodeContentPlaceHolder>3</CodeContentPlaceHolder>  
 위 예제의 선언에서는 변수 `nextForm`을 `specialForm` 클래스의 개체로 제한하지만, `specialForm`의 모든 메서드 및 속성뿐 아니라 `specialForm`이 상속하는 모든 클래스의 모든 멤버도 `nextForm`에서 사용할 수 있도록 합니다.  
  
 다음 예제와 같이 개체 변수를 <xref:System.Windows.Forms.Form> 형식으로 선언하면 보다 일반적인 개체 변수를 만들 수 있습니다.  
  
<CodeContentPlaceHolder>4</CodeContentPlaceHolder>  
 이 예제와 같이 선언하면 응용 프로그램의 폼을 `anyForm`에 할당할 수 있습니다.  그러나 `anyForm`은 <xref:System.Windows.Forms.Form> 클래스의 모든 멤버에 액세스할 수 있지만 `specialForm`과 같은 특정 폼에 정의된 추가 메서드나 속성은 사용할 수 있습니다.  
  
 파생 클래스에서는 기본 클래스의 모든 멤버를 사용할 수 있지만 기본 클래스에서는 파생 클래스의 추가 멤버를 사용할 수 없습니다.  
  
## 참고 항목  
 [Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Object Variable Assignment](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)   
 [Object Variable Values](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)   
 [How to: Declare an Object Variable and Assign an Object to It in Visual Basic](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)   
 [How to: Access Members of an Object](../../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)   
 [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md)   
 [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)