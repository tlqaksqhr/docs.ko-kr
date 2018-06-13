---
title: AutoIncrement 열 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
ms.openlocfilehash: 5972d9e3d84a236104e85e17d8df1e9ee7f56122
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756035"
---
# <a name="creating-autoincrement-columns"></a>AutoIncrement 열 만들기
열에 고유 값을 지정하려면 테이블에 새 행을 추가할 때 열 값이 자동으로 증가하도록 설정합니다. 자동 증분 만들려면 <xref:System.Data.DataColumn>설정는 <xref:System.Data.DataColumn.AutoIncrement%2A> 열의 속성 **true**합니다. <xref:System.Data.DataColumn> 다음에 정의 된 값으로 시작는 <xref:System.Data.DataColumn.AutoIncrementSeed%2A> 속성, 각 행의 값을 추가 하 고는 **AutoIncrement** 열에 정의 된 값 만큼 증가 <xref:System.Data.DataColumn.AutoIncrementStep%2A> 열의 속성입니다.  
  
 에 대 한 **AutoIncrement** 열을 권장 하는 <xref:System.Data.DataColumn.ReadOnly%2A> 속성은 **DataColumn** 로 설정할 수 **true**합니다.  
  
 다음 예제에서는 200으로 시작하여 3씩 증가하여 추가되는 열을 만드는 방법을 보여 줍니다.  
  
```vb  
Dim workColumn As DataColumn = workTable.Columns.Add( _  
    "CustomerID", typeof(Int32))  
workColumn.AutoIncrement = true  
workColumn.AutoIncrementSeed = 200  
workColumn.AutoIncrementStep = 3  
```  
  
```csharp  
DataColumn workColumn = workTable.Columns.Add(  
    "CustomerID", typeof(Int32));  
workColumn.AutoIncrement = true;  
workColumn.AutoIncrementSeed = 200;  
workColumn.AutoIncrementStep = 3;  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Data.DataColumn>  
 [DataTable 스키마 정의](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
