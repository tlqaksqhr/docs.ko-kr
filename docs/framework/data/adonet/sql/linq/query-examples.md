---
title: "쿼리 예제"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 137f8677-494c-4d49-95ce-c17742f2d01f
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 1b3aabf5a47088fa408547527c5f18fa69a48e02
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="query-examples"></a>쿼리 예제
이 단원에서는 일반적인 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 쿼리에 대한 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 및 C# 예제를 제공합니다. [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]를 사용하는 개발자들은 샘플 단원에서 제공하는 샘플 솔루션에서 더 많은 예제를 찾아볼 수 있습니다. 자세한 내용은 참조 [샘플](../../../../../../docs/framework/data/adonet/sql/linq/samples.md)합니다.  
  
> [!IMPORTANT]
>  *db* 의 코드 예제에는 대개 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 설명서입니다. *db* 인스턴스의 것으로 간주 되는 *Northwind* 클래스에서 상속 하는 <xref:System.Data.Linq.DataContext>합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [집계 쿼리](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)  
 <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A> 등의 사용 방법을 설명합니다.  
  
 [시퀀스의 첫 번째 요소 반환](../../../../../../docs/framework/data/adonet/sql/linq/return-the-first-element-in-a-sequence.md)  
 <xref:System.Linq.Enumerable.First%2A> 사용 예제를 제공합니다.  
  
 [시퀀스에서 요소 반환 또는 건너뛰기](../../../../../../docs/framework/data/adonet/sql/linq/return-or-skip-elements-in-a-sequence.md)  
 <xref:System.Linq.Enumerable.Take%2A> 및 <xref:System.Linq.Enumerable.Skip%2A> 사용 예제를 제공합니다.  
  
 [시퀀스의 요소 정렬](../../../../../../docs/framework/data/adonet/sql/linq/sort-elements-in-a-sequence.md)  
 <xref:System.Linq.Enumerable.OrderBy%2A> 사용 예제를 제공합니다.  
  
 [시퀀스의 요소 그룹화](../../../../../../docs/framework/data/adonet/sql/linq/group-elements-in-a-sequence.md)  
 <xref:System.Linq.Enumerable.GroupBy%2A> 사용 예제를 제공합니다.  
  
 [시퀀스에서 중복 요소 제거](../../../../../../docs/framework/data/adonet/sql/linq/eliminate-duplicate-elements-from-a-sequence.md)  
 <xref:System.Linq.Enumerable.Distinct%2A> 사용 예제를 제공합니다.  
  
 [시퀀스에서 일부 또는 모든 요소가 조건을 만족하는지 확인](../../../../../../docs/framework/data/adonet/sql/linq/determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition.md)  
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
  
 [제네릭 목록으로 시퀀스 변환](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-sequence-to-a-generic-list.md)  
 <xref:System.Linq.Enumerable.ToList%2A> 사용 예제를 제공합니다.  
  
 [제네릭 IEnumerable로 형식 변환](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-type-to-a-generic-ienumerable.md)  
 <xref:System.Linq.Enumerable.AsEnumerable%2A> 사용 예제를 제공합니다.  
  
 [조인 및 교차곱 쿼리 작성](../../../../../../docs/framework/data/adonet/sql/linq/formulate-joins-and-cross-product-queries.md)  
 `from`, `where` 및 `select` 절에서 외래 키 탐색 사용 예제를 제공합니다.  
  
 [프로젝션 작성](../../../../../../docs/framework/data/adonet/sql/linq/formulate-projections.md)  
 결합의 예제를 제공 `select` 과 기타 기능 (예를 들어 *익명 형식*) 쿼리 투영을 만드는 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [표준 쿼리 연산자 개요](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)  
 표준 쿼리 연산자의 개념을 설명합니다.  
  
 [쿼리 개념](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 사용 개념이 쿼리에 어떻게 적용되는지 설명합니다.  
  
 [프로그래밍 가이드](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 관련 프로그래밍 개념을 설명하는 항목에 대한 포털을 제공합니다.
