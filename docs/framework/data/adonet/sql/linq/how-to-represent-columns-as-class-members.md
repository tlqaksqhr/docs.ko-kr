---
title: "방법: 클래스 멤버로 열 표현"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 7ab28021-4d15-4d9c-bf2e-6ccc0daa7d1a
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 65d8e44d540f902012d6df6094e85cc70a5d9b1c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-represent-columns-as-class-members"></a>방법: 클래스 멤버로 열 표현
사용 하 여는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute> 필드 또는 속성을 데이터베이스 열과 연결할 특성입니다.  
  
### <a name="to-map-a-field-or-property-to-a-database-column"></a>필드 또는 속성을 데이터베이스 열에 매핑하려면  
  
-   <xref:System.Data.Linq.Mapping.ColumnAttribute> 특성을 속성 또는 필드 선언에 추가합니다.  
  
## <a name="example"></a>예  
 다음 코드에서는 `CustomerID` 클래스의 `Customer` 필드를 `CustomerID` 데이터베이스 테이블의 `Customers` 열에 매핑합니다.  
  
 [!code-csharp[DLinqCustomize#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#2)]
 [!code-vb[DLinqCustomize#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#2)]  
  
 이름을 유추할 수 있는 경우에는 <xref:System.Data.Linq.Mapping.DataAttribute.Name%2A> 속성을 지정할 필요가 없습니다. 이름을 지정하지 않으면 이름은 속성 또는 필드의 이름과 동일한 것으로 간주됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to SQL 개체 모델](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
