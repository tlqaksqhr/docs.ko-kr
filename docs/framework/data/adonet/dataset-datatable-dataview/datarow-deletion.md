---
title: "DataRow 삭제"
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
ms.assetid: c34f531d-4b9b-4071-b2d7-342c402aa586
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f9eb89d711cbf66f3b6816e597c14359be1f3639
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="datarow-deletion"></a>DataRow 삭제
두 가지가 삭제 하는 데 사용할 수는 <xref:System.Data.DataRow> 에서 개체는 <xref:System.Data.DataTable> 개체:는 **제거** 의 메서드는 <xref:System.Data.DataRowCollection> 개체 및 <xref:System.Data.DataRow.Delete%2A> 의 메서드는 **DataRow**개체입니다. 반면는 <xref:System.Data.DataRowCollection.Remove%2A> 메서드 삭제는 **DataRow** 에서 **DataRowCollection**, <xref:System.Data.DataRow.Delete%2A> 메서드는 삭제할 행을 표시만 합니다. 응용 프로그램 호출 때 실제 제거는 **AcceptChanges** 메서드. <xref:System.Data.DataRow.Delete%2A>를 사용하면 행을 실제로 삭제하기 전에 삭제 표시된 행을 프로그래밍 방식으로 확인할 수 있습니다. 삭제 표시된 행의 <xref:System.Data.DataRow.RowState%2A> 속성은 <xref:System.Data.DataRow.Delete%2A>로 설정됩니다.  
  
 <xref:System.Data.DataRow.Delete%2A> 개체를 반복하는 동안에는 foreach 루프에서 <xref:System.Data.DataRowCollection.Remove%2A> 또는 <xref:System.Data.DataRowCollection>가 호출되지 않아야 합니다. <xref:System.Data.DataRow.Delete%2A> 또는 <xref:System.Data.DataRowCollection.Remove%2A>는 컬렉션의 상태를 수정하지 않습니다.  
  
 사용 하는 경우는 <xref:System.Data.DataSet> 또는 **DataTable** 함께에서 **DataAdapter** 및 사용 하 여 관계형 데이터 원본에서 **삭제** 의 메서드는  **DataRow** 행을 제거 합니다. **삭제** 메서드는 해당 행을 표시 **Deleted** 에 **DataSet** 또는 **DataTable** 되지만 제거 되지는 않습니다. 대신,는 **DataAdapter** 로 표시 된 행을 발견 하면 **Deleted**, 실행의 **DeleteCommand** 데이터 소스에서 행을 삭제 하는 메서드. 행 수 다음 영구적으로 제거를 사용 하 여 **AcceptChanges** 메서드. 사용 하는 경우 **제거** 행을 삭제 하려면 해당 행은 테이블에서 완전히 제거 되지만 **DataAdapter** 데이터 소스에서 행을 삭제 하지 것입니다.  
  
 **제거** 의 메서드는 **DataRowCollection** 사용는 **DataRow** 인수로 서 다음 예제와 같이 컬렉션에서 제거 합니다.  
  
```vb  
workTable.Rows.Remove(workRow)  
```  
  
```csharp  
workTable.Rows.Remove(workRow);  
```  
  
 반대로 다음 예제에서는 호출 하는 방법을 **삭제** 에서 메서드는 **DataRow** 변경 하려면 해당 **RowState** 를 **Deleted** .  
  
```vb  
workRow.Delete  
```  
  
```csharp  
workRow.Delete();  
```  
  
 행 삭제로 표시 되 고 호출 하는 경우는 **AcceptChanges** 의 메서드는 **DataTable** 개체에서 행이 제거 되는 **DataTable**합니다. 반대로, 호출 하는 경우 **RejectChanges**, **RowState** 행의 되돌아갑니다로 표시 되기 전에 **Deleted**합니다.  
  
> [!NOTE]
>  경우는 **RowState** 의 **DataRow** 은 **Added**, 테이블에만 추가 되 것을 의미 하 고으로 표시 되어 있어 **Deleted**는 테이블에서 제거 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataRowCollection>  
 <xref:System.Data.DataTable>  
 [DataTable에서 데이터 조작](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
