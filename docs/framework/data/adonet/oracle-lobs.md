---
title: Oracle LOB
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 272e8e1e-a31f-475a-8c2a-ae8e1286bdab
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 6aa72d4c3ac27b3be6704943819596ad628e4f7f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="oracle-lobs"></a><span data-ttu-id="8f365-102">Oracle LOB</span><span class="sxs-lookup"><span data-stu-id="8f365-102">Oracle LOBs</span></span>
<span data-ttu-id="8f365-103">.NET Framework Data Provider for Oracle에 포함 되어는 <xref:System.Data.OracleClient.OracleLob> Oracle을 사용 하는 데 사용 되는 클래스 **LOB** 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8f365-103">The .NET Framework Data Provider for Oracle includes the <xref:System.Data.OracleClient.OracleLob> class, which is used to work with Oracle **LOB** data types.</span></span>  
  
 <span data-ttu-id="8f365-104">**OracleLob** 이 중 하나가 될 수 있습니다 <xref:System.Data.OracleClient.OracleType> 데이터 형식:</span><span class="sxs-lookup"><span data-stu-id="8f365-104">An **OracleLob** may be one of these <xref:System.Data.OracleClient.OracleType> data types:</span></span>  
  
|<span data-ttu-id="8f365-105">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8f365-105">Data type</span></span>|<span data-ttu-id="8f365-106">설명</span><span class="sxs-lookup"><span data-stu-id="8f365-106">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8f365-107">**Blob**</span><span class="sxs-lookup"><span data-stu-id="8f365-107">**Blob**</span></span>|<span data-ttu-id="8f365-108">Oracle **BLOB** 최대 크기가 4gb의 이진 데이터를 포함 하는 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8f365-108">An Oracle **BLOB** data type that contains binary data with a maximum size of 4 gigabytes.</span></span> <span data-ttu-id="8f365-109">매핑되는 **배열** 형식의 **바이트**합니다.</span><span class="sxs-lookup"><span data-stu-id="8f365-109">This maps to an **Array** of type **Byte**.</span></span>|  
|<span data-ttu-id="8f365-110">**Clob**</span><span class="sxs-lookup"><span data-stu-id="8f365-110">**Clob**</span></span>|<span data-ttu-id="8f365-111">Oracle **CLOB** 데이터 형식은 기본 문자에 따라 문자 데이터를 포함 하는 최대 크기가 4gb의 서버에 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f365-111">An Oracle **CLOB** data type that contains character data, based on the default character set on the server, with a maximum size of 4 gigabytes.</span></span> <span data-ttu-id="8f365-112">에 매핑됩니다 **문자열**합니다.</span><span class="sxs-lookup"><span data-stu-id="8f365-112">This maps to **String**.</span></span>|  
|<span data-ttu-id="8f365-113">**NClob**</span><span class="sxs-lookup"><span data-stu-id="8f365-113">**NClob**</span></span>|<span data-ttu-id="8f365-114">Oracle **NCLOB** 국가별 문자 집합에 4gb의 최대 크기를 사용 하 여 서버를 기반으로 문자 데이터를 포함 하는 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8f365-114">An Oracle **NCLOB** data type that contains character data, based on the national character set on the server with a maximum size of 4 gigabytes.</span></span> <span data-ttu-id="8f365-115">에 매핑됩니다 **문자열**합니다.</span><span class="sxs-lookup"><span data-stu-id="8f365-115">This maps to **String**.</span></span>|  
  
 <span data-ttu-id="8f365-116">**OracleLob** 에서 다른는 <xref:System.Data.OracleClient.OracleBFile> 데이터는 운영 체제의 물리적 파일이 아닌 서버에 저장 된다는 점에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f365-116">An **OracleLob** differs from an <xref:System.Data.OracleClient.OracleBFile> in that the data is stored on the server instead of in a physical file in the operating system.</span></span> <span data-ttu-id="8f365-117">와 달리 읽기 / 쓰기 개체 일 수도 있습니다는 **OracleBFile**는 항상 읽기 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="8f365-117">It can also be a read-write object, unlike an **OracleBFile**, which is always read-only.</span></span>  
  
## <a name="creating-retrieving-and-writing-to-a-lob"></a><span data-ttu-id="8f365-118">LOB 만들기, 검색 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="8f365-118">Creating, Retrieving, and Writing to a LOB</span></span>  
 <span data-ttu-id="8f365-119">다음 C# 예제는 Oracle 테이블에 Lob를 만들 하 고 다음 검색 하는 방법의 형태로 쓸 **OracleLob** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="8f365-119">The following C# example demonstrates how you can create LOBs in an Oracle table, and then retrieve and write to them in the form of **OracleLob** objects.</span></span> <span data-ttu-id="8f365-120">예제를 사용 하는 <xref:System.Data.OracleClient.OracleDataReader> 개체 및 **OracleLob** **읽기** 및 **쓰기** 메서드.</span><span class="sxs-lookup"><span data-stu-id="8f365-120">The example demonstrates using the <xref:System.Data.OracleClient.OracleDataReader> object and the **OracleLob** **Read** and **Write** methods.</span></span> <span data-ttu-id="8f365-121">예제에서는 Oracle **BLOB**, **CLOB**, 및 **NCLOB** 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8f365-121">The example uses Oracle **BLOB**, **CLOB**, and **NCLOB** data types.</span></span>  
  
```csharp  
using System;  
using System.IO;              
using System.Text;             
using System.Data;              
using System.Data.OracleClient;  
  
// LobExample  
public class LobExample  
{  
   public static int Main(string[] args)  
   {  
      //Create a connection.  
      OracleConnection conn = new OracleConnection(  
         "Data Source=Oracle8i;Integrated Security=yes");  
      using(conn)  
      {  
         //Open a connection.  
         conn.Open();  
         OracleCommand cmd = conn.CreateCommand();  
  
         //Create the table and schema.  
         CreateTable(cmd);  
  
         //Read example.  
         ReadLobExample(cmd);  
  
         //Write example  
         WriteLobExample(cmd);  
      }  
  
      return 1;  
   }  
  
   // ReadLobExample  
   public static void ReadLobExample(OracleCommand cmd)  
   {  
      int actual = 0;  
  
      // Table Schema:  
      // "CREATE TABLE tablewithlobs (a int, b BLOB, c CLOB, d NCLOB)";  
      // "INSERT INTO tablewithlobs values (1, 'AA', 'AAA', N'AAAA')";  
      // Select some data.  
      cmd.CommandText = "SELECT * FROM tablewithlobs";  
      OracleDataReader reader = cmd.ExecuteReader();  
      using(reader)  
      {  
         //Obtain the first row of data.  
         reader.Read();  
  
         //Obtain the LOBs (all 3 varieties).  
         OracleLob blob = reader.GetOracleLob(1);  
         OracleLob clob = reader.GetOracleLob(2);  
         OracleLob nclob = reader.GetOracleLob(3);  
  
         //Example - Reading binary data (in chunks).  
         byte[] buffer = new byte[100];  
         while((actual = blob.Read(buffer, 0, buffer.Length)) >0)  
            Console.WriteLine(blob.LobType + ".Read(" + buffer + ", " +   
              buffer.Length + ") => " + actual);  
  
         // Example - Reading CLOB/NCLOB data (in chunks).  
         // Note: You can read character data as raw Unicode bytes   
         // (using OracleLob.Read as in the above example).  
         // However, because the OracleLob object inherits directly   
         // from the .Net stream object,   
         // all the existing classes that manipluate streams can   
         // also be used. For example, the   
         // .Net StreamReader makes it easier to convert the raw bytes   
         // into actual characters.  
         StreamReader streamreader =   
           new StreamReader(clob, Encoding.Unicode);  
         char[] cbuffer = new char[100];  
         while((actual = streamreader.Read(cbuffer,   
           0, cbuffer.Length)) >0)  
            Console.WriteLine(clob.LobType + ".Read(  
              " + new string(cbuffer, 0, actual) + ", " +   
              cbuffer.Length + ") => " + actual);  
  
         // Example - Reading data (all at once).  
         // You could use StreamReader.ReadToEnd to obtain   
         // all the string data, or simply  
         // call OracleLob.Value to obtain a contiguous allocation   
         // of all the data.  
         Console.WriteLine(nclob.LobType + ".Value => " + nclob.Value);  
      }  
   }  
  
   // WriteLobExample  
   public static void WriteLobExample(OracleCommand cmd)  
   {  
      //Note: Updating LOB data requires a transaction.  
      cmd.Transaction = cmd.Connection.BeginTransaction();  
  
      // Select some data.  
      // Table Schema:  
      // "CREATE TABLE tablewithlobs (a int, b BLOB, c CLOB, d NCLOB)";  
      // "INSERT INTO tablewithlobs values (1, 'AA', 'AAA', N'AAAA')";  
      cmd.CommandText = "SELECT * FROM tablewithlobs FOR UPDATE";  
      OracleDataReader reader = cmd.ExecuteReader();  
      using(reader)  
      {  
         // Obtain the first row of data.  
         reader.Read();  
  
         // Obtain a LOB.  
         OracleLob blob = reader.GetOracleLob(1/*0:based ordinal*/);  
  
         // Perform any desired operations on the LOB   
         // (read, position, and so on).  
  
         // Example - Writing binary data (directly to the backend).  
         // To write, you can use any of the stream classes, or write  
         // raw binary data using   
         // the OracleLob write method. Writing character vs. binary   
         // is the same;  
         // however note that character is always in terms of   
         // Unicode byte counts  
         // (for example, even number of bytes - 2 bytes for every  
         // Unicode character).  
         byte[] buffer = new byte[100];  
         buffer[0] = 0xCC;  
         buffer[1] = 0xDD;  
         blob.Write(buffer, 0, 2);  
         blob.Position = 0;  
         Console.WriteLine(blob.LobType + ".Write(  
           " + buffer + ", 0, 2) => " + blob.Value);  
  
         // Example - Obtaining a temp LOB and copying data   
         // into it from another LOB.  
         OracleLob templob = CreateTempLob(cmd, blob.LobType);  
         long actual = blob.CopyTo(templob);  
         Console.WriteLine(blob.LobType + ".CopyTo(  
            " + templob.Value + ") => " + actual);  
  
         // Commit the transaction now that everything succeeded.  
         // Note: On error, Transaction.Dispose is called   
         // (from the using statement)  
         // and will automatically roll back the pending transaction.  
         cmd.Transaction.Commit();  
      }  
   }  
  
   // CreateTempLob  
   public static OracleLob CreateTempLob(  
     OracleCommand cmd, OracleType lobtype)  
   {  
      //Oracle server syntax to obtain a temporary LOB.  
      cmd.CommandText = "DECLARE A " + lobtype + "; "+  
                     "BEGIN "+  
                        "DBMS_LOB.CREATETEMPORARY(A, FALSE); "+  
                        ":LOC := A; "+  
                     "END;";  
  
      //Bind the LOB as an output parameter.  
      OracleParameter p = cmd.Parameters.Add("LOC", lobtype);  
      p.Direction = ParameterDirection.Output;  
  
      //Execute (to receive the output temporary LOB).  
      cmd.ExecuteNonQuery();  
  
      //Return the temporary LOB.  
      return (OracleLob)p.Value;  
   }  
  
   // CreateTable  
   public static void CreateTable(OracleCommand cmd)  
   {  
      // Table Schema:  
      // "CREATE TABLE tablewithlobs (a int, b BLOB, c CLOB, d NCLOB)";  
      // "INSERT INTO tablewithlobs VALUES (1, 'AA', 'AAA', N'AAAA')";  
      try  
      {  
         cmd.CommandText   = "DROP TABLE tablewithlobs";  
         cmd.ExecuteNonQuery();  
      }  
      catch(Exception)  
      {  
      }  
  
      cmd.CommandText =   
        "CREATE TABLE tablewithlobs (a int, b BLOB, c CLOB, d NCLOB)";  
      cmd.ExecuteNonQuery();  
      cmd.CommandText =   
        "INSERT INTO tablewithlobs VALUES (1, 'AA', 'AAA', N'AAAA')";  
      cmd.ExecuteNonQuery();  
   }  
}  
```  
  
## <a name="creating-a-temporary-lob"></a><span data-ttu-id="8f365-122">임시 LOB 만들기</span><span class="sxs-lookup"><span data-stu-id="8f365-122">Creating a Temporary LOB</span></span>  
 <span data-ttu-id="8f365-123">다음 C# 예제에서는 임시 LOB를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8f365-123">The following C# example demonstrates how to create a temporary LOB.</span></span>  
  
```csharp  
OracleConnection conn = new OracleConnection(  
  "server=test8172; integrated security=yes;");  
conn.Open();  
  
OracleTransaction tx = conn.BeginTransaction();  
  
OracleCommand cmd = conn.CreateCommand();  
cmd.Transaction = tx;  
cmd.CommandText =   
  "declare xx blob; begin dbms_lob.createtemporary(  
  xx, false, 0); :tempblob := xx; end;";  
cmd.Parameters.Add(new OracleParameter("tempblob",  
  OracleType.Blob)).Direction = ParameterDirection.Output;  
cmd.ExecuteNonQuery();  
OracleLob tempLob = (OracleLob)cmd.Parameters[0].Value;  
tempLob.BeginBatch(OracleLobOpenMode.ReadWrite);  
tempLob.Write(tempbuff,0,tempbuff.Length);  
tempLob.EndBatch();  
cmd.Parameters.Clear();  
cmd.CommandText = "myTable.myProc";  
cmd.CommandType = CommandType.StoredProcedure;    
cmd.Parameters.Add(new OracleParameter(  
  "ImportDoc", OracleType.Blob)).Value = tempLob;  
cmd.ExecuteNonQuery();  
  
tx.Commit();  
```  
  
## <a name="see-also"></a><span data-ttu-id="8f365-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8f365-124">See Also</span></span>  
 [<span data-ttu-id="8f365-125">Oracle 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8f365-125">Oracle and ADO.NET</span></span>](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [<span data-ttu-id="8f365-126">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="8f365-126">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
