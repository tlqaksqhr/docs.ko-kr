---
title: "방법: 데이터베이스에 행 삽입 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 44d99680-69c7-4879-a732-f6771b334211
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# 방법: 데이터베이스에 행 삽입
개체를 연결된 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> 컬렉션에 추가한 다음 변경 내용을 데이터베이스에 전송하여 행을 데이터베이스에 삽입합니다. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 변경 내용을 적절한 SQL `INSERT` 명령으로 변환합니다.  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], `Insert` 및 `Update` 데이터베이스 작업에 대한 `Delete` 기본 메서드를 재정의할 수 있습니다.  자세한 내용은 [삽입, 업데이트 및 삭제 작업 사용자 지정](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)을 참조하세요.  
>   
>  [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]를 사용하는 개발자는 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]를 사용하여 동일한 용도로 저장 프로시저를 개발할 수 있습니다.  
  
 다음 단계에서는 올바른 <xref:System.Data.Linq.DataContext>를 사용하여 사용자가 Northwind 데이터베이스에 연결되는 것으로 가정합니다.  자세한 내용은 [방법: 데이터베이스에 연결](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md)을 참조하세요.  
  
### 데이터베이스에 행을 삽입하려면  
  
1.  전송할 행 데이터가 있는 새 개체를 만듭니다.  
  
2.  새 개체를 데이터베이스의 대상 테이블에 연결된 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] `Table` 컬렉션에 추가합니다.  
  
3.  데이터베이스에 변경 내용을 전송합니다.  
  
## 예제  
 다음 코드 예제에서는 `Order` 형식의 새 개체를 만들어 적절한 값을 채웁니다.  그런 다음 새 개체를 `Order` 컬렉션에 추가합니다.  마지막으로 변경 내용을 `Orders` 테이블의 새 행으로 데이터베이스에 전송합니다.  
  
 [!code-csharp[System.Data.Linq.Table#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.Table#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#1)]  
  
## 참고 항목  
 [방법: 변경 내용 충돌 관리](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)   
 [DataContext 메서드\(O\/R 디자이너\)](../Topic/DataContext%20Methods%20\(O-R%20Designer\).md)   
 [방법: 저장 프로시저를 할당하여 업데이트, 삽입 및 삭제 수행\(O\/R 디자이너\)](../Topic/How%20to:%20Assign%20stored%20procedures%20to%20perform%20updates,%20inserts,%20and%20deletes%20\(O-R%20Designer\).md)   
 [데이터 변경 및 변경 내용 전송](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)