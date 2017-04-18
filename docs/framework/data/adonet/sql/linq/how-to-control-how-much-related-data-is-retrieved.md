---
title: "방법: 관련 데이터가 검색되는 양 제어 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: efdc203e-3da9-4477-815e-54f10c3d7c6c
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 방법: 관련 데이터가 검색되는 양 제어
<xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> 메서드를 사용하여 동시에 검색되어야 하는 주 대상과 관련된 데이터를 지정합니다.  예를 들어 고객 주문에 대한 정보가 필요한 경우 <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>를 사용하여 주문 정보와 고객 정보가 검색되었는지 확인합니다.  이 접근 방법은 두 가지 정보에 대한 데이터베이스에서 원트립만의 결과입니다.  
  
> [!NOTE]
>  고객을 대상으로 할 경우 주문을 검색하는 것과 같이 외적을 하나의 큰 프로젝션처럼 검색하여 쿼리의 주 대상과 관련된 데이터를 검색할 수 있습니다.  그러나 이러한 방법에는 종종 단점이 있습니다.  예를 들어 결과는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 변경되고 유지될 수 있는 엔터티가 아니라 프로젝션에 불과합니다. 또한 필요하지 않은 많은 데이터가 검색될 수 있습니다.  
  
## 예제  
 다음 예제에서 쿼리를 실행하면 런던에 살고 있는 모든 `Customers`에 대한 모든 `Orders`가 검색됩니다.  따라서 이후에 `Customer` 개체의 `Orders` 속성에 액세스해도 새 데이터베이스 쿼리가 트리거되지 않습니다.  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.DataLoadOptions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#2)]  
  
## 참고 항목  
 [데이터베이스 쿼리](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)