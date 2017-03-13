---
title: "Generic Procedures in Visual Basic | Microsoft Docs"
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
  - "generic methods, type inference"
  - "generics [Visual Basic], type inference"
  - "procedures, generic"
  - "generic procedures"
  - "type inference, generics"
  - "generic methods"
  - "type inference"
  - "generics [Visual Basic], procedures"
  - "generic procedures, type inference"
ms.assetid: 95577b28-137f-4d5c-a149-919c828600e5
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Generic Procedures in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

*제네릭 프로시저*는 적어도 하나 이상의 형식 매개 변수로 정의된 프로시저로서 *제네릭 메서드*라고도 합니다.  제네릭 프로시저는 호출 코드를 사용하여, 프로시저를 호출할 때마다 해당 요구 사항을 충족시키도록 데이터 형식을 수정할 수 있습니다.  
  
 제네릭 클래스 또는 제네릭 구조체 내부에 정의되는 것만으로 제네릭 프로시저가 되는 것은 아닙니다.  제네릭 프로시저가 되기 위해서는 적어도 하나 이상의 형식 매개 변수와 일반 매개 변수를 사용해야 합니다.  제네릭 클래스 또는 구조체에는 제네릭이 아닌 프로시저가 포함될 수 있으며 제네릭이 아닌 클래스, 구조체 또는 모듈에는 제네릭 프로시저가 포함될 수 있습니다.  
  
 제네릭 프로시저는 일반 매개 변수 목록, 반환 형식이 있는 경우 해당 반환 형식 및 해당 프로시저 코드에서 해당 형식 매개 변수를 사용할 수 있습니다.  
  
## 형식 유추  
 형식 인수를 전혀 제공하지 않고 제네릭 프로시저를 호출할 수 있습니다.  이러한 방식으로 제네릭 프로시저를 호출하는 경우 컴파일러가 프로시저의 형식 인수에 전달할 적합한 데이터 형식을 결정하려고 시도합니다.  이를 *형식 유추*라고 합니다.  다음 코드에서는 컴파일러가 `String` 형식을 `t` 형식 매개 변수로 전달해야 하는 것으로 유추하는 호출을 보여 줍니다.  
  
 [!code-vb[VbVbalrDataTypes#15](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_1.vb)]  
  
 컴파일러가 호출 컨텍스트에서 형식 인수를 유추할 수 없는 경우 오류를 보고합니다.  예를 들어, 배열 차수가 일치하지 않는 경우 이 오류가 발생합니다.  예를 들어, 일반 매개 변수를 형식 매개 변수의 배열로 정의하는 것으로 가정합니다.  다른 차수\(차원 수\)의 배열을 제공하여 제네릭 프로시저를 호출하는 경우 차수가 일치하지 않으면 형식을 유추할 수 없습니다.  다음 코드에서는 1차원 배열을 예상하는 프로시저에 2차원 배열을 전달하는 호출을 보여 줍니다.  
  
 `Public Sub demoSub(Of t)(ByVal arg() As t)`  
  
 `End Sub`  
  
 `Public Sub callDemoSub()`  
  
 `Dim twoDimensions(,) As Integer`  
  
 `demoSub(twoDimensions)`  
  
 `End Sub`  
  
 모든 형식 인수를 생략해야 형식 유추를 호출할 수 있습니다.  형식 인수를 하나만 제공하는 경우 모두 제공해야 합니다.  
  
 형식 유추는 제네릭 프로시저에만 지원됩니다.  제네릭 클래스, 구조체, 인터페이스 또는 대리자에는 형식 유추를 호출할 수 없습니다.  
  
## 예제  
  
### 설명  
 다음 예제에서는 배열에서 특정 요소를 찾는 제네릭 `Function` 프로시저를 정의합니다.  여기에서는 하나의 형식 매개 변수를 정의하고 이 매개 변수를 사용하여 매개 변수 목록에 두 매개 변수를 만듭니다.  
  
### 코드  
 [!code-vb[VbVbalrDataTypes#14](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_2.vb)]  
  
### 설명  
 앞의 예제에서는 `searchArray`의 각 요소에 대해 `searchValue`를 비교할 수 있는 기능이 필요합니다.  이 예제에서는 이 기능을 사용하기 위해 `T` 형식 매개 변수가 <xref:System.IComparable%601> 인터페이스를 구현하도록 제한합니다.  `T`에 제공된 형식 인수는 `=` 연산자를 지원하지 않을 수 있으므로 이 코드는 `=` 연산자 대신 <xref:System.IComparable%601.CompareTo%2A> 메서드를 사용합니다.  
  
 다음 코드를 사용하여 `findElement` 프로시저를 테스트할 수 있습니다.  
  
 [!code-vb[VbVbalrDataTypes#13](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_3.vb)]  
  
 앞에서 `MsgBox`를 호출하면 각각 "0", "1" 및 "\-1"이 표시됩니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [방법: 다른 데이터 형식에 동일한 기능을 제공할 수 있는 클래스 정의](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)   
 [방법: 제네릭 클래스 사용](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)   
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Type List](../../../../visual-basic/language-reference/statements/type-list.md)   
 [Parameter List](../../../../visual-basic/language-reference/statements/parameter-list.md)