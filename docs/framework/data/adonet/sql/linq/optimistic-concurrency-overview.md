---
title: "낙관적 동시성: 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c2e38512-d0c8-4807-b30a-cb7e30338694
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 낙관적 동시성: 개요
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 낙관적 동시성 제어를 지원합니다.  다음 표에서는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 설명서의 낙관적 동시성에 적용되는 용어에 대해 설명합니다.  
  
|용어|설명|  
|--------|--------|  
|동시성|둘 이상의 사용자가 동일한 데이터베이스 행을 동시에 업데이트하려는 상황입니다.|  
|동시성 충돌|둘 이상의 사용자가 한 행의 하나 이상의 열에 충돌하는 값을 동시에 전송하려는 상황입니다.|  
|동시성 제어|동시성 충돌을 해결하는 데 사용되는 기술입니다.|  
|낙관적 동시성 제어|변경 내용이 전송되도록 허용하기 전에 다른 트랜잭션에서 행의 값을 변경했는지 조사하는 기술입니다.<br /><br /> 동시성 충돌을 방지하기 위해 레코드를 잠그는 *비관적 동시성 제어*와 대비됩니다.<br /><br /> *낙관적* 제어라는 용어가 사용된 것은 한 트랜잭션이 다른 트랜잭션을 방해할 가능성이 거의 없다고 간주하기 때문입니다.|  
|충돌 해결|데이터베이스를 다시 쿼리한 다음 차이를 조정하여 충돌하는 항목을 새로 고치는 프로세스입니다.<br /><br /> 개체를 새로 고칠 경우 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 변경 추적기는 다음 데이터를 보유합니다.<br /><br /> -   처음에 데이터베이스에서 가져왔으며 업데이트 확인에 사용되는 값<br />-   후속 쿼리의 새 데이터베이스 값<br /><br /> 그런 다음 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 개체가 충돌하는지 여부\(즉, 해당 멤버 값 중 하나 이상이 변경되었는지 여부\)를 확인합니다.  개체가 충돌할 경우 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 해당 멤버 중에서 충돌하는 멤버를 확인합니다.<br /><br /> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]이 검색한 모든 멤버 충돌은 충돌 목록에 추가됩니다.|  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 개체 모델에서 *낙관적 동시성 충돌*은 다음 조건을 모두 충족할 경우 발생합니다.  
  
-   클라이언트가 변경 내용을 데이터베이스로 전송하려고 합니다.  
  
-   하나 이상의 업데이트 확인 값이 클라이언트가 마지막으로 읽은 후에 데이터베이스에서 업데이트되었습니다.  
  
 이 충돌을 해결하는 과정에는 충돌하는 개체의 멤버를 검색한 다음 수행할 작업을 결정하는 작업이 포함됩니다.  
  
> [!NOTE]
>  <xref:System.Data.Linq.Mapping.UpdateCheck> 또는 <xref:System.Data.Linq.Mapping.UpdateCheck>로 매핑된 멤버만 낙관적 동시성 검사에 참여합니다.  <xref:System.Data.Linq.Mapping.UpdateCheck>로 표시된 멤버에는 검사가 수행되지 않습니다.  자세한 내용은 <xref:System.Data.Linq.Mapping.UpdateCheck>을 참조하세요.  
  
## 예제  
 예를 들어, 다음 시나리오에서 User1은 데이터베이스에서 행을 쿼리하여 업데이트 준비를 시작합니다.  User1은 Alfreds, Maria 및 Sales 값을 가진 행을 받습니다.  
  
 User1은 Manager 열의 값을 Alfred로 변경하고 Department 열의 값을 Marketing으로 변경하려고 합니다.  User1이 이러한 변경 내용을 전송하기 전에 User2가 데이터베이스에 변경 내용을 전송했습니다.  따라서 이제 Assistant 열의 값은 Mary로 변경되고 Department 열의 값은 Service로 변경되었습니다.  
  
 이제 User1이 변경 내용을 전송하려고 하면 전송이 실패하고 <xref:System.Data.Linq.ChangeConflictException> 예외가 throw됩니다.  Assistant 열과 Department 열에 대한 데이터베이스 값이 예상했던 것과 다르기 때문에 이 결과가 발생합니다.  Assistant 및 Department 열을 나타내는 멤버가 충돌합니다.  다음 표에서는 이 상황을 요약하여 보여 줍니다.  
  
||Manager|Assistant|Department|  
|------|-------------|---------------|----------------|  
|원래 상태|Alfreds|Maria|Sales|  
|User1|Alfred||Marketing|  
|User2||Mary|서비스|  
  
 여러 다른 방법으로 이와 같은 충돌을 해결할 수 있습니다.  자세한 내용은 [방법: 변경 내용 충돌 관리](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)을 참조하세요.  
  
## 충돌 감지 및 해결 검사 목록  
 모든 상세 수준에서 충돌을 감지하고 해결할 수 있습니다.  한편으로는 추가 고려 사항 없이 세 가지 방법\(<xref:System.Data.Linq.RefreshMode> 참조\) 중 하나로 모든 충돌을 해결할 수도 있고  다른 한편으로는 충돌하는 모든 멤버에서 각 충돌 유형에 대한 특정 작업을 지정할 수도 있습니다.  
  
-   개체 모델에서 <xref:System.Data.Linq.Mapping.UpdateCheck> 옵션을 지정하거나 수정합니다.  
  
     자세한 내용은 [방법: 동시성 충돌 테스트 대상 멤버 지정](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)을 참조하세요.  
  
-   <xref:System.Data.Linq.DataContext.SubmitChanges%2A>에 대한 호출의 try\/catch 블록에서 예외를 throw하려는 지점을 지정합니다.  
  
     자세한 내용은 [방법: 동시성 예외가 throw되는 시점 지정](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-when-concurrency-exceptions-are-thrown.md)을 참조하세요.  
  
-   검색하려는 충돌 정보의 양을 결정하고 이에 따라 try\/catch 블록에 코드를 포함시킵니다.  
  
     자세한 내용은 [방법: 엔터티 충돌 정보 검색](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-entity-conflict-information.md) 및 [방법: 멤버 충돌 정보 검색](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-member-conflict-information.md)를 참조하세요.  
  
-   검색한 다양한 충돌을 해결하려는 방법을 `try`\/`catch` 코드에 포함시킵니다.  
  
     자세한 내용은 [방법: 데이터베이스 값을 유지하여 충돌 해결](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-retaining-database-values.md), [방법: 데이터베이스 값을 덮어써서 충돌 해결](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-overwriting-database-values.md) 및 [방법: 데이터베이스 값과 병합하여 충돌 해결](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-merging-with-database-values.md)을 참조하세요.  
  
## 충돌 검색 및 해결을 지원하는 LINQ to SQL 형식  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 낙관적 동시성의 충돌 해결을 지원하기 위한 클래스와 기능은 다음과 같습니다.  
  
-   <xref:System.Data.Linq.ObjectChangeConflict?displayProperty=fullName>  
  
-   <xref:System.Data.Linq.MemberChangeConflict?displayProperty=fullName>  
  
-   <xref:System.Data.Linq.ChangeConflictCollection?displayProperty=fullName>  
  
-   <xref:System.Data.Linq.ChangeConflictException?displayProperty=fullName>  
  
-   <xref:System.Data.Linq.DataContext.ChangeConflicts%2A?displayProperty=fullName>  
  
-   <xref:System.Data.Linq.DataContext.SubmitChanges%2A?displayProperty=fullName>  
  
-   <xref:System.Data.Linq.DataContext.Refresh%2A?displayProperty=fullName>  
  
-   <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A?displayProperty=fullName>  
  
-   <xref:System.Data.Linq.Mapping.UpdateCheck?displayProperty=fullName>  
  
-   <xref:System.Data.Linq.RefreshMode?displayProperty=fullName>  
  
## 참고 항목  
 [방법: 변경 내용 충돌 관리](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)