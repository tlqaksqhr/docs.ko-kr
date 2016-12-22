---
title: "방법: 익명 형식 선언에서 속성 이름 및 형식 유추(Visual Basic) | Microsoft Docs"
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
  - "속성 이름 유추[Visual Basic]"
  - "익명 형식 [Visual Basic], 속성 이름 및 형식 유추"
  - "속성 형식 유추[Visual Basic]"
ms.assetid: 7c748b22-913f-4d9d-b747-6b7bf296a0bc
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 방법: 익명 형식 선언에서 속성 이름 및 형식 유추(Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

익명 형식은 속성의 데이터 형식을 직접 지정하는 메커니즘을 제공하지 않습니다. 모든 속성의 형식이 유추됩니다. 다음 예제에서 `Name` 및 `Price`의 형식은 이를 초기화하는 데 사용되는 값에서 직접 유추됩니다.  
  
 [!CODE [VbVbalrAnonymousTypes#1](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#1)]  
  
 익명 형식은 다른 소스에서 속성 이름 및 형식을 유추할 수도 있습니다. 다음 섹션에서는 유추가 가능한 환경의 목록과 유추가 가능하지 않은 상황의 예를 제공합니다.  
  
## 유추 성공  
  
#### 익명 형식은 다음 소스에서 속성 이름 및 형식을 유추할 수 있습니다.  
  
-   변수 이름에서. 익명 형식 `anonProduct`에는 두 개의 속성 `productName` 및 `productPrice`가 있습니다. 각각의 데이터 형식은 원래 변수 `String` 및 `Double`의 데이터 형식입니다.  
  
     [!CODE [VbVbalrAnonymousTypes#11](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#11)]  
  
-   다른 개체의 속성 또는 필드 이름에서.`Name` 및 `ID` 속성이 포함된 `CarClass` 형식의 `car` 개체를 예로 들겠습니다.`car` 개체의 값으로 초기화되는 `Name` 및 `ID` 속성을 가진 새 익명 형식 인스턴스 `car1`을 만들려면 다음을 작성할 수 있습니다.  
  
     [!CODE [VbVbalrAnonymousTypes#34](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#34)]  
  
     이전 선언은 익명 형식 `car2`를 정의하는 더 긴 코드 줄과 동일합니다.  
  
     [!CODE [VbVbalrAnonymousTypes#35](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#35)]  
  
-   XML 멤버 이름에서.  
  
     [!CODE [VbVbalrAnonymousTypes#12](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#12)]  
  
     `anon`의 결과 형식은 <xref:System.Collections.IEnumerable>\(Of XElement\) 형식의 `Book` 속성 하나를 가집니다.  
  
-   다음 예제에서처럼 `SomeFunction`과 같은 매개 변수가 없는 함수에서.  
  
     `Dim sc As New SomeClass`  
  
     `Dim anon1 = New With {Key sc.SomeFunction()}`  
  
     다음 코드에서 변수 `anon2`은 하나의 속성\(이름이 `First`인 문자\)을 가지는 익명 형식입니다. 이 코드는 함수 <xref:System.Linq.Enumerable.First%2A>에서 반환하는 문자인 “E”를 표시합니다.  
  
     [!CODE [VbVbalrAnonymousTypes#13](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#13)]  
  
## 유추 실패  
  
#### 다음을 포함한 여러 경우에 이름 유추가 실패합니다.  
  
-   인수가 필요한 메서드, 생성자 또는 매개 변수가 있는 속성의 호출에서 유추가 도출되는 경우.`someFunction`에 하나 이상의 인수가 있는 경우 `anon1`의 이전 선언이 실패합니다.  
  
     `' Not valid.`  
  
     `' Dim anon3 = New With {Key sc.someFunction(someArg)}`  
  
     새 속성 이름에 할당하면 문제가 해결됩니다.  
  
     `' Valid.`  
  
     `Dim anon4 = New With {Key .FunResult = sc.someFunction(someArg)}`  
  
-   복잡한 식에서 유추가 도출되는 경우.  
  
    ```  
    Dim aString As String = "Act "  
    ' Not valid.  
    ' Dim label = New With {Key aString & "IV"}  
    ```  
  
     식의 결과를 속성 이름에 할당하여 오류를 해결할 수 있습니다.  
  
     [!CODE [VbVbalrAnonymousTypes#14](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#14)]  
  
-   이름이 동일한 둘 이상의 속성을 생성하는 여러 속성에 대한 유추. 이전 예의 선언을 다시 보면 `product.Name`과 `car1.Name` 모두를 동일한 익명 형식의 속성으로 나열할 수 없습니다. 이는 이 두 가지 각각에 대한 유추된 식별자가 `Name`이기 때문입니다.  
  
     `' Not valid.`  
  
     `' Dim anon5 = New With {Key product.Name, Key car1.Name}`  
  
     고유한 속성 이름에 값을 할당하여 문제를 해결할 수 있습니다.  
  
     [!CODE [VbVbalrAnonymousTypes#36](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#36)]  
  
     대\/소문자를 변경하더라도 두 이름이 고유해지지 않습니다.  
  
     `Dim price = 0`  
  
     `' Not valid, because Price and price are the same name.`  
  
     `' Dim anon7 = New With {Key product.Price, Key price}`  
  
-   속성의 초기 형식 및 값이 아직 설정되지 않은 다른 속성에 따라 달라지는 경우. 예를 들어 `.LastName`이 아직 초기화되지 않은 경우 `.IDName = .LastName`은 익명 형식 선언에서 유효하지 않습니다.  
  
     `' Not valid.`  
  
     `' Dim anon8 = New With {Key .IDName = .LastName, Key .LastName = "Jones"}`  
  
     이 예에서는 속성이 선언되는 순서를 반전시켜서 문제를 해결할 수 있습니다.  
  
     [!CODE [VbVbalrAnonymousTypes#15](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#15)]  
  
-   익명 형식의 속성 이름은 <xref:System.Object>의 멤버 이름과 동일합니다. 예를 들어 `Equals`은 <xref:System.Object>의 메서드이므로 다음 선언은 실패합니다.  
  
     `' Not valid.`  
  
     `' Dim relationsLabels1 = New With {Key .Equals = "equals", Key .Greater = _`  
  
     `'                       "greater than", Key .Less = "less than"}`  
  
     속성 이름을 변경하여 문제를 해결할 수 있습니다.  
  
     [!CODE [VbVbalrAnonymousTypes#16](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#16)]  
  
## 참고 항목  
 [Object Initializers: Named and Anonymous Types](../Topic/Object%20Initializers:%20Named%20and%20Anonymous%20Types%20\(Visual%20Basic\).md)   
 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Key](../../../../visual-basic/language-reference/modifiers/key.md)