---
title: "Anonymous Types (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.AnonymousType"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "anonymous types [Visual Basic], about anonymous types"
  - "anonymous types [Visual Basic]"
  - "types [Visual Basic], anonymous"
ms.assetid: 7b87532c-4b3e-4398-8503-6ea9d67574a4
caps.latest.revision: 46
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 46
---
# Anonymous Types (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Visual Basic에서는 데이터 형식에 대한 클래스 정의를 작성하지 않고 개체를 만들 수 있는 익명 형식을 제공합니다.  대신 컴파일러가 클래스를 생성합니다.  이 클래스는 사용할 수 있는 이름이 없고 <xref:System.Object>에서 직접 상속하며 개체를 선언할 때 지정하는 속성을 포함합니다.  데이터 형식의 이름이 지정되지 않기 때문에 해당 형식을 *익명 형식*이라고 합니다.  
  
 다음 예제에서는 변수 `product`를 `Name` 및 `Price`라는 두 개의 속성을 가지는 익명 형식의 인스턴스로 선언하고 만듭니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#1](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_1.vb)]  
  
 *쿼리 식*에서는 익명 형식을 사용하여 쿼리에서 선택한 데이터 열을 결합합니다.  특정 쿼리에서 선택할 수 있는 열을 예측할 수 없으므로 결과 형식을 미리 정의할 수 없습니다.  익명 형식을 사용하면 열을 그 수나 순서에 제한 없이 선택하는 쿼리를 작성할 수 있습니다.  컴파일러에서 지정된 속성 및 지정된 순서와 일치하는 데이터 형식을 만듭니다.  
  
 다음 예제에서 `products`는 각각 많은 속성이 있는 제품 개체의 목록입니다.  `namePriceQuery` 변수는 실행할 경우 `Name` 및 `Price`라는 두 개의 속성을 가지는 익명 형식의 인스턴스 컬렉션을 반환하는 쿼리 정의를 보유합니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#2](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_2.vb)]  
  
 `nameQuantityQuery` 변수는 실행할 경우 `Name` 및 `OnHand`라는 두 개의 속성을 가지는 익명 형식의 인스턴스 컬렉션을 반환하는 쿼리 정의를 보유합니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#3](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_3.vb)]  
  
 컴파일러에서 익명 형식에 대해 만드는 코드에 대한 자세한 내용은 [Anonymous Type Definition](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)를 참조하십시오.  
  
> [!CAUTION]
>  익명 형식의 이름은 컴파일러에서 생성되며 컴파일할 때마다 달라질 수 있습니다.  프로젝트를 다시 컴파일하면 이름이 변경될 수 있으므로 사용자 코드에서 익명 형식의 이름을 사용하거나 이에 의존해서는 안 됩니다.  
  
## 익명 형식 선언  
 익명 형식의 인스턴스에 대한 선언에서는 이니셜라이저 목록을 사용하여 해당 형식의 속성을 지정합니다.  익명 형식을 선언할 때는 속성만 지정할 수 있고 메서드나 이벤트와 같은 다른 클래스 요소는 지정할 수 없습니다.  다음 예제에서 `product1`은 `Name` 및 `Price`라는 두 개의 속성을 가지는 익명 형식의 인스턴스입니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#4](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_4.vb)]  
  
 속성을 키 속성으로 지정하면 해당 속성을 사용하여 두 개의 익명 형식 인스턴스가 같은지 비교할 수 있습니다.  그러나 키 속성 값은 변경할 수 없습니다.  자세한 내용은 이 항목의 뒷부분에서 키 속성 단원을 참조하십시오.  
  
 익명 형식의 인스턴스를 선언하는 것은 개체 이니셜라이저를 사용하여 명명된 형식의 인스턴스를 선언하는 것과 유사합니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#5](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_5.vb)]  
  
 익명 형식 속성을 지정하는 다른 방법에 대한 자세한 내용은 [방법: 익명 형식 선언에서 속성 이름 및 형식 유추](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)를 참조하십시오.  
  
## 키 속성  
 키 속성은 키가 아닌 속성과 다음과 같이 몇 가지 기본적인 면에서 차이가 납니다.  
  
-   두 인스턴스가 같은지 확인하기 위해 키 속성의 값만 비교합니다.  
  
-   키 속성 값은 읽기 전용이며 변경할 수 없습니다.  
  
-   익명 형식에 대한 컴파일러 생성 해시 코드 알고리즘에는 키 속성 값만 포함됩니다.  
  
### 같음  
 익명 형식의 인스턴스는 같은 익명 형식의 인스턴스인 경우에만 같을 수 있습니다.  컴파일러에서는 다음 조건에 해당하는 경우 두 인스턴스를 같은 형식의 인스턴스로 처리합니다.  
  
-   동일한 어셈블리에서 선언됩니다.  
  
-   해당 속성이 동일한 이름과 유추된 형식을 갖고 같은 순서로 선언됩니다.  이름을 비교할 때 대\/소문자를 구분하지 않습니다.  
  
-   각 인스턴스에서 동일한 속성이 키 속성으로 표시됩니다.  
  
-   각 선언에서 한 개 이상의 속성이 키 속성입니다.  
  
 키 속성이 없는 익명 형식의 인스턴스는 자신하고만 같습니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#6](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_6.vb)]  
  
 동일한 익명 형식의 두 인스턴스는 해당 키 속성의 값이 같은 경우 같습니다.  다음 예제에서는 두 인스턴스가 같은지 테스트하는 방법을 보여 줍니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#7](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_7.vb)]  
  
### 읽기 전용 값  
 키 속성의 값은 변경할 수 없습니다.  예를 들어 위 예제의 `prod8`에서 `Name` 및 `Price` 필드는 `read-only`이지만 `OnHand`는 변경할 수 있습니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#8](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_8.vb)]  
  
## 쿼리 식의 익명 형식  
 쿼리 식에서 항상 익명 형식을 만들어야 하는 것은 아닙니다.  가능한 경우 기존 형식을 사용하여 열 데이터를 저장합니다.  쿼리에서 데이터 소스의 전체 레코드를 반환하거나 각 레코드의 필드 하나만 반환하는 경우에 이렇게 합니다.  다음 코드 예제에서 `customers`는 `Customer` 클래스 개체의 컬렉션입니다.  이 클래스에는 많은 속성이 있으며 이들 속성 중 하나 이상을 쿼리 결과에 원하는 순서로 포함할 수 있습니다.  처음 두 예제에서는 쿼리에서 명명된 형식의 요소를 선택하므로 익명 형식이 필요하지 않습니다.  
  
-   `cust.Name`은 문자열이므로 `custs1`에는 문자열의 컬렉션이 포함됩니다.  
  
     [!code-vb[VbVbalrAnonymousTypes#30](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_9.vb)]  
  
-   `customers`의 각 요소는 `Customer` 개체이고 쿼리에서 전체 요소를 선택하므로 `custs2`에는 `Customer` 개체의 컬렉션이 포함됩니다.  
  
     [!code-vb[VbVbalrAnonymousTypes#31](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_10.vb)]  
  
 그러나 적절한 명명된 형식을 항상 사용할 수 있는 것은 아닙니다.  어떤 경우에는 고객 이름과 주소를 선택하고, 다른 경우에는 고객 ID 번호와 위치를 선택하며, 또 다른 경우에는 고객 이름, 주소 및 주문 기록을 선택할 수 있습니다.  익명 형식을 사용하면 결과를 저장할 명명된 형식을 먼저 선언하지 않고도 원하는 속성 조합을 임의의 순서로 선택할 수 있습니다.  대신 컴파일러에서 각 속성을 컴파일할 때 익명 형식을 만듭니다.  다음 쿼리에서는 `customers`의 각 `Customer` 개체에서 고객 이름과 ID 번호만 선택합니다.  따라서 컴파일러에서는 이러한 두 속성만 포함하는 익명 형식을 만듭니다.  
  
 [!code-vb[VbVbalrAnonymousTYpes#32](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_11.vb)]  
  
 익명 형식에서 속성의 이름과 데이터 형식은 모두 `Select`, `cust.Name` 및 `cust.ID`에 대한 인수에서 가져옵니다.  쿼리에서 만드는 익명 형식의 속성은 항상 키 속성입니다.  `custs3`을 다음과 같은 `For Each` 루프에서 실행하면 `Name` 및 `ID`라는 두 개의 키 속성이 있는 익명 형식의 인스턴스 클래스가 생성됩니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#33](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_12.vb)]  
  
 `custs3`이 나타내는 컬렉션의 요소는 강력한 형식을 가지고 있으며 IntelliSense를 사용하여 사용 가능한 속성을 탐색하고 해당 형식을 확인할 수 있습니다.  
  
 자세한 내용은 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)를 참조하십시오.  
  
## 익명 형식을 사용할지 여부 결정  
 개체를 익명 클래스의 인스턴스로 만들기 전에 이렇게 하는 것이 최선인지 검토합니다.  예를 들어 관련 데이터를 포함할 임시 개체를 만들 때 전체 클래스에 포함될 수 있는 다른 필드와 메서드는 필요하지 않은 경우 익명 형식을 사용하는 것이 좋습니다.  또한 각 선언에 대해 다른 속성을 선택하거나 속성 순서를 변경하려는 경우에 익명 형식을 사용하면 편리합니다.  그러나 같은 속성을 고정된 순서로 지니는 여러 개체가 프로젝트에 포함되는 경우 클래스 생성자와 함께 명명된 형식을 사용하면 이러한 개체를 쉽게 선언할 수 있습니다.  예를 들어 해당 생성자에서 `Product` 클래스의 여러 인스턴스를 선언하는 것이 익명 형식의 여러 인스턴스를 선언하는 것보다 수월합니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#9](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_13.vb)]  
  
 명명된 형식의 다른 이점은 실수로 잘못 입력한 속성 이름을 컴파일러가 찾아낼 수 있다는 것입니다.  앞의 예제에서 `firstProd2`, `secondProd2` 및 `thirdProd2`는 같은 익명 형식의 인스턴스입니다.  그러나 실수로 `thirdProd2`를 다음과 같은 방법 중 하나로 선언하면 그 형식이 `firstProd2` 및 `secondProd2`와 달라집니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#10](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_14.vb)]  
  
 더욱이 명명된 형식의 인스턴스에 적용되지 않는 익명 형식은 사용에 제한이 있습니다.  `firstProd2`, `secondProd2` 및 `thirdProd2`는 동일한 익명 형식의 인스턴스입니다.  그러나 공유 익명 형식의 이름은 사용할 수 없으며 코드에서 형식 이름이 있어야 하는 위치에 나타날 수 없습니다.  예를 들어 익명 형식은 메서드 시니그처를 정의하거나 다른 변수 또는 필드를 선언하는 데 사용할 수 있으며 형식 선언에서도 사용할 수 없습니다.  따라서 메서드 간에 정보를 공유해야 하는 경우에는 익명 형식이 적절하지 않습니다.  
  
## 익명 형식 정의  
 익명 형식의 인스턴스 선언에 대한 응답으로 컴파일러에서는 지정된 속성을 포함하는 새 클래스 정의를 만듭니다.  
  
 익명 형식 선언에 적어도 하나의 키 속성이 포함되어 있으면 형식 정의에서는 <xref:System.Object> <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, 및 <xref:System.Object.ToString%2A>에서 상속된 세 개의 멤버를 재정의합니다.  같음을 테스트하고 해시 코드 값을 판별하기 위해 만든 코드에서는 키 속성만 고려합니다.  익명 형식에 키 속성이 없으면 <xref:System.Object.ToString%2A>만 재정의됩니다.  명시적으로 명명된 익명 형식 속성은 이러한 생성된 메서드와 충돌하지 않습니다.  즉, `.Equals`, `.GetHashCode` 또는 `.ToString`을 사용하여 속성의 이름을 지정할 수 없습니다.  
  
 적어도 하나의 키 속성이 있는 익명 형식 정의에서는 <xref:System.IEquatable%601?displayProperty=fullName> 인터페이스도 구현합니다. 여기에서 `T`는 익명 형식의 형식입니다.  
  
 컴파일러에서 만드는 코드와 재정의된 메서드의 기능에 대한 자세한 내용은 [Anonymous Type Definition](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)를 참조하십시오.  
  
## 참고 항목  
 [Object Initializers: Named and Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [방법: 익명 형식 선언에서 속성 이름 및 형식 유추](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)   
 [Anonymous Type Definition](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)   
 [Key](../../../../visual-basic/language-reference/modifiers/key.md)