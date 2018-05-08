---
title: '방법: 연산자 정의(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- Visual Basic code, operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- operator procedures [Visual Basic], about operator procedures
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: d4b0e253-092a-4e6e-9fe2-01f562140a29
ms.openlocfilehash: c759ebf38ab0727aeada218d288b5ac01e3ecd03
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-define-an-operator-visual-basic"></a>방법: 연산자 정의(Visual Basic)
클래스 또는 구조체를 정의한 경우에 표준 연산자의 동작을 정의할 수 있습니다 (같은 `*`, `<>`, 또는 `And`) 경우 하나 또는 두 개의 피연산자는 클래스 또는 구조체의 형식입니다.  
  
 클래스 또는 구조체 내에서 연산자 프로시저도 표준 연산자를 정의 합니다. 모든 연산자 프로시저 여야 `Public` `Shared`합니다.  
  
 클래스 또는 구조체에서 연산자를 정의 라고도 *오버 로드* 연산자입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 정의 `+` 구조체에 대 한 연산자 호출 `height`합니다. 피트 및 인치 단위로 측정 된 높이 사용 하는 구조입니다. 하나의 *인치* 2.54 센티미터 개와 *foot* 는 12 인치입니다. 정규화 된 값 (인치 < 12.0)을 보장 하려면 생성자는 다음과 같이 수행 됩니다. *모듈로* 산술 12입니다. `+` 연산자 생성자를 사용 하 여 정규화 된 값을 생성 합니다.  
  
 [!code-vb[VbVbcnProcedures#25](./codesnippet/VisualBasic/how-to-define-an-operator_1.vb)]  
  
 구조를 테스트할 수 `height` 다음 코드를 사용 합니다.  
  
 [!code-vb[VbVbcnProcedures#26](./codesnippet/VisualBasic/how-to-define-an-operator_2.vb)]  
  
 자세한 내용과 예제는 [Operator Overloading in Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703)(Visual Basic 2005의 연산자 오버로드)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [연산자 프로시저](./operator-procedures.md)  
 [방법: 변환 연산자 정의](./how-to-define-a-conversion-operator.md)  
 [방법: 연산자 프로시저 호출](./how-to-call-an-operator-procedure.md)  
 [방법: 연산자를 정의하는 클래스 사용](./how-to-use-a-class-that-defines-operators.md)  
 [Operator 문](../../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Structure 문](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [방법: 구조체 선언](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [Mod 연산자](../../../../visual-basic/language-reference/operators/mod-operator.md)
