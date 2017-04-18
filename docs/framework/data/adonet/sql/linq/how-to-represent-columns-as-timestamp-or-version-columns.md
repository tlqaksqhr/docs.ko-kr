---
title: "방법: 열을 타임스탬프 또는 버전 열로 나타내기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5afd5ce8-1d20-4bc3-a34f-49d95449f493
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 방법: 열을 타임스탬프 또는 버전 열로 나타내기
<xref:System.Data.Linq.Mapping.ColumnAttribute> 특성의 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> 속성을 사용하여 데이터베이스 타임스탬프 또는 버전 번호를 저장하는 데이터베이스 열을 나타내도록 필드 또는 속성을 지정합니다.  
  
 코드 예는 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>를 참조하세요.  
  
### 타임스탬프 또는 버전 열을 나타내도록 필드 또는 속성을 지정하려면  
  
1.  <xref:System.Data.Linq.Mapping.ColumnAttribute> 특성에 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> 속성을 추가합니다.  
  
2.  <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> 속성 값을 `true`로 설정합니다.  
  
## 참고 항목  
 [LINQ to SQL 개체 모델](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)   
 [방법: 동시성 충돌 테스트 대상 멤버 지정](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)   
 [방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)