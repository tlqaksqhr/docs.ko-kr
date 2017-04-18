---
title: "방법: 데이터베이스에서 행 삭제 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2144c99b-8055-4080-a5c6-1ea14335e2a3
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# 방법: 데이터베이스에서 행 삭제
테이블 관련 컬렉션에서 해당 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 개체를 제거하여 데이터베이스의 행을 삭제할 수 있습니다. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 사용자의 변경 내용을 적절한 SQL `DELETE` 명령으로 변환합니다.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 하위 삭제 작업을 지원하거나 인식하지 않습니다.  제약 조건이 있는 테이블의 행을 삭제하려면 다음 작업 중 하나를 수행해야 합니다.  
  
-   데이터베이스의 외래 키 제약 조건에 `ON DELETE CASCADE` 규칙을 설정합니다.  
  
-   사용자 고유의 코드를 사용하여 부모 개체를 삭제하는 데 방해가 되는 자식 개체를 먼저 삭제합니다.  
  
 그러지 않으면 예외가 throw됩니다.  이 항목의 뒷부분에 있는 두 번째 코드 예제를 참조하세요.  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], `Insert` 및 `Update` 데이터베이스 작업에 대한 `Delete` 기본 메서드를 재정의할 수 있습니다.  자세한 내용은 [삽입, 업데이트 및 삭제 작업 사용자 지정](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)을 참조하세요.  
>   
>  [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]를 사용하는 개발자는 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]를 사용하여 동일한 용도로 저장 프로시저를 개발할 수 있습니다.  
  
 다음 단계에서는 올바른 <xref:System.Data.Linq.DataContext>를 사용하여 사용자가 Northwind 데이터베이스에 연결되는 것으로 가정합니다.  자세한 내용은 [방법: 데이터베이스에 연결](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md)을 참조하세요.  
  
### 데이터베이스에서 행을 삭제하려면  
  
1.  삭제할 행에 대한 데이터베이스를 쿼리합니다.  
  
2.  <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> 메서드를 호출합니다.  
  
3.  데이터베이스에 변경 내용을 전송합니다.  
  
## 예제  
 첫째 코드 예제에서는 데이터베이스에서 Order \#11000에 속하는 주문 상세 정보를 쿼리하고 이러한 주문 상세 정보를 삭제하도록 표시한 다음 변경 내용을 데이터베이스에 전송합니다.  
  
 [!code-csharp[System.Data.Linq.Table#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#3)]
 [!code-vb[System.Data.Linq.Table#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#3)]  
  
## 예제  
 두 번째 예제의 목표는 주문\(\#10250\)을 제거하는 것입니다.  이 코드에서는 먼저 `OrderDetails` 테이블을 조사하여 제거할 주문에 자식 개체가 있는지 여부를 확인합니다.  주문에 자식 개체가 있으면 먼저 해당 자식을 제거한 다음 주문을 제거하도록 표시합니다.  <xref:System.Data.Linq.DataContext>에서는 데이터베이스로 전달되는 삭제 명령이 데이터베이스 제약 조건을 따르도록 실제 삭제 작업을 올바른 순서대로 배치합니다.  
  
 [!code-csharp[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCascadeWorkaround/cs/Program.cs#1)]
 [!code-vb[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCascadeWorkaround/vb/Module1.vb#1)]  
  
## 참고 항목  
 [방법: 변경 내용 충돌 관리](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)   
 [방법: 저장 프로시저를 할당하여 업데이트, 삽입 및 삭제 수행\(O\/R 디자이너\)](../Topic/How%20to:%20Assign%20stored%20procedures%20to%20perform%20updates,%20inserts,%20and%20deletes%20\(O-R%20Designer\).md)   
 [데이터 변경 및 변경 내용 전송](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)