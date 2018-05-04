---
title: 데이터 집합에 기존 제약 조건 추가
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 307d2809-208b-4cf8-b6a9-5d16f15fc16c
ms.openlocfilehash: c3c28392a9e4bee0e2f9e0dcf553e13b67c378dd
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="adding-existing-constraints-to-a-dataset"></a>데이터 집합에 기존 제약 조건 추가
**채우기** 의 메서드는 **DataAdapter** 채웁니다는 <xref:System.Data.DataSet> 는 테이블 열과 데이터 원본의 행만 하지만 제약 조건을 일반적으로 설정 하 여 데이터 원본에서 **채우기** 메서드는이 스키마 정보를 추가 하지 않습니다는 **DataSet** 기본적으로 합니다. 채우는 한 **데이터 집합** 데이터 소스의 기존 기본 키 제약 조건 정보로 호출할 수 있습니다는 **FillSchema** 의 메서드는 **DataAdapter**, 설정 또는 **MissingSchemaAction** 의 속성은 **DataAdapter** 를 **AddWithKey** 호출 하기 전에 **채우기**합니다. 이렇게 하면 해당 기본 키 제약 조건에는 **DataSet** 데이터 소스에서 반영 합니다. 외래 키 제약 조건 정보에 포함 되며에 표시 된 대로 명시적으로 만들어야 합니다 [DataTable 제약 조건](../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md)합니다.  
  
 스키마 정보를 추가 **DataSet** primary key 제약 조건에 포함 된 사용 하면 데이터로 채우기 전에 <xref:System.Data.DataTable> 개체에 **데이터 집합**합니다. 결과적으로 추가 하는 경우 입력에 대 한 호출의 **데이터 집합** 계산 되는 기본 키 열 정보 각에서 현재 행이 포함 된 데이터 원본에서 새 행과 일치 하는 데 사용 됩니다 **DataTable**, 및의 현재 데이터 데이터 원본의 데이터로 테이블을 덮어씁니다. 스키마 정보가 없으면 데이터 원본에서 새 행에 추가 되는 **데이터 집합**로 중복 행.  
  
> [!NOTE]
>  데이터 원본의 열에 자동 증분으로 식별 되는 **FillSchema** 메서드, 또는 **채우기** 메서드를 한 **MissingSchemaAction** 의  **AddWithKey**, 만듭니다는 **DataColumn** 와 **AutoIncrement** 속성이로 설정 `true`합니다. 그러나 설정 해야 합니다는 **AutoIncrementStep** 및 **AutoIncrementSeed** 값입니다. 자동 증가 열에 대 한 자세한 내용은 참조 [AutoIncrement 열 만들기](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md)합니다.  
  
 사용 하 여 **FillSchema** 또는 설정은 **MissingSchemaAction** 를 **AddWithKey** 기본 키 열 정보를 확인 하려면 데이터 원본에 대 한 추가 처리가 필요 합니다. 이러한 추가 처리로 인해 성능이 낮아질 수 있습니다. 디자인 타임에 기본 키 정보를 알고 있으면 기본 키 열을 명시적으로 지정하여 최상의 성능을 얻을 수 있습니다. 테이블에 대 한 기본 키 정보를 명시적으로 설정 하는 방법에 대 한 정보를 참조 하십시오. [기본 키 정의](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md)합니다.  
  
 다음 코드 예제에서는 스키마 정보를 추가 하는 방법을 보여 줍니다.는 **DataSet** 를 사용 하 여 **FillSchema**합니다.  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers")  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers");  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
 다음 코드 예제에서는 스키마 정보를 추가 하는 방법을 보여 줍니다.는 **데이터 집합** 를 사용 하 여는 **MissingSchemaAction.AddWithKey** 의 속성은 **채우기** 메서드.  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
## <a name="handling-multiple-result-sets"></a>여러 개의 결과 집합 처리  
 경우는 **DataAdapter** 에서 반환 된 여러 결과 집합에서 발견 된 **SelectCommand**에서 여러 테이블을 만드는 **데이터 집합**합니다. 테이블의 0부터 시작 증분 기본 이름인 하 게 할 **테이블** *N*부터 **테이블** "table0"입니다. 테이블 이름에 대 한 인수로 전달 됩니다는 **FillSchema** 메서드, 테이블 이름이 지정 됩니다는 0부터 시작 증분의 **TableName** *N* 부터**TableName** "tablename0"입니다.  
  
> [!NOTE]
>  경우는 **FillSchema** 의 메서드는 **OleDbDataAdapter** 개체를 여러 개의 결과 집합을 반환 하는 명령에 대 한 호출을 첫 번째 결과 집합의 스키마 정보만 반환 됩니다. 여러 결과 대 한 스키마 정보를 반환할가 사용 하 여를 집합 때는 **OleDbDataAdapter**를 지정 하는 것이 좋습니다.는 **MissingSchemaAction** 의 **AddWithKey** 호출할 때 스키마 정보를 가져오려면는 **채우기** 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [DataAdapter 및 DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [DataSet, DataTable 및 DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET에서 데이터 검색 및 수정](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
