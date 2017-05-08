---
title: "방법: 테이블을 클래스로 나타내기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 84dda12b-88a2-4cd2-92b3-8db87b28d14c
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 방법: 테이블을 클래스로 나타내기
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> 특성을 사용하여 클래스를 데이터베이스 테이블과 연결된 엔터티 클래스로 지정합니다.  
  
### 데이터베이스 테이블에 클래스를 매핑하려면  
  
-   <xref:System.Data.Linq.Mapping.TableAttribute> 특성을 클래스 선언에 추가합니다.  
  
## 예제  
 다음 코드에서는 `Customer` 클래스를 `Customers` 데이터베이스 테이블과 연결된 엔터티 클래스로 설정합니다.  
  
 [!code-csharp[DLinqCustomize#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#1)]
 [!code-vb[DLinqCustomize#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#1)]  
  
 이름을 유추할 수 있는 경우에는 <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> 속성을 지정할 필요가 없습니다.  이름을 지정하지 않으면 이름은 속성 또는 필드의 이름과 동일한 것으로 간주됩니다.  
  
## 참고 항목  
 [LINQ to SQL 개체 모델](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)   
 [방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)