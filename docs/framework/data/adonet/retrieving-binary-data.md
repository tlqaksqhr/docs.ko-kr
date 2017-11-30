---
title: "이진 데이터 검색"
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
ms.assetid: 56c5a9e3-31f1-482f-bce0-ff1c41a658d0
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: bd524ed605f1fe125480bae0949745f4f045f03a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="retrieving-binary-data"></a>이진 데이터 검색
기본적으로는 **DataReader** 데이터의 전체 행을 사용할 수 있는 즉시 행으로 들어오는 데이터를 로드 합니다. 그러나 BLOB(Binary Large Object)는 단일 행에 포함할 수 없는 기가바이트 데이터를 포함할 수 있으므로 다르게 처리되어야 합니다. **Command.ExecuteReader** 메서드에 수행 하는 오버 로드는 <xref:System.Data.CommandBehavior> 의 기본 동작을 수정 하는 인수는 **DataReader**합니다. 전달할 수 <xref:System.Data.CommandBehavior.SequentialAccess> 에 **ExecuteReader** 의 기본 동작을 수정 하는 메서드는 **DataReader** 행의 데이터를 로드 하는 대신 해당 데이터를 로드 합니다 순차적으로 받으면 되도록 합니다. 이것은 BLOB 또는 기타 대형 데이터 구조를 로드하는 데 적합합니다. 이 동작은 데이터 소스에 따라 다를 수 있습니다. 예를 들어, Microsoft Access에서 BLOB를 반환할 경우에는 BLOB를 받을 때 데이터를 순서대로 로드하는 것이 아니라 전체 BLOB를 메모리에 로드합니다.  
  
 설정할 때는 **DataReader** 사용할 **SequentialAccess**, 반환 되는 필드에 액세스할 수 있는 시퀀스를 확인 해야 합니다. 기본적으로는 **DataReader**, 다음 행을 읽을 때까지 순서에 관계 없이 반환 된 필드에 액세스할 수 있습니다를 사용할 수는 즉시 전체 행을 로드 합니다. 그러나 사용 하는 경우 **SequentialAccess** 가 반환한 필드에 액세스 해야 합니다는 **DataReader** 순서로 합니다. 예를 들어, 쿼리에서 세 열을 반환하고 그 셋째 열이 BLOB이면 셋째 필드의 BLOB 데이터에 액세스하기 전에 첫째와 둘째 필드의 값을 반환해야 합니다. 첫째나 둘째 필드에 액세스하기 전에 셋째 필드에 액세스하면 첫째와 둘째 필드 값을 더 이상 사용할 수 없습니다. ¿¡´ **SequentialAccess** 가 수정는 **DataReader** 데이터 순서 및 데이터의 반환을 사용할 수 없으면 후의 **DataReader** 읽은 했습니다.  
  
 BLOB 필드의 데이터를 액세스할 때 사용 하 여는 **GetBytes** 또는 **GetChars** 의 형식화 된 접근자는 **DataReader**, 배열을 데이터로 채웁니다입니다. 그러나 사용할 수도 있습니다 **GetString** 문자 데이터에 대해 합니다. 하지만 시스템 리소스를 절약하기 위해 전체 BLOB 값을 단일 문자열 변수에 로드하지 않을 수도 있습니다. 대신 반환될 데이터의 특정 버퍼 크기와 반환된 데이터에서 읽은 첫째 바이트 또는 문자의 시작 위치를 지정할 수 있습니다. **GetBytes** 및 **GetChars** 돌아갑니다는 `long` 값으로, 반환 된 문자 또는 바이트 수를 나타냅니다. Null 배열을 전달 하는 경우 **GetBytes** 또는 **GetChars**, long 값 반환 될은 바이트 또는 문자 BLOB의 총 수입니다. 배열의 인덱스를 읽고 있는 데이터의 시작 위치로서 선택적으로 지정할 수 있습니다.  
  
## <a name="example"></a>예제  
 게시자 ID와 로고를 반환 하는 다음 예제는 **pubs** Microsoft SQL server에서 예제 데이터베이스. 게시자 ID(`pub_id`)는 문자 필드이고 로고는 BLOB 이미지입니다. 때문에 **로고** 필드는 비트맵 이므로 예에서는 이진 데이터를 사용 하 여 반환 **GetBytes**합니다. 필드에 순차적으로 액세스해야 하므로 현재 데이터 행에 대해 게시자 ID가 로고에 앞서 액세스됩니다.  
  
```vb  
' Assumes that connection is a valid SqlConnection object.  
Dim command As SqlCommand = New SqlCommand( _  
  "SELECT pub_id, logo FROM pub_info", connection)  
  
' Writes the BLOB to a file (*.bmp).  
Dim stream As FileStream                   
' Streams the binary data to the FileStream object.  
Dim writer As BinaryWriter                 
' The size of the BLOB buffer.  
Dim bufferSize As Integer = 100        
' The BLOB byte() buffer to be filled by GetBytes.  
Dim outByte(bufferSize - 1) As Byte    
' The bytes returned from GetBytes.  
Dim retval As Long                     
' The starting position in the BLOB output.  
Dim startIndex As Long = 0             
  
' The publisher id to use in the file name.  
Dim pubID As String = ""              
  
' Open the connection and read data into the DataReader.  
connection.Open()  
Dim reader As SqlDataReader = command.ExecuteReader(CommandBehavior.SequentialAccess)  
  
Do While reader.Read()  
  ' Get the publisher id, which must occur before getting the logo.  
  pubID = reader.GetString(0)  
  
  ' Create a file to hold the output.  
  stream = New FileStream( _  
    "logo" & pubID & ".bmp", FileMode.OpenOrCreate, FileAccess.Write)  
  writer = New BinaryWriter(stream)  
  
  ' Reset the starting byte for a new BLOB.  
  startIndex = 0  
  
  ' Read bytes into outByte() and retain the number of bytes returned.  
  retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize)  
  
  ' Continue while there are bytes beyond the size of the buffer.  
  Do While retval = bufferSize  
    writer.Write(outByte)  
    writer.Flush()  
  
    ' Reposition start index to end of the last buffer and fill buffer.  
    startIndex += bufferSize  
    retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize)  
  Loop  
  
  ' Write the remaining buffer.  
  writer.Write(outByte, 0 , retval - 1)  
  writer.Flush()  
  
  ' Close the output file.  
  writer.Close()  
  stream.Close()  
Loop  
  
' Close the reader and the connection.  
reader.Close()  
connection.Close()  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection object.  
SqlCommand command = new SqlCommand(  
  "SELECT pub_id, logo FROM pub_info", connection);  
  
// Writes the BLOB to a file (*.bmp).  
FileStream stream;                            
// Streams the BLOB to the FileStream object.  
BinaryWriter writer;                          
  
// Size of the BLOB buffer.  
int bufferSize = 100;                     
// The BLOB byte[] buffer to be filled by GetBytes.  
byte[] outByte = new byte[bufferSize];    
// The bytes returned from GetBytes.  
long retval;                              
// The starting position in the BLOB output.  
long startIndex = 0;                      
  
// The publisher id to use in the file name.  
string pubID = "";                       
  
// Open the connection and read data into the DataReader.  
connection.Open();  
SqlDataReader reader = command.ExecuteReader(CommandBehavior.SequentialAccess);  
  
while (reader.Read())  
{  
  // Get the publisher id, which must occur before getting the logo.  
  pubID = reader.GetString(0);    
  
  // Create a file to hold the output.  
  stream = new FileStream(  
    "logo" + pubID + ".bmp", FileMode.OpenOrCreate, FileAccess.Write);  
  writer = new BinaryWriter(stream);  
  
  // Reset the starting byte for the new BLOB.  
  startIndex = 0;  
  
  // Read bytes into outByte[] and retain the number of bytes returned.  
  retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize);  
  
  // Continue while there are bytes beyond the size of the buffer.  
  while (retval == bufferSize)  
  {  
    writer.Write(outByte);  
    writer.Flush();  
  
    // Reposition start index to end of last buffer and fill buffer.  
    startIndex += bufferSize;  
    retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize);  
  }  
  
  // Write the remaining buffer.  
  writer.Write(outByte, 0, (int)retval);  
  writer.Flush();  
  
  // Close the output file.  
  writer.Close();  
  stream.Close();  
}  
  
// Close the reader and the connection.  
reader.Close();  
connection.Close();  
```  
  
## <a name="see-also"></a>참고 항목  
 [DataReaders 작업](http://msdn.microsoft.com/en-us/126a966a-d08d-4d22-a19f-f432908b2b54)  
 [SQL Server 이진 및 큰 값 데이터](../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
