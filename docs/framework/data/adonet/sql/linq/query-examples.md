---
title: "쿼리 예제 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 137f8677-494c-4d49-95ce-c17742f2d01f
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 쿼리 예제
이 단원에서는 일반적인 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 쿼리에 대한 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 및 C\# 예제를 제공합니다.  [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]를 사용하는 개발자들은 샘플 단원에서 제공하는 샘플 솔루션에서 더 많은 예제를 찾아볼 수 있습니다.  자세한 내용은 [샘플](../../../../../../docs/framework/data/adonet/sql/linq/samples.md)을 참조하세요.  
  
> [!IMPORTANT]
>  *db*는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 설명서의 코드 예제에서 자주 사용됩니다.  *db*는 *Northwind* 클래스의 인스턴스로 간주되며 <xref:System.Data.Linq.DataContext>에서 상속됩니다.  
  
## 단원 내용  
 [집계 쿼리](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)  
 <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A> 등의 사용 방법을 설명합니다.  
  
 [시퀀스의 첫 번째 요소 반환](../../../../../../docs/framework/data/adonet/sql/linq/return-the-first-element-in-a-sequence.md)  
 <xref:System.Linq.Enumerable.First%2A> 사용 예제를 제공합니다.  
  
 [시퀀스의 요소 반환 또는 건너뛰기](../../../../../../docs/framework/data/adonet/sql/linq/return-or-skip-elements-in-a-sequence.md)  
 <xref:System.Linq.Enumerable.Take%2A> 및 <xref:System.Linq.Enumerable.Skip%2A> 사용 예제를 제공합니다.  
  
 [시퀀스의 요소 정렬](../../../../../../docs/framework/data/adonet/sql/linq/sort-elements-in-a-sequence.md)  
 <xref:System.Linq.Enumerable.OrderBy%2A> 사용 예제를 제공합니다.  
  
 [시퀀스의 요소 그룹화](../../../../../../docs/framework/data/adonet/sql/linq/group-elements-in-a-sequence.md)  
 <xref:System.Linq.Enumerable.GroupBy%2A> 사용 예제를 제공합니다.  
  
 [시퀀스에서 중복 요소 제거](../../../../../../docs/framework/data/adonet/sql/linq/eliminate-duplicate-elements-from-a-sequence.md)  
 <xref:System.Linq.Enumerable.Distinct%2A> 사용 예제를 제공합니다.  
  
 [시퀀스의 요소 중 하나 또는 모든 요소가 조건에 맞는지 확인](../../../../../../docs/framework/data/adonet/sql/linq/determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition.md)  
 <xref:System.Linq.Enumerable.All%2A> 및 <xref:System.Linq.Enumerable.Any%2A> 사용 예제를 제공합니다.  
  
 [두 시퀀스 연결](../../../../../../docs/framework/data/adonet/sql/linq/concatenate-two-sequences.md)  
 <xref:System.Linq.Enumerable.Concat%2A> 사용 예제를 제공합니다.  
  
 [두 시퀀스 간의 차집합 반환](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-difference-between-two-sequences.md)  
 <xref:System.Linq.Enumerable.Except%2A> 사용 예제를 제공합니다.  
  
 [두 시퀀스의 교집합 반환](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-intersection-of-two-sequences.md)  
 <xref:System.Linq.Enumerable.Intersect%2A> 사용 예제를 제공합니다.  
  
 [두 시퀀스의 합집합 반환](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-union-of-two-sequences.md)  
 <xref:System.Linq.Enumerable.Union%2A> 사용 예제를 제공합니다.  
  
 [시퀀스를 배열로 변환](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-sequence-to-an-array.md)  
 <xref:System.Linq.Enumerable.ToArray%2A> 사용 예제를 제공합니다.  
  
 [시퀀스를 제네릭 목록으로 변환](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-sequence-to-a-generic-list.md)  
 <xref:System.Linq.Enumerable.ToList%2A> 사용 예제를 제공합니다.  
  
 [형식을 제네릭 IEnumerable로 변환](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-type-to-a-generic-ienumerable.md)  
 <xref:System.Linq.Enumerable.AsEnumerable%2A> 사용 예제를 제공합니다.  
  
 [조인 및 외적 쿼리 작성](../../../../../../docs/framework/data/adonet/sql/linq/formulate-joins-and-cross-product-queries.md)  
 `from`, `where` 및 `select` 절에서 외래 키 탐색 사용 예제를 제공합니다.  
  
 [투영 작성](../../../../../../docs/framework/data/adonet/sql/linq/formulate-projections.md)  
 `select`와 *익명 형식*과 같은 다른 기능을 결합하여 쿼리 프로젝션을 구성하는 예를 제공합니다.  
  
## 관련 단원  
 [Standard Query Operators Overview](../../../../../../ocs/visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 표준 쿼리 연산자의 개념을 설명합니다.  
  
 [쿼리 개념](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 사용 개념이 쿼리에 어떻게 적용되는지 설명합니다.  
  
 [프로그래밍 가이드](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 관련 프로그래밍 개념을 설명하는 항목에 대한 포털을 제공합니다.