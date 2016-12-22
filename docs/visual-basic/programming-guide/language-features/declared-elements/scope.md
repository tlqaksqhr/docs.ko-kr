---
title: "Scope in Visual Basic | Microsoft Docs"
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
  - "module scope"
  - "scope, levels"
  - "module level"
  - "procedures, scope"
  - "declared elements, scope"
  - "namespaces, scope"
  - "scope, declared elements"
  - "scope, about scope"
  - "levels of scope"
  - "block scope"
  - "scope, Visual Basic"
  - "procedure scope"
ms.assetid: 208106fe-79c9-4eec-93c6-55f08548895f
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Scope in Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

선언 요소의 *범위*는 선언 요소의 이름을 한정하거나 [Imports Statement \(.NET Namespace and Type\)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)을 통하지 않고 선언 요소를 참조할 수 있는 모든 코드 집합입니다.  요소는 다음과 같은 수준의 범위를 가질 수 있습니다.  
  
|수준|설명|  
|--------|--------|  
|블록 범위|요소가 선언된 코드 블록 내에서만 사용 가능|  
|프로시저 범위|요소가 선언된 프로시저 내의 모든 코드에서 사용 가능|  
|모듈 범위|요소가 선언된 모듈, 클래스 또는 구조체 내의 모든 코드에서 사용 가능|  
|네임스페이스 범위|요소가 선언된 네임스페이스의 모든 코드에서 사용 가능|  
  
 이러한 범위의 수준은 가장 좁은 범위\(블록\)로부터 가장 넓은 범위\(네임스페이스\)로 확장되며, 여기서 *가장 좁은 범위*는 한정자 없이 요소를 참조할 수 있는 가장 작은 코드 집합을 의미합니다.  자세한 내용은 이 페이지의 "범위의 수준"을 참조하십시오.  
  
## 범위 지정 및 변수 정의  
 요소의 범위는 요소를 선언할 때 지정하며  다음 인자에 따라 범위가 결정됩니다.  
  
-   요소를 선언한 영역\(블록, 프로시저, 모듈, 클래스 또는 구조체\)  
  
-   요소의 선언을 포함하는 네임스페이스  
  
-   요소에 대해 사용자가 선언한 액세스 수준  
  
 이름은 같지만 범위가 다른 변수를 정의할 경우 예기치 않은 결과가 발생할 수 있으므로 주의해야 합니다.  자세한 내용은 [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)을 참조하십시오.  
  
## 범위의 수준  
 프로그래밍 요소는 이를 선언한 영역 전체에서 사용할 수 있습니다.  같은 영역에 있는 모든 코드는 요소 이름을 지정하지 않고 요소를 참조할 수 있습니다.  
  
### 블록 범위  
 블록은 다음과 같은 선언 시작 문과 종결 문 사이에 있는 일련의 문입니다.  
  
-   `Do` 및 `Loop`  
  
-   `For` \[`Each`\] 및 `Next`  
  
-   `If` 및 `End If`  
  
-   `Select` 및 `End Select`  
  
-   `SyncLock` 및 `End SyncLock`  
  
-   `Try` 및 `End Try`  
  
-   `While` 및 `End While`  
  
-   `With` 및 `End With`  
  
 블록 내에 변수를 선언하면 해당 블록 내에서만 변수를 사용할 수 있습니다.  다음 예제에서 정수 변수 `cube`의 범위는 `If`와 `End If` 사이의 블록이며 이 블록 밖의 코드가 실행될 때는 `cube`를 더 이상 참조할 수 없습니다.  
  
```  
If n < 1291 Then  
    Dim cube As Integer  
    cube = n ^ 3  
End If  
```  
  
> [!NOTE]
>  변수의 범위가 특정 블록으로 제한되더라도 변수의 수명은 전체 프로시저의 수명과 같습니다.  프로시저 도중 블록에 여러 번 들어가는 경우 각 블록 변수는 이전 값을 유지합니다.  그러나 예기치 않은 결과를 방지하려면 블록의 시작 부분에서 블록 변수를 초기화하는 것이 좋습니다.  
  
### 프로시저 범위  
 특정 프로시저 내에서 선언한 요소는 해당 프로시저 외부에서 사용할 수 없습니다.  요소를 선언한 프로시저만 이 요소를 사용할 수 있습니다.  이 수준의 변수를 *지역 변수*라고도 하며  [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)을 사용하여 선언합니다. 이 경우 [Static](../../../../visual-basic/language-reference/modifiers/static.md) 키워드는 사용해도 되고 사용하지 않아도 됩니다.  
  
 프로시저와 블록 범위는 밀접한 관련이 있습니다.  변수를 프로시저 안에 있는 블록 외부에서 선언했더라도 이 선언이 프로시저 내부에서 이루어졌다면 해당 변수는 블록 범위를 갖는 것으로 간주할 수 있으며 전체 프로시저가 블록이 됩니다.  
  
> [!NOTE]
>  `Static` 변수를 비롯한 모든 지역 요소는 해당 요소가 나타나는 프로시저에 대해 전용입니다.  프로시저 내에서는 [Public](../../../../visual-basic/language-reference/modifiers/public.md) 키워드를 사용하여 요소를 선언할 수 없습니다.  
  
### 모듈 범위  
 편의상 모듈, 클래스 및 구조체에 대해 똑같이 *모듈 수준*이라는 하나의 용어를 사용합니다.  이 수준의 요소는 모듈, 클래스 또는 구조체 내에서 선언문을 프로시저나 블록의 외부에 두어 선언할 수 있습니다.  
  
 모듈 수준에서 선언하는 경우 선택하는 액세스 수준에 따라 범위가 결정됩니다.  모듈, 클래스 또는 구조체를 포함하는 네임스페이스도 범위에 영향을 줍니다.  
  
 [Private](../../../../visual-basic/language-reference/modifiers/private.md) 액세스 수준으로 선언한 요소는 해당 모듈 내의 모든 프로시저에서 사용할 수 있지만 다른 모듈의 코드에서는 사용할 수 없습니다.  액세스 수준 키워드를 사용하지 않는 경우 모듈 수준의 `Dim` 문은 기본적으로 `Private`으로 설정됩니다.  그러나 `Dim` 문에 `Private` 키워드를 사용하여 범위 및 액세스 수준을 보다 명확하게 만들 수 있습니다.  
  
 다음 예제에서 모듈에 정의된 모든 프로시저는 문자열 변수 `strMsg`를 참조할 수 있습니다.  두 번째 프로시저가 호출되면 문자열 변수 `strMsg`의 내용이 대화 상자에 표시됩니다.  
  
```  
' Put the following declaration at module level (not in any procedure).  
Private strMsg As String  
' Put the following Sub procedure in the same module.  
Sub initializePrivateVariable()  
    strMsg = "This variable cannot be used outside this module."  
End Sub  
' Put the following Sub procedure in the same module.  
Sub usePrivateVariable()  
    MsgBox(strMsg)  
End Sub  
```  
  
### 네임스페이스 범위  
 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) 또는 [Public](../../../../visual-basic/language-reference/modifiers/public.md) 키워드를 사용하여 모듈 수준에서 요소를 선언하면 요소가 선언된 네임스페이스에 있는 모든 프로시저에서 이 요소를 사용할 수 있습니다.  위 예제를 다음과 같이 변경하면 변수가 선언된 네임스페이스에 있는 모든 코드에서 문자열 변수 `strMsg`를 참조할 수 있습니다.  
  
```  
' Include this declaration at module level (not inside any procedure).  
Public strMsg As String  
```  
  
 네임스페이스의 범위에는 중첩 네임스페이스가 포함됩니다.  특정 네임스페이스 내에서 사용할 수 있는 요소는 해당 네임스페이스 안에 중첩된 네임스페이스에서도 사용할 수 있습니다.  
  
 프로젝트에 [Namespace Statement](../../../../visual-basic/language-reference/statements/namespace-statement.md)이 없으면 프로젝트의 모든 개체는 같은 네임스페이스에 존재합니다.  이 경우 네임스페이스 범위는 프로젝트 범위로 간주할 수 있습니다.  모듈, 클래스 또는 구조체의 `Public` 요소는 해당 프로젝트를 참조하는 모든 프로젝트에서도 사용할 수 있습니다.  
  
## 범위 선택  
 변수를 선언할 때는 다음 사항을 고려해서 변수 범위를 선택해야 합니다.  
  
### 지역 변수의 장점  
 다음과 같은 이유로 임시적인 계산에는 지역 변수를 사용하는 것이 좋습니다.  
  
-   **이름 충돌 방지.** 지역 변수 이름은 충돌할 가능성이 없습니다.  예를 들어, `intTemp`라는 변수를 여러 프로시저에서 사용할 수 있습니다.  각 `intTemp`를 지역 변수로 선언하면 각 프로시저는 자체적으로 포함된 `intTemp`만 인식합니다.  각 프로시저는 다른 프로시저의 `intTemp` 변수에 영향을 주지 않고 해당 `intTemp`의 값을 변경할 수 있습니다.  
  
-   **메모리 사용.** 지역 변수는 해당 프로시저가 실행되는 동안에만 메모리를 사용합니다.  프로시저가 호출 코드로 반환되면 해당 지역 변수에서 사용하던 메모리가 해제됩니다.  반면에 [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) 및 [Static](../../../../visual-basic/language-reference/modifiers/static.md) 변수는 응용 프로그램의 실행이 중지될 때까지 메모리 리소스를 사용하므로 이러한 변수는 반드시 필요한 경우에만 사용해야 합니다.  *인스턴스 변수*는 해당 인스턴스가 존재하는 동안 계속 메모리를 사용하므로 지역 변수보다 효율적이지 않지만 `Shared` 또는 `Static` 변수보다는 효율적입니다.  
  
### 범위 최소화  
 일반적으로 변수나 상수를 선언할 때는 최대한 범위를 좁게 설정\(예: 블록\) 하는 것이 좋습니다.  범위를 좁게 설정하면 메모리 사용을 줄일 수 있으며 코드에서 변수를 잘못 참조할 가능성이 최소화됩니다.  또한 프로시저를 호출하는 동안 값을 유지해야 하는 경우에만 변수를 [Static](../../../../visual-basic/language-reference/modifiers/static.md)으로 선언해야 합니다.  
  
## 참고 항목  
 [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)   
 [How to: Control the Scope of a Variable](../Topic/How%20to:%20Control%20the%20Scope%20of%20a%20Variable%20\(Visual%20Basic\).md)   
 [Lifetime in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)   
 [Access Levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [변수 선언](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)