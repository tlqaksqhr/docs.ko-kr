---
title: "데이터 조작"
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
ms.assetid: 51096a2e-8b38-4c4d-a523-799bfdb7ec69
caps.latest.revision: "6"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 65042cecc5a6841ffb9b74e471cb9f237d15373f
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="manipulating-data"></a><span data-ttu-id="18dbd-102">데이터 조작</span><span class="sxs-lookup"><span data-stu-id="18dbd-102">Manipulating Data</span></span>
<span data-ttu-id="18dbd-103">MARS(Multiple Active Result Sets)가 도입되기 전까지 개발자는 다중 연결이나 서버측 커서를 사용하여 특정 시나리오를 해결해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="18dbd-103">Before the introduction of Multiple Active Result Sets (MARS), developers had to use either multiple connections or server-side cursors to solve certain scenarios.</span></span> <span data-ttu-id="18dbd-104">또한 트랜잭션 상황에서 여러 개의 연결이 사용 되 던 때 바인딩된 연결 (으로 **sp_getbindtoken** 및 **sp_bindsession**) 필요 했습니다.</span><span class="sxs-lookup"><span data-stu-id="18dbd-104">In addition, when multiple connections were used in a transactional situation, bound connections (with **sp_getbindtoken** and **sp_bindsession**) were required.</span></span> <span data-ttu-id="18dbd-105">다음 시나리오에서는 다중 연결 대신 MARS 사용 연결을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="18dbd-105">The following scenarios show how to use a MARS-enabled connection instead of multiple connections.</span></span>  
  
## <a name="using-multiple-commands-with-mars"></a><span data-ttu-id="18dbd-106">MARS로 여러 명령 사용</span><span class="sxs-lookup"><span data-stu-id="18dbd-106">Using Multiple Commands with MARS</span></span>  
 <span data-ttu-id="18dbd-107">다음 콘솔 응용 프로그램에서는 두 개의 <xref:System.Data.SqlClient.SqlDataReader> 개체와 MARS가 활성화된 두 개의 <xref:System.Data.SqlClient.SqlCommand> 개체 및 하나의 <xref:System.Data.SqlClient.SqlConnection> 개체를 함께 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="18dbd-107">The following Console application demonstrates how to use two <xref:System.Data.SqlClient.SqlDataReader> objects with two <xref:System.Data.SqlClient.SqlCommand> objects and a single <xref:System.Data.SqlClient.SqlConnection> object with MARS enabled.</span></span>  
  
### <a name="example"></a><span data-ttu-id="18dbd-108">예</span><span class="sxs-lookup"><span data-stu-id="18dbd-108">Example</span></span>  
 <span data-ttu-id="18dbd-109">이 예제에서는 단일 연결을 열어 고 **AdventureWorks** 데이터베이스입니다.</span><span class="sxs-lookup"><span data-stu-id="18dbd-109">The example opens a single connection to the **AdventureWorks** database.</span></span> <span data-ttu-id="18dbd-110"><xref:System.Data.SqlClient.SqlCommand> 개체를 사용하면 <xref:System.Data.SqlClient.SqlDataReader>가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="18dbd-110">Using a <xref:System.Data.SqlClient.SqlCommand> object, a <xref:System.Data.SqlClient.SqlDataReader> is created.</span></span> <span data-ttu-id="18dbd-111">판독기를 사용하면 두 번째 <xref:System.Data.SqlClient.SqlDataReader>가 열리고 첫 번째 <xref:System.Data.SqlClient.SqlDataReader>의 데이터가 두 번째 판독기의 WHERE 절에 대한 입력으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="18dbd-111">As the reader is used, a second <xref:System.Data.SqlClient.SqlDataReader> is opened, using data from the first <xref:System.Data.SqlClient.SqlDataReader> as input to the WHERE clause for the second reader.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="18dbd-112">다음 예제에서는 샘플을 사용 하 여 **AdventureWorks** 에 포함 된 데이터베이스 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="18dbd-112">The following example uses the sample **AdventureWorks** database included with [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="18dbd-113">샘플 코드에 제공된 연결 문자열은 데이터베이스가 로컬 컴퓨터에 설치되었으며 사용 가능하다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="18dbd-113">The connection string provided in the sample code assumes that the database is installed and available on the local computer.</span></span> <span data-ttu-id="18dbd-114">사용자 환경의 필요에 따라 연결 문자열을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="18dbd-114">Modify the connection string as necessary for your environment.</span></span>  
  
```vb  
Option Strict On  
Option Explicit On  
  
Imports System  
Imports System.Data  
Imports System.Data.SqlClient  
Module Module1  
  Sub Main()  
    ' By default, MARS is disabled when connecting  
    ' to a MARS-enabled host.  
    ' It must be enabled in the connection string.  
    Dim connectionString As String = GetConnectionString()  
  
    Dim vendorID As Integer  
  
    Dim vendorCmd As SqlCommand  
    Dim productCmd As SqlCommand  
    Dim productReader As SqlDataReader  
  
    Dim vendorSQL As String = & _   
      "SELECT VendorId, Name FROM Purchasing.Vendor"  
    Dim productSQL As String = _  
        "SELECT Production.Product.Name FROM Production.Product " & _  
        "INNER JOIN Purchasing.ProductVendor " & _  
        "ON Production.Product.ProductID = " & _  
        "Purchasing.ProductVendor.ProductID " & _  
        "WHERE Purchasing.ProductVendor.VendorID = @VendorId"  
  
    Using awConnection As New SqlConnection(connectionString)  
      vendorCmd = New SqlCommand(vendorSQL, awConnection)  
      productCmd = New SqlCommand(productSQL, awConnection)  
      productCmd.Parameters.Add("@VendorId", SqlDbType.Int)  
  
      awConnection.Open()  
      Using vendorReader As SqlDataReader = vendorCmd.ExecuteReader()  
        While vendorReader.Read()  
          Console.WriteLine(vendorReader("Name"))  
  
          vendorID = CInt(vendorReader("VendorId"))  
  
          productCmd.Parameters("@VendorId").Value = vendorID  
  
          ' The following line of code requires  
          ' a MARS-enabled connection.  
          productReader = productCmd.ExecuteReader()  
          Using productReader  
            While productReader.Read()  
              Console.WriteLine("  " & CStr(productReader("Name")))  
            End While  
          End Using  
        End While  
      End Using  
    End Using  
  
    Console.WriteLine("Press any key to continue")  
    Console.ReadLine()  
  End Sub  
  
  Function GetConnectionString() As String  
    ' To avoid storing the connection string in your code,  
    ' you can retrive it from a configuration file.  
    Return "Data Source=(local);Integrated Security=SSPI;" & _  
      "Initial Catalog=AdventureWorks; MultipleActiveResultSets=True"  
  End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
class Class1  
{  
static void Main()  
{  
  // By default, MARS is disabled when connecting  
  // to a MARS-enabled host.  
  // It must be enabled in the connection string.  
  string connectionString = GetConnectionString();  
  
  int vendorID;  
  SqlDataReader productReader = null;  
  string vendorSQL =   
    "SELECT VendorId, Name FROM Purchasing.Vendor";  
  string productSQL =   
    "SELECT Production.Product.Name FROM Production.Product " +  
    "INNER JOIN Purchasing.ProductVendor " +  
    "ON Production.Product.ProductID = " +   
    "Purchasing.ProductVendor.ProductID " +  
    "WHERE Purchasing.ProductVendor.VendorID = @VendorId";  
  
  using (SqlConnection awConnection =   
    new SqlConnection(connectionString))  
  {  
    SqlCommand vendorCmd = new SqlCommand(vendorSQL, awConnection);  
    SqlCommand productCmd =   
      new SqlCommand(productSQL, awConnection);  
  
    productCmd.Parameters.Add("@VendorId", SqlDbType.Int);  
  
    awConnection.Open();  
    using (SqlDataReader vendorReader = vendorCmd.ExecuteReader())  
    {  
      while (vendorReader.Read())  
      {  
        Console.WriteLine(vendorReader["Name"]);  
  
        vendorID = (int)vendorReader["VendorId"];  
  
        productCmd.Parameters["@VendorId"].Value = vendorID;  
        // The following line of code requires  
        // a MARS-enabled connection.  
        productReader = productCmd.ExecuteReader();  
        using (productReader)  
        {  
          while (productReader.Read())  
          {  
            Console.WriteLine("  " +  
              productReader["Name"].ToString());  
          }  
        }  
      }  
  }  
      Console.WriteLine("Press any key to continue");  
      Console.ReadLine();  
    }  
  }  
  private static string GetConnectionString()  
  {  
    // To avoid storing the connection string in your code,  
    // you can retrive it from a configuration file.  
    return "Data Source=(local);Integrated Security=SSPI;" +   
      "Initial Catalog=AdventureWorks;MultipleActiveResultSets=True";  
  }  
}  
```  
  
## <a name="reading-and-updating-data-with-mars"></a><span data-ttu-id="18dbd-115">MARS로 데이터 읽기 및 업데이트</span><span class="sxs-lookup"><span data-stu-id="18dbd-115">Reading and Updating Data with MARS</span></span>  
 <span data-ttu-id="18dbd-116">MARS를 사용하면 하나의 연결을 둘 이상의 보류 중인 작업과 함께 읽기 작업 및 DML(데이터 조작 언어) 작업 모두에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18dbd-116">MARS allows a connection to be used for both read operations and data manipulation language (DML) operations with more than one pending operation.</span></span> <span data-ttu-id="18dbd-117">이 기능을 사용하면 응용 프로그램에서 연결 사용 오류를 처리할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="18dbd-117">This feature eliminates the need for an application to deal with connection-busy errors.</span></span> <span data-ttu-id="18dbd-118">또한 MARS는 일반적으로 더 많은 리소스를 사용하는 서버측 커서의 사용자를 대체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18dbd-118">In addition, MARS can replace the user of server-side cursors, which generally consume more resources.</span></span> <span data-ttu-id="18dbd-119">마지막으로 여러 작업이 단일 연결에서 실행 수, 있으므로 사용 하지 않아도 동일한 트랜잭션 컨텍스트를 공유 수 **sp_getbindtoken** 및 **sp_bindsession** 시스템 저장 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="18dbd-119">Finally, because multiple operations can operate on a single connection, they can share the same transaction context, eliminating the need to use **sp_getbindtoken** and **sp_bindsession** system stored procedures.</span></span>  
  
### <a name="example"></a><span data-ttu-id="18dbd-120">예</span><span class="sxs-lookup"><span data-stu-id="18dbd-120">Example</span></span>  
 <span data-ttu-id="18dbd-121">다음 콘솔 응용 프로그램에서는 두 개의 <xref:System.Data.SqlClient.SqlDataReader> 개체와 MARS가 활성화된 세 개의 <xref:System.Data.SqlClient.SqlCommand> 개체 및 하나의 <xref:System.Data.SqlClient.SqlConnection> 개체를 함께 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="18dbd-121">The following Console application demonstrates how to use two <xref:System.Data.SqlClient.SqlDataReader> objects with three <xref:System.Data.SqlClient.SqlCommand> objects and a single <xref:System.Data.SqlClient.SqlConnection> object with MARS enabled.</span></span> <span data-ttu-id="18dbd-122">첫 번째 명령 개체에서는 신용 등급이 5인 공급업체 목록을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="18dbd-122">The first command object retrieves a list of vendors whose credit rating is 5.</span></span> <span data-ttu-id="18dbd-123">두 번째 명령 개체는 <xref:System.Data.SqlClient.SqlDataReader>에서 제공한 공급업체 ID를 사용하여 두 번째 <xref:System.Data.SqlClient.SqlDataReader>와 함께 특정 공급업체의 모든 제품을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="18dbd-123">The second command object uses the vendor ID provided from a <xref:System.Data.SqlClient.SqlDataReader> to load the second <xref:System.Data.SqlClient.SqlDataReader> with all of the products for the particular vendor.</span></span> <span data-ttu-id="18dbd-124">각 제품 레코드에는 두 번째 <xref:System.Data.SqlClient.SqlDataReader>에서 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="18dbd-124">Each product record is visited by the second <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="18dbd-125">새로운 결정 하는 계산을 수행 하는 **OnOrderQty** 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18dbd-125">A calculation is performed to determine what the new **OnOrderQty** should be.</span></span> <span data-ttu-id="18dbd-126">세 번째 명령 개체는 다음 업데이트 하는 데는 **ProductVendor** 새 값이 있는 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="18dbd-126">The third command object is then used to update the **ProductVendor** table with the new value.</span></span> <span data-ttu-id="18dbd-127">이 전체 프로세스가 단일 트랜잭션에서 발생하며 프로세스가 끝나면 롤백됩니다.</span><span class="sxs-lookup"><span data-stu-id="18dbd-127">This entire process takes place within a single transaction, which is rolled back at the end.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="18dbd-128">다음 예제에서는 샘플을 사용 하 여 **AdventureWorks** 에 포함 된 데이터베이스 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="18dbd-128">The following example uses the sample **AdventureWorks** database included with [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="18dbd-129">샘플 코드에 제공된 연결 문자열은 데이터베이스가 로컬 컴퓨터에 설치되었으며 사용 가능하다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="18dbd-129">The connection string provided in the sample code assumes that the database is installed and available on the local computer.</span></span> <span data-ttu-id="18dbd-130">사용자 환경의 필요에 따라 연결 문자열을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="18dbd-130">Modify the connection string as necessary for your environment.</span></span>  
  
```vb  
Option Strict On  
Option Explicit On  
  
Imports System  
Imports System.Data  
Imports System.Data.SqlClient  
  
Module Module1  
  
  Sub Main()  
    ' By default, MARS is disabled when connecting  
    ' to a MARS-enabled host.  
    ' It must be enabled in the connection string.  
    Dim connectionString As String = GetConnectionString()  
  
    Dim updateTx As SqlTransaction  
    Dim vendorCmd As SqlCommand  
    Dim prodVendCmd As SqlCommand  
    Dim updateCmd As SqlCommand  
  
    Dim prodVendReader As SqlDataReader  
  
    Dim vendorID As Integer  
    Dim productID As Integer  
    Dim minOrderQty As Integer  
    Dim maxOrderQty As Integer  
    Dim onOrderQty As Integer  
    Dim recordsUpdated As Integer  
    Dim totalRecordsUpdated As Integer  
  
    Dim vendorSQL As String = _  
        "SELECT VendorID, Name FROM Purchasing.Vendor " & _  
        "WHERE CreditRating = 5"  
    Dim prodVendSQL As String = _  
        "SELECT ProductID, MaxOrderQty, MinOrderQty, OnOrderQty " & _  
        "FROM Purchasing.ProductVendor " & _  
        "WHERE VendorID = @VendorID"  
    Dim updateSQL As String = _  
        "UPDATE Purchasing.ProductVendor " & _   
        "SET OnOrderQty = @OrderQty " & _  
        "WHERE ProductID = @ProductID AND VendorID = @VendorID"  
  
    Using awConnection As New SqlConnection(connectionString)  
      awConnection.Open()  
      updateTx = awConnection.BeginTransaction()  
  
      vendorCmd = New SqlCommand(vendorSQL, awConnection)  
      vendorCmd.Transaction = updateTx  
  
      prodVendCmd = New SqlCommand(prodVendSQL, awConnection)  
      prodVendCmd.Transaction = updateTx  
      prodVendCmd.Parameters.Add("@VendorId", SqlDbType.Int)  
  
      updateCmd = New SqlCommand(updateSQL, awConnection)  
      updateCmd.Transaction = updateTx  
      updateCmd.Parameters.Add("@OrderQty", SqlDbType.Int)  
      updateCmd.Parameters.Add("@ProductID", SqlDbType.Int)  
      updateCmd.Parameters.Add("@VendorID", SqlDbType.Int)  
  
      Using vendorReader As SqlDataReader = vendorCmd.ExecuteReader()  
        While vendorReader.Read()  
          Console.WriteLine(vendorReader("Name"))  
  
          vendorID = CInt(vendorReader("VendorID"))  
          prodVendCmd.Parameters("@VendorID").Value = vendorID  
          prodVendReader = prodVendCmd.ExecuteReader()  
  
          Using prodVendReader  
            While (prodVendReader.Read)  
              productID = CInt(prodVendReader("ProductID"))  
  
              If IsDBNull(prodVendReader("OnOrderQty")) Then  
                minOrderQty = CInt(prodVendReader("MinOrderQty"))  
                onOrderQty = minOrderQty  
              Else  
                maxOrderQty = CInt(prodVendReader("MaxOrderQty"))  
                onOrderQty = CInt(maxOrderQty / 2)  
              End If  
  
              updateCmd.Parameters("@OrderQty").Value = onOrderQty  
              updateCmd.Parameters("@ProductID").Value = productID  
              updateCmd.Parameters("@VendorID").Value = vendorID  
  
              recordsUpdated = updateCmd.ExecuteNonQuery()  
              totalRecordsUpdated += recordsUpdated  
            End While  
          End Using  
        End While  
      End Using  
  
      Console.WriteLine("Total Records Updated: " & _   
        CStr(totalRecordsUpdated))  
      updateTx.Rollback()  
      Console.WriteLine("Transaction Rolled Back")  
    End Using  
  
    Console.WriteLine("Press any key to continue")  
    Console.ReadLine()  
  
  End Sub  
  
  Function GetConnectionString() As String  
    ' To avoid storing the connection string in your code,  
    ' you can retrive it from a configuration file.  
    Return "Data Source=(local);Integrated Security=SSPI;" & _  
      "Initial Catalog=AdventureWorks;MultipleActiveResultSets=True"  
  End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.Data;  
using System.Data.SqlClient;  
  
class Program  
{  
static void Main()  
{  
  // By default, MARS is disabled when connecting  
  // to a MARS-enabled host.  
  // It must be enabled in the connection string.  
  string connectionString = GetConnectionString();  
  
  SqlTransaction updateTx = null;  
  SqlCommand vendorCmd = null;  
  SqlCommand prodVendCmd = null;  
  SqlCommand updateCmd = null;  
  
  SqlDataReader prodVendReader = null;  
  
  int vendorID = 0;  
  int productID = 0;  
  int minOrderQty = 0;  
  int maxOrderQty = 0;  
  int onOrderQty = 0;  
  int recordsUpdated = 0;  
  int totalRecordsUpdated = 0;  
  
  string vendorSQL =  
      "SELECT VendorID, Name FROM Purchasing.Vendor " +   
      "WHERE CreditRating = 5";  
  string prodVendSQL =  
      "SELECT ProductID, MaxOrderQty, MinOrderQty, OnOrderQty " +  
      "FROM Purchasing.ProductVendor " +   
      "WHERE VendorID = @VendorID";  
  string updateSQL =  
      "UPDATE Purchasing.ProductVendor " +   
      "SET OnOrderQty = @OrderQty " +  
      "WHERE ProductID = @ProductID AND VendorID = @VendorID";  
  
  using (SqlConnection awConnection =   
    new SqlConnection(connectionString))  
  {  
    awConnection.Open();  
    updateTx = awConnection.BeginTransaction();  
  
    vendorCmd = new SqlCommand(vendorSQL, awConnection);  
    vendorCmd.Transaction = updateTx;  
  
    prodVendCmd = new SqlCommand(prodVendSQL, awConnection);  
    prodVendCmd.Transaction = updateTx;  
    prodVendCmd.Parameters.Add("@VendorId", SqlDbType.Int);  
  
    updateCmd = new SqlCommand(updateSQL, awConnection);  
    updateCmd.Transaction = updateTx;  
    updateCmd.Parameters.Add("@OrderQty", SqlDbType.Int);  
    updateCmd.Parameters.Add("@ProductID", SqlDbType.Int);  
    updateCmd.Parameters.Add("@VendorID", SqlDbType.Int);  
  
    using (SqlDataReader vendorReader = vendorCmd.ExecuteReader())  
    {  
      while (vendorReader.Read())  
      {  
        Console.WriteLine(vendorReader["Name"]);  
  
        vendorID = (int) vendorReader["VendorID"];  
        prodVendCmd.Parameters["@VendorID"].Value = vendorID;  
        prodVendReader = prodVendCmd.ExecuteReader();  
  
        using (prodVendReader)  
        {  
          while (prodVendReader.Read())  
          {  
            productID = (int) prodVendReader["ProductID"];  
  
            if (prodVendReader["OnOrderQty"] == DBNull.Value)  
            {  
              minOrderQty = (int) prodVendReader["MinOrderQty"];  
              onOrderQty = minOrderQty;  
            }  
            else  
            {  
              maxOrderQty = (int) prodVendReader["MaxOrderQty"];  
              onOrderQty = (int)(maxOrderQty / 2);  
            }  
  
            updateCmd.Parameters["@OrderQty"].Value = onOrderQty;  
            updateCmd.Parameters["@ProductID"].Value = productID;  
            updateCmd.Parameters["@VendorID"].Value = vendorID;  
  
            recordsUpdated = updateCmd.ExecuteNonQuery();  
            totalRecordsUpdated += recordsUpdated;  
          }  
        }  
      }  
    }  
    Console.WriteLine("Total Records Updated: " +   
      totalRecordsUpdated.ToString());  
    updateTx.Rollback();  
    Console.WriteLine("Transaction Rolled Back");  
  }  
  
  Console.WriteLine("Press any key to continue");  
  Console.ReadLine();  
}  
private static string GetConnectionString()  
{  
  // To avoid storing the connection string in your code,  
  // you can retrive it from a configuration file.  
  return "Data Source=(local);Integrated Security=SSPI;" +   
    "Initial Catalog=AdventureWorks;" +   
    "MultipleActiveResultSets=True";  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="18dbd-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18dbd-131">See Also</span></span>  
 [<span data-ttu-id="18dbd-132">MARS(Multiple Active Result Sets)</span><span class="sxs-lookup"><span data-stu-id="18dbd-132">Multiple Active Result Sets (MARS)</span></span>](../../../../../docs/framework/data/adonet/sql/multiple-active-result-sets-mars.md)  
 [<span data-ttu-id="18dbd-133">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="18dbd-133">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
