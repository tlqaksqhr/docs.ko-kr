---
title: "Overloaded Properties and Methods (Visual Basic) | Microsoft Docs"
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
  - "properties [Visual Basic], overloading"
  - "methods [Visual Basic], overloading"
  - "shadowing"
  - "names, multiple procedures with same"
  - "procedures, mulltiples with same name"
  - "classes [Visual Basic], properties"
  - "classes [Visual Basic], methods"
  - "method overloading"
  - "Overloads keyword, overloaded members"
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Overloaded Properties and Methods (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

오버로딩은 하나의 클래스에 이름은 같고 인수 형식은 다른 프로시저, 인스턴스 생성자 또는 속성을 두 개 이상 만드는 것을 말합니다.  
  
## 오버로딩 사용법  
 오버로딩은 개체 모델의 필요성에 의해, 다른 데이터 형식에서 작동하는 서로 다른 프로시저에 동일한 이름을 사용해야 할 때 특히 유용합니다.  예를 들어, 여러 다른 데이터 형식을 나타낼 수 있는 하나의 클래스에는 다음과 같은 `Display` 프로시저가 포함될 수 있습니다.  
  
 [!code-vb[VbVbalrOOP#64](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#64)]  
  
 오버로딩을 사용하지 않는 경우에는 다음에서 볼 수 있는 것처럼 프로시저가 동일한 작업을 수행하는 경우에도 각 프로시저에 대해 고유한 이름을 만들어야 합니다.  
  
 [!code-vb[VbVbalrOOP#65](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#65)]  
  
 오버로딩을 사용하면 여러 데이터 형식 중에서 선택할 수 있으므로 속성이나 메서드를 보다 쉽게 사용할 수 있습니다.  예를 들어, 앞에서 설명한 오버로드된 `Display` 메서드는 다음 코드를 사용하여 호출할 수 있습니다.  
  
 [!code-vb[VbVbalrOOP#66](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#66)]  
  
 런타임에 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]은 지정한 매개 변수의 데이터 형식을 기준으로 올바른 프로시저를 호출합니다.  
  
## 오버로딩 규칙  
 클래스에 이름이 같은 속성이나 메서드를 두 개 이상 추가하여 오버로드된 멤버를 만듭니다.  오버로드된 멤버 중 파생된 멤버를 제외한 각 멤버는 여러 매개 변수 목록을 가지고 있어야 하며, 속성이나 프로시저를 오버로드할 경우 다음 항목을 별도의 기능으로 사용할 수 없습니다.  
  
-   멤버 또는 멤버의 매개 변수에 적용되는 `ByVal` 또는 `ByRef`와 같은 한정자  
  
-   매개 변수의 이름  
  
-   프로시저의 반환 형식  
  
 `Overloads` 키워드는 오버로드할 때 반드시 필요하지는 않지만, 오버로드된 멤버가 `Overloads` 키워드를 사용할 경우에는 오버로드된 멤버 중 이름이 같은 다른 모든 멤버도 이 키워드를 지정해야 합니다.  
  
 파생된 클래스는 상속된 멤버를 동일한 매개 변수 및 매개 변수 형식을 갖는 멤버로 오버로드할 수 있습니다. 이 프로세스를 *이름 및 시그니처로 숨김*이라고 합니다.  이름 및 시그니처로 숨길 때 `Overloads` 키워드를 사용할 경우, 멤버의 파생된 클래스 구현이 기본 클래스의 구현 대신 사용되며 해당 멤버에 대한 다른 모든 오버로드를 파생된 클래스의 인스턴스에 사용할 수 있습니다.  
  
 상속된 멤버를 동일한 매개 변수 및 매개 변수 형식을 갖는 멤버로 오버로드할 때 `Overloads` 키워드를 생략하는 오버로딩을 *이름으로 숨김*이라고 합니다.  이름 숨김은 멤버의 상속된 구현을 대체하며 다른 모든 오버로드를 파생된 클래스의 인스턴스 및 관련 계승자에서 사용할 수 없게 합니다.  
  
 `Overloads`와 `Shadows` 한정자를 동일한 속성이나 메서드와 함께 사용할 수 없습니다.  
  
### 예제  
 다음 예제에서는 달러 금액의 `String` 또는 `Decimal` 표시를 받아 판매세가 포함된 문자열을 반환하는 오버로드된 메서드를 만듭니다.  
  
##### 이 예제를 사용하여 오버로드된 메서드를 만들려면  
  
1.  새 프로젝트를 열고 `TaxClass` 클래스를 추가합니다.  
  
2.  `TaxClass` 클래스에 다음 코드를 추가합니다.  
  
     [!code-vb[VbVbalrOOP#67](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#67)]  
  
3.  폼에 다음 프로시저를 추가합니다.  
  
     [!code-vb[VbVbalrOOP#68](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#68)]  
  
4.  폼에 단추를 추가하고 단추의 `Button1_Click` 이벤트에서 `ShowTax` 프로시저를 호출합니다.  
  
5.  프로젝트를 실행하고 폼에서 해당 단추를 클릭하여 오버로드된 `ShowTax` 프로시저를 테스트합니다.  
  
 런타임에 컴파일러는 사용 중인 매개 변수와 일치하는 오버로드된 함수를 선택합니다.  해당 단추를 클릭하면 먼저 문자열인 `Price` 매개 변수를 갖는 오버로드된 메서드가 호출되고 "Price is a String.  Tax is $5.12"라는 메시지가 표시됩니다.  그런 다음 `Decimal` 값을 갖는 `TaxAmount`가 호출되고 "Price is a Decimal.  Tax is $5.12"라는 메시지가 표시됩니다.  
  
## 참고 항목  
 [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)   
 [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Inheritance Basics](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)   
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)   
 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)   
 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)   
 [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)   
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)