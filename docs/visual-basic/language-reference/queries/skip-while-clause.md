---
title: "Skip While Clause (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QuerySkipWhile"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Skip While statement"
  - "Skip While clause"
  - "queries [Visual Basic], Skip While"
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Skip While Clause (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

지정된 조건이 `true`이면 컬렉션에 있는 요소를 무시하고 나머지 요소를 반환합니다.  
  
## 구문  
  
```  
Skip While expression  
```  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`expression`|필수 요소.  요소를 테스트할 조건을 나타내는 식입니다.  식은 `Boolean` 값 또는 이에 상응하는 값\(예: `Boolean`으로 계산되는 `Integer`\)을 반환해야 합니다|  
  
## 설명  
 `Skip While` 절은 쿼리 결과의 시작 부분부터 제공된 `expression`에서 `false`를 반환할 때까지 요소를 건너뜁니다.  `expression`에서 `false`를 반환한 후 쿼리에서 나머지 요소를 모두 반환합니다.  `expression`은 나머지 결과에 대해 무시됩니다.  
  
 `Where` 절이 특정 조건을 만족하지 않는 쿼리에서 모든 요소를 제외하는 데 사용할 수 있다는 점에서 `Skip While` 절은 `Where` 절과 다릅니다.  `Skip While` 절은 처음으로 조건이 만족하지 않을 때까지만 요소를 제외합니다.  순서가 지정된 쿼리 결과를 사용할 때 `Skip While` 절이 가장 유용합니다.  
  
 `Skip` 절을 사용하여 쿼리 결과의 시작 부분에서 특정 수의 결과를 건너뛸 수 있습니다.  
  
## 예제  
 다음 코드 예제에서는 `Skip While` 절을 사용하여 United States의 첫 번째 고객을 찾을 때까지 결과를 건너뜁니다.  
  
 [!code-vb[VbSimpleQuerySamples#3](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-while-clause_1.vb)]  
  
## 참고 항목  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Queries](../../../visual-basic/language-reference/queries/queries.md)   
 [Select Clause](../../../visual-basic/language-reference/queries/select-clause.md)   
 [From Clause](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Skip Clause](../../../visual-basic/language-reference/queries/skip-clause.md)   
 [Take While Clause](../../../visual-basic/language-reference/queries/take-while-clause.md)   
 [Where Clause](../../../visual-basic/language-reference/queries/where-clause.md)