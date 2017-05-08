---
title: "LINQ to Entities 쿼리의 표준 쿼리 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: 7fa55a9b-6219-473d-b1e5-2884a32dcdff
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# LINQ to Entities 쿼리의 표준 쿼리 연산자
쿼리에는 데이터 소스에서 검색하려는 정보를 지정합니다.  또한 정보를 반환하기 전에 정보에 대한 정렬, 그룹화 및 구체화하는 방법을 쿼리에 지정할 수 있습니다.  LINQ에서는 쿼리에서 사용할 수 있는 표준 쿼리 메서드 집합을 제공합니다.  이 메서드 중 대부분은 시퀀스에서 작동합니다. 여기서 시퀀스란 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스 또는 <xref:System.Linq.IQueryable%601> 인터페이스를 구현하는 형식의 개체입니다.  표준 쿼리 연산자 쿼리 기능에는 필터링, 프로젝션, 집계, 정렬, 그룹화, 페이징 등이 포함됩니다.  자주 사용되는 표준 쿼리 연산자 중 일부는 전용 키워드 구문이 있어서 쿼리 식 구문을 사용하여 호출할 수 있습니다.  쿼리 식은 메서드 기반 방법과는 다른, 가독성이 더 우수한 쿼리 표현 방법입니다.  쿼리 식 절은 컴파일 타임에 쿼리 메서드 호출로 변환됩니다.  해당 쿼리 식 절이 있는 표준 쿼리 연산자의 목록은 [Standard Query Operators Overview](../../../../../../ocs/visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)를 참조하세요.  
  
 일부 표준 쿼리 연산자는 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] 쿼리에서 지원되지 않습니다.  자세한 내용은 [지원되는 LINQ 메서드 및 지원되지 않는 LINQ 메서드\(LINQ to Entities\)](../../../../../../docs/framework/data/adonet/ef/language-reference/supported-and-unsupported-linq-methods-linq-to-entities.md)를 참조하세요. 이 항목에서는 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]와 관련된 표준 쿼리 연산자에 대한 정보를 제공합니다.  [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] 쿼리의 알려진 문제에 대한 자세한 내용은 [LINQ to Entities의 알려진 문제 및 고려 사항](../../../../../../docs/framework/data/adonet/ef/language-reference/known-issues-and-considerations-in-linq-to-entities.md)를 참조하세요.  
  
## 프로젝션 및 필터링 메서드  
 *프로젝션*은 결과 집합의 요소를 원하는 형태로 변환하는 것을 말합니다.  예를 들어, 결과 집합의 각 개체에서 필요한 속성의 하위 집합을 프로젝션하거나, 속성을 프로젝션하여 이에 대해 수학적 계산을 수행하거나, 개체 자체를 결과 집합으로부터 프로젝션할 수 있습니다.  프로젝션 메서드는 `Select` 및 `SelectMany`입니다.  
  
 *필터링*은 지정된 조건과 일치하는 요소만 포함하도록 결과 집합을 제한하는 작업을 가리킵니다.  필터링 메서드는 `Where`입니다.  
  
 위치 인수를 사용하는 메서드를 제외하고, 프로젝션 및 필터링 메서드의 오버로드 대부분은 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]에서 지원됩니다.  
  
## 조인 메서드  
 조인은 서로 탐색할 수 없는 관계를 가진 데이터 소스를 대상으로 하는 쿼리에 사용되는 중요한 작업입니다.  두 데이터 소스를 조인하는 것은 한 데이터 소스의 개체를 공통 특성 또는 속성을 공유하는 다른 데이터 소스의 개체와 연결하는 것입니다.  조인 메서드는 `Join` 및 `GroupJoin`입니다.  
  
 <xref:System.Collections.Generic.IEqualityComparer%601>를 사용하는 메서드를 제외하고, 조인 메서드의 오버로드 중 대부분이 지원됩니다.  이는 비교자를 데이터 원본으로 변환할 수 없기 때문입니다.  
  
## Set 메서드  
 LINQ의 Set 작업은 동일 컬렉션이나 다른 컬렉션\(또는 집합\)에 동등한 요소가 있는지 여부에 따라 결과 집합이 결정되는 쿼리 작업입니다.  set 메서드는 `All`, `Any`, `Concat`, `Contains`, `DefaultIfEmpty`, `Distinct`, `EqualAll`, `Except`, `Intersect` 및 `Union`입니다.  
  
 set 메서드의 오버로드 중 대부분은 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]에서 지원되지만, LINQ to Objects와 비교하여 다소 동작의 차이가 있습니다.  그러나 <xref:System.Collections.Generic.IEqualityComparer%601>를 사용하는 set 메서드는 지원되지 않습니다. 이 비교자는 데이터 원본으로 변환될 수 없기 때문입니다.  
  
## 정렬 메서드  
 정렬은 하나 이상의 특성을 기준으로 결과 집합의 요소를 정렬하는 작업을 가리킵니다.  정렬 조건 둘 이상을 지정하여 그룹 내의 결속을 끊을 수 있습니다.  
  
 <xref:System.Collections.Generic.IComparer%601>를 사용하는 메서드를 제외하고, 정렬 메서드의 오버로드 중 대부분이 지원됩니다.  이는 비교자를 데이터 원본으로 변환할 수 없기 때문입니다.  정렬 메서드는 `OrderBy`, `OrderByDescending`, `ThenBy`, `ThenByDescending` 및 `Reverse`입니다.  
  
 쿼리가 데이터 소스에서 실행되므로 정렬 동작이 CLR에서 실행되는 쿼리와 다를 수 있습니다.  이는 대소문자 정렬, 간지 정렬, null 정렬과 같은 정렬 옵션을 데이터 소스에서 설정할 수 있기 때문입니다.  데이터 소스에 따라 이러한 정렬 옵션이 CLR에서와 다른 결과를 생성할 수 있습니다.  
  
 둘 이상의 정렬 작업에서 동일한 키 선택기를 지정한 경우 중복 정렬이 생성됩니다.  이는 유효하지 않으며 예외가 throw됩니다.  
  
## 그룹화 메서드  
 그룹화는 데이터를 그룹에 배치하여 각 그룹의 요소가 공통 특성을 공유하게 하는 작업을 가리킵니다.  그룹화 메서드는 `GroupBy`입니다.  
  
 <xref:System.Collections.Generic.IEqualityComparer%601>를 사용하는 메서드를 제외하고, 그룹화 메서드의 오버로드 중 대부분이 지원됩니다.  이는 비교자를 데이터 원본으로 변환할 수 없기 때문입니다.  
  
 그룹화 메서드는 키 선택기에 대한 고유의 하위 쿼리를 사용하여 데이터 소스에 매핑됩니다.  키 선택기 비교 하위 쿼리는 `null` 값 비교 관련 항목을 포함하여 데이터 원본의 의미 체계를 사용하여 실행됩니다.  
  
## 집계 메서드  
 집계 작업에서는 값의 컬렉션에서 하나의 값을 계산합니다.  예를 들어, 일일 온도 값 1개월분에서 평균 일일 온도를 계산하는 것이 집계 작업입니다.  집계 메서드는 `Aggregate`, `Average`, `Count`, `LongCount`, `Max`, `Min` 및 `Sum`입니다.  
  
 집계 메서드의 오버로드 중 대부분이 지원됩니다.  null 값 관련 동작의 경우 집계 메서드에는 데이터 원본 의미 체계가 사용됩니다.  null 값이 사용되는 경우, 집계 메서드의 동작은 사용 중인 백 엔드 데이터 소스에 따라 달라질 수 있습니다.  데이터 소스의 의미 체계를 사용하는 집계 메서드 동작은 CLR 메서드에서 실행되는 것과 다를 수도 있습니다.  예를 들어, SQL Server에서 `Sum` 메서드의 기본 동작은 예외를 throw하지 않고 모든 null 값을 무시하는 것입니다.  
  
 `Sum` 함수로부터의 오버플로와 같이 집계에서 발생하는 예외는 쿼리 결과의 구체화 과정에서 데이터 소스 예외 또는 Entity Framework 예외로 throw됩니다.  
  
 `Sum` 또는 `Average` 등과 같이 시퀀스에 대한 계산을 수행하는 메서드에서 실제 계산은 서버에서 수행됩니다.  따라서 서버에서 형식 변환 및 정밀도 손실이 발생할 수 있으며, CLR 의미 체계를 사용할 때와는 다른 결과가 나오기도 합니다.  
  
 null 값 및 null이 아닌 값에 대한 집계 메서드의 기본 동작은 다음 표를 참조하세요.  
  
|메서드|데이터 없음|모든 null 값|일부 null 값|null 값 없음|  
|---------|------------|---------------|---------------|---------------|  
|`Average`|@FSHO2@null을 반환합니다.|@FSHO2@null을 반환합니다.|시퀀스의 null이 아닌 값의 평균을 반환합니다.|숫자 값 시퀀스의 평균을 계산합니다.|  
|`Count`|0을 반환합니다.|시퀀스의 null 값의 개수를 반환합니다.|시퀀스의 null 값과 null이 아닌 값의 개수를 반환합니다.|시퀀스의 요소 개수를 반환합니다.|  
|`Max`|@FSHO2@null을 반환합니다.|@FSHO2@null을 반환합니다.|시퀀스의 null이 아닌 값의 최대값을 반환합니다.|시퀀스의 최대값을 반환합니다.|  
|`Min`|@FSHO2@null을 반환합니다.|@FSHO2@null을 반환합니다.|시퀀스의 null이 아닌 값의 최소값을 반환합니다.|시퀀스의 최소값을 반환합니다.|  
|`Sum`|@FSHO2@null을 반환합니다.|@FSHO2@null을 반환합니다.|시퀀스의 null이 아닌 값의 합계를 반환합니다.|숫자 값 시퀀스의 합계를 계산합니다.|  
  
## 형식 메서드  
 형식 변환과 테스트를 다루는 두 LINQ 메서드는 모두 [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]의 컨텍스트에서 지원됩니다.  즉 해당 [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] 형식에 매핑되는 형식만 지원됩니다.  이 형식의 목록은 [Conceptual Model Types \(CSDL\)](http://msdn.microsoft.com/ko-kr/987b995f-e429-4569-9559-b4146744def4)을 참조하세요.  형식 메서드는 `Convert` 및 `OfType`입니다.  
  
 `OfType`은 엔터티 형식에 대해 지원됩니다.  `Convert`는 개념적 모델 기본 형식에 대해 지원됩니다.  C\# `is` 및 `as` 메서드 역시 지원됩니다.  
  
## 페이징 메서드  
 페이징 작업은 시퀀스에서 특정 단일 요소를 반환합니다.  이 요소 메서드는 `ElementAt`, `First`, `FirstOrDefault`, `Last`, `LastOrDefault`, `Single`, `Skip`, `Take` 및 `TakeWhile`입니다.  
  
 함수를 데이터 원본에 매핑할 수 없거나 데이터 원본 내에 집합이 암시적으로 정렬되어 있지 않아서 페이징 메서드 중 상당수가 지원되지 않습니다.  기본값을 반환하는 메서드는 null 기본값을 갖는 개념적 모델 기본 형식과 참조 형식으로 제한됩니다.  빈 시퀀스에서 페이징 메서드가 실행되면 null이 반환됩니다.  
  
## 참고 항목  
 [지원되는 LINQ 메서드 및 지원되지 않는 LINQ 메서드\(LINQ to Entities\)](../../../../../../docs/framework/data/adonet/ef/language-reference/supported-and-unsupported-linq-methods-linq-to-entities.md)   
 [Standard Query Operators Overview](../../../../../../ocs/visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)