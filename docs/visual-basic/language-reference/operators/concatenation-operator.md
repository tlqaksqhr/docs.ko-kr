---
title: '&amp; 연산자 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.&
helpviewer_keywords:
- And (&) operator
- ampersand operator (&)
- '& operator'
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
ms.assetid: fefc3d00-cbf1-475c-8c5e-6fb213b3f85a
ms.openlocfilehash: 28d8cdb22974d77edf055ab9b2c6c767872e6783
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="amp-operator-visual-basic"></a>&amp; 연산자 (Visual Basic)
두 식의 문자열 연결을 생성합니다.  
  
## <a name="syntax"></a>구문  
  
```  
result = expression1 & expression2  
```  
  
## <a name="parts"></a>요소  
 `result`  
 필수. 모든 `String` 또는 `Object` 변수입니다.  
  
 `expression1`  
 필수. 모든 식으로 확장 되는 데이터 형식과 `String`합니다.  
  
 `expression2`  
 필수. 모든 식으로 확장 되는 데이터 형식과 `String`합니다.  
  
## <a name="remarks"></a>설명  
 데이터 형식이 `expression1` 또는 `expression2` 않습니다 `String` 로 확대 하지만 `String`로 변환 됩니다 `String`합니다. 하는 경우 데이터 형식 중 하나가 확대 변환 되지 않으면에 `String`, 컴파일러에 오류가 발생 합니다.  
  
 데이터 형식이 `result` 은 `String`합니다. 하나 또는 두 식의 계산 하는 경우 [Nothing](../../../visual-basic/language-reference/nothing.md) 의 값이 있는 <xref:System.DBNull.Value?displayProperty=nameWithType>, 처리 되는 값이 문자열 ""입니다.  
  
> [!NOTE]
>  `&` 연산자 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다. 이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.  
  
> [!NOTE]
>  앰퍼샌드 (&) 문자 사용할 수도 있습니다 형식으로 변수를 식별 하 `Long`합니다. 자세한 내용은 참조 [형식 문자](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)합니다.  
  
## <a name="example"></a>예제  
 사용 하 여이 예제는 `&` 문자열을 연결 하는 연산자입니다. 결과 두 문자열 피연산자의 연결을 나타내는 문자열 값입니다.  
  
 [!code-vb[VbVbalrOperators#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/concatenation-operator_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [&= 연산자](../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [연결 연산자](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Visual Basic의 연결 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
