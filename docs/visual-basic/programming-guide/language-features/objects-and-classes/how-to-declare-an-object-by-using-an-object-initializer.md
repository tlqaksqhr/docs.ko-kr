---
title: '방법: 개체 이니셜라이저를 사용하여 개체 선언(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring objects using object initializer
- object initializers [Visual Basic]
- initializers [Visual Basic]
- Video How tos, Visual Basic
ms.assetid: 0f53a553-efd6-466d-80bf-6b679e5cd174
ms.openlocfilehash: 3a372ba91377b53c87c05976e416ca8ed55ccbbe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649167"
---
# <a name="how-to-declare-an-object-by-using-an-object-initializer-visual-basic"></a>방법: 개체 이니셜라이저를 사용하여 개체 선언(Visual Basic)
개체 이니셜라이저를 사용 하 여 선언 하 고 단일 문에서 클래스의 인스턴스를 인스턴스화할 수 있습니다. 또한 매개 변수가 있는 생성자를 호출 하지 않고 같은 시간에 하나 이상의 멤버 인스턴스를 초기화할 수 있습니다.  
  
 개체 이니셜라이저를 사용 하 여 명명 된 형식의 인스턴스를 만들 때 지정한 순서에 지정 된 멤버의 초기화가 수행 클래스에 대 한 기본 생성자 호출 됩니다.  
  
 다음 절차의 인스턴스를 만드는 방법을 보여 줍니다는 `Student` 세 가지 방법으로 클래스입니다. 클래스 이름, 성, 이름 및 다른 규칙 으로부터 클래스 연도 속성에 있습니다. 새 인스턴스를 만들고 각각의 세 가지 선언을 `Student`를 속성과 함께 `First` "Michael," 속성으로 설정 `Last` "Tucker"로 설정 하 고 다른 모든 멤버를 기본값으로 설정 합니다. 개체 이니셜라이저를 사용 하지 않는 다음 예제에서는 절차의 각 선언의 결과가 같습니다.  
  
 [!code-vb[VbVbalrObjectInit#20](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_1.vb)]  
  
 구현은 `Student` 클래스를 참조 하십시오. [하는 방법: 항목 목록 만들기](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)합니다. 클래스를 설정 하 고 목록을 만들 해당 항목에서 코드를 복사할 수 `Student` 작업할 개체입니다.  
  
### <a name="to-create-an-object-of-a-named-class-by-using-an-object-initializer"></a>개체 이니셜라이저를 사용 하 여 명명된 된 클래스의 개체를 만들려면  
  
1.  생성자를 사용 하는 미리 계획 하는 경우 선언을 시작 합니다.  
  
     `Dim student1 As New Student`  
  
2.  키워드를 입력 `With`초기화 목록을 중괄호로 이어집니다.  
  
     `Dim student1 As New Student With { <initialization list> }`  
  
3.  초기화 목록에서 초기화 하 고 초기 값을 할당 하려는 각 속성을 포함 합니다. 속성의 이름에 마침표 앞입니다.  
  
     [!code-vb[VbVbalrObjectInit#21](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_2.vb)]  
  
     클래스의 하나 이상의 멤버를 초기화할 수 있습니다.  
  
4.  또는 클래스의 새 인스턴스를 선언 하 고에 값을 할당할 수 있습니다. 인스턴스를 먼저 선언 `Student`:  
  
     `Dim student2 As Student`  
  
5.  인스턴스를 만들기 시작 `Student` 일반적인 방식입니다.  
  
     `Dim student2 As Student = New Student`  
  
6.  형식 `With` 한 다음 개체 이니셜라이저 하나 이상의 멤버의 새 인스턴스를 초기화 합니다.  
  
     [!code-vb[VbVbalrObjectInit#22](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_3.vb)]  
  
7.  생략 하 여 이전 단계에서 정의 단순화할 수 `As Student`합니다. 이 작업을 수행 하는 경우 컴파일러가 판단 하는 `student3` 의 인스턴스가 `Student` 지역 형식 유추를 사용 하 여 합니다.  
  
     [!code-vb[VbVbalrObjectInit#23](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_4.vb)]  
  
     자세한 내용은 참조 [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [방법: 항목 목록 만들기](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)  
 [개체 이니셜라이저: 명명된 형식과 익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
