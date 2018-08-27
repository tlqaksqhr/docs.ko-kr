---
title: '개체 이니셜라이저: 명명된 형식과 익명 형식(Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.ObjectInitializer
helpviewer_keywords:
- object initializers [Visual Basic]
- anonymous types [Visual Basic], object initializers
- initializing properties [Visual Basic]
- initializers [Visual Basic]
- named types [Visual Basic]
ms.assetid: e2df3807-a70f-49dd-ac94-f1e07f472b1b
ms.openlocfilehash: 612b1dcea0f776dfd4580803e76f2785e7d28da6
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42930592"
---
# <a name="object-initializers-named-and-anonymous-types-visual-basic"></a>개체 이니셜라이저: 명명된 형식과 익명 형식(Visual Basic)
개체 이니셜라이저를 사용 하는 단일 식을 사용 하 여 복잡 한 개체에 대 한 속성을 지정할 수 있습니다. 명명 된 형식 및 무명 형식의 인스턴스를 만드는 데 사용할 수 있습니다.  
  
## <a name="declarations"></a>선언  
 인스턴스의 명명 된 형식과 익명 형식 선언 수와 거의 동일 보이지만 그 효과가 다릅니다. 각 범주에는 고유한 기능과 제한 사항이 있습니다. 다음 예제에서는 선언 하 고 명명된 된 클래스의 인스턴스를 초기화 하는 편리한 방법을 `Customer`, 개체 이니셜라이저 목록을 사용 하 여 합니다. 키워드 뒤에 클래스의 이름 지정은 `New`합니다.  
  
 [!code-vb[VbVbalrObjectInit#1](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_1.vb)]  
  
 익명 형식에 사용할 수 있는 이름이 없습니다. 따라서 익명 형식의 인스턴스화 클래스 이름을 포함할 수 없습니다.  
  
 [!code-vb[VbVbalrObjectInit#2](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_2.vb)]  
  
 요구 사항 및 두 가지 선언의 결과 동일 하지 않습니다. 에 대 한 `namedCust`, `Customer` 가 있는 클래스는 `Name` 속성이 이미 존재 해야 하며 선언을 해당 클래스의 인스턴스를 만듭니다. 에 대 한 `anonymousCust`, 한 속성을 호출 하는 문자열을 가진 새 클래스를 정의 하는 컴파일러 `Name`, 해당 클래스의 새 인스턴스를 만듭니다.  
  
## <a name="named-types"></a>명명 된 형식  
 개체 이니셜라이저를 형식의 생성자를 호출 하 여 단일 문에서 일부 또는 모든 속성의 값을 설정 하는 간단한 방법을 제공 합니다. 문에 대 한 적절 한 생성자를 호출 하는 컴파일러: 인수에 제공 하는 경우 기본 생성자 또는 하나 이상의 인수를 전송 하는 경우 매개 변수화 된 생성자입니다. 그 후 지정된 된 속성은 이니셜라이저 목록에 표시 된 순서 대로 초기화 됩니다.  
  
 이니셜라이저 목록에서 각 초기화 클래스의 멤버에 초기 값을 할당 이루어져 있습니다. 클래스가 정의 되어 있는 경우 이름 및 멤버의 데이터 형식을 결정 됩니다. 다음 예제에서는 합니다 `Customer` 클래스 존재 해야 하며 라는 멤버가 있어야 `Name` 고 `City` 문자열 값을 받아들일 수 있는 합니다.  
  
 [!code-vb[VbVbalrObjectInit#3](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_3.vb)]  
  
 또는 다음 코드를 사용 하 여 동일한 결과 얻을 수 있습니다.  
  
 [!code-vb[VbVbalrObjectInit#4](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_4.vb)]  
  
 각 이러한 선언을 만드는 다음 예제와 동일을 `Customer` 기본 생성자를 사용 하 여 개체 및 다음에 대 한 초기 값을 지정 합니다 `Name` 및 `City` 를 사용 하 여 속성을 `With` 문입니다.  
  
 [!code-vb[VbVbalrObjectInit#5](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_5.vb)]  
  
 경우는 `Customer` 에 대 한 값으로 보낼 수 있도록 매개 변수가 있는 생성자를 포함 하는 클래스 `Name`, 예를 들어 수 또한 선언 하 고 초기화를 `Customer` 다음과 같은 방법으로 개체:  
  
 [!code-vb[VbVbalrObjectInit#6](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_6.vb)]  
  
 다음 코드와 같이 모든 속성을 초기화할 필요가 없습니다.  
  
 [!code-vb[VbVbalrObjectInit#7](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_7.vb)]  
  
 그러나 초기화 목록 비워둘 수 없습니다. 초기화 되지 않은 속성을 기본값으로 유지 합니다.  
  
### <a name="type-inference-with-named-types"></a>명명 된 형식으로 형식 유추  
 선언에 대 한 코드를 줄일 수 `cust1` 개체 이니셜라이저 및 지역 형식 유추를 결합 하 여 합니다. 생략 하면이 `As` 변수 선언 절. 변수의 데이터 형식은 할당 하 여 만든 개체의 형식에서 유추 됩니다. 다음 예에서 유형의 `cust6` 는 `Customer`합니다.  
  
 [!code-vb[VbVbalrObjectInit#8](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_8.vb)]  
  
### <a name="remarks-about-named-types"></a>명명 된 형식에 대 한 설명  
  
-   개체 이니셜라이저 목록에서 여러 번 클래스 멤버를 초기화할 수 없습니다. 선언의 `cust7` 오류가 발생 합니다.  
  
     [!code-vb[VbVbalrObjectInit#9](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_9.vb)]  
  
-   자신 또는 다른 필드를 초기화 하는 멤버를 사용할 수 있습니다. 이 초기화 되었으면 다음 선언 에서처럼 전에 멤버에 액세스 하는 경우 `cust8`, 기본 값이 사용 됩니다. 개체 이니셜라이저를 사용 하는 선언을 처리 되 면 가장 먼저 발생 하는 적절 한 생성자가 호출 해야 합니다. 그런 다음 이니셜라이저 목록에서 개별 필드 초기화 됩니다. 다음 예제에서는 기본값이 `Name` 에 대해 할당 `cust8`, 초기화 된 값에 할당 됩니다 `cust9`합니다.  
  
     [!code-vb[VbVbalrObjectInit#10](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_10.vb)]  
  
     다음 예제에서 매개 변수가 있는 생성자를 사용 `cust3` 하 고 `cust4` 선언 하 고 초기화 `cust10` 고 `cust11`입니다.  
  
     [!code-vb[VbVbalrObjectInit#11](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_11.vb)]  
  
-   개체 이니셜라이저를 중첩할 수 있습니다. 다음 예에서 `AddressClass` 는 두 개의 속성이 있는 클래스 `City` 하 고 `State`, 및 `Customer` 클래스에는 `Address` 인스턴스의 속성 `AddressClass`합니다.  
  
     [!code-vb[VbVbalrObjectInit#12](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_12.vb)]  
  
-   초기화 목록을 비워 둘 수 없습니다.  
  
-   초기화 되는 인스턴스 개체 형식일 수 없습니다.  
  
-   초기화 되는 클래스 멤버는 공유 멤버, 읽기 전용 멤버, 상수 또는 메서드 호출 일 수 없습니다.  
  
-   초기화 되는 클래스 멤버는 인덱싱된 하거나 정규화 될 수 없습니다. 다음 예제에서는 컴파일러 오류가 발생 합니다.  
  
     `'' Not valid.`  
  
     `' Dim c1 = New Customer With {.OrderNumbers(0) = 148662}`  
  
     `' Dim c2 = New Customer with {.Address.City = "Springfield"}`  
  
## <a name="anonymous-types"></a>익명 형식  
 익명 형식 이름과 새 형식을 명시적으로 정의 하지 않은 인스턴스를 만들고 개체 이니셜라이저를 사용 합니다. 대신, 컴파일러는 개체 이니셜라이저 목록에서 지정한 속성에 따라 형식을 생성 합니다. 형식의 이름을 지정 하지 않으면 때문 이라고 하는 *무명 형식*합니다. 예를 들어 다음 선언에 대 한 이전 비교 `cust6`합니다.  
  
 [!code-vb[VbVbalrObjectInit#13](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_13.vb)]  
  
 구문상 점만 후 지정 된 이름이 없는 `New` 데이터 형식에 대 한 합니다. 그러나 어떤 일이 생기는 크게 다릅니다. 컴파일러는 두 속성을 가진 새 익명 형식 정의 `Name` 및 `City`, 지정된 된 값을 사용 하 여 해당 인스턴스를 만듭니다. 유형을 결정 하는 형식 유추 `Name` 고 `City` 예제 문자열 이어야 합니다.  
  
> [!CAUTION]
>  익명 형식의 이름을 컴파일러에 의해 생성 되 고 컴파일할 때마다 다를 수 있습니다. 코드 사용 하거나 익명 형식의 이름을 사용 해야 합니다.  
  
 형식의 이름을 사용 가능 하지 않으므로 사용할 수 없습니다는 `As` 선언에 절 `cust13`합니다. 해당 형식을 유추 해야 합니다. 런타임에 바인딩을 사용 하지 않고 지역 변수에 익명 형식의 사용이 제한 됩니다.  
  
 익명 형식에 대 한 중요 한 지원 제공 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 합니다. 쿼리에서 익명 형식을 사용 하는 방법에 대 한 자세한 내용은 참조 [무명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) 하 고 [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)합니다.  
  
### <a name="remarks-about-anonymous-types"></a>익명 형식에 대 한 설명  
  
-   일반적으로 무명 형식 선언에서 속성의 전체 또는 대부분 됩니다 키워드를 입력 하 여 표시 된 키 속성을 `Key` 속성 이름 앞에 있습니다.  
  
     [!code-vb[VbVbalrObjectInit#14](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_14.vb)]  
  
     키 속성에 대 한 자세한 내용은 참조 하세요. [키](../../../../visual-basic/language-reference/modifiers/key.md)합니다.  
  
-   명명 된 형식과 마찬가지로, 이니셜라이저 목록 하나 이상의 속성을 선언 해야 하는 익명 형식 정의 대 한 합니다.  
  
     [!code-vb[VbVbalrObjectInit#2](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_2.vb)]  
  
-   무명 형식의 인스턴스를 선언할 때 컴파일러는 일치 하는 익명 형식 정의 생성 합니다. 이름 및 속성의 데이터 형식을 인스턴스 선언에서 이동 하 고 정의에 컴파일러에 의해 포함 됩니다. 속성 없습니다 명명 되 고 명명 된 형식에 대 한 것 처럼 미리 정의 합니다. 해당 형식이 유추 됩니다. 속성의 데이터 형식을 사용 하 여 지정할 수 없습니다는 `As` 절.  
  
-   익명 형식 이름 및 해당 속성의 값을 여러 가지 방법으로 설정할 수 있습니다. 예를 들어, 무명 형식 속성 이름 및 값의 변수 이름 및 다른 개체의 속성 값을 걸릴 수 있습니다.  
  
     [!code-vb[VbVbalrObjectInit#15](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_15.vb)]  
  
     익명 형식에서 속성을 정의 하기 위한 옵션에 대 한 자세한 내용은 참조 하세요. [방법: 속성 이름 유추 및 익명 형식 선언에서 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [방법: 익명 형식 선언에서 속성 이름 및 형식 유추](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)  
 [키](../../../../visual-basic/language-reference/modifiers/key.md)  
 [방법: 개체 이니셜라이저를 사용하여 개체 선언](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
