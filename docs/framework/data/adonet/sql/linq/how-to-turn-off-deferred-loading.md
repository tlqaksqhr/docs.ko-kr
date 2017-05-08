---
title: "방법: 지연된 로드 해제 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1b84b852-3cad-41a7-8077-149a70d50c8b
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 방법: 지연된 로드 해제
<xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A>를 `false`로 설정하여 지연된 로드를 해제할 수 있습니다.  자세한 내용은 [지연된 로드와 즉시 로드 비교](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)을 참조하세요.  
  
> [!NOTE]
>  개체 추적이 해제되면 지연된 로드는 암시적으로 해제된 것입니다.  자세한 내용은 [방법: 정보를 읽기 전용으로 검색](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-information-as-read-only.md)을 참조하세요.  
  
## 예제  
 다음 예제에서는 <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A>를 `false`로 설정하여 지연된 로드를 해제하는 방법을 보여 줍니다.  
  
 [!code-csharp[DLinqQuerying#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#3)]
 [!code-vb[DLinqQuerying#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#3)]  
  
## 참고 항목  
 [쿼리 개념](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)   
 [데이터베이스 쿼리](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)