---
title: "Is 연산자(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4b1f3f0fa1fd782550c08c816f47b7541399198e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="is-operator-visual-basic"></a>Is 연산자(Visual Basic)
두 개체 참조 변수를 비교합니다.  
  
## <a name="syntax"></a>구문  
  
```  
result = object1 Is object2  
```  
  
## <a name="parts"></a>요소  
 `result`  
 필수 요소. 모든 `Boolean` 값입니다.  
  
 `object1`  
 필수 요소. 모든 `Object` 이름입니다.  
  
 `object2`  
 필수 요소. 모든 `Object` 이름입니다.  
  
## <a name="remarks"></a>설명  
 `Is` 연산자 두 개체 참조가 동일한 개체를 참조 하는지 여부를 결정 합니다. 그러나 값 비교를 수행 하지 않습니다. 경우 `object1` 및 `object2` 정확히 동일한 개체 인스턴스를 둘 다 참조 `result` 은 `True`그렇지 않은 경우 `result` 은 `False`합니다.  
  
 `Is`함께 사용할 수도 `TypeOf` 있도록 키워드는 `TypeOf`... `Is` 개체 변수 데이터 형식과 호환 되는지 여부를 테스트 하는 식입니다.  
  
> [!NOTE]
>  `Is` 키워드는 또한는 [선택... Case 문](../../../visual-basic/language-reference/statements/select-case-statement.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Is` 개체 참조의 쌍을 비교 연산자. 결과에 할당 되는 `Boolean` 두 개체가 동일한 지 여부를 나타내는 값입니다.  
  
 [!code-vb[VbVbalrOperators#27](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/is-operator_1.vb)]  
  
 사용할 수 있습니다 앞의 예제에서 보여 주듯이는 `Is` 모두 테스트할 연산자 초기 바인딩 및 런타임에 바인딩된 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [TypeOf 연산자](../../../visual-basic/language-reference/operators/typeof-operator.md)  
 [IsNot 연산자](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [Visual Basic의 비교 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [연산자 및 식](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
