---
title: '방법: 다른 데이터 형식에 동일한 기능을 제공할 수 있는 클래스 정의(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- data type arguments [Visual Basic], using
- type parameters [Visual Basic], defining
- data type arguments [Visual Basic], defining
- arguments [Visual Basic], data types
- Of keyword [Visual Basic], using
- constraints, Visual Basic generic types
- generic parameters
- data type parameters
- data type parameters [Visual Basic], using
- generics [Visual Basic], defining classes with type parameters
- data types [Visual Basic], as parameters
- data types [Visual Basic], as arguments
- parameters [Visual Basic], type
- type arguments
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- type parameters
- data type arguments
- parameters [Visual Basic], data type
- generics [Visual Basic], defining generic types
- data type parameters [Visual Basic], defining
- type arguments [Visual Basic], defining
- arguments [Visual Basic], type
ms.assetid: a914adf8-e68f-4819-a6b1-200d1cf1c21c
ms.openlocfilehash: 3570a1c851bb8fead33f4cd208489c4ae087a68d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650350"
---
# <a name="how-to-define-a-class-that-can-provide-identical-functionality-on-different-data-types-visual-basic"></a>방법: 다른 데이터 형식에 동일한 기능을 제공할 수 있는 클래스 정의(Visual Basic)
여러 데이터 형식에 대해 동일한 기능을 제공하는 개체를 만들 수 있는 클래스를 정의할 수 있습니다. 이렇게 하려면 정의에 하나 이상의 *형식 매개 변수* 를 지정합니다. 그러면 클래스는 여러 데이터 형식을 사용하는 개체의 템플릿 역할을 할 수 있습니다. 이 방법으로 정의된 클래스를 *제네릭 클래스*라고 합니다.  
  
 제네릭 클래스를 정의할 때의 장점은 한 번만 정의하면 코드에서 이를 사용하여 다양한 데이터 형식을 사용하는 여러 개체를 만들 수 있다는 점입니다. 그 결과 `Object` 형식으로 클래스를 정의할 때보다 성능이 향상됩니다.  
  
 클래스 이외에도 제네릭 구조체, 인터페이스, 프로시저 및 대리자도 정의할 수 있습니다.  
  
### <a name="to-define-a-class-with-a-type-parameter"></a>형식 매개 변수로 클래스를 정의하려면  
  
1.  일반적인 방법으로 클래스를 정의합니다.  
  
2.  형식 매개 변수를 지정하려면 클래스 이름 바로 뒤에 `(Of` *typeparameter*`)` 를 추가하세요.  
  
3.  형식 매개 변수가 두 개 이상인 경우에는 쉼표로 구분된 목록을 괄호 안에 넣으세요. `Of` 키워드는 반복하지 마세요.  
  
4.  코드가 단순한 할당 이외의 형식 매개 변수에 대한 작업을 수행하는 경우 해당 형식 매개 변수 뒤에 `As` 절을 사용하여 하나 이상의 *제약 조건*을 추가하세요. 제약 조건을 사용하면 해당 형식 매개 변수에 대해 제공되는 형식이 다음과 같은 요구 사항을 충족해야 합니다.  
  
    -   코드에서 수행하는 `>`등의 작업을 지원  
  
    -   코드에서 액세스하는 메서드와 같은 멤버를 지원  
  
    -   매개 변수 없는 생성자 노출  
  
     제약 조건을 지정하지 않으면 [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)에서 지원되는 작업 및 멤버만 코드에서 사용할 수 있습니다. 자세한 내용은 [Type List](../../../../visual-basic/language-reference/statements/type-list.md)을 참조하세요.  
  
5.  제공된 형식으로 선언될 모든 클래스 멤버를 식별하고 이를 `As` `typeparameter`로 선언합니다. 이는 내부 저장소, 프로시저 매개 변수 및 반환 값에 적용됩니다.  
  
6.  `itemType`에 제공할 수 있는 모든 데이터 형식이 지원하는 작업 및 메서드만 코드에서 사용해야 합니다.  
  
     다음 예에서는 매우 간단한 목록을 관리하는 클래스를 정의합니다. 내부 배열 `items`에 목록을 저장하며 코드를 사용하여 목록 요소의 데이터 형식을 선언할 수 있습니다. 매개 변수를 사용하는 생성자를 사용하면 코드로 `items`의 상한을 설정할 수 있습니다. 기본 생성자는 이 상한을 9(총 10개 항목)로 설정합니다.  
  
     [!code-vb[VbVbalrDataTypes#7](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/how-to-define-a-class-that-can-provide-identical-functionality_1.vb)]  
  
     `simpleList` 값 목록을 저장할 클래스, `Integer` 값 목록을 저장할 클래스, `String` 값을 저장할 클래스를 `Date` 로부터 선언할 수 있습니다. 목록 요소의 데이터 형식을 제외하고 이러한 모든 클래스에서 만들어진 개체는 동일하게 동작합니다.  
  
     코드에서 `itemType` 에 제공하는 형식 인수는 `Boolean` 또는 `Double`, 구조체, 열거형 또는 응용 프로그램이 정의하는 형식을 포함한 모든 클래스 형식과 같은 내부 형식일 수 있습니다.  
  
     다음 코드로 클래스 `simpleList` 를 테스트할 수 있습니다.  
  
     [!code-vb[VbVbalrDataTypes#8](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/how-to-define-a-class-that-can-provide-identical-functionality_2.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Visual Basic의 제네릭 형식](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [언어 독립성 및 언어 독립적 구성 요소](../../../../standard/language-independence-and-language-independent-components.md)  
 [Of](../../../../visual-basic/language-reference/statements/of-clause.md)  
 [형식 목록](../../../../visual-basic/language-reference/statements/type-list.md)  
 [방법: 제네릭 클래스 사용](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [Object 데이터 형식](../../../../visual-basic/language-reference/data-types/object-data-type.md)
