---
title: "Yield 문(Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Yield"
helpviewer_keywords: 
  - "반복기, Yield 문[Visual Basic]"
  - "반복기[Visual Basic]"
  - "Yield 문[Visual Basic]"
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Yield 문(Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

컬렉션의 다음 요소로 보냅니다는 `For Each...Next` 문.  
  
## 구문  
  
```  
Yield expression  
```  
  
#### 매개 변수  
  
|||  
|-|-|  
|용어|정의|  
|`expression`|필수 요소.  반복기 함수 형식으로 암시적으로 변환할 수 있는 식 또는 `Get` 를 포함 하는 접근자의 `Yield` 문.|  
  
## 설명  
 `Yield` 의 컬렉션을 한 번에 하나의 요소 반환 하는 명령문입니다.  `Yield` 문의 반복기 함수에 포함 되어 또는 `Get` 컬렉션에서 사용자 지정 반복을 수행 하는 접근자입니다.  
  
 사용 하 여 반복기 함수는 소비는 [For Each...Next 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md) 또는 LINQ 쿼리 합니다.  각 반복의 `For Each` 루프 반복기 함수를 호출 합니다.  때에 `Yield` 문에 반복기 함수에 도달 `expression` 반환 됩니다 코드에서 현재 위치를 유지 합니다.  실행 위치에서 다음 반복기 함수가 호출 될 때 다시 시작 됩니다.  
  
 암시적 변환의 형식에서 존재 해야 `expression` 에 `Yield` 문은 반복기의 반환 형식입니다.  
  
 사용할 수 있습니다는 `Exit Function` 또는 `Return` 문을 반복을 종료 합니다.  
  
 "Yield"는 예약어 이며에서 사용 될 때 특별 한 의미가 있는 `Iterator` 함수 또는 `Get` 접근자입니다.  
  
 반복기 함수에 대 한 자세한 내용은 및 `Get` 을 참조 하십시오 [반복기](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md).  
  
## 반복기 함수와 Get 접근자  
 반복기 함수의 선언 또는 `Get` 접근자는 다음 요구 사항을 충족 해야 합니다.  
  
-   포함 해야는  [반복기](../../../visual-basic/language-reference/modifiers/iterator.md) 한정자입니다.  
  
-   The return type must be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.  
  
-   이 사용할 수 없습니다 `ByRef` 매개 변수입니다.  
  
 반복기 함수는 이벤트, 인스턴스 생성자, 정적 생성자 또는 정적 소멸자에서 발생할 수 없습니다.  
  
 반복기 함수는 익명 함수를 수 있습니다.  자세한 내용은 [반복기](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md)을 참조하십시오.  
  
## 예외 처리  
 A `Yield` 문 안에 수은 `Try` 블록은 [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  A `Try` 있는 블록은 `Yield` 문이 있을 수 있습니다 `Catch` 차단 되지 않으며 가질 수는 `Finally` 블록.  
  
 A `Yield` 문 안 내는 `Catch` 블록 또는 `Finally` 블록.  
  
 경우는 `For Each` 본문 반복기 기능\) \(외부 예외를 throw 한 `Catch` 블록 반복기 함수에서 실행 되지 않습니다 있지만 `Finally` 반복기 함수에서 블록이 실행.  A `Catch` 는 반복기 함수 블록 catch 반복기 함수 안에서 발생 하는 예외에 대해서만 합니다.  
  
## 기술 구현  
 다음 반환 코드는 `IEnumerable (Of String)` 는 반복기 함수에서 다음의 요소를 통해 반복 하 고 있는 `IEnumerable (Of String)`.  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 호출을 `MyIteratorFunction` 함수의 본문은 실행 하지 않습니다.  대신 호출에서 반환 된 `IEnumerable(Of String)` 에 `elements` 변수.  
  
 반복 중에 `For Each` 루프의 <xref:System.Collections.IEnumerator.MoveNext%2A> 메서드 호출에 대 한 `elements`.  본문에이 호출을 실행 합니다. `MyIteratorFunction` 다음까지 `Yield` 문에 도달 합니다.  `Yield` 값 뿐만 아니라 결정 하는 식을 반환 하는 명령문의 `element` 변수는 루프 본문에서 소비에 대 한도 <xref:System.Collections.Generic.IEnumerator%601.Current%2A> 속성 요소는 `IEnumerable (Of String)`.  
  
 각 후속 반복에서의 `For Each` 어디에서 반복기 본문의 실행을 계속 하 여 반복에 이르렀을 때를 다시 중지 해제 상태로 `Yield` 문.  `For Each` 루프 완료 되 면 반복기 함수의 끝 또는 `Return` 또는 `Exit Function` 문에 도달 합니다.  
  
## 예제  
 다음 예제는 `Yield` 문 내부에  [에 대 한...다음](../../../visual-basic/language-reference/statements/for-next-statement.md) 루프.  각 반복에서  [각각에 대 한](../../../visual-basic/language-reference/statements/for-each-next-statement.md) 문의 본문에 `Main` 호출을 만듭니다는 `Power` 반복기 기능.  반복기 함수를 호출할 때마다 다음 실행에 진행 되는 `Yield` 의 다음 반복 동안에 발생 하는 문의 `For…Next` 루프.  
  
 반복기 메서드 반환 형식이 <xref:System.Collections.Generic.IEnumerable%601>, 반복기 인터페이스 형식입니다.  반복기 메서드 호출 되 면 숫자의 거듭제곱이 들어 있는 열거 가능한 개체를 반환 합니다.  
  
 [!code-vb[VbVbalrStatements#98](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/yield-statement_1.vb)]  
  
## 예제  
 다음 예제는 `Get` 접근자는 반복기입니다.  속성 선언에 포함 된 `Iterator` 한정자입니다.  
  
 [!code-vb[VbVbalrStatements#99](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/yield-statement_2.vb)]  
  
 다른 예제를 보려면 [반복기](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md)를 참조하십시오.  
  
## 요구 사항  
 [!INCLUDE[vs_dev11_long](../../../csharp/includes/vs_dev11_long_md.md)]  
  
## 참고 항목  
 [반복기](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md)   
 [Statements](../../../visual-basic/language-reference/statements/index.md)