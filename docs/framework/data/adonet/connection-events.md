---
title: "연결 이벤트 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5a29de74-acfc-4134-8616-829dd7ce0710
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# 연결 이벤트
모든 .NET Framework 데이터 공급자에는 데이터 소스에서 정보 메시지를 검색하거나 **Connection** 상태의 변경 여부를 판단하는 데 사용할 수 있는 두 가지 이벤트가 포함된 **Connection** 개체가 있습니다.  다음 표에서는 **Connection** 개체의 이벤트에 대해 설명합니다.  
  
|Event|설명|  
|-----------|--------|  
|**InfoMessage**|정보 메시지가 데이터 소스에서 반환될 때 발생합니다.  정보 메시지는 예외가 throw되지 않는 데이터 소스의 메시지입니다.|  
|**StateChange**|**Connection** 상태가 변경될 때 발생합니다.|  
  
## InfoMessage 이벤트 사용  
 <xref:System.Data.SqlClient.SqlConnection> 개체의 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 이벤트를 사용하여 SQL Server 데이터 소스에서 경고 및 정보 메시지를 검색할 수 있습니다.  데이터 소스에서 반환된 오류의 심각도 수준이 11~16에 해당하면 예외가 throw됩니다.  그러나 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 이벤트를 사용하여 오류와 무관한 데이터 소스의 메시지를 가져올 수 있습니다.  Microsoft SQL Server의 경우 심각도 수준 10 이하의 모든 오류는 정보 메시지로 간주되고 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 이벤트를 사용하여 캡처될 수 있습니다.  자세한 내용은 SQL Server 온라인 설명서의 "Error Message Severity Levels" 항목을 참조하세요.  
  
 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 이벤트는 <xref:System.Data.SqlClient.SqlInfoMessageEventArgs> 개체를 받으며 이 개체의 **Errors** 속성에는 데이터 소스의 메시지 컬렉션이 포함되어 있습니다.  그러면 이 컬렉션의 **Error** 개체에서 오류 소스뿐 아니라 오류 번호와 메시지 텍스트를 쿼리할 수 있습니다.  .NET Framework Data Provider for SQL Server는 메시지가 발생한 데이터베이스, 저장 프로시저 및 줄 번호에 대한 자세한 내용도 포함하고 있습니다.  
  
### 예제  
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
  
## 오류를 InfoMessages로 처리  
 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 이벤트는 일반적으로 서버에서 전송되는 정보 및 경고 메시지에 대해서만 발생합니다.  그러나 실제 오류가 발생하면 서버 작업을 시작한 **ExecuteNonQuery** 또는 **ExecuteReader** 메서드의 실행이 중지되고 예외가 throw됩니다.  
  
 서버에서 발생한 오류와는 상관없이 명령에서 나머지 문을 계속 처리하려면 <xref:System.Data.SqlClient.SqlConnection>의 <xref:System.Data.SqlClient.SqlConnection.FireInfoMessageEventOnUserErrors%2A> 속성을 `true`로 설정합니다.  이렇게 하면 연결에서 예외를 throw하고 처리를 중단하는 대신 오류에 대해 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 이벤트를 발생시킵니다.  그러면 클라이언트 응용 프로그램에서 이 이벤트를 처리하고 오류 조건에 응답할 수 있습니다.  
  
> [!NOTE]
>  심각도 수준이 17 이상인 오류는 서버에서 명령 처리를 중지하도록 하며 예외로 처리되어야 합니다.  이 경우 오류가 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 이벤트에서 처리되는 방법과 상관없이 예외가 throw됩니다.  
  
## StateChange 이벤트 사용  
 **Connection** 상태가 바뀌면 **StateChange** 이벤트가 발생합니다.  **StateChange** 이벤트는 **OriginalState** 및 **CurrentState** 속성을 사용하여 **Connection**의 상태 변화를 확인할 수 있도록 하는 <xref:System.Data.StateChangeEventArgs>를 받습니다.  **OriginalState** 속성은 변경 전의 **Connection** 상태를 나타내는 <xref:System.Data.ConnectionState> 열거형입니다.  **CurrentState**는 변경 후의 **Connection** 상태를 나타내는 <xref:System.Data.ConnectionState> 열거형입니다.  
  
 다음 코드 예제에서는 **Connection** 상태가 변경될 때 **StateChange** 이벤트를 사용하여 콘솔에 메시지를 씁니다.  
  
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
  
## 참고 항목  
 [데이터 소스에 연결](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)