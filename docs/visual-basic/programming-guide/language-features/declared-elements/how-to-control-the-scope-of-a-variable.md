---
title: "How to: Control the Scope of a Variable (Visual Basic) | Microsoft Docs"
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
  - "variables [Visual Basic], scope"
  - "declared elements, scope"
  - "visibility, declared elements"
  - "variables [Visual Basic], visibility"
  - "scope, declared elements"
  - "scope, variables"
  - "scope, Visual Basic"
  - "declared elements, visibility"
  - "visibility, variables"
ms.assetid: 44b7f62a-cb5c-4d50-bce9-60ae68f87072
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# How to: Control the Scope of a Variable (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

일반적으로 변수는 해당 변수가 선언된 영역 전체에서 *범위*에 있다고 하거나 참조할 수 있다고 합니다.  일부 경우 변수의 *액세스 수준*이 변수 범위에 영향을 줄 수 있습니다.  
  
 자세한 내용은 [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)를 참조하십시오.  
  
## 블록 또는 프로시저 수준의 범위  
  
#### 블록 내에서만 변수를 참조할 수 있도록 하려면  
  
-   해당 블록의 선언 시작 문과 종결 문 사이에 변수에 대한 [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)을 넣습니다. 예를 들어, `For` 루프의 경우 `For` 문과 `Next` 문 사이에 넣습니다.  
  
     해당 블록 내에서만 변수를 참조할 수 있습니다.  
  
#### 프로시저 내에서만 변수를 참조할 수 있도록 하려면  
  
-   프로시저 내에서 `With`...`End With`를 비롯한 모든 블록의 바깥쪽 위치에 변수에 대한 `Dim` 문을 넣습니다.  
  
     해당 프로시저에 포함된 모든 블록을 포함하여 프로시저 내에서만 변수를 참조할 수 있습니다.  
  
## 모듈 또는 네임스페이스 수준의 범위  
 편의상 모듈, 클래스 및 구조체에 대해 똑같이 *모듈 수준*이라는 하나의 용어를 사용합니다.  모듈 수준 변수의 범위는 해당 변수의 액세스 수준에 따라 결정됩니다.  모듈, 클래스 또는 구조체를 포함하는 네임스페이스도 범위에 영향을 줍니다.  
  
#### 모듈, 클래스 또는 구조체 전체에서 변수를 참조할 수 있도록 하려면  
  
1.  모듈, 클래스 또는 구조체 내에서 모든 프로시저의 바깥쪽 위치에 변수에 대한 `Dim` 문을 넣습니다.  
  
2.  `Dim` 문에 [Private](../../../../visual-basic/language-reference/modifiers/private.md) 키워드를 포함시킵니다.  
  
3.  해당 모듈, 클래스 또는 구조체 내에서만 변수를 참조할 수 있고 외부에서는 참조할 수 없습니다.  
  
#### 네임스페이스 전체에서 변수를 참조할 수 있도록 하려면  
  
1.  모듈, 클래스 또는 구조체 내에서 모든 프로시저의 바깥쪽 위치에 변수에 대한 `Dim` 문을 넣습니다.  
  
2.  `Dim` 문에 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) 또는 [Public](../../../../visual-basic/language-reference/modifiers/public.md) 키워드를 포함합니다.  
  
3.  해당 모듈, 클래스 또는 구조체가 들어 있는 네임스페이스 내의 모든 위치에서 변수를 참조할 수 있습니다.  
  
## 예제  
 다음 예제에서는 모듈 수준에서 변수를 선언하고 모듈 내의 코드에서만 이 변수를 참조할 수 있도록 제한합니다.  
  
```  
Module demonstrateScope  
    Private strMsg As String  
    Sub initializePrivateVariable()  
        strMsg = "This variable cannot be used outside this module."  
    End Sub  
    Sub usePrivateVariable()  
        MsgBox(strMsg)  
    End Sub  
End Module  
```  
  
 위 예제에서 `demonstrateScope` 모듈에 정의된 모든 프로시저는 `String` 변수 `strMsg`를 참조할 수 있습니다.  `usePrivateVariable` 프로시저가 호출되면 문자열 변수 `strMsg`의 내용이 대화 상자에 표시됩니다.  
  
 위 예제를 다음과 같이 변경하면 변수가 선언된 네임스페이스에 있는 모든 코드에서 문자열 변수 `strMsg`를 참조할 수 있습니다.  
  
```  
Public strMsg As String  
```  
  
## 강력한 프로그래밍  
 변수의 범위가 좁을수록 실수로 같은 이름의 다른 변수를 참조하게 될 가능성이 줄어듭니다.  또한 참조 일치 문제를 최소화할 수 있습니다.  
  
## .NET Framework 보안  
 변수의 범위가 좁을수록 악의적인 코드에서 변수를 부적절하게 사용할 가능성이 줄어듭니다.  
  
## 참고 항목  
 [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)   
 [Lifetime in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)   
 [Access Levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md)   
 [변수 선언](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)