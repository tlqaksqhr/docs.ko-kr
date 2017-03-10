---
title: "How to: Declare a Structure (Visual Basic) | Microsoft Docs"
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
  - "declarations, structures"
  - "structure statements"
  - "statements [Visual Basic], structure"
  - "structures, declaring"
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# How to: Declare a Structure (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

구조체 선언은 [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md)으로 시작하고 `End` `Structure` 문으로 끝납니다.  이 두 개의 문 사이에 *요소*를 적어도 하나 선언해야 합니다.  모든 데이터 형식의 요소를 선언할 수 있지만 적어도 하나는 비공유 변수거나 사용자 지정되지 않은 비공유 이벤트여야 합니다.  
  
 구조체 선언에서는 구조체 요소를 초기화할 수 없습니다.  변수를 구조체 형식으로 선언하는 경우 해당 변수를 통해 값에 액세스하는 방식으로 요소에 값을 할당합니다.  
  
 구조체와 클래스의 차이점에 대한 자세한 내용은 [Structures and Classes](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)를 참조하십시오.  
  
 예를 들어 직원의 이름, 내선 전화 번호 및 급여를 관리하려는 경우  구조체를 사용하면 단일 변수에서 이 작업을 수행할 수 있습니다.  
  
### 구조체를 선언하려면  
  
1.  구조체 시작 문과 종결 문을 만듭니다.  
  
     [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) 또는 [Private](../../../../visual-basic/language-reference/modifiers/private.md) 키워드를 사용하여 구조체의 액세스 수준을 직접 지정하거나 기본값 `Public`을 사용할 수 있습니다.  
  
    ```  
    Private Structure employee  
    End Structure  
    ```  
  
2.  구조체의 본문에 요소를 추가합니다.  
  
     구조체에는 요소가 적어도 한 개 있어야 합니다.  모든 요소를 선언하고 해당 요소의 액세스 수준을 지정해야 합니다.  키워드 없이 [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)을 사용하는 경우 기본 액세스 권한은 `Public`입니다.  
  
    ```  
    Private Structure employee  
        Public givenName As String  
        Public familyName As String  
        Public phoneExtension As Long  
        Private salary As Decimal  
        Public Sub giveRaise(raise As Double)  
            salary *= raise  
        End Sub  
        Public Event salaryReviewTime()  
    End Structure  
    ```  
  
     위 예제의 `salary` 필드는 `Private`이므로 구조체 외부에서는 액세스할 수 없습니다. 심지어 포함하는 클래스에서도 액세스할 수 없습니다.  그러나 `giveRaise` 프로시저는 `Public`이므로 구조체 외부에서 호출할 수 있습니다.  마찬가지로 구조체의 외부에서 `salaryReviewTime` 이벤트를 발생시킬 수 있습니다.  
  
     변수, `Sub` 프로시저 및 이벤트 외에도 상수, `Function` 프로시저 및 속성을 구조체에 정의할 수 있습니다.  하나 이상의 인수를 사용하는 속성 하나를 *기본 속성*으로 지정할 수 있습니다.  이벤트는 [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub` 프로시저로 처리할 수 있습니다.  자세한 내용은 [How to: Declare and Call a Default Property in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)을 참조하십시오.  
  
## 참고 항목  
 [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)   
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Structures](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Structure Variables](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)   
 [Structures and Other Programming Elements](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)   
 [Structures and Classes](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)   
 [User\-Defined Data Type](../../../../visual-basic/language-reference/data-types/user-defined-data-type.md)