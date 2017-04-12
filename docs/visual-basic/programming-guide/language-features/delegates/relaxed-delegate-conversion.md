---
title: "완화 대리자 변환 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions, relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: c0160165d3df9755481b89570b4cd135b3a990a2
ms.lasthandoff: 03/13/2017

---
# <a name="relaxed-delegate-conversion-visual-basic"></a>완화된 대리자 변환(Visual Basic)
완화 된 대리자 변환에는 해당 서명이 동일 하지 않은 경우에 처리기에 sub 및 함수를 할당할 수 있습니다. 따라서, 대리자에 대 한 바인딩 메서드 호출에 대해 이미 허용 된 바인딩과 일치 됩니다.  
  
## <a name="parameters-and-return-type"></a>매개 변수 및 반환 형식  
 서명이 완전히 일치 하는 대신 완화 된 변환을 수행 하려면 다음 조건이 충족 될 때 `Option Strict` 로 설정 된 `On`:  
  
-   확대 변환에서 각 대리자 매개 변수의 데이터 형식에서 할당 된 함수는 해당 매개 변수의 데이터 형식에 존재 해야 합니다 또는 `Sub`합니다. 다음 예제에서는 대리자에서에서 `Del1` 하나의 매개 변수가 있는 `Integer`합니다. 매개 변수 `m` 할당된 된 람다 식에서 확대 변환 되는 데이터 형식이 있어야 `Integer`, 예: `Long` 또는 `Double`합니다.  
  
     [!code-vb[VbVbalrRelaxedDelegates #&1;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]  
  
     [!code-vb[VbVbalrRelaxedDelegates #&2;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_2.vb)]  
  
     축소 변환에는 경우에만 허용 됩니다 `Option Strict` 로 설정 된 `Off`합니다.  
  
     [!code-vb[VbVbalrRelaxedDelegates #&8;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_3.vb)]  
  
-   확대 변환 할당 된 함수의 반환 형식에서 반대 방향으로 존재 해야 합니다 또는 `Sub` 대리자의 반환 형식입니다. 다음 예제에서 각 할당 된 람다 식의 본문은 확대 변환 되는 데이터 형식으로 계산 되어야 `Integer` 의 반환 형식이 때문에 `del1` 는 `Integer`합니다.  
  
     [!code-vb[VbVbalrRelaxedDelegates #&3;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_4.vb)]  
  
 경우 `Option Strict` 로 설정 된 `Off`, 제한 확대 각 방향에서 제거 됩니다.  
  
 [!code-vb[VbVbalrRelaxedDelegates #&4;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_5.vb)]  
  
## <a name="omitting-parameter-specifications"></a>매개 변수 사양 생략  
 완화 된 대리자 할당 된 메서드에서 매개 변수 사양 완전히 생략할 수도 있습니다.  
  
 [!code-vb[VbVbalrRelaxedDelegates #&5;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_6.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates #&6;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_7.vb)]  
  
 참고 일부 매개 변수를 지정 되 고 다른 사용자를 생략할 수 없습니다.  
  
 [!code-vb[VbVbalrRelaxedDelegates #&15;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_8.vb)]  
  
 매개 변수를 생략 하는 기능 몇 가지 복잡 한 매개 변수 수행 되는 이벤트 처리기를 정의 하는 경우에 유용 합니다. 일부 이벤트 처리기에 대 한 인수는 사용 되지 않습니다. 대신, 처리기는 이벤트를 등록 하 고는 인수를 무시 하는 컨트롤의 상태를 직접 액세스 합니다. 완화 된 대리자를 통해 모호성이 없는 선언에서 인수를 생략할 수 있습니다. 다음 예제에서는 완전 하 게 지정 된 메서드가에서 `OnClick` 으로 다시 작성할 수 있습니다 `RelaxedOnClick`합니다.  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a>AddressOf 예제  
 람다 식은 형식 관계를 쉽게 확인할 수 있도록 이전 예제에서 사용 됩니다. 동일한 relaxations 사용 하는 대리자 할당에 허용 되는 반면 `AddressOf`, `Handles`, 또는 `AddHandler`합니다.  
  
 다음 예제에서는 함수 `f1`, `f2`, `f3`, 및 `f4` 모두에 할당할 수 있습니다 `Del1`합니다.  
  
 [!code-vb[VbVbalrRelaxedDelegates #&1;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates #&7;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_9.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates #&9;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_10.vb)]  
  
 다음 예제는 경우에만 유효 `Option Strict` 로 설정 된 `Off`합니다.  
  
 [!code-vb[VbVbalrRelaxedDelegates #&14;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_11.vb)]  
  
## <a name="dropping-function-returns"></a>함수 반환 값 삭제  
 완화 된 대리자 변환을 사용 하면 함수를 할당 하는 `Sub` 대리자를 효과적으로 함수의 반환 값을 무시 합니다. 그러나, 할당할 수 없습니다는 `Sub` 함수 대리자입니다. 다음 예제에서는 함수의 주소에서에서 `doubler` 에 할당 된 `Sub` 위임 `Del3`합니다.  
  
 [!code-vb[VbVbalrRelaxedDelegates #&10;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_12.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates #&11;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_13.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [람다 식](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)   
 [확대 변환과 축소 변환](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [대리자](../../../../visual-basic/programming-guide/language-features/delegates/index.md)   
 [방법: 프로시저에 Visual Basic에서 다른 프로시저 전달](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)   
 [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
