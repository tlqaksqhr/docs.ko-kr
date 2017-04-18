---
title: "방법: 전용 저장소 필드 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5a40e816-cc6e-43a0-b32a-9caaa0ab6912
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 방법: 전용 저장소 필드 지정
<xref:System.Data.Linq.Mapping.DataAttribute> 특성에 대해 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> 속성을 사용하여 기본 저장소 필드의 이름을 지정합니다.  
  
 코드 예는 <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>를 참조하세요.  
  
### 기본 저장소 필드의 이름을 지정하려면  
  
1.  <xref:System.Data.Linq.Mapping.ColumnAttribute> 특성에 <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> 속성을 추가합니다.  
  
2.  필드의 이름을 <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> 속성의 값으로 지정합니다.  
  
## 참고 항목  
 [LINQ to SQL 개체 모델](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)   
 [방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)