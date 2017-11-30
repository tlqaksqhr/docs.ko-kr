---
title: "DataRelation 추가"
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
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 31494ee9ac6fc8efc9a041f5d56dbba4a4bddad1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="adding-datarelations"></a>DataRelation 추가
여러 <xref:System.Data.DataSet> 개체가 포함된 <xref:System.Data.DataTable>에서는 <xref:System.Data.DataRelation> 개체를 사용하여 하나의 테이블을 다른 테이블에 연관시키거나, 테이블 사이를 탐색하거나, 연관된 테이블의 자식 또는 부모 행을 반환할 수 있습니다.  
  
 만드는 데 필요한 인수로 **DataRelation** 됩니다에 대 한 이름을 **DataRelation** 만들고 하나 이상의 배열 <xref:System.Data.DataColumn> 부모 및 자식으로 사용 되는 열에 대 한 참조 관계의 열입니다. 만든 후는 **DataRelation**, 테이블 간의 탐색 하 고 값을 검색 하려면 사용할 수 있습니다.  
  
 추가 **DataRelation** 에 <xref:System.Data.DataSet> 기본적으로 추가 <xref:System.Data.UniqueConstraint> 부모 테이블에 및 <xref:System.Data.ForeignKeyConstraint> 자식 테이블에 있습니다. 이러한 기본 제약 조건에 대 한 자세한 내용은 참조 [DataTable 제약 조건](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md)합니다.  
  
 다음 코드 예제에서는 한 **DataRelation** 두 개를 사용 하 여 <xref:System.Data.DataTable> 개체에 <xref:System.Data.DataSet>합니다. 각 <xref:System.Data.DataTable> 라는 열이 포함 되어 **CustID**, 둘 사이의 링크로 제공 되 <xref:System.Data.DataTable> 개체입니다. 예제에서는 추가 하는 단일 **DataRelation** 에 **관계** 의 컬렉션은 <xref:System.Data.DataSet>합니다. 예제에서 첫 번째 인수의 이름을 지정 하는 **DataRelation** 만들려는 합니다. 부모를 설정 하는 두 번째 인수 **DataColumn** 자식을 설정 하는 세 번째 인수 및 **DataColumn**합니다.  
  
```vb  
customerOrders.Relations.Add("CustOrders", _  
  customerOrders.Tables("Customers").Columns("CustID"), _  
  customerOrders.Tables("Orders").Columns("CustID"))  
```  
  
```csharp  
customerOrders.Relations.Add("CustOrders",  
  customerOrders.Tables["Customers"].Columns["CustID"],  
  customerOrders.Tables["Orders"].Columns["CustID"]);  
```  
  
 A **DataRelation** 역시는 **Nested** 속성을로 설정 된 경우 **true**, 부모 테이블의 관련된 행 내에 중첩 될 자식 테이블의 행을 하면 사용 하 여 XML 요소로 작성할 때 <xref:System.Data.DataSet.WriteXml%2A> 합니다. 자세한 내용은 [데이터 집합에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [DataSet, DataTable 및 DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
