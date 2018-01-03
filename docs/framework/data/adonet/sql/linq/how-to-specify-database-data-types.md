---
title: "방법: 데이터베이스 데이터 형식 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2228fdad-7e6a-4b1b-b4d1-79d0198b7c28
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 60f07a629c981eb0ad72f7c3e2d8537d5ca77515
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-database-data-types"></a>방법: 데이터베이스 데이터 형식 지정
사용 하 여는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> 속성에는 <xref:System.Data.Linq.Mapping.ColumnAttribute> T-SQL 테이블 선언에는 열을 정의 하는 정확한 텍스트를 지정 하는 특성입니다.  
  
 <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>를 사용하여 데이터베이스 인스턴스를 만들려고 계획한 경우에만 <xref:System.Data.Linq.DataContext.CreateDatabase%2A> 속성을 지정해야 합니다.  
  
 코드 예는 <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>를 참조하세요.  
  
### <a name="to-specify-text-to-define-a-data-type-in-a-t-sql-table"></a>T-SQL 테이블에서 데이터 형식을 정의하기 위한 텍스트를 지정하려면  
  
1.  <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> 특성에 <xref:System.Data.Linq.Mapping.ColumnAttribute> 속성을 추가합니다.  
  
2.  <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> 속성 값을 T-SQL에서 사용되는 정확한 텍스트로 설정합니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to SQL 개체 모델](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
