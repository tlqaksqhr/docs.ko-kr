---
title: "Structures and Classes (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "classes [Visual Basic], vs. structures"
  - "structures"
  - "classes [Visual Basic]"
  - "structures, compared to classes"
  - "structures, structure variables"
  - "structure variables"
ms.assetid: a221e74a-ffcf-4bdc-a0f6-a088a9bf26cc
caps.latest.revision: 21
caps.handback.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Structures and Classes (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 구조체와 클래스에 대한 구문이 단일화되었습니다. 그 결과 두 엔터티는 동일한 기능을 대부분 지원하지만,  구조체와 클래스 사이에는 중요한 차이점 또한 존재합니다.  
  
 클래스는 참조 형식이 될 수 있는 장점이 있습니다. 참조를 전달하는 것은 모든 데이터와 함께 구조체 변수를 전달하는 것보다 더욱 효율적이기 때문입니다.  한편, 구조체의 경우에는 전역 힙에 메모리를 할당할 필요가 없다는 장점이 있습니다.  
  
 구조체에서는 상속할 수 없으므로 확장할 필요가 없는 개체에만 구조체를 사용해야 합니다.  인스턴스 크기가 작은 개체를 만들 때에는 구조체를 사용하고 클래스와 구조체의 성능 특성을 비교하여 고려하십시오.  
  
## 유사점  
 구조체와 클래스는 다음과 같은 점에서 비슷합니다.  
  
-   둘 다 *container* 형식이므로 다른 형식을 멤버로 포함합니다.  
  
-   둘 다 생성자, 메서드, 속성, 필드, 상수, 열거형, 이벤트 및 이벤트 처리기를 포함할 수 있는 멤버를 가집니다.  그러나 이러한 멤버를 구조체의 선언된 *요소*와 혼동하지 말아야 합니다.  
  
-   구조체와 클래스의 멤버는 모두 개별화된 액세스 수준을 가질 수 있습니다.  예를 들어, 한 멤버는 `Public`으로 선언하고 다른 멤버는 `Private`으로 선언할 수 있습니다.  
  
-   둘 다 인터페이스를 구현할 수 있습니다.  
  
-   둘 다 매개 변수의 유무에 관계없이 공유 생성자를 가질 수 있습니다.  
  
-   둘 다 *기본 속성*을 노출할 수 있습니다. 단, 해당 속성은 매개 변수를 적어도 하나는 사용해야 합니다.  
  
-   둘 다 이벤트를 선언하고 발생시킬 수 있으며 대리자를 선언할 수 있습니다.  
  
## 차이점  
 구조체와 클래스는 다음과 같은 점에서 서로 다릅니다.  
  
-   구조체는 *값 형식*이고 클래스는 *참조 형식*입니다.  구조체 형식 변수는 클래스 형식처럼 데이터에 대한 참조를 포함하지 않고 구조체의 데이터를 포함합니다.  
  
-   구조체는 스택 할당을 사용하고 클래스는 힙 할당을 사용합니다.  
  
-   구조체 요소는 모두 기본적으로 `Public`이지만, 클래스의 경우 변수와 상수는 기본적으로 `Private`이고 다른 클래스 멤버는 기본적으로 `Public`입니다.  클래스 멤버의 이러한 특성 때문에 기본적으로 Visual Basic 6.0 시스템과 호환됩니다.  
  
-   구조체에는 비공유 변수나 사용자 지정되지 않는 비공유 이벤트 요소가 적어도 하나 있어야 하지만, 클래스는 완전히 비어 있을 수 있습니다.  
  
-   구조체 요소는 `Protected`로 선언하는 것이 가능하지 않지만 클래스 멤버는 가능합니다.  
  
-   구조체 프로시저는 [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub` 프로시저인 경우에 한해 [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md)을 통해서만 이벤트를 처리할 수 있지만, 클래스 프로시저는 [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) 키워드나 `AddHandler` 문을 사용하여 이벤트를 처리할 수 있습니다.  자세한 내용은 [Events](../../../../visual-basic/programming-guide/language-features/events/events.md)를 참조하십시오.  
  
-   이니셜라이저나 배열의 초기 크기를 지정하는 것은 구조체 변수 선언에서는 가능하지 않지만 클래스 변수 선언에서는 가능합니다.  
  
-   구조체는 <xref:System.ValueType?displayProperty=fullName> 클래스로부터 암시적으로 상속할 수 있고 다른 형식으로부터는 상속할 수 없습니다. 반면 클래스는 <xref:System.ValueType?displayProperty=fullName>을 제외한 모든 클래스로부터 상속할 수 있습니다.  
  
-   구조체는 상속되지 않지만 클래스는 상속됩니다.  
  
-   구조체는 절대 종료되지 않으므로 CLR\(공용 언어 런타임\)은 어떠한 구조체에서도 <xref:System.Object.Finalize%2A> 메서드를 호출하지 않습니다. 반면 클래스는 남아 있는 활성 참조가 없다는 것이 감지될 때 클래스에 대해 <xref:System.Object.Finalize%2A>를 호출하는 GC\(가비지 수집기\)에 의해 종료됩니다.  
  
-   구조체에는 생성자가 필요하지 않지만 클래스에는 생성자가 필요합니다.  
  
-   구조체는 매개 변수가 사용되는 경우에만 비공유 생성자를 가질 수 있지만 클래스는 매개 변수의 유무에 관계없이 비공유 생성자를 가질 수 있습니다.  
  
 모든 구조체는 매개 변수가 없는 암시적인 공용 생성자를 갖습니다.  이 생성자는 구조체의 모든 데이터 요소를 기본값으로 초기화합니다.  이 동작은 재정의할 수 없습니다.  
  
## 인스턴스 및 변수  
 구조체는 값 형식이므로 각 구조체 변수는 영구적으로 개별 구조체 인스턴스에 바인딩됩니다.  그러나 클래스는 참조 형식이며 개체 변수는 시기에 따라 다양한 클래스 인스턴스를 참조할 수 있습니다.  이러한 차이점은 구조체 및 클래스의 사용에 다음과 같은 영향을 줍니다.  
  
-   **초기화.** 구조체 변수에는 해당 구조체의 매개 변수 없는 생성자를 사용한 요소의 초기화가 암시적으로 포함됩니다.  따라서 `Dim s As struct1`은 `Dim s As struct1 = New struct1()`과 같습니다.  
  
-   **변수 할당.** 구조체 변수에 다른 구조체 변수를 할당하거나 구조체 인스턴스를 프로시저 인수로 전달할 경우 모든 변수 요소의 현재 값이 새 구조체로 복사됩니다.  개체 변수에 다른 개체 변수를 할당하거나 개체 변수를 프로시저로 전달할 경우에는 해당 참조 포인터만 복사됩니다.  
  
-   **Nothing 할당.** [Nothing](../../../../visual-basic/language-reference/nothing.md) 값을 구조체 변수에 할당할 수 있지만 해당 인스턴스는 변수와의 연결 상태를 계속 유지합니다.  할당을 통하여 변수 요소가 다시 초기화되어도 계속 해당 메서드를 호출하고 해당 데이터 요소에 액세스할 수 있습니다.  
  
     반대로 개체 변수를 `Nothing`으로 설정하면 클래스 인스턴스로부터 분리되므로 변수에 다른 인스턴스를 할당할 때까지 변수를 통하여 멤버에 액세스할 수 없습니다.  
  
-   **여러 인스턴스.** 개체 변수는 각기 다른 시기에 할당된 서로 다른 클래스 인스턴스를 가질 수 있으며 여러 개의 개체 변수가 동시에 같은 클래스 인스턴스를 참조할 수 있습니다.  클래스 멤버 값에 대한 변경 사항은 같은 인스턴스를 가리키는 다른 변수를 통하여 액세스할 때 멤버에 영향을 줍니다.  
  
     그러나 구조체 요소는 자체 인스턴스 내에 격리됩니다.  멤버 값에 대한 변경 사항은 같은 `Structure` 선언의 다른 인스턴스에 있는 변수를 포함하여 다른 구조체 변수에는 적용되지 않습니다.  
  
-   **일치.** 두 구조체에 대한 일치 테스트는 요소 단위로 수행되어야 합니다.  <xref:System.Object.Equals%2A> 메서드를 사용하여 두 개체 변수를 비교할 수 있습니다.  <xref:System.Object.Equals%2A>는 두 변수가 같은 인스턴스를 가리키는지 여부를 나타냅니다.  
  
## 참고 항목  
 [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)   
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Structures](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Structures and Other Programming Elements](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)   
 [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)