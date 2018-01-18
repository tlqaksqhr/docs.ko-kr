---
title: "파일에서 이미지 삽입"
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
ms.assetid: 35900aa2-5615-4174-8212-ba184c6b82fb
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: a913e660292713d4c728da75e91d812a285edc51
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="inserting-an-image-from-a-file"></a><span data-ttu-id="15d0e-102">파일에서 이미지 삽입</span><span class="sxs-lookup"><span data-stu-id="15d0e-102">Inserting an Image from a File</span></span>
<span data-ttu-id="15d0e-103">데이터 소스의 필드 형식에 따라 BLOB(Binary Large Object)를 이진 또는 문자 데이터로 데이터베이스에 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15d0e-103">You can write a binary large object (BLOB) to a database as either binary or character data, depending on the type of field at your data source.</span></span> <span data-ttu-id="15d0e-104">BLOB는 주로 문서와 그림이 포함된 `text`, `ntext` 및 `image` 데이터 형식을 나타내는 일반적인 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="15d0e-104">BLOB is a generic term that refers to the `text`, `ntext`, and `image` data types, which typically contain documents and pictures.</span></span>  
  
 <span data-ttu-id="15d0e-105">BLOB 값을 해당 데이터베이스를 작성 하려면 적절 한 INSERT 또는 UPDATE 문을 실행 하 고 입력된 매개 변수로 BLOB 값을 전달 (참조 [구성 매개 변수 및 매개 변수 데이터 형식](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)).</span><span class="sxs-lookup"><span data-stu-id="15d0e-105">To write a BLOB value to your database, issue the appropriate INSERT or UPDATE statement and pass the BLOB value as an input parameter (see [Configuring Parameters and Parameter Data Types](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)).</span></span> <span data-ttu-id="15d0e-106">BLOB를 SQL Server `text` 필드와 같이 텍스트로 저장하면 BLOB를 문자열 매개 변수로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15d0e-106">If your BLOB is stored as text, such as a SQL Server `text` field, you can pass the BLOB as a string parameter.</span></span> <span data-ttu-id="15d0e-107">BLOB를 SQL Server `image` 필드와 같이 이진 형식으로 저장하면 `byte` 형식의 배열을 이진 매개 변수로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15d0e-107">If the BLOB is stored in binary format, such as a SQL Server `image` field, you can pass an array of type `byte` as a binary parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15d0e-108">예제</span><span class="sxs-lookup"><span data-stu-id="15d0e-108">Example</span></span>  
 <span data-ttu-id="15d0e-109">다음 코드 예제에서는 Northwind 데이터베이스의 Employees 테이블에 직원 정보를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="15d0e-109">The following code example adds employee information to the Employees table in the Northwind database.</span></span> <span data-ttu-id="15d0e-110">파일에서 직원 사진을 읽어 테이블의 Photo 필드에 추가합니다. 이 필드는 이미지 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="15d0e-110">A photo of the employee is read from a file and added to the Photo field in the table, which is an image field.</span></span>  
  
```vb  
Public Shared Sub AddEmployee( _  
  lastName As String, _  
  firstName As String, _  
  title As String, _  
  hireDate As DateTime, _  
  reportsTo As Integer, _  
  photoFilePath As String, _  
  connectionString As String)  
  
  Dim photo() as Byte = GetPhoto(photoFilePath)  
  
  Using connection As SqlConnection = New SqlConnection( _  
    connectionString)  
  
  Dim command As SqlCommand = New SqlCommand( _  
    "INSERT INTO Employees (LastName, FirstName, Title, " & _  
    "HireDate, ReportsTo, Photo) " & _  
    "Values(@LastName, @FirstName, @Title, " & _  
    "@HireDate, @ReportsTo, @Photo)", connection)   
  
  command.Parameters.Add("@LastName",  _  
    SqlDbType.NVarChar, 20).Value = lastName  
  command.Parameters.Add("@FirstName", _  
    SqlDbType.NVarChar, 10).Value = firstName  
  command.Parameters.Add("@Title", _  
    SqlDbType.NVarChar, 30).Value = title  
  command.Parameters.Add("@HireDate", _  
    SqlDbType.DateTime).Value = hireDate  
  command.Parameters.Add("@ReportsTo", _  
    SqlDbType.Int).Value = reportsTo  
  
  command.Parameters.Add("@Photo", _  
    SqlDbType.Image, photo.Length).Value = photo  
  
  connection.Open()  
  command.ExecuteNonQuery()  
  
  End Using  
End Sub  
  
Public Shared Function GetPhoto(filePath As String) As Byte()  
  Dim stream As FileStream = new FileStream( _  
     filePath, FileMode.Open, FileAccess.Read)  
  Dim reader As BinaryReader = new BinaryReader(stream)  
  
  Dim photo() As Byte = reader.ReadBytes(stream.Length)  
  
  reader.Close()  
  stream.Close()  
  
  Return photo  
End Function  
```  
  
```csharp  
public static void AddEmployee(  
  string lastName,   
  string firstName,   
  string title,   
  DateTime hireDate,   
  int reportsTo,   
  string photoFilePath,   
  string connectionString)  
{  
  byte[] photo = GetPhoto(photoFilePath);  
  
  using (SqlConnection connection = new SqlConnection(  
    connectionString))  
  
  SqlCommand command = new SqlCommand(  
    "INSERT INTO Employees (LastName, FirstName, " +  
    "Title, HireDate, ReportsTo, Photo) " +  
    "Values(@LastName, @FirstName, @Title, " +  
    "@HireDate, @ReportsTo, @Photo)", connection);   
  
  command.Parameters.Add("@LastName",    
     SqlDbType.NVarChar, 20).Value = lastName;  
  command.Parameters.Add("@FirstName",   
      SqlDbType.NVarChar, 10).Value = firstName;  
  command.Parameters.Add("@Title",       
      SqlDbType.NVarChar, 30).Value = title;  
  command.Parameters.Add("@HireDate",   
       SqlDbType.DateTime).Value = hireDate;  
  command.Parameters.Add("@ReportsTo",   
      SqlDbType.Int).Value = reportsTo;  
  
  command.Parameters.Add("@Photo",  
      SqlDbType.Image, photo.Length).Value = photo;  
  
  connection.Open();  
  command.ExecuteNonQuery();  
  }  
}  
  
public static byte[] GetPhoto(string filePath)  
{  
  FileStream stream = new FileStream(  
      filePath, FileMode.Open, FileAccess.Read);  
  BinaryReader reader = new BinaryReader(stream);  
  
  byte[] photo = reader.ReadBytes((int)stream.Length);  
  
  reader.Close();  
  stream.Close();  
  
  return photo;  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="15d0e-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="15d0e-111">See Also</span></span>  
 [<span data-ttu-id="15d0e-112">명령을 사용하여 데이터 수정</span><span class="sxs-lookup"><span data-stu-id="15d0e-112">Using Commands to Modify Data</span></span>](../../../../../docs/framework/data/adonet/using-commands-to-modify-data.md)  
 [<span data-ttu-id="15d0e-113">이진 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="15d0e-113">Retrieving Binary Data</span></span>](../../../../../docs/framework/data/adonet/retrieving-binary-data.md)  
 [<span data-ttu-id="15d0e-114">SQL Server 이진 및 큰 값 데이터</span><span class="sxs-lookup"><span data-stu-id="15d0e-114">SQL Server Binary and Large-Value Data</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 [<span data-ttu-id="15d0e-115">SQL Server 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="15d0e-115">SQL Server Data Type Mappings</span></span>](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 [<span data-ttu-id="15d0e-116">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="15d0e-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
