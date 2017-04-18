---
title: "방법: 기본 키 나타내기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 63c65289-6539-42b2-8493-891c232018fa
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 방법: 기본 키 나타내기
<xref:System.Data.Linq.Mapping.ColumnAttribute> 특성에 대해 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> 속성을 사용하여 데이터베이스 열의 기본 키를 나타내도록 속성 또는 필드를 지정합니다.  
  
 코드 예는 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>를 참조하세요.  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 기본 키로 계산된 열을 지원하지 않습니다.  
  
### 속성 또는 필드를 기본 키로 지정하려면  
  
1.  <xref:System.Data.Linq.Mapping.ColumnAttribute> 특성에 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> 속성을 추가합니다.  
  
2.  값을 `true`로 지정합니다.  
  
## 참고 항목  
 [LINQ to SQL 개체 모델](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)   
 [방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)