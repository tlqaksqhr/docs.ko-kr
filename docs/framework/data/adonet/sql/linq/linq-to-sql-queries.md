---
title: "LINQ to SQL 쿼리 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f4897aaa-7f44-4c20-a471-b948c2971aae
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# LINQ to SQL 쿼리
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 동일한 구문을 사용하여  [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] 쿼리를 정의합니다.  유일한 차이점은 쿼리에서 참조된 개체가 데이터베이스의 요소에 매핑된다는 것입니다.  자세한 내용은 [Introduction to LINQ Queries \(C\#\)](../Topic/Introduction%20to%20LINQ%20Queries%20\(C%23\).md)를 참조하세요.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 작성한 쿼리를 해당 SQL 쿼리로 변환하고 SQL Server에 전달하여 처리합니다. 다시 말해서 응용 프로그램에서는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] API를 사용하여 쿼리 실행을 요청합니다.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 공급자는 쿼리를 SQL 텍스트로 변환하고 ADO 공급자에게 실행을 위임합니다. ADO 공급자는 `DataReader`의 결과로 쿼리를 반환합니다.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 공급자는 ADO 결과를 사용자 개체의 <xref:System.Linq.IQueryable> 컬렉션으로 변환합니다.  
  
> [!NOTE]
>  [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] 기본 제공 형식에서 대부분의 메서드와 연산자는 SQL로 직접 변환됩니다.  [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]에서 변환할 수 없는 일부는 런타임 예외를 발생시킵니다.  자세한 내용은 [SQL\-CLR 형식 매핑](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)를 참조하세요.  
  
 다음 테이블에서는 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]와 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 쿼리 항목의 유사점과 차이점에 대해 설명합니다.  
  
|항목|LINQ 쿼리|[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 쿼리|  
|--------|-------------|-------------------------------------------------------------------|  
|시퀀스를 반환하는 쿼리에 대한 쿼리를 보관하는 지역 변수의 반환 형식|제네릭 `IEnumerable`|제네릭 `IQueryable`|  
|데이터 소스 지정|`From` \([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]\) 또는 `from`\(C\#\) 절을 사용합니다.|왼쪽과 같음|  
|필터링|`Where`\/`where` 절을 사용합니다.|왼쪽과 같음|  
|그룹화|`Group…By`\/`groupby` 절을 사용합니다.|왼쪽과 같음|  
|선택\(프로젝팅\)|`Select`\/`select` 절을 사용합니다.|왼쪽과 같음|  
|지연된 실행과 즉시 실행 비교|[Introduction to LINQ Queries \(C\#\)](../Topic/Introduction%20to%20LINQ%20Queries%20\(C%23\).md)를 참조하세요.|왼쪽과 같음|  
|조인 구현|`Join`\/`join` 절을 사용합니다.|`Join`\/`join` 절을 사용할 수 있으나 <xref:System.Data.Linq.Mapping.AssociationAttribute> 속성이 보다 효율적으로 사용됩니다.  자세한 내용은 [관계 간 쿼리](../../../../../../docs/framework/data/adonet/sql/linq/querying-across-relationships.md)를 참조하세요.|  
|원격 실행과 로컬 실행 비교||자세한 내용은 [원격 실행과 로컬 실행 비교](../../../../../../docs/framework/data/adonet/sql/linq/remote-vs-local-execution.md)를 참조하세요.|  
|스트리밍 쿼리와 캐시된 쿼리 비교|지역 메모리 시나리오에서는 사용할 수 없습니다.||  
  
## 참고 항목  
 [Introduction to LINQ Queries \(C\#\)](../Topic/Introduction%20to%20LINQ%20Queries%20\(C%23\).md)   
 [Basic LINQ Query Operations](../Topic/Basic%20LINQ%20Query%20Operations%20\(C%23\).md)   
 [Type Relationships in LINQ Query Operations](../Topic/Type%20Relationships%20in%20LINQ%20Query%20Operations%20\(C%23\).md)   
 [쿼리 개념](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)