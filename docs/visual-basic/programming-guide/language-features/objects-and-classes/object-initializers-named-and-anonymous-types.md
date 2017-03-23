---
title: "개체 이니셜라이저: 명명 된 형식과 익명 형식 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ObjectInitializer
dev_langs:
- VB
helpviewer_keywords:
- object initializers [Visual Basic]
- anonymous types [Visual Basic], object initializers
- initializing properties [Visual Basic]
- initializers [Visual Basic]
- named types [Visual Basic]
ms.assetid: e2df3807-a70f-49dd-ac94-f1e07f472b1b
caps.latest.revision: 27
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d684ad4f3dd47dc7400ea401a94660af832ef866
ms.lasthandoff: 03/13/2017

---
# <a name="object-initializers-named-and-anonymous-types-visual-basic"></a>개체 이니셜라이저: 명명된 형식과 익명 형식(Visual Basic)
개체 이니셜라이저를 사용 하는 단일 식을 사용 하 여 복잡 한 개체에 대 한 속성을 지정할 수 있습니다. 명명 된 형식의 및 익명 형식의 인스턴스를 만드는 데 사용할 수 있습니다.  
  
## <a name="declarations"></a>선언  
 명명 된 형식과 익명 형식의 인스턴스 선언은 수 거의 동일 보이지만 그 효과가 다릅니다. 각 범주에는 기능과 자체의 제한 사항이 있습니다. 다음 예제에서는 선언 하 고 명명된 된 클래스의 인스턴스를 초기화 하는 편리한 방법을 `Customer`, 개체 이니셜라이저 목록을 사용 하 여 합니다. 키워드 다음에 클래스의 이름을 지정 됩니다 `New`합니다.  
  
 [!code-vb[VbVbalrObjectInit #&1;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_1.vb)]  
  
 익명 형식에 사용할 수 있는 이름이 없습니다. 따라서 익명 형식의 인스턴스는 클래스 이름을 포함할 수 없습니다.  
  
 [!code-vb[VbVbalrObjectInit #&2;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_2.vb)]  
  
 두 선언이의 결과 요구 사항을 동일 하지 않으면. 에 대 한 `namedCust`, `Customer` 있는 클래스는 `Name` 속성 이미 있어야 하며, 선언을 해당 클래스의 인스턴스를 만듭니다. 에 대 한 `anonymousCust`, 하나의 속성을 호출 하는 문자열에 있는 새 클래스를 정의 하는 컴파일러 `Name`, 해당 클래스의 새 인스턴스를 만듭니다.  
  
## <a name="named-types"></a>명명 된 형식  
 개체 이니셜라이저는 형식의 생성자를 호출 하 고 다음 단일 문을 일부 또는 모든 속성의 값을 설정 하는 간단한 방법을 제공 합니다. 문에 대 한 적절 한 생성자를 호출 하는 컴파일러: 기본 생성자는 인수가 없는 제공한 또는 하나 이상의 인수를 전송 하는 경우 매개 변수화 된 생성자입니다. 그런 다음 이니셜라이저 목록에 소개 된 순서에 지정된 된 속성 초기화 됩니다.  
  
 이니셜라이저 목록에서 각 초기화 구성 클래스의 멤버에는 초기 값이 할당 됩니다. 클래스를 정의 하는 경우 이름, 멤버의 데이터 형식이 결정 됩니다. 다음 예제에서는 `Customer` 클래스 있어야 하며, 라는 멤버가 있어야 `Name` 및 `City` 문자열 값을 받아들일 수 있는 합니다.  
  
 [!code-vb[VbVbalrObjectInit #&3;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_3.vb)]  
  
 또는 다음 코드를 사용 하 여 동일한 결과 가져올 수 있습니다.  
  
 [!code-vb[VbVbalrObjectInit #&4;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_4.vb)]  
  
 만드는 다음 예제에 해당 하는 이러한 각 선언은 `Customer` 기본 생성자를 사용 하 여 개체를 다음에 대 한 초기 값을 지정는 `Name` 및 `City` 를 사용 하 여 속성을 `With` 문입니다.  
  
 [!code-vb[VbVbalrObjectInit #&5;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_5.vb)]  
  
 하는 경우는 `Customer` 클래스에 대 한 값에서을 보낼 수 있도록 매개 변수가 있는 생성자를 포함 `Name`, 예를 들어 수 또한 선언 하 고 초기화는 `Customer` 다음과 같은 방법으로 개체:  
  
 [!code-vb[VbVbalrObjectInit #&6;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_6.vb)]  
  
 다음 코드와 같이 모든 속성을 초기화할 필요가 없습니다.  
  
 [!code-vb[VbVbalrObjectInit #&7;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_7.vb)]  
  
 그러나 초기화 목록은 비워 둘 수 없습니다. 초기화 되지 않은 속성을 기본값으로 유지 합니다.  
  
### <a name="type-inference-with-named-types"></a>명명 된 형식으로 형식 유추  
 선언에 대 한 코드를 줄일 수 `cust1` 개체 이니셜라이저 및 지역 형식 유추를 결합 하 여 합니다. 생략 하면이 `As` 변수 선언 절. 변수의 데이터 형식은 할당 하 여 생성 된 개체의 형식에서 유추 됩니다. 다음 예에서 유형의 `cust6` 는 `Customer`합니다.  
  
 [!code-vb[VbVbalrObjectInit #&8;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_8.vb)]  
  
### <a name="remarks-about-named-types"></a>명명 된 형식에 대 한 설명  
  
-   클래스 멤버는 개체 이니셜라이저 목록에서 한 번 초기화할 수 없습니다. 선언 `cust7` 하면 오류가 발생 합니다.  
  
     [!code-vb[VbVbalrObjectInit #&9;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_9.vb)]  
  
-   자신 또는 다른 필드를 초기화 하는 멤버를 사용할 수 있습니다. 초기화 된에 대 한 다음 선언 처럼 전에 멤버에 액세스 하는 경우 `cust8`, 기본 값이 사용 됩니다. 개체 이니셜라이저를 사용 하는 선언을 처리 될 때 가장 먼저 발생 하는 주의 적절 한 생성자가 호출 됩니다. 그런 다음 이니셜라이저 목록에서 개별 필드 초기화 됩니다. 다음 예제에서의 기본값에 대 한 `Name` 에 대해 할당 `cust8`, 초기화 된 값에 할당 됩니다 `cust9`합니다.  
  
     [!code-vb[VbVbalrObjectInit #&10;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_10.vb)]  
  
     다음 예제에서는 매개 변수가 있는 생성자를 사용 하 여 `cust3` 및 `cust4` 선언 하 고 초기화 `cust10` 및 `cust11`합니다.  
  
     [!code-vb[VbVbalrObjectInit #&11;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_11.vb)]  
  
-   개체 이니셜라이저를 중첩할 수 있습니다. 다음 예에서 `AddressClass` 는 두 개의 속성이 있는 클래스 `City` 및 `State`, 및 `Customer` 클래스에는 `Address` 의 인스턴스가 속성 `AddressClass`합니다.  
  
     [!code-vb[VbVbalrObjectInit #&12;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_12.vb)]  
  
-   초기화 목록은 비워 둘 수 없습니다.  
  
-   초기화 되는 인스턴스 개체 형식일 수 없습니다.  
  
-   초기화 되는 클래스 멤버는 공유 멤버, 읽기 전용 멤버, 상수 또는 메서드 호출 수 없습니다.  
  
-   초기화 되는 클래스 멤버는 인덱싱된 하거나 한정 될 수 없습니다. 다음 예제에서는 컴파일러 오류가 발생 합니다.  
  
     `'' Not valid.`  
  
     `' Dim c1 = New Customer With {.OrderNumbers(0) = 148662}`  
  
     `' Dim c2 = New Customer with {.Address.City = "Springfield"}`  
  
## <a name="anonymous-types"></a>익명 형식  
 익명 형식을 명시적으로 정의 하지 않은 새 형식 및 이름을의 인스턴스를 만들 개체 이니셜라이저를 사용 합니다. 대신, 컴파일러는 개체 이니셜라이저 목록에서 지정한 속성에 따라 형식을 생성 합니다. 형식의 이름을 지정 되어 있지 않으므로 것 이라고는 *익명 형식*합니다. 예를 들어, 다음 선언을 대 한 이전에 비교 `cust6`합니다.  
  
 [!code-vb[VbVbalrObjectInit #&13;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_13.vb)]  
  
 구문적으로 다른 점은 없습니다 이름이 지정 되 면 `New` 데이터 형식에 대 한 합니다. 그러나 일어나는 크게 다릅니다. 컴파일러는 두 개의 속성이 있는 새 익명 형식을 정의 `Name` 및 `City`, 지정된 된 값을 사용 하 여 형식의 인스턴스를 만듭니다. 형식 유추의 종류를 결정 `Name` 및 `City` 예제 문자열 이어야 합니다.  
  
> [!CAUTION]
>  익명 형식의 이름은 컴파일러에 의해 생성 되 고 컴파일할 다를 수 있습니다. 코드 사용 하거나 익명 형식의 이름을 사용 해야 합니다.  
  
 사용할 수 없습니다 형식의 이름을 사용할 수 없어서는 `As` 선언 하는 절 `cust13`합니다. 해당 형식 유추 되어야 합니다. 런타임에 바인딩을 사용 하지 않고 지역 변수에 익명 형식의 사용이 제한 됩니다.  
  
 익명 형식에 대 한 중요 한 지원을 제공 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 쿼리 합니다. 쿼리에서 익명 형식 사용 하는 방법에 대 한 자세한 내용은 참조 하십시오. [익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) 및 [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)합니다.  
  
### <a name="remarks-about-anonymous-types"></a>익명 형식에 대 한 설명  
  
-   일반적으로 익명 형식 선언에서 속성의 전체 또는 대부분 됩니다 키워드를 입력 하 여 표시 되는 키 속성을 `Key` 속성 이름 앞에 있습니다.  
  
     [!code-vb[VbVbalrObjectInit #&14;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_14.vb)]  
  
     키 속성에 대 한 자세한 내용은 참조 [키](../../../../visual-basic/language-reference/modifiers/key.md)합니다.  
  
-   명명 된 형식과 마찬가지로, 이니셜라이저 목록에 익명 형식 정의 하나 이상의 속성을 선언 해야 합니다.  
  
     [!code-vb[VbVbalrObjectInit #&2;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_2.vb)]  
  
-   익명 형식의 인스턴스를 선언 하는 컴파일러는 일치 하는 익명 형식 정의 생성 합니다. 이름 및 속성의 데이터 형식을 인스턴스 선언에서 수행 되 고 정의에 컴파일러에 의해 포함 됩니다. 속성은 라는, 명명 된 형식에 대 한 것 처럼 미리 정의 되지 않습니다. 형식은 유추 됩니다. 속성의 데이터 형식을 사용 하 여 지정할 수 없습니다는 `As` 절.  
  
-   익명 형식 이름 및 해당 속성의 값 다른 여러 가지 방법으로 설정할 수 있습니다. 예를 들어, 익명 형식 속성의 이름 및 변수는 이름 또는 값과 다른 개체의 속성 값을 모두 걸릴 수 있습니다.  
  
     [!code-vb[VbVbalrObjectInit #&15;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_15.vb)]  
  
     익명 형식의 속성을 정의 하기 위한 옵션에 대 한 자세한 내용은 참조 [하는 방법: 익명 형식 선언에서 속성 이름 유추 및 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [방법: 익명 형식 선언에서 속성 이름 및 형식 유추](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)   
 [키](../../../../visual-basic/language-reference/modifiers/key.md)   
 [방법: 개체 이니셜라이저를 사용하여 개체 선언](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
