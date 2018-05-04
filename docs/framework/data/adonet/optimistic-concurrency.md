---
title: 낙관적 동시성
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e380edac-da67-4276-80a5-b64decae4947
ms.openlocfilehash: b1395c3bd81f7f9d2f12d5b1ea2ec4b784f7aab9
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="optimistic-concurrency"></a>낙관적 동시성
다중 사용자 환경에서는 낙관적 동시성 및 비관적 동시성의 두 가지 모델을 사용하여 데이터베이스의 데이터를 업데이트할 수 있습니다. <xref:System.Data.DataSet> 개체는 데이터를 원격으로 사용하거나 데이터와 상호 작용하는 등의 장기 실행 작업에 대해 낙관적 동시성을 사용하기에 적합하도록 만들어졌습니다.  
  
 비관적 동시성은 데이터 소스의 행을 잠가 다른 사용자가 데이터를 수정하더라도 현재 사용자에게 영향을 미치지 못하도록 합니다. 비관적 모델에서 잠금이 적용되는 작업을 수행하면, 해당 잠금 소유자가 잠금을 해제하기 전까지 다른 사용자는 잠금과 충돌하는 작업을 수행할 수 없습니다. 이 모델은 동시성 충돌이 발생하는 경우 트랜잭션 롤백에 필요한 비용보다 잠금을 통해 데이터를 보호하는 비용이 적게 들도록 데이터 경합이 높은 환경에서 주로 사용됩니다.  
  
 따라서 비관적 동시성 모델에서는 행을 업데이트하는 사용자가 잠금을 설정합니다. 이 사용자가 업데이트 작업을 마치고 잠금을 해제할 때까지 다른 사용자는 해당 행을 변경할 수 없습니다. 이러한 이유로 비관적 동시성은 레코드를 프로그래밍 방식으로 처리하는 경우와 같이 잠금 시간이 짧은 경우에 가장 잘 구현됩니다. 비관적 동시성 모델은 사용자가 데이터와 상호 작용하여 비교적 오랜 시간 레코드를 잠그는 경우에는 사용하지 않는 것이 좋습니다.  
  
> [!NOTE]
>  동일한 작업에서 여러 행을 업데이트해야 하는 경우에는 비관적 잠금을 사용하는 것보다는 트랜잭션을 만드는 것이 훨씬 확장성이 좋습니다.  
  
 비관적 동시성과 달리, 낙관적 동시성의 사용자는 특정 행을 읽을 때 행을 잠그지 않습니다. 이 경우 사용자가 행을 업데이트할 때 행을 읽은 후 다른 사용자가 해당 행을 변경했는지 여부를 응용 프로그램에서 확인해야 합니다. 낙관적 동시성은 주로 데이터 경합이 낮은 환경에서 사용됩니다. 레코드를 잠그려면 서버 리소스가 추가로 소요되기 때문에, 낙관적 동시성을 사용하면 레코드를 잠글 필요가 없어 성능이 향상됩니다. 또한 레코드 잠금을 유지하기 위해서는 데이터베이스 서버와의 연결이 유지되어야 하는데, 낙관적 동시성 모델에서는 그럴 필요가 없기 때문에 짧은 시간에 더 많은 클라이언트가 서버에 연결할 수 있습니다.  
  
 낙관적 동시성 모델에서는 한 사용자가 데이터베이스에서 값을 읽은 후 해당 값의 수정을 시도하기 전에 다른 사용자가 해당 값을 변경하면 위반이 발생한 것으로 간주됩니다. 다음 예제의 첫 번째 설명에는 서버에서 동시성 위반을 해결하는 방법이 가장 잘 나타나 있습니다.  
  
 다음 표에서는 낙관적 동시성의 예제를 보여 줍니다.  
  
 오후 1시에 User1이 다음 값을 갖는 행을 데이터베이스에서 읽습니다.  
  
 **CustID 성, 이름**  
  
 101 Smith Bob  
  
|열 이름|원래 값|현재 값|데이터베이스 값|  
|-----------------|--------------------|-------------------|-----------------------|  
|CustID|101|101|101|  
|LastName|Smith|Smith|Smith|  
|FirstName|Bob|Bob|Bob|  
  
 오후 1시 1분에 User2가 같은 행을 읽습니다.  
  
 오후 1시 03분에 User2 변경 **FirstName** "Robert"을 "Bob"에서 데이터베이스를 업데이트 합니다.  
  
|열 이름|원래 값|현재 값|데이터베이스 값|  
|-----------------|--------------------|-------------------|-----------------------|  
|CustID|101|101|101|  
|LastName|Smith|Smith|Smith|  
|FirstName|Bob|Robert|Bob|  
  
 이 시점에서 업데이트할 때의 데이터베이스 값과 User2가 가진 원래 값이 일치하므로 업데이트는 성공적으로 이루어집니다.  
  
 오후 1시 5분에 User1이 "Bob"의 이름을 "James"로 변경하고 해당 행을 업데이트하려고 합니다.  
  
|열 이름|원래 값|현재 값|데이터베이스 값|  
|-----------------|--------------------|-------------------|-----------------------|  
|CustID|101|101|101|  
|LastName|Smith|Smith|Smith|  
|FirstName|Bob|James|Robert|  
  
 이 시점에서 데이터베이스 값("Robert")과 User1이 예상한 원래 값("Bob")이 일치하지 않기 때문에 낙관적 동시성 위반이 발생하게 되며, 동시성 위반을 통해 업데이트가 실패했음을 간단하게 알 수 있습니다. User2가 제공한 변경 내용을 User1이 제공한 내용으로 덮어쓸지, 아니면 User1의 변경 내용을 취소할지 여부를 결정해야 합니다.  
  
## <a name="testing-for-optimistic-concurrency-violations"></a>낙관적 동시성 위반 테스트  
 여러 가지 기법을 사용하여 낙관적 동시성 위반을 테스트할 수 있는데, 그 중 하나가 테이블에 타임스탬프 열을 포함시키는 것입니다. 일반적으로 데이터베이스에서는 레코드가 마지막으로 업데이트된 날짜와 시간을 식별하기 위해 타임스탬프 기능을 제공합니다. 이 기법을 사용하면 타임스탬프 열이 테이블 정의에 포함됩니다. 타임스탬프는 레코드가 업데이트될 때마다 현재 날짜와 시간을 적용하도록 업데이트됩니다. 낙관적 동시성 위반을 테스트하는 경우, 타임스탬프 열은 테이블의 내용에 대한 모든 쿼리와 함께 반환됩니다. 업데이트를 시도하면 데이터베이스의 타임스탬프 값과 수정된 행에 포함된 원래 타임스탬프 값이 비교됩니다. 두 값이 일치하면 업데이트가 수행되고 업데이트를 적용하기 위해 타임스탬프 열이 현재 시간에 맞게 업데이트됩니다. 반대로, 두 값이 일치하지 않으면 낙관적 동시성 위반이 발생합니다.  
  
 원래 열의 모든 값이 데이터베이스에 있는 해당 값과 계속 일치하는지를 확인하여 낙관적 동시성 위반을 테스트하는 기법도 있습니다. 예를 들어, 다음과 같은 쿼리를 가정해 봅시다.  
  
```  
SELECT Col1, Col2, Col3 FROM Table1  
```  
  
 행을 업데이트할 때 낙관적 동시성 위반을 테스트 하려면 **Table1**, 다음 UPDATE 문을 실행 합니다.  
  
```  
UPDATE Table1 Set Col1 = @NewCol1Value,  
              Set Col2 = @NewCol2Value,  
              Set Col3 = @NewCol3Value  
WHERE Col1 = @OldCol1Value AND  
      Col2 = @OldCol2Value AND  
      Col3 = @OldCol3Value  
```  
  
 원래 값과 데이터베이스의 값이 일치하면 업데이트가 수행됩니다. 특정 값을 수정한 경우 WHERE 절과 일치하는 항목을 찾을 수 없으므로 업데이트를 수행하더라도 해당 행은 수정되지 않습니다.  
  
 항상 쿼리에 고유한 기본 키 값을 반환하는 것이 좋습니다. 그렇지 않으면 이전 UPDATE 문이 의도했던 것과는 달리 둘 이상의 행을 업데이트할 수도 있습니다.  
  
 데이터 소스의 열에 null이 허용되는 경우에는 일치하는 null 참조를 로컬 테이블 및 데이터 소스에서도 확인하도록 WHERE 절을 확장해야 할 수 있습니다. 예를 들어, 다음 UPDATE 문은 로컬 행의 null 참조가 데이터 소스의 null 참조와 일치하는지 또는 로컬 행의 값이 데이터 소스의 값과 계속 일치하는지 여부를 확인합니다.  
  
```  
UPDATE Table1 Set Col1 = @NewVal1  
  WHERE (@OldVal1 IS NULL AND Col1 IS NULL) OR Col1 = @OldVal1  
```  
  
 낙관적 동시성 모델을 사용할 때는 덜 제한적인 조건을 적용할 수도 있습니다. 예를 들어, WHERE 절에 기본 키 열만 사용하면 마지막 쿼리 이후에 다른 열이 업데이트되었는지 여부와 상관없이 데이터를 덮어씁니다. 또한 특정 열에 대해서만 WHERE 절을 사용할 수도 있는데, 이 경우 마지막으로 쿼리된 이후에 특정 필드가 업데이트되지 않았으면 데이터를 덮어씁니다.  
  
### <a name="the-dataadapterrowupdated-event"></a>DataAdapter.RowUpdated 이벤트  
 **RowUpdated** 의 이벤트는 <xref:System.Data.Common.DataAdapter> 개체를 낙관적 동시성 위반의 응용 프로그램에 대 한 알림을 제공할를 앞에서 설명한 기법과 함께 함께에서 사용할 수 있습니다. **RowUpdated** 를 업데이트 하려는 각 시도 후에 발생 한 **Modified** 에서 행는 **데이터 집합**합니다. 이로써 예외 발생 시의 처리와 사용자 지정 오류 정보 및 다시 시도 논리 등의 추가를 포함하여 특별한 처리 코드를 추가할 수 있습니다. <xref:System.Data.Common.RowUpdatedEventArgs> 반환 개체는 **RecordsAffected** 테이블의 수정된 된 행에 대 한 특정 업데이트 명령으로 영향을 받는 행 수를 포함 하는 속성입니다. 낙관적 동시성을 테스트 하도록 업데이트 명령을 설정 하 여는 **RecordsAffected** 속성은, 결과적으로, 반환 값이 0 낙관적 동시성 위반이 발생 했을 때 업데이트 된 레코드가 없으므로 합니다. 또한 이 경우 예외가 throw됩니다. **RowUpdated** 이벤트를 사용 하면이 항목을 처리 하 고 적절 한 설정 하 여 예외를 방지할 수 있습니다 **RowUpdatedEventArgs.Status** 같은 값  **UpdateStatus.SkipCurrentRow**합니다. 에 대 한 자세한 내용은 **RowUpdated** 이벤트 참조 [DataAdapter 이벤트 처리](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)합니다.  
  
 설정할 수 있습니다 **DataAdapter.ContinueUpdateOnError** 를 **true**를 호출 하기 전에 **업데이트**는 에저장된오류정보에응답할**RowError** 경우 속성의 특정 행의 **업데이트** 완료 합니다. 자세한 내용은 참조 [행 오류 정보](../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-error-information.md)합니다.  
  
## <a name="optimistic-concurrency-example"></a>낙관적 동시성 예제  
 다음은 설정 하는 간단한 예제는 **UpdateCommand** 의 **DataAdapter** 낙관적 동시성을 테스트 하려면 다음 사용 하 여는 **RowUpdated** 를 테스트 하는 이벤트 낙관적 동시성 위반 수입니다. 낙관적 동시성 위반이 발생 하는 경우 응용 프로그램 설정의 **RowError** 낙관적 동시성 위반을 반영 하도록 업데이트에 대 한 발급 하는 행의 합니다.  
  
 UPDATE 명령의 WHERE 절에 전달 된 매개 변수 값에 매핑되는 참고는 **원래** 은 해당 열의 값입니다.  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT CustomerID, CompanyName FROM Customers ORDER BY CustomerID", _  
  connection)  
  
' The Update command checks for optimistic concurrency violations  
' in the WHERE clause.  
adapter.UpdateCommand = New SqlCommand("UPDATE Customers " &  
  "(CustomerID, CompanyName) VALUES(@CustomerID, @CompanyName) " & _  
  "WHERE CustomerID = @oldCustomerID AND CompanyName = " &  
  "@oldCompanyName", connection)  
adapter.UpdateCommand.Parameters.Add( _  
  "@CustomerID", SqlDbType.NChar, 5, "CustomerID")  
adapter.UpdateCommand.Parameters.Add( _  
  "@CompanyName", SqlDbType.NVarChar, 30, "CompanyName")  
  
' Pass the original values to the WHERE clause parameters.  
Dim parameter As SqlParameter = dataSet.UpdateCommand.Parameters.Add( _  
  "@oldCustomerID", SqlDbType.NChar, 5, "CustomerID")  
parameter.SourceVersion = DataRowVersion.Original  
parameter = adapter.UpdateCommand.Parameters.Add( _  
  "@oldCompanyName", SqlDbType.NVarChar, 30, "CompanyName")  
parameter.SourceVersion = DataRowVersion.Original  
  
' Add the RowUpdated event handler.  
AddHandler adapter.RowUpdated, New SqlRowUpdatedEventHandler( _  
  AddressOf OnRowUpdated)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, "Customers")  
  
' Modify the DataSet contents.  
adapter.Update(dataSet, "Customers")  
  
Dim dataRow As DataRow  
  
For Each dataRow In dataSet.Tables("Customers").Rows  
    If dataRow.HasErrors Then   
       Console.WriteLine(dataRow (0) & vbCrLf & dataRow.RowError)  
    End If  
Next  
  
Private Shared Sub OnRowUpdated( _  
  sender As object, args As SqlRowUpdatedEventArgs)  
   If args.RecordsAffected = 0  
      args.Row.RowError = "Optimistic Concurrency Violation!"  
      args.Status = UpdateStatus.SkipCurrentRow  
   End If  
End Sub  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
SqlDataAdapter adapter = new SqlDataAdapter(  
  "SELECT CustomerID, CompanyName FROM Customers ORDER BY CustomerID",  
  connection);  
  
// The Update command checks for optimistic concurrency violations  
// in the WHERE clause.  
adapter.UpdateCommand = new SqlCommand("UPDATE Customers Set CustomerID = @CustomerID, CompanyName = @CompanyName " +  
   "WHERE CustomerID = @oldCustomerID AND CompanyName = @oldCompanyName, connection);  
adapter.UpdateCommand.Parameters.Add(  
  "@CustomerID", SqlDbType.NChar, 5, "CustomerID");  
adapter.UpdateCommand.Parameters.Add(  
  "@CompanyName", SqlDbType.NVarChar, 30, "CompanyName");  
  
// Pass the original values to the WHERE clause parameters.  
SqlParameter parameter = adapter.UpdateCommand.Parameters.Add(  
  "@oldCustomerID", SqlDbType.NChar, 5, "CustomerID");  
parameter.SourceVersion = DataRowVersion.Original;  
parameter = adapter.UpdateCommand.Parameters.Add(  
  "@oldCompanyName", SqlDbType.NVarChar, 30, "CompanyName");  
parameter.SourceVersion = DataRowVersion.Original;  
  
// Add the RowUpdated event handler.  
adapter.RowUpdated += new SqlRowUpdatedEventHandler(OnRowUpdated);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, "Customers");  
  
// Modify the DataSet contents.  
  
adapter.Update(dataSet, "Customers");  
  
foreach (DataRow dataRow in dataSet.Tables["Customers"].Rows)  
{  
    if (dataRow.HasErrors)  
       Console.WriteLine(dataRow [0] + "\n" + dataRow.RowError);  
}  
  
protected static void OnRowUpdated(object sender, SqlRowUpdatedEventArgs args)  
{  
  if (args.RecordsAffected == 0)   
  {  
    args.Row.RowError = "Optimistic Concurrency Violation Encountered";  
    args.Status = UpdateStatus.SkipCurrentRow;  
  }  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [ADO.NET에서 데이터 검색 및 수정](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [DataAdapter로 데이터 원본 업데이트](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 [행 오류 정보](../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-error-information.md)  
 [트랜잭션 및 동시성](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
