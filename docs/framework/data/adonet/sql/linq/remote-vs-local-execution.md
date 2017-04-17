---
title: "원격 실행과 로컬 실행 비교 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ee50e943-9349-4c84-ab1c-c35d3ada1a9c
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 원격 실행과 로컬 실행 비교
쿼리를 원격으로 실행할지\(즉, 데이터베이스 엔진이 데이터베이스에 대해 쿼리 실행\) 아니면 로컬로 실행할지\(즉, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]이 로컬 캐시에 대해 쿼리 실행\) 결정할 수 있습니다.  
  
## 원격 실행  
 다음 쿼리를 살펴보세요.  
  
 [!code-csharp[DLinqQueryConcepts#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#7)]
 [!code-vb[DLinqQueryConcepts#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#7)]  
  
 데이터베이스에 수천 개의 주문 행이 있는 경우 작은 하위 집합을 처리하기 위해 이러한 행을 모두 검색하고 싶지 않을 것입니다.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 <xref:System.Data.Linq.EntitySet%601> 클래스는 <xref:System.Linq.IQueryable> 인터페이스를 구현합니다.  이 방법을 사용하면 이러한 쿼리를 원격으로 실행할 수 있습니다.  이 기술의 두 가지 주요 이점은 다음과 같습니다.  
  
-   불필요한 데이터가 검색되지 않습니다.  
  
-   데이터베이스 엔진이 실행하는 쿼리는 일반적으로 데이터베이스 인덱스로 인해 더 효율적입니다.  
  
## 로컬 실행  
 다른 상황에서는 관련 엔터티의 전체 집합을 로컬 캐시에 포함하려고 할 수 있습니다.  이를 위해 <xref:System.Data.Linq.EntitySet%601>은 <xref:System.Data.Linq.EntitySet%601>의 모든 멤버를 명시적으로 로드하기 위한 <xref:System.Data.Linq.EntitySet%601.Load%2A> 메서드를 제공합니다.  
  
 <xref:System.Data.Linq.EntitySet%601>이 이미 로드된 경우 후속 쿼리는 로컬로 실행됩니다.  이 방법은 다음과 같은 두 가지 이점이 있습니다.  
  
-   전체 집합을 로컬로 사용하거나 여러 번 사용해야 할 경우 원격 쿼리 및 연관된 대기 시간을 방지할 수 있습니다.  
  
-   엔터티를 완전한 엔터티로 serialize할 수 있습니다.  
  
 다음 코드 조각에서는 로컬 실행을 수행하는 방법을 보여 줍니다.  
  
 [!code-csharp[DLinqQueryConcepts#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#8)]
 [!code-vb[DLinqQueryConcepts#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#8)]  
  
## 비교  
 이러한 두 기능은 대규모 컬렉션을 위한 원격 실행과 소규모 컬렉션 또는 완전한 컬렉션이 필요한 상황을 위한 로컬 실행이라는 옵션이 결합된 강력한 기능을 제공합니다.  <xref:System.Linq.IQueryable>을 통해 원격 실행을 구현하고 메모리 내 <xref:System.Collections.Generic.IEnumerable%601> 컬렉션에 대해 로컬 실행을 구현합니다.  로컬 실행을 강제하려면\(즉, <xref:System.Collections.Generic.IEnumerable%601>\) [형식을 제네릭 IEnumerable로 변환](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-type-to-a-generic-ienumerable.md)을 참조하세요.  
  
### 정렬되지 않은 집합에 대한 쿼리  
 <xref:System.Collections.Generic.List%601>를 구현하는 로컬 컬렉션과 관계형 데이터베이스의 *정렬되지 않은 집합*에 대해 실행되는 원격 쿼리를 제공하는 컬렉션의 중요한 차이점에 주의해야 합니다.  인덱스 값을 사용하는 메서드와 같은 <xref:System.Collections.Generic.List%601> 메서드에는 목록 의미 체계가 필요한데 이는 일반적으로 정렬되지 않은 집합에 대한 원격 쿼리를 통해 얻을 수 없습니다.  이와 같은 이유 때문에 이러한 메서드는 로컬 실행을 허용하기 위해 <xref:System.Data.Linq.EntitySet%601>을 암시적으로 로드합니다.  
  
## 참고 항목  
 [쿼리 개념](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)