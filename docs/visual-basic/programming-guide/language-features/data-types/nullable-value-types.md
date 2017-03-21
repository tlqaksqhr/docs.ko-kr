---
title: "Nullable 값 형식 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Nullable
dev_langs:
- VB
helpviewer_keywords:
- nullable types [Visual Basic]
- '? [Visual Basic]'
- types [Visual Basic], nullable
- nullable types
- data types [Visual Basic], nullable
ms.assetid: 9ac3b602-6f96-4e6d-96f7-cd4e81c468a6
caps.latest.revision: 23
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
ms.openlocfilehash: 9cdf1864fe955a082936596821ee84c831b86444
ms.lasthandoff: 03/13/2017

---
# <a name="nullable-value-types-visual-basic"></a>Nullable 값 형식(Visual Basic)
경우에 따라 상황에 따라 정의 된 값이 없는 값 형식으로 작업할 수도 있습니다. 예를 들어 한 데이터베이스의 필드에에서 의미 있는 할당된 된 값 들이 없는 할당된 된 값을 구분 해야 합니다. 값 형식 변수 정상 값 또는 null 값을 확장할 수 있습니다. 이러한 확장 이라고는 *nullable 형식*합니다.  
  
 각 nullable 형식이 제네릭에서 생성 된 <xref:System.Nullable%601>구조.</xref:System.Nullable%601> 작업 관련 작업을 추적 하는 데이터베이스를 고려해 야 합니다. 다음 구성 예제는 null을 허용 `Boolean` 입력 하 고 해당 형식의 변수를 선언 합니다. 세 가지 방법으로 선언을 작성할 수 있습니다.  
  
 [!code-vb[VbVbalrNullableValue #&1;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_1.vb)]  
  
 변수 `ridesBusToWork` 의 값을 보유할 수 `True`, 값이 `False`, 또는 모두에 값이 없습니다. 초기 기본값은 값이 없는 전혀는 예제의 것을 의미할 수도이 사용자에 대 한 정보가 아직 획득 하지. 반면, `False` 정보를 획득 한를 사람이 버스로 작동 하지 않음을 의미할 수 있습니다.  
  
 Nullable 형식의 변수 및 속성을 선언할 수 및 nullable 형식의 요소가 포함 된 배열을 선언할 수 있습니다. Nullable 형식의 매개 변수로 프로시저를 선언할 수 있고에서 null 허용 형식을 반환할 수는 `Function` 프로시저입니다.  
  
 배열 등과 같이 참조 형식에는 nullable 형식을 구성할 수 없습니다. 한 `String`, 또는 클래스입니다. 기본 형식이 값 형식 이어야 합니다. 자세한 내용은 참조 [값 형식과 참조 형식이](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)합니다.  
  
## <a name="using-a-nullable-type-variable"></a>Nullable 형식 변수를 사용 하 여  
 Nullable 형식의 가장 중요 한 멤버는 해당 <xref:System.Nullable%601.HasValue%2A>및 <xref:System.Nullable%601.Value%2A>속성.</xref:System.Nullable%601.Value%2A> </xref:System.Nullable%601.HasValue%2A> Nullable 형식의 변수에 대 한 <xref:System.Nullable%601.HasValue%2A>변수에 정의 된 값을 포함 하는 여부를 알려줍니다.</xref:System.Nullable%601.HasValue%2A> 경우 <xref:System.Nullable%601.HasValue%2A>은 `True`, <xref:System.Nullable%601.Value%2A>.</xref:System.Nullable%601.Value%2A> 에서 값을 읽을 수</xref:System.Nullable%601.HasValue%2A> 모두 <xref:System.Nullable%601.HasValue%2A>및 <xref:System.Nullable%601.Value%2A>는 `ReadOnly` 속성.</xref:System.Nullable%601.Value%2A> </xref:System.Nullable%601.HasValue%2A>  
  
### <a name="default-values"></a>기본값  
 Nullable 형식으로 변수를 선언 하는 경우 해당 <xref:System.Nullable%601.HasValue%2A>속성의 기본값은 `False`.</xref:System.Nullable%601.HasValue%2A> 즉, 기본적으로 변수에 있는 내부 값 형식의 기본값 대신 정의 된 값 없음. 다음 예제에서는 변수에서에서 `numberOfChildren` 처음 정의 된 값이 없는 경우에 기본의 값이 고 `Integer` 유형 0입니다.  
  
 [!code-vb[VbVbalrNullableValue #&2;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_2.vb)]  
  
 Null 값이 정의 되지 않거나 알 수 없는 값을 나타내는 데 유용 합니다. 경우 `numberOfChildren` 로 선언 `Integer`, 정보를 현재 사용할 수 없다는 나타낼 수 있는 값이 없는 것입니다.  
  
### <a name="storing-values"></a>값 저장  
 일반적인 방식으로 변수나 nullable 형식의 속성에 값을 저장 합니다. 다음 예제에서는 값을 변수에 할당 `numberOfChildren` 이전 예제의 선언 합니다.  
  
 [!code-vb[VbVbalrNullableValue #&3;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_3.vb)]  
  
 변수 또는 nullable 형식의 속성에 정의 된 값이 있으면 값이 할당 하지 않는 경우의 초기 상태로 되돌릴 발생할 수 있습니다. 변수 또는 속성을 설정 하 여이 작업을 수행 `Nothing`다음 예제와 같이 합니다.  
  
 [!code-vb[VbVbalrNullableValue #&4;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_4.vb)]  
  
> [!NOTE]
>  할당할 수 있지만 `Nothing` nullable 형식의 변수에 테스트할 수는 없습니다에 대 한 `Nothing` 등호를 사용 하 여 합니다. 등호를 사용 하 여 비교 `someVar = Nothing`, 언제나 평가 `Nothing`합니다. 변수를 테스트할 수 <xref:System.Nullable%601.HasValue%2A>속성에 대 한 `False`, 또는 사용 하 여 테스트는 `Is` 또는 `IsNot` 연산자.</xref:System.Nullable%601.HasValue%2A>  
  
### <a name="retrieving-values"></a>값 검색  
 Nullable 형식의 변수 값을 검색 하려면 먼저을 테스트 해야 해당 <xref:System.Nullable%601.HasValue%2A>속성을 값이 있는지 확인 합니다.</xref:System.Nullable%601.HasValue%2A> 값을 읽고 하려고 하면 때 <xref:System.Nullable%601.HasValue%2A>은 `False`, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] throw는 <xref:System.InvalidOperationException>예외가.</xref:System.InvalidOperationException> </xref:System.Nullable%601.HasValue%2A> 다음 예에서는 변수를 읽은 하는 권장된 방법은 `numberOfChildren` 앞의 예제입니다.  
  
 [!code-vb[VbVbalrNullableValue #&5;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_5.vb)]  
  
## <a name="comparing-nullable-types"></a>Nullable 형식 비교  
 Null을 허용 하는 경우 `Boolean` 변수는 부울 식에 사용 될 수 있습니다, `True`, `False`, 또는 `Nothing`합니다. 다음은 truth 테이블에 대 한 `And` 및 `Or`합니다. 때문에 `b1` 및 `b2` 만들었습니다 다음&3; 가지 값을&9; 개 조합을 평가 해야 합니다.  
  
|b1|b&2;|b1 및 b&2;|b1 또는 b&2;|  
|--------|--------|---------------|--------------|  
|`Nothing`|`Nothing`|`Nothing`|`Nothing`|  
|`Nothing`|`True`|`Nothing`|`True`|  
|`Nothing`|`False`|`False`|`Nothing`|  
|`True`|`Nothing`|`Nothing`|`True`|  
|`True`|`True`|`True`|`True`|  
|`True`|`False`|`False`|`True`|  
|`False`|`Nothing`|`False`|`Nothing`|  
|`False`|`True`|`False`|`True`|  
|`False`|`False`|`False`|`False`|  
  
 부울 변수 또는 식의 값이 `Nothing`가 아닌 `true` 나 `false`합니다. 다음 예제를 살펴보십시오.  
  
 [!code-vb[VbVbalrNullableValue #&6;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_6.vb)]  
  
 이 예제에서는 `b1 And b2` 계산 `Nothing`합니다. 결과적으로 `Else` 각 절이 실행 `If` 문과 출력은 다음과 같습니다.  
  
 `Expression is not true`  
  
 `Expression is not false`  
  
> [!NOTE]
>  `AndAlso`및 `OrElse`, 단락 계산을 사용 하는 계산 되어야 두 번째 피연산자는 첫 번째 일 때 `Nothing`합니다.  
  
## <a name="propagation"></a>전파  
 산술, 비교, 시프트 또는 형식 작업의 피연산자 중 하나 또는 모두 이면 null을 허용 연산의 결과가 null을 허용 이기도 합니다. 두 피연산자 값이 없는 경우 `Nothing`, 작업은 피연산자의 내부 값에 것 처럼 수행 모두 nullable 형식입니다. 다음 예제에서 변수 `compare1` 및 `sum1` 는 암시적으로 형식화 합니다. 위로 마우스 포인터를 놓으면 컴파일러 둘 다에 대 한 null 허용 형식 유추는 표시 됩니다.  
  
 [!code-vb[VbVbalrNullableValue #&7;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_7.vb)]  
  
 하나 또는 두 피연산자의 값이 없는 경우 `Nothing`, 결과 `Nothing`합니다.  
  
 [!code-vb[VbVbalrNullableValue #&8;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_8.vb)]  
  
## <a name="using-nullable-types-with-data"></a>데이터와 Nullable 형식 사용  
 데이터베이스에는 nullable 형식을 사용 하 여 가장 중요 한 위치 중 하나입니다. 모든 데이터베이스 개체에는 현재 nullable 형식 지원 않지만 테이블 디자이너에서 생성 된 어댑터입니다. "Nullable 형식에 대 한 TableAdapter 지원"을 참조 [TableAdapter 개요](https://docs.microsoft.com/visualstudio/data-tools/tableadapter-overview)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.InvalidOperationException></xref:System.InvalidOperationException>   
 <xref:System.Nullable%601.HasValue%2A></xref:System.Nullable%601.HasValue%2A>   
 [Nullable 형식 사용](../../../../csharp/programming-guide/nullable-types/using-nullable-types.md)   
 [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [값 형식과 참조 형식](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [데이터 형식 문제 해결](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [TableAdapter 개요](https://docs.microsoft.com/visualstudio/data-tools/tableadapter-overview)   
 [경우 연산자](../../../../visual-basic/language-reference/operators/if-operator.md)   
 [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Is 연산자](../../../../visual-basic/language-reference/operators/is-operator.md)   
 [IsNot 연산자](../../../../visual-basic/language-reference/operators/isnot-operator.md)
