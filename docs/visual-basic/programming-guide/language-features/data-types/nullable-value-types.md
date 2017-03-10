---
title: "Nullable Value Types (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Nullable"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "nullable types [Visual Basic]"
  - "? [Visual Basic]"
  - "types [Visual Basic], nullable"
  - "nullable types"
  - "data types [Visual Basic], nullable"
ms.assetid: 9ac3b602-6f96-4e6d-96f7-cd4e81c468a6
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 23
---
# Nullable Value Types (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

정의된 값이 없는 값 형식을 사용하는 경우가 있습니다.  예를 들어 데이터베이스의 필드는 의미 있는 값이 할당된 경우와 값이 할당되지 않은 경우를 구분해야 합니다.  일반 값이나 Null 값 중 하나를 사용하도록 값 형식을 확장할 수 있습니다.  이러한 확장을 *Nullable 형식*이라고 합니다.  
  
 각 Nullable 형식은 제네릭 <xref:System.Nullable%601> 구조체에서 생성됩니다.  작업 관련 작업을 추적하는 데이터베이스가 있다고 가정할 때  다음 예제에서는 Nullable `Boolean` 형식을 생성하고 해당 형식의 변수를 선언합니다.  다음 세 가지 방법으로 선언을 작성할 수 있습니다.  
  
 [!code-vb[VbVbalrNullableValue#1](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/visualbasic/nullable-value-types_1.vb)]  
  
 `ridesBusToWork` 변수에는 `True` 값이나 `False` 값을 지정할 수 있으며 값을 지정하지 않을 수도 있습니다.  초기 기본값은 값 없음이며 이 경우 이 사람에 대한 정보를 아직 얻지 못했음을 의미할 수 있습니다.  반대로 `False`는 정보를 얻었지만 이 사람이 버스로 통근하지 않음을 의미할 수 있습니다.  
  
 변수와 속성을 Nullable 형식으로 선언하고 배열을 Null 허용 형식의 요소로 선언할 수 있습니다.  Nullable 형식의 프로시저를 매개 변수로 선언하고 `Function` 프로시저에서 Null 허용 형식을 반환할 수 있습니다.  
  
 배열, `String` 또는 클래스와 같은 참조 형식에는 Nullable 형식을 생성할 수 없으며  내부 형식이 값 형식이어야 합니다.  자세한 내용은 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)를 참조하십시오.  
  
## Nullable 형식 변수 사용  
 Nullable 형식의 가장 중요한 멤버는 해당 <xref:System.Nullable%601.HasValue%2A> 및 <xref:System.Nullable%601.Value%2A> 속성입니다.  Nullable 형식 변수의 경우 <xref:System.Nullable%601.HasValue%2A>는 변수에 정의된 값이 포함되어 있는지 여부를 알려 줍니다.  <xref:System.Nullable%601.HasValue%2A>가 `True`이면 <xref:System.Nullable%601.Value%2A>에서 값을 읽을 수 있습니다.  <xref:System.Nullable%601.HasValue%2A> 및 <xref:System.Nullable%601.Value%2A> 모두 `ReadOnly` 속성입니다.  
  
### 기본값  
 변수를 Nullable 형식으로 선언하면 해당 <xref:System.Nullable%601.HasValue%2A> 속성에 기본값 `False`가 지정됩니다.  즉, 기본적으로 변수에는 내부 값 형식의 기본값 대신 정의된 값이 없습니다.  다음 예제에서는 `Integer` 형식의 기본값이 0임에도 불구하고 `numberOfChildren` 변수에 기본적으로 정의된 값이 없습니다.  
  
 [!code-vb[VbVbalrNullableValue#2](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/visualbasic/nullable-value-types_2.vb)]  
  
 Null 값은 정의되지 않은 값이나 알 수 없는 값을 나타내는 데 유용합니다.  `numberOfChildren`을 `Integer`로 선언하면 해당 정보를 현재 사용할 수 없음을 나타낼 수 있는 값이 없게 됩니다.  
  
### 값 저장  
 Nullable 형식의 변수나 속성에 일반적인 방법으로 값을 저장합니다.  다음 예제에서는 앞의 예제에서 선언한 `numberOfChildren` 변수에 값을 할당합니다.  
  
 [!code-vb[VbVbalrNullableValue#3](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/visualbasic/nullable-value-types_3.vb)]  
  
 Nullable 형식의 변수나 속성이 정의된 값을 포함하는 경우 값이 할당되지 않은 초기 상태로 이러한 변수나 속성을 되돌릴 수 있습니다.  다음 예와 같이 변수나 속성을 `Nothing`으로 설정하여 이를 수행할 수 있습니다.  
  
 [!code-vb[VbVbalrNullableValue#4](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/visualbasic/nullable-value-types_4.vb)]  
  
> [!NOTE]
>  Nullable 형식의 변수에 `Nothing`을 할당할 수 있지만 등호\(\=\)를 사용하여 `Nothing`에 대해 이 변수를 테스트할 수는 없습니다.  등호\(\=\)를 사용하는 비교, `someVar = Nothing`은 항상 `Nothing`이 됩니다.  `False`에 대해 변수의 <xref:System.Nullable%601.HasValue%2A> 속성을 테스트하거나 `Is` 또는 `IsNot` 연산자를 사용하여 테스트할 수 있습니다.  
  
### 값 검색  
 Nullable 형식의 변수 값을 검색하려면 먼저 해당 <xref:System.Nullable%601.HasValue%2A> 속성을 테스트하여 값이 있는지 확인해야 합니다.  <xref:System.Nullable%601.HasValue%2A>가 `False`일 때 값을 읽으려고 하면 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 <xref:System.InvalidOperationException> 예외를 throw합니다.  다음 예제에서는 이전 예제의 `numberOfChildren` 변수를 읽는 권장 방법을 보여 줍니다.  
  
 [!code-vb[VbVbalrNullableValue#5](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/visualbasic/nullable-value-types_5.vb)]  
  
## Nullable 형식 비교  
 Nullable `Boolean` 변수를 부울 식에 사용하는 경우 결과는 `True`, `False` 또는 `Nothing`일 수 있습니다.  아래에는 `And` 및 `Or`의 참 테이블이 나와 있습니다.  `b1` 및 `b2`에 세 개의 값을 사용할 수 있으므로 총 9개 조합을 평가해야 합니다.  
  
|b1|b2|b1 And b2|b1 Or b2|  
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
  
 부울 변수나 식의 값이 `Nothing`인 경우 `true` 도 아니고 `false`도 아닙니다.  다음 예제를 살펴보십시오.  
  
 [!code-vb[VbVbalrNullableValue#6](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/visualbasic/nullable-value-types_6.vb)]  
  
 이 예제에서 `b1 And b2`는 `Nothing`이 됩니다.  따라서 각 `If` 문에서 `Else` 절이 실행되며 출력은 다음과 같습니다.  
  
 `Expression is not true`  
  
 `Expression is not false`  
  
> [!NOTE]
>  단락 계산을 사용하는 `AndAlso` 및 `OrElse`는 첫 번째 피연산자가 `Nothing`일 때 두 번째 피연산자를 계산해야 합니다.  
  
## 전파  
 산술, 비교, 시프트 또는 형식 연산의 피연산자 중 하나 또는 둘 다가 Nullable이면 연산 결과도 Nullable입니다.  두 피연산자에 모두 `Nothing`이 아닌 값이 있는 경우 둘 다 Nullable 형식이 아닌 것처럼 피연산자의 내부 값에 연산이 수행됩니다.  다음 예제에서 `compare1` 및 `sum1` 변수는 암시적으로 형식화되어 있습니다.  변수 위에 마우스 포인터를 놓고 컴파일러에서 두 변수에 대해 Nullable 형식을 유추하는지 확인합니다.  
  
 [!code-vb[VbVbalrNullableValue#7](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/visualbasic/nullable-value-types_7.vb)]  
  
 피연산자 중 하나 또는 둘 다에 `Nothing` 값이 있는 경우 결과는 `Nothing`이 됩니다.  
  
 [!code-vb[VbVbalrNullableValue#8](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/visualbasic/nullable-value-types_8.vb)]  
  
## 데이터에 Nullable 형식 사용  
 데이터베이스는 Nullable 형식 사용이 가장 중요한 위치 중 하나입니다.  현재 일부 데이터베이스 개체는 Nullable 형식을 지원하지 않지만 디자이너에서 생성한 테이블 어댑터는 Null 허용 형식을 지원합니다.  [TableAdapter 개요](/visual-studio/data-tools/tableadapter-overview)의 "TableAdapter의 Null 허용 형식 지원"을 참조하십시오.  
  
## 참고 항목  
 <xref:System.InvalidOperationException>   
 <xref:System.Nullable%601.HasValue%2A>   
 [Nullable 형식 사용](../../../../csharp/programming-guide/nullable-types/using-nullable-types.md)   
 [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [TableAdapter 개요](/visual-studio/data-tools/tableadapter-overview)   
 [If Operator](../../../../visual-basic/language-reference/operators/if-operator.md)   
 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md)   
 [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md)