---
title: "연결 이벤트"
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
ms.assetid: 5a29de74-acfc-4134-8616-829dd7ce0710
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: e0eb38eb764faa51524565e57826db17311fc5dd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="connection-events"></a>연결 이벤트
모든.NET Framework 데이터 공급자가 **연결** 데이터 원본에서 정보 메시지를 검색 하거나 여부를 확인 하려면 사용할 수 있는 두 개의 이벤트를 사용 하 여 개체의 상태는 **연결** 했습니다 읽기 전용 이므로 다음 표에서 설명의 이벤트는 **연결** 개체입니다.  
  
|이벤트(event)|설명|  
|-----------|-----------------|  
|**InfoMessage**|정보 메시지가 데이터 소스에서 반환될 때 발생합니다. 정보 메시지는 예외가 throw되지 않는 데이터 소스의 메시지입니다.|  
|**StateChange**|발생 경우의 상태는 **연결** 변경 합니다.|  
  
## <a name="working-with-the-infomessage-event"></a>InfoMessage 이벤트 사용  
 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 개체의 <xref:System.Data.SqlClient.SqlConnection> 이벤트를 사용하여 SQL Server 데이터 소스에서 경고 및 정보 메시지를 검색할 수 있습니다. 데이터 소스에서 반환된 오류의 심각도 수준이 11~16에 해당하면 예외가 throw됩니다. 그러나 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 이벤트를 사용하여 오류와 무관한 데이터 소스의 메시지를 가져올 수 있습니다. Microsoft SQL Server의 경우 심각도 수준 10 이하의 모든 오류는 정보 메시지로 간주되고 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 이벤트를 사용하여 캡처될 수 있습니다. 자세한 내용은 SQL Server 온라인 설명서의 "Error Message Severity Levels" 항목을 참조하세요.  
  
 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 이벤트 수신는 <xref:System.Data.SqlClient.SqlInfoMessageEventArgs> 개체 포함 해당 **오류** 속성, 데이터 원본에서 메시지의 컬렉션입니다. 쿼리할 수 있습니다는 **오류** 오류의 원인을 뿐만 아니라 오류 번호와 메시지 텍스트에 대 한이 컬렉션의 개체입니다. .NET Framework Data Provider for SQL Server는 메시지가 발생한 데이터베이스, 저장 프로시저 및 줄 번호에 대한 자세한 내용도 포함하고 있습니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 이벤트에 대한 이벤트 처리기를 추가하는 방법을 보여 줍니다.  
  
```vb  
' Assumes that connection represents a SqlConnection object.  
  AddHandler connection.InfoMessage, _  
    New SqlInfoMessageEventHandler(AddressOf OnInfoMessage)  
  
Private Shared Sub OnInfoMessage(sender As Object, _  
  args As SqlInfoMessageEventArgs)  
  Dim err As SqlError  
  For Each err In args.Errors  
    Console.WriteLine("The {0} has received a severity {1}, _  
       state {2} error number {3}\n" & _  
      "on line {4} of procedure {5} on server {6}:\n{7}", _  
      err.Source, err.Class, err.State, err.Number, err.LineNumber, _  
    err.Procedure, err.Server, err.Message)  
  Next  
End Sub  
```  
  
```csharp  
// Assumes that connection represents a SqlConnection object.  
  connection.InfoMessage +=   
    new SqlInfoMessageEventHandler(OnInfoMessage);  
  
protected static void OnInfoMessage(  
  object sender, SqlInfoMessageEventArgs args)  
{  
  foreach (SqlError err in args.Errors)  
  {  
    Console.WriteLine(  
  "The {0} has received a severity {1}, state {2} error number {3}\n" +  
  "on line {4} of procedure {5} on server {6}:\n{7}",  
   err.Source, err.Class, err.State, err.Number, err.LineNumber,   
   err.Procedure, err.Server, err.Message);  
  }  
}  
```  
  
## <a name="handling-errors-as-infomessages"></a>오류를 InfoMessages로 처리  
 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 이벤트는 일반적으로 서버에서 전송되는 정보 및 경고 메시지에 대해서만 발생합니다. 그러나 실제 오류가 발생할 때, 실행 된 **ExecuteNonQuery** 또는 **ExecuteReader** 을 서버 작업을 시작한 메서드에 중지 되 고 예외가 throw 됩니다.  
  
 서버에서 발생한 오류와는 상관없이 명령에서 나머지 문을 계속 처리하려면 <xref:System.Data.SqlClient.SqlConnection.FireInfoMessageEventOnUserErrors%2A>의 <xref:System.Data.SqlClient.SqlConnection> 속성을 `true`로 설정합니다. 이렇게 하면 연결에서 예외를 throw하고 처리를 중단하는 대신 오류에 대해 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 이벤트를 발생시킵니다. 그러면 클라이언트 응용 프로그램에서 이 이벤트를 처리하고 오류 조건에 응답할 수 있습니다.  
  
> [!NOTE]
>  심각도 수준이 17 이상인 오류는 서버에서 명령 처리를 중지하도록 하며 예외로 처리되어야 합니다. 이 경우 오류가 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 이벤트에서 처리되는 방법과 상관없이 예외가 throw됩니다.  
  
## <a name="working-with-the-statechange-event"></a>StateChange 이벤트 사용  
 **StateChange** 이벤트가 발생할 때의 상태는 **연결** 변경 합니다. **StateChange** 이벤트 수신 <xref:System.Data.StateChangeEventArgs> 의 상태에 변경 내용을 확인할 수 있도록 하는 **연결** 를 사용 하 여는 **OriginalState** 및 **CurrentState** 속성입니다. **OriginalState** 속성은 한 <xref:System.Data.ConnectionState> 열거형의 상태를 나타내는 **연결** 변경 하기 전에. **CurrentState** 는 <xref:System.Data.ConnectionState> 의 상태를 나타내는 열거는 **연결** 변경 후 합니다.  
  
 다음 코드 예제에서는 **StateChange** 콘솔에 메시지를 작성 하는 이벤트 때의 상태는 **연결** 변경 합니다.  
  
```vb  
' Assumes connection represents a SqlConnection object.  
  AddHandler connection.StateChange, _  
    New StateChangeEventHandler(AddressOf OnStateChange)  
  
Protected Shared Sub OnStateChange( _  
  sender As Object, args As StateChangeEventArgs)  
  
  Console.WriteLine( _  
  "The current Connection state has changed from {0} to {1}.", _  
  args.OriginalState, args.CurrentState)  
End Sub  
```  
  
```csharp  
// Assumes connection represents a SqlConnection object.  
  connection.StateChange  += new StateChangeEventHandler(OnStateChange);  
  
protected static void OnStateChange(object sender,   
  StateChangeEventArgs args)  
{  
  Console.WriteLine(  
    "The current Connection state has changed from {0} to {1}.",  
      args.OriginalState, args.CurrentState);  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [데이터 소스에 연결](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
