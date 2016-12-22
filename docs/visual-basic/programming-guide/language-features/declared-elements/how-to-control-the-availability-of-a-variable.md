---
title: "How to: Control the Availability of a Variable (Visual Basic) | Microsoft Docs"
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
  - "access levels, declared elements"
  - "Private keyword, accessing variables"
  - "access levels, variables"
  - "Public keyword, accessing variables"
  - "Friend keyword, accessing variables"
  - "variables [Visual Basic], access level"
  - "declared elements, access level"
  - "Protected keyword, accessing variables"
ms.assetid: eaf4f073-7922-43ce-ae1e-90ff376ae947
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Control the Availability of a Variable (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

*액세스 수준*을 지정하여 변수의 사용 가능성을 제어할 수 있습니다.  액세스 수준에 따라 변수를 읽거나 쓸 수 있는 권한이 있는 코드가 결정됩니다.  
  
-   모듈 수준 및 프로시저 외부에 정의된 *멤버 변수*의 기본 액세스 수준은 Public입니다. 즉, 해당 변수를 볼 수 있는 모든 코드에서 액세스할 수 있습니다.  액세스 한정자를 지정하여 이를 변경할 수 있습니다.  
  
-   프로시저 내에 정의된 *지역 변수*의 액세스 수준도 일반적으로 Public이지만 해당 프로시저 내의 코드에서만 액세스할 수 있습니다.  지역 변수의 액세스 수준은 변경할 수 없지만 지역 변수가 포함된 프로시저의 액세스 수준은 변경할 수 있습니다.  
  
 자세한 내용은 [Access Levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조하십시오.  
  
## Private 및 Public 액세스 수준  
  
#### 변수를 모듈, 클래스 또는 구조체 내에서만 액세스할 수 있도록 하려면  
  
1.  모듈, 클래스 또는 구조체 내에서 모든 프로시저의 바깥쪽 위치에 변수에 대한 [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)을 넣습니다.  
  
2.  `Dim` 문에 [Private](../../../../visual-basic/language-reference/modifiers/private.md) 키워드를 포함시킵니다.  
  
     이렇게 하면 변수 읽기 또는 쓰기가 해당 모듈, 클래스 또는 구조체 내에서만 가능하고 외부에서는 가능하지 않습니다.  
  
#### 변수를 볼 수 있는 모든 코드에서 액세스할 수 있도록 하려면  
  
1.  멤버 변수의 경우, 모듈, 클래스 또는 구조체 내에서 모든 프로시저의 바깥쪽 위치에 변수에 대한 `Dim` 문을 넣습니다.  
  
2.  `Dim` 문에 [Public](../../../../visual-basic/language-reference/modifiers/public.md) 키워드를 포함시킵니다.  
  
     이렇게 하면 해당 어셈블리와 상호 작용하는 모든 코드에서 변수를 읽고 쓸 수 있습니다.  
  
 또는  
  
1.  지역 변수의 경우, 프로시저 내에 변수에 대한 `Dim` 문을 넣습니다.  
  
2.  `Dim` 문에 `Public` 키워드를 포함하지 않습니다.  
  
     이렇게 하면 변수 읽기 또는 쓰기가 해당 프로시저 내에서만 가능하고 외부에서는 가능하지 않습니다.  
  
## Protected 및 Friend 액세스 수준  
 변수의 액세스 수준을 해당 클래스와 모든 파생 클래스 또는 어셈블리로 제한할 수 있습니다.  이러한 제한을 여러 개 결합할 수도 있습니다. 이렇게 하면 동일한 어셈블리의 파생 클래스나 다른 위치에 있는 코드에서 변수에 액세스할 수 있습니다.  동일한 선언에 `Protected` 키워드와 `Friend` 키워드를 모두 사용하여 이 제한 조합을 지정합니다.  
  
#### 변수를 해당 클래스와 모든 파생 클래스 내에서만 액세스할 수 있도록 하려면  
  
1.  클래스 내에서 모든 프로시저의 바깥쪽 위치에 변수에 대한 `Dim` 문을 넣습니다.  
  
2.  `Dim` 문에 [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) 키워드를 포함시킵니다.  
  
     이렇게 하면 변수 읽기 또는 쓰기가 해당 클래스와 해당 클래스에서 파생된 클래스 내에서만 가능하고 파생 체인에 있는 클래스의 외부에서는 가능하지 않습니다.  
  
#### 변수를 동일한 어셈블리 내에서만 액세스할 수 있도록 하려면  
  
1.  모듈, 클래스 또는 구조체 내에서 모든 프로시저의 바깥쪽 위치에 변수에 대한 `Dim` 문을 넣습니다.  
  
2.  `Dim` 문에 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) 키워드를 포함시킵니다.  
  
     변수 읽기 또는 쓰기가 모듈, 클래스 또는 구조체 내의 모든 위치뿐 아니라 동일한 어셈블리의 모든 코드에서도 가능하지만 어셈블리 외부에서는 가능하지 않습니다.  
  
## 예제  
 다음 예제에서는 `Public`, `Protected`, `Friend`, `Protected Friend` 또는 `Private` 액세스 수준을 사용한 변수 선언을 보여 줍니다.  `Dim` 문에서 액세스 수준을 지정한 경우에는 `Dim` 키워드를 사용하지 않아도 됩니다.  
  
```  
Public Class classForEverybody  
Protected Class classForMyHeirs  
Friend stringForThisProject As String  
Protected Friend stringForProjectAndHeirs As String  
Private numberForMeOnly As Integer  
```  
  
## .NET Framework 보안  
 변수의 액세스 수준이 제한적일수록 악의적인 코드에서 변수를 부적절하게 사용할 가능성이 줄어듭니다.  
  
## 참고 항목  
 [Access Levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)   
 [Public](../../../../visual-basic/language-reference/modifiers/public.md)   
 [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)   
 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)   
 [Private](../../../../visual-basic/language-reference/modifiers/private.md)