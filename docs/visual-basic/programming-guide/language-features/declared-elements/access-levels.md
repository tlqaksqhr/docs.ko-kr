---
title: "Access Levels in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "members, accessing in Visual Basic"
  - "Friend access modifier"
  - "access levels, declared elements"
  - "access levels"
  - "access modifiers"
  - "Public access modifier"
  - "Protected access modifier"
  - "Protected Friend access modifier"
  - "Private access modifier"
  - "declared elements, access level"
ms.assetid: 6e06c1ab-fd78-47f0-83a8-1152780b5e1a
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Access Levels in Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

선언 요소의 *액세스 수준*은 해당 요소에 액세스할 수 있는 범위, 즉 해당 요소를 읽거나 쓸 수 있는 코드 범위를 나타냅니다.  액세스 수준은 요소 자체를 선언한 방법뿐만 아니라 해당 요소의 컨테이너에 대한 액세스 수준에 의해서도 결정됩니다.  포함하는 요소에 액세스할 수 없는 코드는 포함된 모든 요소에도 액세스할 수 없습니다. 이는 포함된 요소가 `Public`으로 선언된 경우에도 해당됩니다.  예를 들어, `Private` 구조체의 `Public` 변수는 해당 구조체를 포함하는 클래스 내에서는 액세스할 수 있지만 외부에서는 액세스할 수 없습니다.  
  
## Public  
 선언 문에서 [Public](../../../../visual-basic/language-reference/modifiers/public.md) 키워드로 선언된 요소는 같은 프로젝트의 코드, 해당 프로젝트를 참조하는 다른 프로젝트 및 해당 프로젝트에서 빌드된 어셈블리에서 액세스할 수 있습니다.  다음 코드는 `Public` 선언의 예입니다.  
  
```  
Public Class classForEverybody  
```  
  
 `Public` 키워드는 모듈, 인터페이스 또는 네임스페이스 수준에서만 사용할 수 있습니다.  즉, public 요소는 소스 파일 또는 네임스페이스의 수준이나 인터페이스, 모듈, 클래스 또는 구조체 내에서 선언할 수 있지만 프로시저에서는 선언할 수 없습니다.  
  
## Protected  
 선언 문에서 [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) 키워드로 선언된 요소는 같은 클래스 또는 해당 클래스에서 파생된 클래스에서만 액세스할 수 있습니다.  다음 코드는 `Protected` 선언의 예입니다.  
  
```  
Protected Class classForMyHeirs  
```  
  
 `Protected`는 클래스의 멤버를 선언할 때 클래스 수준에서만 사용할 수 있습니다.  즉, protected 요소는 클래스에서 선언할 수 있지만 소스 파일 또는 네임스페이스의 수준이나 인터페이스, 모듈, 구조체 또는 프로시저 내에서는 선언할 수 없습니다.  
  
## Friend  
 선언 문에서 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) 키워드로 선언된 요소는 같은 어셈블리 내에서만 액세스할 수 있고 어셈블리 외부에서는 액세스할 수 없습니다.  다음 코드는 `Friend` 선언의 예입니다.  
  
```  
Friend stringForThisProject As String  
```  
  
 `Friend` 키워드는 모듈, 인터페이스 또는 네임스페이스 수준에서만 사용할 수 있습니다.  즉, friend 요소는 소스 파일 또는 네임스페이스의 수준이나 인터페이스, 모듈, 클래스 또는 구조체 내에서 선언할 수 있지만 프로시저에서는 선언할 수 없습니다.  
  
## Protected Friend  
 선언 문에서 `Protected`와 `Friend` 키워드로 선언된 요소는 파생된 클래스나 같은 어셈블리 내에서 액세스할 수 있습니다.  다음 코드는 `Protected` `Friend` 선언의 예입니다.  
  
```  
Protected Friend stringForProjectAndHeirs As String  
```  
  
 `Protected` `Friend`는 클래스 수준에서, 클래스의 멤버를 선언할 때만 사용할 수 있습니다.  즉, protected friend 요소는 클래스에서 선언할 수 있지만 소스 파일 또는 네임스페이스의 수준이나 인터페이스, 모듈, 구조체 또는 프로시저 내에서는 선언할 수 없습니다.  
  
## Private  
 선언 문에서 [Private](../../../../visual-basic/language-reference/modifiers/private.md)으로 선언된 키워드는 같은 모듈, 클래스 또는 구조체 내에서만 액세스할 수 있습니다.  다음 코드는 `Private` 선언의 예입니다.  
  
```  
Private numberForMeOnly As Integer  
```  
  
 `Private` 키워드는 모듈 수준에서만 사용할 수 있습니다.  즉, private 요소는 모듈, 클래스 또는 구조체 내에서 선언할 수 있지만 소스 파일 또는 네임스페이스의 수준이나 인터페이스 또는 프로시저에서는 선언할 수 없습니다.  
  
 모듈 수준에서 액세스 수준 키워드가 지정되지 않은 `Dim` 문은 `Private` 선언과 동일합니다.  그러나 `Private` 키워드를 사용하면 더 쉽게 코드를 읽고 해석할 수 있습니다.  
  
## 액세스 한정자  
 액세스 수준을 지정하는 키워드를 *액세스 한정자*라고 합니다.  다음 표에서는 액세스 한정자를 비교합니다.  
  
|액세스 한정자|부여된 액세스 수준|이 액세스 수준으로 선언할 수 있는 요소|이 한정자를 사용할 수 있는 선언 컨텍스트|  
|-------------|----------------|----------------------------|-----------------------------|  
|`Public`|무제한:<br /><br /> public 요소를 볼 수 있는 모든 코드에서 액세스할 수 있음|인터페이스<br /><br /> 모듈<br /><br /> 클래스<br /><br /> 구조체<br /><br /> 구조체 멤버<br /><br /> 절차<br /><br /> 속성<br /><br /> 멤버 변수<br /><br /> 상수<br /><br /> 열거형<br /><br /> 이벤트<br /><br /> 외부 선언<br /><br /> 대리자|소스 파일<br /><br /> Namespace<br /><br /> Interface<br /><br /> 모듈<br /><br /> 클래스<br /><br /> 구조체|  
|`Protected`|파생:<br /><br /> protected 요소를 선언하는 클래스 또는 이 클래스에서 파생된 클래스의 코드에서 액세스할 수 있음|인터페이스<br /><br /> 클래스<br /><br /> 구조체<br /><br /> 절차<br /><br /> 속성<br /><br /> 멤버 변수<br /><br /> 상수<br /><br /> 열거형<br /><br /> 이벤트<br /><br /> 외부 선언<br /><br /> 대리자|클래스|  
|`Friend`|어셈블리:<br /><br /> friend 요소를 선언하는 어셈블리의 코드에서 액세스할 수 있음|인터페이스<br /><br /> 모듈<br /><br /> 클래스<br /><br /> 구조체<br /><br /> 구조체 멤버<br /><br /> 절차<br /><br /> 속성<br /><br /> 멤버 변수<br /><br /> 상수<br /><br /> 열거형<br /><br /> 이벤트<br /><br /> 외부 선언<br /><br /> 대리자|소스 파일<br /><br /> Namespace<br /><br /> Interface<br /><br /> 모듈<br /><br /> 클래스<br /><br /> 구조체|  
|`Protected` `Friend`|`Protected`와 `Friend`의 통합:<br /><br /> protected friend 요소와 동일한 클래스 또는 어셈블리 내의 코드나 해당 요소의 클래스에서 파생된 모든 클래스의 코드에서 액세스할 수 있음|인터페이스<br /><br /> 클래스<br /><br /> 구조체<br /><br /> 절차<br /><br /> 속성<br /><br /> 멤버 변수<br /><br /> 상수<br /><br /> 열거형<br /><br /> 이벤트<br /><br /> 외부 선언<br /><br /> 대리자|클래스|  
|`Private`|선언 컨텍스트:<br /><br /> private 요소를 선언하는 형식의 코드와 포함된 형식 내의 코드에서 액세스할 수 있음|인터페이스<br /><br /> 클래스<br /><br /> 구조체<br /><br /> 구조체 멤버<br /><br /> 절차<br /><br /> 속성<br /><br /> 멤버 변수<br /><br /> 상수<br /><br /> 열거형<br /><br /> 이벤트<br /><br /> 외부 선언<br /><br /> 대리자|모듈<br /><br /> 클래스<br /><br /> 구조체|  
  
## 참고 항목  
 [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)   
 [Static](../../../../visual-basic/language-reference/modifiers/static.md)   
 [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)   
 [Lifetime in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)   
 [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)   
 [How to: Control the Availability of a Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-availability-of-a-variable.md)   
 [Variables](../../../../visual-basic/reference/command-line-compiler/index.md)   
 [변수 선언](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)