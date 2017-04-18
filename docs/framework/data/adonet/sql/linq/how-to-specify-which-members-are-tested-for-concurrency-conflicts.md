---
title: "방법: 동시성 충돌 테스트 대상 멤버 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d2cda293-1e2f-4878-af0e-5aaf0d092120
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 방법: 동시성 충돌 테스트 대상 멤버 지정
세 가지 열거형 중 하나를 <xref:System.Data.Linq.Mapping.ColumnAttribute> 특성의 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 속성에 적용하여 멤버를 낙관적 동시성 충돌 감지에 대한 업데이트 확인에 포함시키도록 지정합니다.  
  
 디자인 타임에 매핑된 <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 속성은 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 런타임 동시성 기능과 함께 사용됩니다.  자세한 내용은 [낙관적 동시성: 개요](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md)을 참조하세요.  
  
> [!NOTE]
>  `IsVersion=true`로 디자인된 멤버가 없으면 원래 멤버 값이 현재 데이터베이스 상태와 비교됩니다.  자세한 내용은 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>을 참조하세요.  
  
 코드 예는 <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>를 참조하세요.  
  
### 충돌 확인에 항상 이 멤버를 사용하려면  
  
1.  <xref:System.Data.Linq.Mapping.ColumnAttribute> 특성에 <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 속성을 추가합니다.  
  
2.  <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 속성 값을 `Always`로 설정합니다.  
  
### 충돌 확인에 이 멤버를 사용하지 않으려면  
  
1.  <xref:System.Data.Linq.Mapping.ColumnAttribute> 특성에 <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 속성을 추가합니다.  
  
2.  <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 속성 값을 `Never`로 설정합니다.  
  
### 응용 프로그램이 멤버의 값을 변경하는 경우에만 충돌 확인에 이 멤버를 사용하려면  
  
1.  <xref:System.Data.Linq.Mapping.ColumnAttribute> 특성에 <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 속성을 추가합니다.  
  
2.  <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 속성 값을 `WhenChanged`로 설정합니다.  
  
## 예제  
 다음 예제에서는 업데이트를 확인하는 동안 `HomePage` 개체를 테스트하지 말아야 함을 지정합니다.  자세한 내용은 <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>을 참조하세요.  
  
 [!code-csharp[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.mapping.updatecheck/cs/northwind.cs#1)]
 [!code-vb[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.mapping.updatecheck/vb/northwind.vb#1)]  
  
## 참고 항목  
 [방법: 변경 내용 충돌 관리](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)   
 [데이터 변경 및 변경 내용 전송](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)