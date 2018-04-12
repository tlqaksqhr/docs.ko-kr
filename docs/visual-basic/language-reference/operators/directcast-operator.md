---
title: DirectCast 연산자(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.directCast
- directCast
helpviewer_keywords:
- DirectCast keyword [Visual Basic]
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d9b81abea364e328b831ee98c3b847161c3f7dd3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="directcast-operator-visual-basic"></a>DirectCast 연산자(Visual Basic)
상속 또는 구현에 따라 형식 변환 작업을 소개 합니다.  
  
## <a name="remarks"></a>설명  
 `DirectCast`변환의 경우 다소을 제공할 수 있도록 런타임에 도우미 루틴 보다 뛰어난 성능을 Visual Basic을 사용 하지 않는 `CType` 데이터 형식에서 변환할 때 `Object`합니다.  
  
 사용 된 `DirectCast` 키워드를 사용 하는 방식과 비슷합니다는 [CType 함수](../../../visual-basic/language-reference/functions/ctype-function.md) 및 [TryCast 연산자](../../../visual-basic/language-reference/operators/trycast-operator.md) 키워드입니다. 식을 첫 번째 인수 및 두 번째 인수로 변환 하는 형식으로 제공 합니다. `DirectCast`두 인수의 데이터 형식 간의 상속 또는 구현 관계를 필요합니다. 즉, 한 형식에서 상속 하거나, 다른 구현 해야 합니다.  
  
## <a name="errors-and-failures"></a>오류 및 실패  
 `DirectCast`상속 또는 구현 관계 없는 있는지 검색 하는 경우 컴파일러 오류를 생성 합니다. 하지만 컴파일러 오류가 없다고 성공적인 변환을 보장 하지 않습니다. 원하는 변환이 축소 하는 경우 런타임 시 실패할 수 있습니다. 이 경우 런타임에서 throw 된 <xref:System.InvalidCastException> 오류입니다.  
  
## <a name="conversion-keywords"></a>변환 키워드  
 형식 변환 키워드의 비교는 다음과 같습니다.  
  
|키워드|데이터 형식|인수가 관계|런타임 오류|  
|---|---|---|---|  
|[CType 함수](../../../visual-basic/language-reference/functions/ctype-function.md)|모든 데이터 형식|두 데이터 형식 간에 확대 또는 축소 변환을 정의 해야 합니다.|Throw<xref:System.InvalidCastException>|  
|`DirectCast`|모든 데이터 형식|한 형식에서 상속 하거나 다른 형식을 구현 해야|Throw<xref:System.InvalidCastException>|  
|[TryCast 연산자](../../../visual-basic/language-reference/operators/trycast-operator.md)|참조 형식에만|한 형식에서 상속 하거나 다른 형식을 구현 해야|반환 [Nothing](../../../visual-basic/language-reference/nothing.md)|  
  
## <a name="example"></a>예제  
 다음 예의 두 가지 용도 `DirectCast`, 성공 하는 런타임과에 하나가 실패 합니다.  
  
 [!code-vb[VbVbalrKeywords#1](../../../visual-basic/language-reference/codesnippet/VisualBasic/directcast-operator_1.vb)]  
  
 앞의 예제에서의 실행 시간은 입력 `q` 은 `Double`합니다. `CType`있기 때문에 성공 `Double` 로 변환할 수 `Integer`합니다. 그러나 첫 번째 `DirectCast` 의 실행 시간을 입력 하기 때문에 런타임에 실패 `Double` 별칭과 없는 상속 관계가 `Integer`한 변환이 존재 하는 경우에 합니다. 두 번째 `DirectCast` 형식에서 변환 되기 때문에 성공 하면 <xref:System.Windows.Forms.Form> 입력 <xref:System.Windows.Forms.Control>, 올 <xref:System.Windows.Forms.Form> 상속 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Convert.ChangeType%2A?displayProperty=nameWithType>  
 [확대 변환과 축소 변환](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [암시적 변환과 명시적 변환](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
