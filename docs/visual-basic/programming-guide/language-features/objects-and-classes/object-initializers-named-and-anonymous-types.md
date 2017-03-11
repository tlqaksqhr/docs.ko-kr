---
title: "Object Initializers: Named and Anonymous Types (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.ObjectInitializer"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "object initializers [Visual Basic]"
  - "anonymous types [Visual Basic], object initializers"
  - "initializing properties [Visual Basic]"
  - "initializers [Visual Basic]"
  - "named types [Visual Basic]"
ms.assetid: e2df3807-a70f-49dd-ac94-f1e07f472b1b
caps.latest.revision: 27
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 27
---
# Object Initializers: Named and Anonymous Types (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

개체 이니셜라이저를 사용하면 단일 식으로 복잡한 개체의 속성을 지정할 수 있습니다.  개체 이니셜라이저를 사용하여 명명된 형식과 익명 형식의 인스턴스를 만들 수 있습니다.  
  
## Declarations  
 명명된 형식과 익명 형식의 인스턴스 선언은 거의 동일해 보일 수 있지만 그 결과는 동일하지 않습니다.  각 범주에는 해당하는 기능과 제한 사항이 있습니다.  다음 예제에서는 개체 이니셜라이저 목록을 사용하여 명명된 클래스 `Customer`의 인스턴스를 선언하고 초기화하는 편리한 방법을 보여 줍니다.  클래스 이름은 `New` 키워드 뒤에 지정됩니다.  
  
 [!code-vb[VbVbalrObjectInit#1](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/object-initializers-name_1.vb)]  
  
 익명 형식에는 사용할 수 있는 이름이 없습니다.  따라서 익명 형식의 인스턴스는 클래스 이름을 포함할 수 없습니다.  
  
 [!code-vb[VbVbalrObjectInit#2](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/object-initializers-name_2.vb)]  
  
 두 선언의 요구 사항과 결과는 동일하지 않습니다.  `namedCust`의 경우 `Name` 속성을 가진 `Customer` 클래스가 이미 있어야 하며 선언에서 해당 클래스의 인스턴스를 만듭니다.  `anonymousCust`의 경우 컴파일러에서 `Name`이라는 문자열인 하나의 속성을 가진 새 클래스를 정의하고 해당 클래스의 새 인스턴스를 만듭니다.  
  
## 명명된 형식  
 개체 이니셜라이저를 사용하면 특정 형식의 생성자를 호출한 다음 일부 또는 모든 속성의 값을 설정하는 작업을 단일 문으로 간단하게 수행할 수 있습니다.  컴파일러는 문에 적합한 생성자를 호출합니다. 인수를 지정하지 않으면 기본 생성자를 호출하고 하나 이상의 인수를 보내면 매개 변수가 있는 생성자를 호출합니다.  그런 후에 이니셜라이저 목록에 표시되는 순서대로 지정한 속성이 초기화됩니다  
  
 이니셜라이저 목록의 각 초기화는 클래스 멤버에 초기 값을 할당하는 작업으로 구성됩니다.  멤버의 이름과 데이터 형식은 클래스를 정의할 때 결정됩니다.  다음 예제에서는 `Customer` 클래스가 있어야 하며, 이 클래스에는 문자열 값을 받아들일 수 있는 `Name` 및 `City`라는 멤버가 있어야 합니다.  
  
 [!code-vb[VbVbalrObjectInit#3](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/object-initializers-name_3.vb)]  
  
 또는 다음 코드를 사용하여 동일한 결과를 얻을 수도 있습니다.  
  
 [!code-vb[VbVbalrObjectInit#4](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/object-initializers-name_4.vb)]  
  
 이러한 각 선언은 기본 생성자를 사용하여 `Customer` 개체를 만든 다음 `With` 문을 사용하여 `Name` 및 `City` 속성의 초기 값을 지정하는 다음 예제와 같습니다.  
  
 [!code-vb[VbVbalrObjectInit#5](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/object-initializers-name_5.vb)]  
  
 예를 들어 `Customer` 클래스가 `Name`의 값으로 보낼 수 있는 매개 변수가 있는 생성자를 포함하는 경우 다음과 같은 방법으로 `Customer` 개체를 선언하고 초기화할 수도 있습니다.  
  
 [!code-vb[VbVbalrObjectInit#6](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/object-initializers-name_6.vb)]  
  
 다음 코드와 같이 모든 속성을 초기화할 필요는 없습니다.  
  
 [!code-vb[VbVbalrObjectInit#7](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/object-initializers-name_7.vb)]  
  
 그러나 초기화 목록이 비어 있으면 안 됩니다.  초기화되지 않은 속성은 해당 기본값을 유지합니다.  
  
### 명명된 형식을 사용하여 형식 유추  
 개체 이니셜라이저와 지역 형식 유추를 결합하여 `cust1`의 선언을 위한 코드를 줄일 수 있습니다.  이렇게 하면 변수 선언에서 `As` 절을 생략할 수 있습니다.  변수의 데이터 형식은 할당에 의해 만들어진 개체의 형식에서 유추됩니다.  다음 예제에서 `cust6`의 형식은 `Customer`입니다.  
  
 [!code-vb[VbVbalrObjectInit#8](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/object-initializers-name_8.vb)]  
  
### 명명된 형식에 대한 설명  
  
-   개체 이니셜라이저 목록에서 클래스 멤버를 두 번 이상 초기화할 수 없습니다.  `cust7`의 선언에서 오류가 발생합니다.  
  
     [!code-vb[VbVbalrObjectInit#9](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/object-initializers-name_9.vb)]  
  
-   멤버를 사용하여 해당 멤버나 다른 필드를 초기화할 수 있습니다.  `cust8`에 대한 다음 선언과 같이 초기화되기 전에 멤버에 액세스하면 기본값이 사용됩니다.  개체 이니셜라이저를 사용하는 선언을 처리하는 경우 먼저 해당 생성자가 호출됩니다.  그런 후에 이니셜라이저 목록의 개별 필드가 초기화됩니다.  다음 예제에서는 `Name`의 기본값이 `cust8`에 대해 할당되고 초기화된 값이 `cust9`에 할당됩니다.  
  
     [!code-vb[VbVbalrObjectInit#10](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/object-initializers-name_10.vb)]  
  
     다음 예제에서는 `cust3` 및 `cust4`의 매개 변수가 있는 생성자를 사용하여 `cust10` 및 `cust11`을 선언하고 초기화합니다.  
  
     [!code-vb[VbVbalrObjectInit#11](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/object-initializers-name_11.vb)]  
  
-   개체 이니셜라이저는 중첩될 수 있습니다.  다음 예제에서 `AddressClass`는 두 개의 속성, `City`와 `State`를 포함하는 클래스이고 `Customer` 클래스에는 `AddressClass`의 인스턴스인 `Address` 속성이 있습니다.  
  
     [!code-vb[VbVbalrObjectInit#12](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/object-initializers-name_12.vb)]  
  
-   초기화 목록이 비어 있으면 안 됩니다.  
  
-   초기화되는 인스턴스는 Object 형식일 수 없습니다.  
  
-   초기화되는 클래스 멤버는 공유 멤버, 읽기 전용 멤버, 상수 또는 메서드 호출일 수 없습니다.  
  
-   초기화되는 클래스 멤버는 인덱싱하거나 정규화할 수 없습니다.  다음 예제에서는 컴파일러 오류가 발생합니다.  
  
     `'' Not valid.`  
  
     `' Dim c1 = New Customer With {.OrderNumbers(0) = 148662}`  
  
     `' Dim c2 = New Customer with {.Address.City = "Springfield"}`  
  
## 익명 형식  
 익명 형식은 개체 이니셜라이저를 사용하여 명시적으로 정의하고 명명하지 않는 새 형식의 인스턴스를 만듭니다.  대신 컴파일러가 개체 이니셜라이저 목록에서 지정한 속성에 따라 형식을 생성합니다.  형식의 이름이 지정되지 않았으므로 해당 형식을 *익명 형식*이라고 합니다.  예를 들어 다음 선언을 `cust6`에 대한 이전 선언과 비교해 보십시오.  
  
 [!code-vb[VbVbalrObjectInit#13](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/object-initializers-name_13.vb)]  
  
 유일한 구문상의 차이점은 `New` 다음에 데이터 형식의 이름이 지정되지 않는다는 점입니다.  그러나 결과는 완전히 다릅니다.  컴파일러는 두 개의 속성, `Name`과 `City`가 있는 새 익명 형식을 정의하고 지정된 값으로 해당 인스턴스를 만듭니다.  이 예제에서 `Name`과 `City`의 형식은 형식 유추에 의해 문자열로 결정됩니다.  
  
> [!CAUTION]
>  익명 형식의 이름은 컴파일러에서 생성되며 컴파일할 때마다 달라질 수 있습니다.  코드에서 익명 형식의 이름을 사용하거나 의존하면 안 됩니다.  
  
 형식의 이름을 사용할 수 없으므로 `As` 절을 사용하여 `cust13`을 선언할 수 없습니다.  해당 형식은 유추되어야 합니다.  따라서 런타임에 바인딩을 사용하지 않는 경우 지역 변수에만 익명 형식을 사용할 수 있습니다.  
  
 익명 형식은 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] 쿼리에 대한 중요한 지원을 제공합니다.  쿼리에서 익명 형식을 사용하는 방법에 대한 자세한 내용은 [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) 및 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)를 참조하십시오.  
  
### 익명 형식에 대한 설명  
  
-   일반적으로 익명 형식 선언의 속성은 모두 또는 대부분 키 속성이며, `Key` 키워드를 속성 이름 앞에 입력하여 표시됩니다.  
  
     [!code-vb[VbVbalrObjectInit#14](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/object-initializers-name_14.vb)]  
  
     키 속성에 대한 자세한 내용은 [Key](../../../../visual-basic/language-reference/modifiers/key.md)를 참조하십시오.  
  
-   명명된 형식과 마찬가지로 익명 형식 정의에 대한 이니셜라이저 목록에서 속성을 하나 이상 선언해야 합니다.  
  
     [!code-vb[VbVbalrObjectInit#2](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/object-initializers-name_2.vb)]  
  
-   익명 형식의 인스턴스를 선언하면 컴파일러에서 일치하는 익명 형식 정의를 생성합니다.  속성의 이름과 데이터 형식은 인스턴스 선언에서 가져오며 컴파일러에 의해 정의에 포함됩니다.  명명된 형식의 경우와 달리 속성이 미리 명명되고 정의되지 않습니다.  속성의 형식은 유추됩니다.  `As` 절을 사용하여 속성의 데이터 형식을 지정할 수 없습니다.  
  
-   익명 형식은 다른 여러 방법으로 속성의 이름과 값을 설정할 수도 있습니다.  예를 들어 익명 형식 속성은 변수의 이름과 값을 모두 사용하거나 다른 개체의 속성 이름과 값을 사용할 수 있습니다.  
  
     [!code-vb[VbVbalrObjectInit#15](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/object-initializers-name_15.vb)]  
  
     익명 형식의 속성 정의 옵션에 대한 자세한 내용은 [방법: 익명 형식 선언에서 속성 이름 및 형식 유추](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)를 참조하십시오.  
  
## 참고 항목  
 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [방법: 익명 형식 선언에서 속성 이름 및 형식 유추](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)   
 [Key](../../../../visual-basic/language-reference/modifiers/key.md)   
 [How to: Declare an Object by Using an Object Initializer](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)