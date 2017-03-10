---
title: "Structure Variables (Visual Basic) | Microsoft Docs"
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
  - "structures, variables"
  - "structures, structure variables"
  - "variables [Visual Basic], structure variables"
  - "structure variables"
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Structure Variables (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

구조체를 만든 후 이 형식으로 프로시저 수준과 모듈 수준의 변수를 선언할 수 있습니다.  예를 들어, 컴퓨터 시스템에 대한 정보를 기록하는 구조체를 만들 수 있습니다.  다음 예제에서는 이 작업을 보여 줍니다.  
  
```  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public purchaseDate As Date  
End Structure  
```  
  
 그런 다음 해당 형식의 변수를 선언할 수 있습니다.  다음 선언에서는 이러한 예를 보여 줍니다.  
  
```  
Dim mySystem, yourSystem As systemInfo  
```  
  
> [!NOTE]
>  클래스와 모듈에서 [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)을 사용하여 선언된 구조체의 액세스 수준은 기본적으로 Public입니다.  구조체의 액세스 수준을 Private으로 설정하려면 [Private](../../../../visual-basic/language-reference/modifiers/private.md) 키워드를 사용하여 선언해야 합니다.  
  
## 구조체 값 액세스  
 구조체 변수의 요소에서 값을 할당하거나 검색하려면 개체의 속성을 설정하고 가져오는 데 사용하는 것과 동일한 구문을 사용합니다.  구조 변수 이름과 요소 이름 사이에 멤버 액세스 연산자\(`.`\)를 삽입합니다.  다음 예제에서는 앞에서 `systemInfo` 형식으로 선언된 변수의 요소에 액세스합니다.  
  
```  
mySystem.cPU = "486"  
Dim tooOld As Boolean  
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True  
```  
  
## 구조체 변수 할당  
 또한 두 변수가 모두 동일한 구조체 형식인 경우 한 변수를 다른 변수에 할당할 수 있습니다.  이렇게 하면 한 구조체의 모든 요소가 다른 구조체의 해당 요소로 복사됩니다.  다음 선언에서는 이러한 예를 보여 줍니다.  
  
```  
yourSystem = mySystem  
```  
  
 구조체 요소가 `String`, `Object` 또는 배열 등의 참조 형식일 경우 해당 데이터에 대한 포인터가 복사됩니다.  위 예제의 경우 `systemInfo`에 개체 변수가 포함되었으면 포인터는 `mySystem`에서 `yourSystem`으로 복사되며, 한 구조체를 통해 수행한 개체 데이터의 변경 내용은 다른 구조체를 통해 액세스할 때 적용됩니다.  
  
## 참고 항목  
 [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)   
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Structures](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [How to: Declare a Structure](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)   
 [Structures and Other Programming Elements](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)   
 [Structures and Classes](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)   
 [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md)