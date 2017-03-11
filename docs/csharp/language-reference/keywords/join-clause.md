---
title: "join 절(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "join"
  - "join_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "join 절[C#]"
  - "join 키워드[C#]"
ms.assetid: 76e9df84-092c-41a6-9537-c3f1cbd7f0fb
caps.latest.revision: 29
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 29
---
# join 절(C# 참조)
`join` 절은 개체 모델에서 직접 관계가 없는 여러 소스 시퀀스의 요소를 연결하는 데 유용합니다.  유일한 요구 사항은 각 소스의 요소가 같은지 비교할 수 있는 일부 값을 공유해야 한다는 것입니다.  예를 들어 식품 유통업체에는 특정 제품의 공급자 목록과 구매자 목록이 있을 수 있습니다.  예를 들어 해당 제품의 공급자와 구매자가 모두 동일한 특정 지역에 있는 경우 `join` 절을 사용하여 이러한 공급자와 구매자의 목록을 만들 수 있습니다.  
  
 `join` 절은 두 개의 소스 시퀀스를 입력으로 사용합니다.  각 시퀀스의 요소는 다른 시퀀스의 해당 속성과 비교할 수 있는 속성이거나 이러한 속성을 포함해야 합니다.  `join` 절은 특별한 `equals` 키워드를 사용하여 지정된 키가 같은지 비교합니다.  `join` 절에서 수행하는 모든 조인은 동등 조인입니다.  `join` 절의 출력 모양은 수행하는 특정 조인 형식에 따라 달라집니다.  가장 일반적인 세 가지 조인 형식은 다음과 같습니다.  
  
-   내부 조인  
  
-   그룹 조인  
  
-   왼쪽 우선 외부 조인  
  
## 내부 조인  
 다음 예제에서는 단순한 내부 동등 조인을 보여 줍니다.  이 쿼리는 "제품 이름\/범주" 쌍의 기본 시퀀스를 생성합니다.  동일한 범주 문자열이 여러 요소에 나타납니다.  `categories`의 요소에 일치하는 `products`가 없을 경우 해당 범주는 결과에 표시되지 않습니다.  
  
 [!code-cs[cscsrefQueryKeywords#24](../../../csharp/language-reference/keywords/codesnippet/csharp/csquerykeywords/Join.cs#24)]  
  
 자세한 내용은 [방법: 내부 조인 수행](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md)를 참조하십시오.  
  
## Group Join  
 `into` 식이 있는 `join` 절을 그룹 조인이라고 합니다.  
  
 [!code-cs[cscsrefQueryKeywords#25](../../../csharp/language-reference/keywords/codesnippet/csharp/csquerykeywords/Join.cs#25)]  
  
 그룹 조인은 왼쪽 소스 시퀀스의 요소를 오른쪽 소스 시퀀스에 있는 하나 이상의 일치하는 요소와 연결하는 계층적 결과를 생성합니다.  그룹 조인은 동등한 관계형 용어가 없으며 기본적으로 개체 배열의 시퀀스입니다.  
  
 왼쪽 소스의 요소와 일치하는 오른쪽 소스 시퀀스의 요소가 없을 경우 `join` 절은 해당 항목에 대해 빈 배열을 생성합니다.  따라서 그룹 조인은 결과 시퀀스가 그룹으로 구성된다는 점을 제외하고 기본적으로 내부 동등 조인입니다.  
  
 단순히 그룹 조인의 결과를 선택하면 항목에 액세스할 수 있지만 항목이 일치하는 키를 식별할 수는 없습니다.  따라서 앞의 예제와 같이 그룹 조인의 결과를 키 이름도 있는 새 형식으로 선택하는 것이 더 유용합니다.  
  
 물론 그룹 조인의 결과를 다른 하위 쿼리의 생성기로 사용할 수도 있습니다.  
  
 [!code-cs[cscsrefQueryKeywords#26](../../../csharp/language-reference/keywords/codesnippet/csharp/csquerykeywords/Join.cs#26)]  
  
 자세한 내용은 [방법: 그룹화 조인 수행](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md)를 참조하십시오.  
  
## 왼쪽 우선 외부 조인  
 왼쪽 우선 외부 조인에서는 오른쪽 시퀀스에 일치하는 요소가 없는 경우에도 왼쪽 소스 시퀀스의 모든 요소가 반환됩니다.  [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)]에서 왼쪽 우선 외부 조인을 수행하려면 `DefaultIfEmpty` 메서드를 그룹 조인과 함께 사용하여 왼쪽 요소에 일치 항목이 없을 경우 생성할 기본 오른쪽 요소를 지정합니다.  `null`을 참조 형식의 기본값으로 사용하거나 사용자 정의 기본 형식을 지정할 수 있습니다.  다음 예제에서는 사용자 정의 기본 형식이 표시됩니다.  
  
 [!code-cs[cscsrefQueryKeywords#27](../../../csharp/language-reference/keywords/codesnippet/csharp/csquerykeywords/Join.cs#27)]  
  
 자세한 내용은 [방법: 왼쪽 우선 외부 조인 수행](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md)를 참조하십시오.  
  
## 같음 연산자  
 `join` 절은 동등 조인을 수행합니다.  즉, 일치 항목만 기준으로 두 키가 같은지 비교할 수 있습니다.  "보다 큼" 또는 "같지 않음"과 같은 다른 비교 형식은 지원되지 않습니다.  모든 조인이 동등 조인임을 확인하기 위해 `join` 절은 `==` 연산자 대신 `equals` 키워드를 사용합니다.  `equals` 키워드는 `join` 절에서만 사용할 수 있으며 `==` 연산자와 중요한 한 가지 차이점이 있습니다.  `equals`를 사용하는 경우 왼쪽 키는 외부 소스 시퀀스를 사용하고 오른쪽 키는 내부 소스를 사용합니다.  외부 소스는 `equals`의 왼쪽 범위에만 있고 내부 소스 시퀀스는 오른쪽 범위에만 있습니다.  
  
## 비동등 조인  
 여러 개의 `from` 절을 사용하여 새 시퀀스를 개별적으로 쿼리에 적용하면 비동등 조인, 교차 조인 및 기타 사용자 지정 조인 작업을 수행할 수 있습니다.  자세한 내용은 [방법: 사용자 지정 조인 작업 수행](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-custom-join-operations.md)를 참조하십시오.  
  
## 개체 컬렉션 및관계형 테이블의 조인  
 [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] 쿼리 식에서는 조인 작업이 개체 컬렉션에서 수행됩니다.  개체 컬렉션은 두 개의 관계형 테이블과 정확히 동일한 방식으로 "조인"할 수 없습니다.  [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)]에서 명시적 `join` 절은 두 개의 소스 시퀀스가 어떤 관계로도 연결되지 않은 경우에만 필요합니다.  [!INCLUDE[vbtecdlinq](../../../csharp/includes/vbtecdlinq-md.md)]을 사용하는 경우 외래 키 테이블은 개체 모델에 기본 테이블의 속성으로 표현됩니다.  예를 들어 Northwind 데이터베이스의 Customer 테이블은 Orders 테이블과 외래 키 관계가 있습니다.  테이블을 개체 모델에 매핑하면 Customer 클래스에 해당 Customer와 연결된 Orders 컬렉션을 포함하는 Orders 속성이 있습니다.  실제로 조인이 이미 수행되었습니다.  
  
 [!INCLUDE[vbtecdlinq](../../../csharp/includes/vbtecdlinq-md.md)] 컨텍스트에서 관계형 테이블을 쿼리하는 방법에 대한 자세한 내용은 [방법: 데이터베이스 관계 매핑](../Topic/How%20to:%20Map%20Database%20Relationships.md)을 참조하십시오.  
  
## 복합 키  
 복합 키를 사용하여 여러 값이 같은지 테스트할 수 있습니다.  자세한 내용은 [방법: 복합 키를 사용하여 조인](../../../csharp/programming-guide/linq-query-expressions/how-to-join-by-using-composite-keys.md)를 참조하십시오.  복합 키는 `group` 절에서도 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 일치하는 동일한 키를 사용하여 동일한 데이터 소스에서 수행한 내부 조인, 그룹 조인 및 왼쪽 우선 외부 조인의 결과를 비교합니다.  콘솔 표시의 결과를 명확하게 지정하기 위해 이러한 예제에 일부 다른 코드가 추가됩니다.  
  
 [!code-cs[cscsrefQueryKeywords#23](../../../csharp/language-reference/keywords/codesnippet/csharp/csquerykeywords/Join.cs#23)]  
  
## 설명  
 뒤에 `into`가 없는 `join` 절은 <xref:System.Linq.Enumerable.Join%2A> 메서드 호출로 변환됩니다.  뒤에 `into`가 있는 `join` 절은 <xref:System.Linq.Enumerable.GroupJoin%2A> 메서드 호출로 변환됩니다.  
  
## 참고 항목  
 [쿼리 키워드\(LINQ\)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Join Operations](../../../visual-basic/programming-guide/concepts/linq/join-operations.md)   
 [group 절](../../../csharp/language-reference/keywords/group-clause.md)   
 [방법: 왼쪽 우선 외부 조인 수행](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md)   
 [방법: 내부 조인 수행](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md)   
 [방법: 그룹화 조인 수행](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md)   
 [방법: Join 절 결과의 순서 정렬](../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md)   
 [방법: 복합 키를 사용하여 조인](../../../csharp/programming-guide/linq-query-expressions/how-to-join-by-using-composite-keys.md)   
 [방법: 샘플 데이터베이스 설치](../Topic/How%20to:%20Install%20Sample%20Databases.md)