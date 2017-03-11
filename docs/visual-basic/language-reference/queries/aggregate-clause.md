---
title: "Aggregate Clause (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QueryAggregateIn"
  - "vb.QueryAggregate"
  - "vb.QueryAggregateInto"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Aggregate clause"
  - "Aggregate statement"
  - "queries [Visual Basic], Aggregate"
ms.assetid: 1315a814-5db6-4077-b34b-b141e11cc0eb
caps.latest.revision: 25
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 25
---
# Aggregate Clause (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

컬렉션에 하나 이상의 집계 함수를 적용합니다.  
  
## 구문  
  
```  
Aggregate element [As type] In collection _  
  [, element2 [As type2] In collection2, [...]]  
  [ clause ]  
  Into expressionList  
```  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`element`|필수 요소.  컬렉션의 요소를 반복하는 데 사용되는 변수입니다.|  
|`type`|선택적 요소.  `element`의 형식입니다.  형식을 지정하지 않은 경우 `element`의 형식이 `collection`에서 유추됩니다.|  
|`collection`|필수 요소.  작업할 컬렉션을 참조합니다.|  
|`clause`|선택적 요소.  Aggregate 절을 적용할 쿼리 결과의 범위를 좁히기 위한 `Where` 절과 같은 하나 이상의 쿼리 절입니다.|  
|`expressionList`|필수 요소.  컬렉션에 적용할 집계 함수를 식별하는 쉼표로 구분된 하나 이상의 식입니다.  집계 함수에 별칭을 적용하여 쿼리 결과에 대한 멤버 이름을 지정할 수 있습니다.  별칭이 제공되지 않으면 집계 함수의 이름이 사용됩니다.  예제는 이 항목 뒷부분에 있는 집계 함수에 대한 단원을 참조하십시오.|  
  
## 설명  
 `Aggregate` 절을 사용하여 쿼리에 집계 함수를 포함할 수 있습니다.  집계 함수는 값 집합에 대한 검사 및 계산을 수행하고 단일 값을 반환합니다.  쿼리 결과 형식의 멤버를 사용하여 계산된 값에 액세스할 수 있습니다.  사용할 수 있는 표준 집계 함수는 `All`, `Any`, `Average`, `Count`, `LongCount`, `Max`, `Min` 및 `Sum` 함수입니다.  이러한 함수는 SQL에서 집계를 사용해 본 개발자들에게는 익숙한 함수로  이 항목의 다음 단원에 설명되어 있습니다.  
  
 집계 함수의 결과는 쿼리 결과에 쿼리 결과 형식의 필드로 포함됩니다.  집계 함수 결과에 별칭을 제공하여 집계 값을 보관할 쿼리 결과 형식의 멤버 이름을 지정할 수 있습니다.  별칭이 제공되지 않으면 집계 함수의 이름이 사용됩니다.  
  
 `Aggregate` 절은 쿼리를 시작하거나 쿼리에 추가 절로 포함될 수 있습니다.  `Aggregate` 절이 쿼리를 시작하는 경우 결과는 `Into` 절에 지정된 집계 함수의 결과인 단일 값입니다.  `Into` 절에 여러 개의 집계 함수가 지정된 경우에는 쿼리가 단일 형식을 `Into` 절에 있는 각 집계 함수의 결과를 참조하는 별도의 속성과 함께 반환합니다.  `Aggregate` 절이 쿼리에 추가 절로 포함된 경우에는 `Into` 절에 있는 각 집계 함수의 결과를 참조하는 별도의 속성이 쿼리 컬렉션에서 반환되는 형식에 포함됩니다.  
  
## 집계 함수  
 다음 목록은 `Aggregate` 절과 함께 사용할 수 있는 표준 집계 함수에 대해 설명합니다.  
  
|||  
|-|-|  
|Function|설명|  
|`All`|컬렉션의 모든 요소가 지정된 조건을 충족하는 경우 `true`를 반환하고, 그렇지 않으면 `false`를 반환합니다.  예를 들면 다음과 같습니다.<br /><br /> [!code-vb[VbSimpleQuerySamples#5](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#5)]|  
|`Any`|지정된 조건을 충족하는 요소가 컬렉션에 하나라도 있는 경우 `true`를 반환하고, 그렇지 않으면 `false`를 반환합니다.  예를 들면 다음과 같습니다.<br /><br /> [!code-vb[VbSimpleQuerySamples#6](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#6)]|  
|`Average`|컬렉션에서 모든 요소의 평균을 계산하거나 컬렉션에 있는 모든 요소에 대해 제공된 식을 계산합니다.  예를 들면 다음과 같습니다.<br /><br /> [!code-vb[VbSimpleQuerySamples#7](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#7)]|  
|`Count`|컬렉션에 있는 요소의 수를 계산합니다.  선택적인 `Boolean` 식을 제공하여 컬렉션에 있는 요소 중 조건을 충족하는 요소의 수만 계산할 수 있습니다.  예를 들면 다음과 같습니다.<br /><br /> [!code-vb[VbSimpleQuerySamples#8](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#8)]|  
|`Group`|`Group By` 또는 `Group Join` 절의 결과로 그룹화된 쿼리 결과를 참조합니다.  `Group` 함수는 `Group By` 또는 `Group Join` 절의 `Into` 절에서만 유효합니다.  자세한 내용 및 예제를 보려면 [Group By 절](../../../visual-basic/language-reference/queries/group-by-clause.md) 및 [Group Join Clause](../../../visual-basic/language-reference/queries/group-join-clause.md)를 참조하십시오.|  
|`LongCount`|컬렉션에 있는 요소의 수를 계산합니다.  선택적인 `Boolean` 식을 제공하여 컬렉션에 있는 요소 중 조건을 충족하는 요소의 수만 계산할 수 있습니다.  결과를 `Long`으로 반환합니다.  예제를 보려면 `Count` 집계 함수를 참조하십시오.|  
|`Max`|컬렉션에서 최대값을 계산하거나 컬렉션의 모든 요소에 대해 제공된 식을 계산합니다.  예를 들면 다음과 같습니다.<br /><br /> [!code-vb[VbSimpleQuerySamples#9](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#9)]|  
|`Min`|컬렉션에서 최소값을 계산하거나 컬렉션의 모든 요소에 대해 제공된 식을 계산합니다.  예를 들면 다음과 같습니다.<br /><br /> [!code-vb[VbSimpleQuerySamples#10](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#10)]|  
|`Sum`|컬렉션에서 모든 요소의 합계를 계산하거나 컬렉션에 있는 모든 요소에 대해 제공된 식을 계산합니다.  예를 들면 다음과 같습니다.<br /><br /> [!code-vb[VbSimpleQuerySamples#15](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#15)]|  
  
## 예제  
 다음 코드 예제는 `Aggregate` 절을 사용하여 집계 함수를 쿼리 결과에 적용하는 방법을 보여 줍니다.  
  
 [!code-vb[VbSimpleQuerySamples#4](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#4)]  
  
## 사용자 정의 집계 함수 만들기  
 확장 메서드를 <xref:System.Collections.Generic.IEnumerable%601> 형식에 추가함으로써 사용자 지정 집계 함수를 쿼리 식에 포함할 수 있습니다.  그러면 사용자 지정 메서드가 집계 함수를 참조한 열거 가능한 컬렉션에서 계산 또는 작업을 수행할 수 있습니다.  확장 메서드에 대한 자세한 내용은 [확장 메서드](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)를 참조하십시오.  
  
 예를 들어 다음 코드 예제는 숫자 컬렉션의 중간 값을 계산하는 사용자 지정 집계 함수를 보여 줍니다.  `Median` 확장 메서드의 오버로드가 두 개 있습니다.  첫 번째 오버로드는 입력으로서 `IEnumerable(Of Double)` 형식의 컬렉션을 받아들입니다.  `Median` 집계 함수가 `Double` 형식의 쿼리 필드에 대해 호출될 경우에는 이 메서드가 호출되지 않습니다.  `Median` 메서드의 두 번째 오버로드는 모든 제네릭 형식을 전달받을 수 있습니다.  `Median` 메서드의 제네릭 오버로드는 `Func(Of T, Double)` 람다 식을 참조하는 두 번째 매개 변수를 사용하는데 이 식은 컬렉션에 있는 형식에 대한 값을 `Double` 형식의 해당 값으로 변환합니다.  그런 다음 중간 값의 계산을 `Median` 메서드의 다른 오버로드에 위임합니다.  람다 식에 대한 자세한 내용은 [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)을 참조하십시오.  
  
 [!code-vb[VbSimpleQuerySamples#18](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/UserDefinedAggregates.vb#18)]  
  
 다음 코드 예제에서는 `Integer` 형식의 컬렉션과 `Double` 형식의 컬렉션에 `Median` 집계 함수를 호출하는 간단한 쿼리를 보여 줍니다.  `Double` 형식의 컬렉션에 `Median` 집계 함수를 호출하는 쿼리는 입력으로서 `Double` 형식의 컬렉션을 받아들이는 `Median` 메서드의 오버로드를 호출합니다.  `Integer` 형식의 컬렉션에 `Median` 집계 함수를 호출하는 쿼리는 `Median` 메서드의 제네릭 오버로드를 호출합니다.  
  
 [!code-vb[VbSimpleQuerySamples#19](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/UserDefinedAggregates.vb#19)]  
  
## 참고 항목  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Queries](../../../visual-basic/language-reference/queries/queries.md)   
 [Select Clause](../../../visual-basic/language-reference/queries/select-clause.md)   
 [From Clause](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Where Clause](../../../visual-basic/language-reference/queries/where-clause.md)   
 [Group By 절](../../../visual-basic/language-reference/queries/group-by-clause.md)