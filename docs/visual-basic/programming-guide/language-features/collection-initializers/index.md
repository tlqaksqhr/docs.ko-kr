---
title: "Collection Initializers (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.CollectionInitializer"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "collection initializers [Visual Basic]"
ms.assetid: a9290329-77b0-4fdf-ae75-8fc17287f469
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 23
---
# Collection Initializers (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

*컬렉션 이니셜라이저*에서는 컬렉션을 만들고 초기 값 집합으로 채울 수 있는 약식 구문을 제공합니다.  컬렉션 이니셜라이저는 메뉴 옵션 또는 범주 목록, 초기 숫자 값 집합, 정적 문자열 목록\(예: 일 또는 월 이름\), 지리적 위치\(예: 유효성 검사에 사용되는 상태 목록\) 등과 같은 알려진 값 집합에서 컬렉션을 만드는 경우에 유용합니다.  
  
 컬렉션에 대한 자세한 내용은 [컬렉션](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md)를 참조하십시오.  
  
 컬렉션 이니셜라이저는 `From` 키워드 다음에 중괄호\(`{}`\)를 사용하여 식별합니다.  이는 [배열](../../../../visual-basic/programming-guide/language-features/arrays/index.md)에서 설명한 배열 리터럴 구문과 비슷합니다.  다음 예제에서는 컬렉션 이니셜라이저를 사용하여 컬렉션을 만드는 여러 가지 방법을 보여 줍니다.  
  
 [!code-vb[VbVbalrCollectionInitializers#1](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/visualbasic/index_1.vb)]  
  
> [!NOTE]
>  C\#에서도 컬렉션 이니셜라이저가 제공됩니다.  C\# 컬렉션 이니셜라이저는 Visual Basic 컬렉션 이니셜라이저와 동일한 기능을 제공합니다.  C\# 컬렉션 이니셜라이저에 대한 자세한 내용은 [개체 및 컬렉션 이니셜라이저](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)를 참조하십시오.  
  
## 구문  
 컬렉션 이니셜라이저는 다음 코드와 같이 `From` 키워드 다음에 쉼표로 구분되고 중괄호\(`{}`\)로 묶인 값 목록으로 구성됩니다.  
  
 [!code-vb[VbVbalrCollectionInitializers#2](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/visualbasic/index_2.vb)]  
  
 <xref:System.Collections.Generic.List%601> 또는 <xref:System.Collections.Generic.Dictionary%602>와 같은 컬렉션을 만들 경우에는 다음 코드에서와 같이 컬렉션 이니셜라이저 앞에 컬렉션 형식을 제공해야 합니다.  
  
 [!code-vb[VbVbalrCollectionInitializers#13](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/visualbasic/index_3.vb)]  
  
> [!NOTE]
>  같은 컬렉션 개체를 초기화하기 위해 컬렉션 이니셜라이저와 개체 이니셜라이저를 결합할 수 없습니다.  개체 이니셜라이저를 사용하여 컬렉션 이니셜라이저의 개체를 초기화할 수 있습니다.  
  
## 컬렉션 이니셜라이저를 사용하여 컬렉션 만들기  
 컬렉션 이니셜라이저를 사용하여 컬렉션을 만들 경우 컬렉션 이니셜라이저에 제공된 각 값은 컬렉션의 해당 `Add` 메서드로 전달됩니다.  예를 들어, 컬렉션 이니셜라이저를 사용하여 <xref:System.Collections.Generic.List%601>을 만들 경우 컬렉션 이니셜라이저의 각 문자열 값은 <xref:System.Collections.Generic.List%601.Add%2A> 메서드로 전달됩니다.  컬렉션 이니셜라이저를 사용하여 컬렉션을 만들 경우에는 지정한 형식이 유효한 컬렉션 형식이어야 합니다.  유효한 컬렉션 형식의 예로는 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스를 구현하거나 <xref:System.Collections.CollectionBase> 클래스를 상속한 클래스가 있습니다.  지정된 형식은 또한 다음 조건을 충족하는 `Add` 메서드를 노출해야 합니다.  
  
-   `Add` 메서드는 컬렉션 이니셜라이저가 호출되는 범위에서 사용할 수 있어야 합니다.  컬렉션의 public이 아닌 메서드에 액세스할 수 있는 시나리오에서 컬렉션 이니셜라이저를 사용할 경우에는 `Add` 메서드가 public이 아니어도 됩니다.  
  
-   `Add` 메서드는 컬렉션 클래스의 인스턴스 멤버 또는 `Shared` 멤버이거나 확장 메서드여야 합니다.  
  
-   오버로드 확인 규칙에 따라 컬렉션 이니셜라이저에서 제공되는 형식과 일치할 수 있도록 `Add` 메서드가 존재해야 합니다.  
  
 예를 들어, 다음 코드 예제에서는 컬렉션 이니셜라이저를 사용하여 `List(Of Customer)` 컬렉션을 만드는 방법을 보여 줍니다.  코드를 실행하면 각 `Customer` 개체가 제네릭 목록의 `Add(Customer)` 메서드로 전달됩니다.  
  
 [!code-vb[VbVbalrCollectionInitializers#9](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/visualbasic/index_4.vb)]  
  
 다음 코드 예제에서는 컬렉션 이니셜라이저를 사용하지 않으면서 동일한 기능을 제공하는 코드를 보여 줍니다.  
  
 [!code-vb[VbVbalrCollectionInitializers#10](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/visualbasic/index_5.vb)]  
  
 컬렉션의 `Add` 메서드에 `Customer` 개체의 생성자와 일치하는 매개 변수가 있는 경우 컬렉션 이니셜라이저 내에서 `Add` 메서드의 매개 변수 값을 중첩시킬 수 있습니다. 이에 대한 설명은 다음 단원에서 제공합니다.  컬렉션에 이와 같은 `Add` 메서드가 없는 경우 이 메서드를 확장 메서드로 만들 수 있습니다.  `Add` 메서드를 컬렉션의 확장 메서드로 만드는 방법의 예제를 보려면 [How to: Create an Add Extension Method Used by a Collection Initializer](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)를 참조하십시오.  컬렉션 이니셜라이저와 함께 사용할 수 있는 사용자 지정 컬렉션을 만드는 방법의 예제를 보려면 [How to: Create a Collection Used by a Collection Initializer](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)를 참조하십시오.  
  
## 컬렉션 이니셜라이저 중첩  
 만들고 있는 컬렉션에 대한 `Add` 메서드의 특정 오버로드를 식별하기 위해 컬렉션 이니셜라이저 내에서 값을 중첩시킬 수 있습니다.  `Add` 메서드로 전달되는 값은 배열 리터럴이나 컬렉션 이니셜라이저에서와 같이 쉼표로 구분하고 중괄호\(`{}`\)로 묶어야 합니다.  
  
 중첩된 값을 사용하여 컬렉션을 만들 경우 중첩된 값 목록의 각 요소는 해당 요소 형식과 일치하는 `Add` 메서드에 대한 인수로 전달됩니다.  예를 들어, 다음 코드 예제에서는 키 형식이 `Integer`이고 값 형식이 `String`인 <xref:System.Collections.Generic.Dictionary%602>를 만듭니다.  각각의 중첩된 값 목록은 `Dictionary`의 <xref:System.Collections.Generic.Dictionary%602.Add%2A> 메서드와 일치합니다.  
  
 [!code-vb[VbVbalrCollectionInitializers#5](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/visualbasic/index_6.vb)]  
  
 이전 코드 예제는 다음 코드와 동일합니다.  
  
 [!code-vb[VbVbalrCollectionInitializers#6](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/visualbasic/index_7.vb)]  
  
 첫 번째 중첩 수준의 중첩된 값 목록만 컬렉션 형식의 `Add` 메서드에 전달됩니다.  보다 깊은 중첩 수준은 배열 리터럴로 간주되기 때문에 중첩된 값 목록이 컬렉션의 `Add` 메서드와 일치하지 않습니다.  
  
## 관련 항목  
  
|||  
|-|-|  
|제목|설명|  
|[How to: Create an Add Extension Method Used by a Collection Initializer](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)|라고 하는 확장 메서드를 작성 하는 방법을 보여 줍니다. `Add` 컬렉션 컬렉션 이니셜라이저 값으로 채우는 데 사용할 수 있습니다.|  
|[How to: Create a Collection Used by a Collection Initializer](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)|포함 하 여 컬렉션 이니셜라이저를 사용 하는 방법을 보여 줍니다 있는 `Add` 메서드를 구현 하는 컬렉션 클래스에 `IEnumerable`.|  
  
## 참고 항목  
 [컬렉션](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md)   
 [배열](../../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [Object Initializers: Named and Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md)   
 [Auto\-Implemented Properties](../../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)   
 [How to: Initialize an Array Variable in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)   
 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)