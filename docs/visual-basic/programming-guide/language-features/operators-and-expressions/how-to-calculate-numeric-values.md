---
title: "방법: 숫자 값 계산 (Visual Basic) | Microsoft 문서"
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
- operator precedence
- operators [Visual Basic]
- expressions [Visual Basic], numeric
- calculations, numeric expressions
- precedence, of operators
- Visual Basic code, operators
- Visual Basic code, expressions
- numeric expressions
ms.assetid: ba6bf43d-bd96-49b8-b1de-4a7797551372
caps.latest.revision: 13
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
ms.openlocfilehash: d844e2af3892d897125e21d3fd7047a8b295d10a
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-calculate-numeric-values-visual-basic"></a>방법: 숫자 값 계산(Visual Basic)
숫자 식 사용 하 여 숫자 값을 계산할 수 있습니다. A *숫자 식* 리터럴, 상수 및 숫자 값을 나타내는 변수를 포함 하는 식을 이며 해당 값에 대해 작동 하는 연산자입니다.  
  
## <a name="calculating-numeric-values"></a>숫자 값 계산  
  
#### <a name="to-calculate-a-numeric-value"></a>숫자 값을 계산 하려면  
  
-   숫자 식으로 하나 이상의 숫자 리터럴, 상수 및 변수를 결합 합니다. 다음 예제에는 유효한 숫자 식을 보여 줍니다.  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     처음 세 줄은 리터럴, 상수 및 변수를 보여 줍니다. 각 자체적으로 유효한 숫자 식을 형성합니다. 마지막 줄의 두 가지 리터럴 사용 하 여 변수 조합을 보여 줍니다.  
  
     참고 숫자 식 전체 형성 하지 않습니다 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 자체적으로 문의 합니다. 전체 문의 일부로 식을 사용 해야 합니다.  
  
#### <a name="to-store-a-numeric-value"></a>숫자 값을 저장 하려면  
  
-   다음 예제 에서처럼 변수에 숫자 식을 사용 하 여 표시 되는 값을 할당 하는 대입문을 사용할 수 있습니다.  
  
     [!code-vb[VbVbalrOperators #&82;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_1.vb)]  
  
     위의 예제에서는 같음 연산자의 오른쪽에 있는 식의 값 (`=`) 변수에 할당 `j` 연산자의 왼쪽에 있으므로 `j` 276으로 계산 합니다.  
  
     자세한 내용은 참조 [문을](../../../../visual-basic/language-reference/statements/index.md)합니다.  
  
## <a name="multiple-operators"></a>여러 명의 연산자  
 숫자 식에 하나 이상의 연산자, 평가 되는 순서는 연산자 우선 순위 규칙에 의해 결정 됩니다. 식 위의 예와 괄호로 묶어 있습니다의 연산자 우선 순위 규칙을 재정의 하려면 괄호 안의 식이 먼저 계산 됩니다.  
  
#### <a name="to-override-normal-operator-precedence"></a>일반 연산자 우선 순위를 재정의 하려면  
  
-   괄호를 사용 하 여 먼저 수행 하려는 작업을 묶습니다. 다음 예제에서는 동일한 연산자와 피연산자와 두 개의 서로 다른 결과 보여 줍니다.  
  
     [!code-vb[VbVbalrOperators #&83;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_2.vb)]  
  
     앞의 예제에 대 한 계산에서 `j` 더하기 연산자를 수행 (`+`) 첫 번째 때문에 괄호로 `(67 + i)` 일반 우선 순위에 할당 된 값을 재정의 `j` 은 276 (4 회 69). 에 대 한 계산 `k` 일반 우선 순위에 연산자를 수행 하므로 (`*` 하기 전에 `+`), 및에 할당 된 값 `k` 은 270 (268 + 2).  
  
     자세한 내용은 참조 [Visual Basic의 연산자 우선 순위](../../../../visual-basic/language-reference/operators/operator-precedence.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [연산자 및 식](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [값 비교](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)   
 [문](../../../../visual-basic/language-reference/statements/index.md)   
 [Visual Basic의 연산자 우선 순위](../../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [산술 연산자](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [연산자의 효율적 결합](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
