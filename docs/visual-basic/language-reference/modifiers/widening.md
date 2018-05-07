---
title: Widening(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.widening
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Widening keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 646ae263-94d3-40a2-b0cc-64f619292f56
ms.openlocfilehash: 2323aa38c81ce4e027f256d0e29c069f7ec77c00
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="widening-visual-basic"></a>Widening(Visual Basic)
나타냅니다 변환 연산자 (`CType`) 클래스 또는 구조체를 원래 클래스 또는 구조체의 모든 가능한 값을 보유할 수 있는 형식으로 변환 합니다.  
  
## <a name="converting-with-the-widening-keyword"></a>확대는 키워드와 함께 변환  
 변환 프로시저를 지정 해야 `Public Shared` 외에 `Widening`합니다.  
  
 확대 변환 실행 시 항상 성공 하 고 데이터가 손실 되지 마십시오. 예로 `Single` 를 `Double`, `Char` 를 `String`, 및 해당 기본 형식에는 파생 된 형식입니다. 파생된 형식이 기본 형식의 모든 멤버를 포함 하 고 기본 형식의 인스턴스가 되므로이 마지막으로 변환이 확대 합니다.  
  
 사용 하는 코드를 사용 하지 않아도 `CType` 확대 변환에 대 한 경우에 `Option Strict` 은 `On`합니다.  
  
 `Widening` 키워드는이 컨텍스트에서 사용할 수 있습니다.  
  
 [Operator 문](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 확대 변환과 축소 변환 연산자의 정의가 참조 하는 예를 들어 [하는 방법: 변환 연산자 정의](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Operator 문](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [확대 변환과 축소 변환](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [방법: 연산자 정의](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [CType 함수](../../../visual-basic/language-reference/functions/ctype-function.md)  
 [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [방법: 변환 연산자 정의](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
