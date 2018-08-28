---
title: IsTrue 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: bf81384b0cecfd1ee3d438e4463949381279a181
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43003192"
---
# <a name="istrue-operator-visual-basic"></a>IsTrue 연산자(Visual Basic)
식이 인지 결정 `True`합니다.  
  
 호출할 수 없습니다 `IsTrue` 명시적으로 코드 에서만 Visual Basic 컴파일러는 데 사용할 수에서 코드를 생성할 `OrElse` 절. 클래스 또는 구조체 정의 다음에 있는 해당 유형의 변수를 사용 하는 경우는 `OrElse` 정의 해야 절 `IsTrue` 해당 클래스 또는 구조체에서 합니다.  
  
 컴파일러에서 고려 하는 `IsTrue` 및 `IsFalse` 연산자는 *일치 하는 쌍*합니다. 이 그 중 하나를 정의 하는 경우 정의 해야 합니다도 다른 것을 의미 합니다.  
  
## <a name="compiler-use-of-istrue"></a>IsTrue 컴파일러 사용  
 클래스 또는 구조체를 정의한 경우에 해당 형식에서 변수의 사용할 수 있습니다는 `For`, `If`를 `Else If`, 또는 `While` 문, 또는 `When` 절. 이렇게 하면 컴파일러 형식으로 변환 하는 연산자가 필요는 `Boolean` 값 조건을 테스트할 수 있도록 합니다. 다음 순서 대로 연산자를 적절 한 검색 됩니다.  
  
1.  클래스 또는 구조체에서 확대 변환 연산자 `Boolean`합니다.  
  
2.  클래스 또는 구조체에서 확대 변환 연산자 `Boolean?`합니다.  
  
3.  `IsTrue` 클래스 또는 구조체에서 연산자입니다.  
  
4.  로 축소 변환 `Boolean?` 변환에서 포함 하지 않는 `Boolean` 에 `Boolean?`입니다.  
  
5.  클래스 또는 구조체에서 축소 변환 연산자 `Boolean`합니다.  
  
 으로 변환이 정의 하지 않은 경우 `Boolean` 요소나 `IsTrue` 연산자, 컴파일러에서 오류를 알립니다.  
  
> [!NOTE]
>  합니다 `IsTrue` 연산자 *오버 로드 된*, 클래스 또는 구조체 수 할 동작 피연산자에 해당 클래스 또는 구조체 형식의 경우. 이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에 대 한 정의 포함 하는 구조체의 윤곽선을 정의 합니다 `IsFalse` 고 `IsTrue` 연산자입니다.  
  
 [!code-vb[VbVbalrOperators#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/istrue-operator_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [IsFalse 연산자](../../../visual-basic/language-reference/operators/isfalse-operator.md)  
 [방법: 연산자 정의](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [OrElse 연산자](../../../visual-basic/language-reference/operators/orelse-operator.md)
