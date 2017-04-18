---
title: "방법: 데이터베이스 데이터 형식 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2228fdad-7e6a-4b1b-b4d1-79d0198b7c28
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 방법: 데이터베이스 데이터 형식 지정
<xref:System.Data.Linq.Mapping.ColumnAttribute> 특성에서 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> 속성을 사용하여 T\-SQL 테이블 선언에서 열을 정의하는 정확한 텍스트를 지정할 수 있습니다.  
  
 <xref:System.Data.Linq.DataContext.CreateDatabase%2A>를 사용하여 데이터베이스 인스턴스를 만들려고 계획한 경우에만 <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> 속성을 지정해야 합니다.  
  
 코드 예는 <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>를 참조하세요.  
  
### T\-SQL 테이블에서 데이터 형식을 정의하기 위한 텍스트를 지정하려면  
  
1.  <xref:System.Data.Linq.Mapping.ColumnAttribute> 특성에 <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> 속성을 추가합니다.  
  
2.  <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> 속성 값을 T\-SQL에서 사용되는 정확한 텍스트로 설정합니다.  
  
## 참고 항목  
 [LINQ to SQL 개체 모델](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)   
 [방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)