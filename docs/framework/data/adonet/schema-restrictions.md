---
title: "스키마 제한"
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
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: f5b004b70716c61af8ac37fef76f660c488e5a74
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="schema-restrictions"></a><span data-ttu-id="152c9-102">스키마 제한</span><span class="sxs-lookup"><span data-stu-id="152c9-102">Schema Restrictions</span></span>
<span data-ttu-id="152c9-103">두 번째 선택적 매개 변수는 **GetSchema** 메서드는 스키마 정보의 양을 제한 하는 데 사용 되는 제한을 반환 되 고에 전달 되는 **GetSchema** 문자열의 배열로 메서드 .</span><span class="sxs-lookup"><span data-stu-id="152c9-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="152c9-104">배열의 위치는 전달할 수 있는 값을 결정하며 이 위치는 제한 번호와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="152c9-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="152c9-105">예를 들어 다음 표에는 .NET Framework Data Provider for SQL Server를 사용하는 "Table" 스키마 컬렉션에서 지원되는 제한에 대한 설명이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="152c9-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="152c9-106">SQL Server 스키마 컬렉션의 추가 제한은 이 항목의 맨 마지막에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="152c9-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="152c9-107">제한 이름</span><span class="sxs-lookup"><span data-stu-id="152c9-107">Restriction Name</span></span>|<span data-ttu-id="152c9-108">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="152c9-108">Parameter Name</span></span>|<span data-ttu-id="152c9-109">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="152c9-109">Restriction Default</span></span>|<span data-ttu-id="152c9-110">제한 번호</span><span class="sxs-lookup"><span data-stu-id="152c9-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="152c9-111">Catalog</span><span class="sxs-lookup"><span data-stu-id="152c9-111">Catalog</span></span>|@Catalog|<span data-ttu-id="152c9-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="152c9-112">TABLE_CATALOG</span></span>|<span data-ttu-id="152c9-113">1</span><span class="sxs-lookup"><span data-stu-id="152c9-113">1</span></span>|  
|<span data-ttu-id="152c9-114">Owner</span><span class="sxs-lookup"><span data-stu-id="152c9-114">Owner</span></span>|@Owner|<span data-ttu-id="152c9-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="152c9-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="152c9-116">2</span><span class="sxs-lookup"><span data-stu-id="152c9-116">2</span></span>|  
|<span data-ttu-id="152c9-117">표</span><span class="sxs-lookup"><span data-stu-id="152c9-117">Table</span></span>|@Name|<span data-ttu-id="152c9-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="152c9-118">TABLE_NAME</span></span>|<span data-ttu-id="152c9-119">3</span><span class="sxs-lookup"><span data-stu-id="152c9-119">3</span></span>|  
|<span data-ttu-id="152c9-120">TableType</span><span class="sxs-lookup"><span data-stu-id="152c9-120">TableType</span></span>|@TableType|<span data-ttu-id="152c9-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="152c9-121">TABLE_TYPE</span></span>|<span data-ttu-id="152c9-122">4</span><span class="sxs-lookup"><span data-stu-id="152c9-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="152c9-123">제한 값 지정</span><span class="sxs-lookup"><span data-stu-id="152c9-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="152c9-124">"Tables" 스키마 컬렉션의 제한 중 하나를 사용하려면 네 가지 요소로 된 문자열 배열을 만든 다음 제한 번호와 일치하는 요소에 값을 지정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="152c9-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="152c9-125">반환 되는 테이블의 제한 된 **GetSchema** 전달 하기 전에 "Sales" 배열의 두 번째 요소를 설정 하는 메서드를 "Sales" 스키마의 테이블만 **GetSchema** 메서드.</span><span class="sxs-lookup"><span data-stu-id="152c9-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="152c9-126">`SqlClient` 및 `OracleClient`의 제한 컬렉션에는 하나의 추가 `ParameterName` 열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="152c9-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="152c9-127">제한 기본 열은 이전 버전과 여전히 호환되지만 현재는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="152c9-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="152c9-128">문자열 대체보다는 매개 변수가 있는 쿼리를 사용하여 제한 값을 지정할 때 SQL 삽입 공격 위험을 최소화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="152c9-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="152c9-129">배열의 요소 개수는 지정된 스키마 컬렉션에 대해 지원되는 제한 개수보다 작거나 같아야 합니다. 그렇지 않으면 <xref:System.ArgumentException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="152c9-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="152c9-130">제한의 최대 개수보다 작을 수 있으며</span><span class="sxs-lookup"><span data-stu-id="152c9-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="152c9-131">제한이 없으면 null(무제한)로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="152c9-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="152c9-132">호출 하 여 지원 되는 제한 사항 목록을 확인 하려면.NET Framework 관리 공급자를 쿼리할 수 있습니다는 **GetSchema** 메서드는 "제한" 제한 스키마 컬렉션의 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="152c9-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="152c9-133">그러면 컬렉션 이름, 제한 이름, 기본 제한 값 및 제한 번호 목록과 함께 <xref:System.Data.DataTable>이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="152c9-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="152c9-134">예</span><span class="sxs-lookup"><span data-stu-id="152c9-134">Example</span></span>  
 <span data-ttu-id="152c9-135">다음 예에서는 사용 하는 방법을 보여 줍니다는 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> 메서드는.NET Framework 데이터 공급자의 SQL Server에 대 한 <xref:System.Data.SqlClient.SqlConnection> 모든에 포함 된 테이블에 대 한 스키마 정보를 검색 하는 클래스는 **AdventureWorks**예제 데이터베이스를 "Sales" 스키마의 테이블만 반환 된 정보를 제한 하 고:</span><span class="sxs-lookup"><span data-stu-id="152c9-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
```vb  
Imports System.Data.SqlClient  
  
Module Module1  
Sub Main()  
  Dim connectionString As String = _  
    "Data Source=(local);Database=AdventureWorks;" & _  
       "Integrated Security=true;";  
  
  Dim restrictions(3) As String  
  Using connection As New SqlConnection(connectionString)  
    connection.Open()  
  
    'Specify the restrictions.  
    restrictions(1) = "Sales"  
    Dim table As DataTable = connection.GetSchema("Tables", _  
       restrictions)  
  
    ' Display the contents of the table.  
      For Each row As DataRow In table.Rows  
         For Each col As DataColumn In table.Columns  
            Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
         Next  
         Console.WriteLine("============================")  
      Next  
    Console.WriteLine("Press any key to continue.")  
    Console.ReadKey()  
  End Using  
End Sub  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
class Program  
{  
  static void Main()  
  {  
    string connectionString =   
       "Data Source=(local);Database=AdventureWorks;" +  
       "Integrated Security=true;";  
    using (SqlConnection connection =  
       new SqlConnection(connectionString))  
    {  
        connection.Open();  
  
        // Specify the restrictions.  
        string[] restrictions = new string[4];  
        restrictions[1] = "Sales";  
        System.Data.DataTable table = connection.GetSchema(  
          "Tables", restrictions);  
  
        // Display the contents of the table.  
        foreach (System.Data.DataRow row in table.Rows)  
        {  
            foreach (System.Data.DataColumn col in table.Columns)  
            {  
                Console.WriteLine("{0} = {1}",   
                  col.ColumnName, row[col]);  
            }  
            Console.WriteLine("============================");  
        }  
        Console.WriteLine("Press any key to continue.");  
        Console.ReadKey();  
    }  
  }  
  
  private static string GetConnectionString()  
  {  
     // To avoid storing the connection string in your code,  
     // you can retrieve it from a configuration file.  
     return "Data Source=(local);Database=AdventureWorks;" +  
        "Integrated Security=true;";  
  }  
  
  private static void DisplayData(System.Data.DataTable table)  
  {  
     foreach (System.Data.DataRow row in table.Rows)  
     {  
        foreach (System.Data.DataColumn col in table.Columns)  
        {  
           Console.WriteLine("{0} = {1}", col.ColumnName, row[col]);  
        }  
     Console.WriteLine("============================");  
     }  
  }  
}  
```  
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="152c9-136">SQL Server 스키마 제한</span><span class="sxs-lookup"><span data-stu-id="152c9-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="152c9-137">다음 표에는 SQL Server 스키마 컬렉션의 제한이 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="152c9-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="152c9-138">Users</span><span class="sxs-lookup"><span data-stu-id="152c9-138">Users</span></span>  
  
|<span data-ttu-id="152c9-139">제한 이름</span><span class="sxs-lookup"><span data-stu-id="152c9-139">Restriction Name</span></span>|<span data-ttu-id="152c9-140">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="152c9-140">Parameter Name</span></span>|<span data-ttu-id="152c9-141">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="152c9-141">Restriction Default</span></span>|<span data-ttu-id="152c9-142">제한 번호</span><span class="sxs-lookup"><span data-stu-id="152c9-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="152c9-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="152c9-143">User_Name</span></span>|@Name|<span data-ttu-id="152c9-144">name</span><span class="sxs-lookup"><span data-stu-id="152c9-144">name</span></span>|<span data-ttu-id="152c9-145">1</span><span class="sxs-lookup"><span data-stu-id="152c9-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="152c9-146">Databases</span><span class="sxs-lookup"><span data-stu-id="152c9-146">Databases</span></span>  
  
|<span data-ttu-id="152c9-147">제한 이름</span><span class="sxs-lookup"><span data-stu-id="152c9-147">Restriction Name</span></span>|<span data-ttu-id="152c9-148">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="152c9-148">Parameter Name</span></span>|<span data-ttu-id="152c9-149">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="152c9-149">Restriction Default</span></span>|<span data-ttu-id="152c9-150">제한 번호</span><span class="sxs-lookup"><span data-stu-id="152c9-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="152c9-151">name</span><span class="sxs-lookup"><span data-stu-id="152c9-151">Name</span></span>|@Name|<span data-ttu-id="152c9-152">name</span><span class="sxs-lookup"><span data-stu-id="152c9-152">Name</span></span>|<span data-ttu-id="152c9-153">1</span><span class="sxs-lookup"><span data-stu-id="152c9-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="152c9-154">Tables</span><span class="sxs-lookup"><span data-stu-id="152c9-154">Tables</span></span>  
  
|<span data-ttu-id="152c9-155">제한 이름</span><span class="sxs-lookup"><span data-stu-id="152c9-155">Restriction Name</span></span>|<span data-ttu-id="152c9-156">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="152c9-156">Parameter Name</span></span>|<span data-ttu-id="152c9-157">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="152c9-157">Restriction Default</span></span>|<span data-ttu-id="152c9-158">제한 번호</span><span class="sxs-lookup"><span data-stu-id="152c9-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="152c9-159">Catalog</span><span class="sxs-lookup"><span data-stu-id="152c9-159">Catalog</span></span>|@Catalog|<span data-ttu-id="152c9-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="152c9-160">TABLE_CATALOG</span></span>|<span data-ttu-id="152c9-161">1</span><span class="sxs-lookup"><span data-stu-id="152c9-161">1</span></span>|  
|<span data-ttu-id="152c9-162">Owner</span><span class="sxs-lookup"><span data-stu-id="152c9-162">Owner</span></span>|@Owner|<span data-ttu-id="152c9-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="152c9-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="152c9-164">2</span><span class="sxs-lookup"><span data-stu-id="152c9-164">2</span></span>|  
|<span data-ttu-id="152c9-165">표</span><span class="sxs-lookup"><span data-stu-id="152c9-165">Table</span></span>|@Name|<span data-ttu-id="152c9-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="152c9-166">TABLE_NAME</span></span>|<span data-ttu-id="152c9-167">3</span><span class="sxs-lookup"><span data-stu-id="152c9-167">3</span></span>|  
|<span data-ttu-id="152c9-168">TableType</span><span class="sxs-lookup"><span data-stu-id="152c9-168">TableType</span></span>|@TableType|<span data-ttu-id="152c9-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="152c9-169">TABLE_TYPE</span></span>|<span data-ttu-id="152c9-170">4</span><span class="sxs-lookup"><span data-stu-id="152c9-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="152c9-171">Columns</span><span class="sxs-lookup"><span data-stu-id="152c9-171">Columns</span></span>  
  
|<span data-ttu-id="152c9-172">제한 이름</span><span class="sxs-lookup"><span data-stu-id="152c9-172">Restriction Name</span></span>|<span data-ttu-id="152c9-173">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="152c9-173">Parameter Name</span></span>|<span data-ttu-id="152c9-174">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="152c9-174">Restriction Default</span></span>|<span data-ttu-id="152c9-175">제한 번호</span><span class="sxs-lookup"><span data-stu-id="152c9-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="152c9-176">Catalog</span><span class="sxs-lookup"><span data-stu-id="152c9-176">Catalog</span></span>|@Catalog|<span data-ttu-id="152c9-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="152c9-177">TABLE_CATALOG</span></span>|<span data-ttu-id="152c9-178">1</span><span class="sxs-lookup"><span data-stu-id="152c9-178">1</span></span>|  
|<span data-ttu-id="152c9-179">Owner</span><span class="sxs-lookup"><span data-stu-id="152c9-179">Owner</span></span>|@Owner|<span data-ttu-id="152c9-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="152c9-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="152c9-181">2</span><span class="sxs-lookup"><span data-stu-id="152c9-181">2</span></span>|  
|<span data-ttu-id="152c9-182">표</span><span class="sxs-lookup"><span data-stu-id="152c9-182">Table</span></span>|@Table|<span data-ttu-id="152c9-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="152c9-183">TABLE_NAME</span></span>|<span data-ttu-id="152c9-184">3</span><span class="sxs-lookup"><span data-stu-id="152c9-184">3</span></span>|  
|<span data-ttu-id="152c9-185">열</span><span class="sxs-lookup"><span data-stu-id="152c9-185">Column</span></span>|@Column|<span data-ttu-id="152c9-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="152c9-186">COLUMN_NAME</span></span>|<span data-ttu-id="152c9-187">4</span><span class="sxs-lookup"><span data-stu-id="152c9-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="152c9-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="152c9-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="152c9-189">제한 이름</span><span class="sxs-lookup"><span data-stu-id="152c9-189">Restriction Name</span></span>|<span data-ttu-id="152c9-190">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="152c9-190">Parameter Name</span></span>|<span data-ttu-id="152c9-191">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="152c9-191">Restriction Default</span></span>|<span data-ttu-id="152c9-192">제한 번호</span><span class="sxs-lookup"><span data-stu-id="152c9-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="152c9-193">Catalog</span><span class="sxs-lookup"><span data-stu-id="152c9-193">Catalog</span></span>|@Catalog|<span data-ttu-id="152c9-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="152c9-194">TABLE_CATALOG</span></span>|<span data-ttu-id="152c9-195">1</span><span class="sxs-lookup"><span data-stu-id="152c9-195">1</span></span>|  
|<span data-ttu-id="152c9-196">Owner</span><span class="sxs-lookup"><span data-stu-id="152c9-196">Owner</span></span>|@Owner|<span data-ttu-id="152c9-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="152c9-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="152c9-198">2</span><span class="sxs-lookup"><span data-stu-id="152c9-198">2</span></span>|  
|<span data-ttu-id="152c9-199">표</span><span class="sxs-lookup"><span data-stu-id="152c9-199">Table</span></span>|@Table|<span data-ttu-id="152c9-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="152c9-200">TABLE_NAME</span></span>|<span data-ttu-id="152c9-201">3</span><span class="sxs-lookup"><span data-stu-id="152c9-201">3</span></span>|  
|<span data-ttu-id="152c9-202">열</span><span class="sxs-lookup"><span data-stu-id="152c9-202">Column</span></span>|@Column|<span data-ttu-id="152c9-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="152c9-203">COLUMN_NAME</span></span>|<span data-ttu-id="152c9-204">4</span><span class="sxs-lookup"><span data-stu-id="152c9-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="152c9-205">뷰</span><span class="sxs-lookup"><span data-stu-id="152c9-205">Views</span></span>  
  
|<span data-ttu-id="152c9-206">제한 이름</span><span class="sxs-lookup"><span data-stu-id="152c9-206">Restriction Name</span></span>|<span data-ttu-id="152c9-207">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="152c9-207">Parameter Name</span></span>|<span data-ttu-id="152c9-208">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="152c9-208">Restriction Default</span></span>|<span data-ttu-id="152c9-209">제한 번호</span><span class="sxs-lookup"><span data-stu-id="152c9-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="152c9-210">Catalog</span><span class="sxs-lookup"><span data-stu-id="152c9-210">Catalog</span></span>|@Catalog|<span data-ttu-id="152c9-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="152c9-211">TABLE_CATALOG</span></span>|<span data-ttu-id="152c9-212">1</span><span class="sxs-lookup"><span data-stu-id="152c9-212">1</span></span>|  
|<span data-ttu-id="152c9-213">Owner</span><span class="sxs-lookup"><span data-stu-id="152c9-213">Owner</span></span>|@Owner|<span data-ttu-id="152c9-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="152c9-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="152c9-215">2</span><span class="sxs-lookup"><span data-stu-id="152c9-215">2</span></span>|  
|<span data-ttu-id="152c9-216">표</span><span class="sxs-lookup"><span data-stu-id="152c9-216">Table</span></span>|@Table|<span data-ttu-id="152c9-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="152c9-217">TABLE_NAME</span></span>|<span data-ttu-id="152c9-218">3</span><span class="sxs-lookup"><span data-stu-id="152c9-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="152c9-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="152c9-219">ViewColumns</span></span>  
  
|<span data-ttu-id="152c9-220">제한 이름</span><span class="sxs-lookup"><span data-stu-id="152c9-220">Restriction Name</span></span>|<span data-ttu-id="152c9-221">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="152c9-221">Parameter Name</span></span>|<span data-ttu-id="152c9-222">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="152c9-222">Restriction Default</span></span>|<span data-ttu-id="152c9-223">제한 번호</span><span class="sxs-lookup"><span data-stu-id="152c9-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="152c9-224">Catalog</span><span class="sxs-lookup"><span data-stu-id="152c9-224">Catalog</span></span>|@Catalog|<span data-ttu-id="152c9-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="152c9-225">VIEW_CATALOG</span></span>|<span data-ttu-id="152c9-226">1</span><span class="sxs-lookup"><span data-stu-id="152c9-226">1</span></span>|  
|<span data-ttu-id="152c9-227">Owner</span><span class="sxs-lookup"><span data-stu-id="152c9-227">Owner</span></span>|@Owner|<span data-ttu-id="152c9-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="152c9-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="152c9-229">2</span><span class="sxs-lookup"><span data-stu-id="152c9-229">2</span></span>|  
|<span data-ttu-id="152c9-230">표</span><span class="sxs-lookup"><span data-stu-id="152c9-230">Table</span></span>|@Table|<span data-ttu-id="152c9-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="152c9-231">VIEW_NAME</span></span>|<span data-ttu-id="152c9-232">3</span><span class="sxs-lookup"><span data-stu-id="152c9-232">3</span></span>|  
|<span data-ttu-id="152c9-233">열</span><span class="sxs-lookup"><span data-stu-id="152c9-233">Column</span></span>|@Column|<span data-ttu-id="152c9-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="152c9-234">COLUMN_NAME</span></span>|<span data-ttu-id="152c9-235">4</span><span class="sxs-lookup"><span data-stu-id="152c9-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="152c9-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="152c9-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="152c9-237">제한 이름</span><span class="sxs-lookup"><span data-stu-id="152c9-237">Restriction Name</span></span>|<span data-ttu-id="152c9-238">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="152c9-238">Parameter Name</span></span>|<span data-ttu-id="152c9-239">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="152c9-239">Restriction Default</span></span>|<span data-ttu-id="152c9-240">제한 번호</span><span class="sxs-lookup"><span data-stu-id="152c9-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="152c9-241">Catalog</span><span class="sxs-lookup"><span data-stu-id="152c9-241">Catalog</span></span>|@Catalog|<span data-ttu-id="152c9-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="152c9-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="152c9-243">1</span><span class="sxs-lookup"><span data-stu-id="152c9-243">1</span></span>|  
|<span data-ttu-id="152c9-244">Owner</span><span class="sxs-lookup"><span data-stu-id="152c9-244">Owner</span></span>|@Owner|<span data-ttu-id="152c9-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="152c9-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="152c9-246">2</span><span class="sxs-lookup"><span data-stu-id="152c9-246">2</span></span>|  
|<span data-ttu-id="152c9-247">name</span><span class="sxs-lookup"><span data-stu-id="152c9-247">Name</span></span>|@Name|<span data-ttu-id="152c9-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="152c9-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="152c9-249">3</span><span class="sxs-lookup"><span data-stu-id="152c9-249">3</span></span>|  
|<span data-ttu-id="152c9-250">매개 변수</span><span class="sxs-lookup"><span data-stu-id="152c9-250">Parameter</span></span>|@Parameter|<span data-ttu-id="152c9-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="152c9-251">PARAMETER_NAME</span></span>|<span data-ttu-id="152c9-252">4</span><span class="sxs-lookup"><span data-stu-id="152c9-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="152c9-253">절차</span><span class="sxs-lookup"><span data-stu-id="152c9-253">Procedures</span></span>  
  
|<span data-ttu-id="152c9-254">제한 이름</span><span class="sxs-lookup"><span data-stu-id="152c9-254">Restriction Name</span></span>|<span data-ttu-id="152c9-255">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="152c9-255">Parameter Name</span></span>|<span data-ttu-id="152c9-256">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="152c9-256">Restriction Default</span></span>|<span data-ttu-id="152c9-257">제한 번호</span><span class="sxs-lookup"><span data-stu-id="152c9-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="152c9-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="152c9-258">Catalog</span></span>|@Catalog|<span data-ttu-id="152c9-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="152c9-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="152c9-260">1</span><span class="sxs-lookup"><span data-stu-id="152c9-260">1</span></span>|  
|<span data-ttu-id="152c9-261">Owner</span><span class="sxs-lookup"><span data-stu-id="152c9-261">Owner</span></span>|@Owner|<span data-ttu-id="152c9-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="152c9-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="152c9-263">2</span><span class="sxs-lookup"><span data-stu-id="152c9-263">2</span></span>|  
|<span data-ttu-id="152c9-264">name</span><span class="sxs-lookup"><span data-stu-id="152c9-264">Name</span></span>|@Name|<span data-ttu-id="152c9-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="152c9-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="152c9-266">3</span><span class="sxs-lookup"><span data-stu-id="152c9-266">3</span></span>|  
|<span data-ttu-id="152c9-267">형식</span><span class="sxs-lookup"><span data-stu-id="152c9-267">Type</span></span>|@Type|<span data-ttu-id="152c9-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="152c9-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="152c9-269">4</span><span class="sxs-lookup"><span data-stu-id="152c9-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="152c9-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="152c9-270">IndexColumns</span></span>  
  
|<span data-ttu-id="152c9-271">제한 이름</span><span class="sxs-lookup"><span data-stu-id="152c9-271">Restriction Name</span></span>|<span data-ttu-id="152c9-272">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="152c9-272">Parameter Name</span></span>|<span data-ttu-id="152c9-273">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="152c9-273">Restriction Default</span></span>|<span data-ttu-id="152c9-274">제한 번호</span><span class="sxs-lookup"><span data-stu-id="152c9-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="152c9-275">Catalog</span><span class="sxs-lookup"><span data-stu-id="152c9-275">Catalog</span></span>|@Catalog|<span data-ttu-id="152c9-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="152c9-276">db_name()</span></span>|<span data-ttu-id="152c9-277">1</span><span class="sxs-lookup"><span data-stu-id="152c9-277">1</span></span>|  
|<span data-ttu-id="152c9-278">Owner</span><span class="sxs-lookup"><span data-stu-id="152c9-278">Owner</span></span>|@Owner|<span data-ttu-id="152c9-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="152c9-279">user_name()</span></span>|<span data-ttu-id="152c9-280">2</span><span class="sxs-lookup"><span data-stu-id="152c9-280">2</span></span>|  
|<span data-ttu-id="152c9-281">표</span><span class="sxs-lookup"><span data-stu-id="152c9-281">Table</span></span>|@Table|<span data-ttu-id="152c9-282">o.name</span><span class="sxs-lookup"><span data-stu-id="152c9-282">o.name</span></span>|<span data-ttu-id="152c9-283">3</span><span class="sxs-lookup"><span data-stu-id="152c9-283">3</span></span>|  
|<span data-ttu-id="152c9-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="152c9-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="152c9-285">x.name</span><span class="sxs-lookup"><span data-stu-id="152c9-285">x.name</span></span>|<span data-ttu-id="152c9-286">4</span><span class="sxs-lookup"><span data-stu-id="152c9-286">4</span></span>|  
|<span data-ttu-id="152c9-287">열</span><span class="sxs-lookup"><span data-stu-id="152c9-287">Column</span></span>|@Column|<span data-ttu-id="152c9-288">c.name</span><span class="sxs-lookup"><span data-stu-id="152c9-288">c.name</span></span>|<span data-ttu-id="152c9-289">5</span><span class="sxs-lookup"><span data-stu-id="152c9-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="152c9-290">Indexes</span><span class="sxs-lookup"><span data-stu-id="152c9-290">Indexes</span></span>  
  
|<span data-ttu-id="152c9-291">제한 이름</span><span class="sxs-lookup"><span data-stu-id="152c9-291">Restriction Name</span></span>|<span data-ttu-id="152c9-292">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="152c9-292">Parameter Name</span></span>|<span data-ttu-id="152c9-293">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="152c9-293">Restriction Default</span></span>|<span data-ttu-id="152c9-294">제한 번호</span><span class="sxs-lookup"><span data-stu-id="152c9-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="152c9-295">Catalog</span><span class="sxs-lookup"><span data-stu-id="152c9-295">Catalog</span></span>|@Catalog|<span data-ttu-id="152c9-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="152c9-296">db_name()</span></span>|<span data-ttu-id="152c9-297">1</span><span class="sxs-lookup"><span data-stu-id="152c9-297">1</span></span>|  
|<span data-ttu-id="152c9-298">Owner</span><span class="sxs-lookup"><span data-stu-id="152c9-298">Owner</span></span>|@Owner|<span data-ttu-id="152c9-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="152c9-299">user_name()</span></span>|<span data-ttu-id="152c9-300">2</span><span class="sxs-lookup"><span data-stu-id="152c9-300">2</span></span>|  
|<span data-ttu-id="152c9-301">표</span><span class="sxs-lookup"><span data-stu-id="152c9-301">Table</span></span>|@Table|<span data-ttu-id="152c9-302">o.name</span><span class="sxs-lookup"><span data-stu-id="152c9-302">o.name</span></span>|<span data-ttu-id="152c9-303">3</span><span class="sxs-lookup"><span data-stu-id="152c9-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="152c9-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="152c9-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="152c9-305">제한 이름</span><span class="sxs-lookup"><span data-stu-id="152c9-305">Restriction Name</span></span>|<span data-ttu-id="152c9-306">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="152c9-306">Parameter Name</span></span>|<span data-ttu-id="152c9-307">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="152c9-307">Restriction Default</span></span>|<span data-ttu-id="152c9-308">제한 번호</span><span class="sxs-lookup"><span data-stu-id="152c9-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="152c9-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="152c9-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="152c9-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="152c9-310">assemblies.name</span></span>|<span data-ttu-id="152c9-311">1</span><span class="sxs-lookup"><span data-stu-id="152c9-311">1</span></span>|  
|<span data-ttu-id="152c9-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="152c9-312">udt_name</span></span>|@UDTName|<span data-ttu-id="152c9-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="152c9-313">types.assembly_class</span></span>|<span data-ttu-id="152c9-314">2</span><span class="sxs-lookup"><span data-stu-id="152c9-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="152c9-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="152c9-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="152c9-316">제한 이름</span><span class="sxs-lookup"><span data-stu-id="152c9-316">Restriction Name</span></span>|<span data-ttu-id="152c9-317">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="152c9-317">Parameter Name</span></span>|<span data-ttu-id="152c9-318">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="152c9-318">Restriction Default</span></span>|<span data-ttu-id="152c9-319">제한 번호</span><span class="sxs-lookup"><span data-stu-id="152c9-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="152c9-320">Catalog</span><span class="sxs-lookup"><span data-stu-id="152c9-320">Catalog</span></span>|@Catalog|<span data-ttu-id="152c9-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="152c9-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="152c9-322">1</span><span class="sxs-lookup"><span data-stu-id="152c9-322">1</span></span>|  
|<span data-ttu-id="152c9-323">Owner</span><span class="sxs-lookup"><span data-stu-id="152c9-323">Owner</span></span>|@Owner|<span data-ttu-id="152c9-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="152c9-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="152c9-325">2</span><span class="sxs-lookup"><span data-stu-id="152c9-325">2</span></span>|  
|<span data-ttu-id="152c9-326">표</span><span class="sxs-lookup"><span data-stu-id="152c9-326">Table</span></span>|@Table|<span data-ttu-id="152c9-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="152c9-327">TABLE_NAME</span></span>|<span data-ttu-id="152c9-328">3</span><span class="sxs-lookup"><span data-stu-id="152c9-328">3</span></span>|  
|<span data-ttu-id="152c9-329">name</span><span class="sxs-lookup"><span data-stu-id="152c9-329">Name</span></span>|@Name|<span data-ttu-id="152c9-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="152c9-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="152c9-331">4</span><span class="sxs-lookup"><span data-stu-id="152c9-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="152c9-332">SQL Server 2008       </span><span class="sxs-lookup"><span data-stu-id="152c9-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="152c9-333">다음 표에는 SQL Server 2008 스키마 컬렉션의 제한이 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="152c9-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="152c9-334">이러한 제한은 .NET Framework 버전 3.5 SP1 및 SQL Server 2008 이상에서 유효하며</span><span class="sxs-lookup"><span data-stu-id="152c9-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="152c9-335">이전 버전의 .NET Framework 및 SQL Server에서는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="152c9-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="152c9-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="152c9-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="152c9-337">제한 이름</span><span class="sxs-lookup"><span data-stu-id="152c9-337">Restriction Name</span></span>|<span data-ttu-id="152c9-338">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="152c9-338">Parameter Name</span></span>|<span data-ttu-id="152c9-339">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="152c9-339">Restriction Default</span></span>|<span data-ttu-id="152c9-340">제한 번호</span><span class="sxs-lookup"><span data-stu-id="152c9-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="152c9-341">Catalog</span><span class="sxs-lookup"><span data-stu-id="152c9-341">Catalog</span></span>|@Catalog|<span data-ttu-id="152c9-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="152c9-342">TABLE_CATALOG</span></span>|<span data-ttu-id="152c9-343">1</span><span class="sxs-lookup"><span data-stu-id="152c9-343">1</span></span>|  
|<span data-ttu-id="152c9-344">Owner</span><span class="sxs-lookup"><span data-stu-id="152c9-344">Owner</span></span>|@Owner|<span data-ttu-id="152c9-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="152c9-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="152c9-346">2</span><span class="sxs-lookup"><span data-stu-id="152c9-346">2</span></span>|  
|<span data-ttu-id="152c9-347">표</span><span class="sxs-lookup"><span data-stu-id="152c9-347">Table</span></span>|@Table|<span data-ttu-id="152c9-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="152c9-348">TABLE_NAME</span></span>|<span data-ttu-id="152c9-349">3</span><span class="sxs-lookup"><span data-stu-id="152c9-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="152c9-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="152c9-350">AllColumns</span></span>  
  
|<span data-ttu-id="152c9-351">제한 이름</span><span class="sxs-lookup"><span data-stu-id="152c9-351">Restriction Name</span></span>|<span data-ttu-id="152c9-352">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="152c9-352">Parameter Name</span></span>|<span data-ttu-id="152c9-353">제한 기본값</span><span class="sxs-lookup"><span data-stu-id="152c9-353">Restriction Default</span></span>|<span data-ttu-id="152c9-354">제한 번호</span><span class="sxs-lookup"><span data-stu-id="152c9-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="152c9-355">Catalog</span><span class="sxs-lookup"><span data-stu-id="152c9-355">Catalog</span></span>|@Catalog|<span data-ttu-id="152c9-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="152c9-356">TABLE_CATALOG</span></span>|<span data-ttu-id="152c9-357">1</span><span class="sxs-lookup"><span data-stu-id="152c9-357">1</span></span>|  
|<span data-ttu-id="152c9-358">Owner</span><span class="sxs-lookup"><span data-stu-id="152c9-358">Owner</span></span>|@Owner|<span data-ttu-id="152c9-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="152c9-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="152c9-360">2</span><span class="sxs-lookup"><span data-stu-id="152c9-360">2</span></span>|  
|<span data-ttu-id="152c9-361">표</span><span class="sxs-lookup"><span data-stu-id="152c9-361">Table</span></span>|@Table|<span data-ttu-id="152c9-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="152c9-362">TABLE_NAME</span></span>|<span data-ttu-id="152c9-363">3</span><span class="sxs-lookup"><span data-stu-id="152c9-363">3</span></span>|  
|<span data-ttu-id="152c9-364">열</span><span class="sxs-lookup"><span data-stu-id="152c9-364">Column</span></span>|@Column|<span data-ttu-id="152c9-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="152c9-365">COLUMN_NAME</span></span>|<span data-ttu-id="152c9-366">4</span><span class="sxs-lookup"><span data-stu-id="152c9-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="152c9-367">참고 항목</span><span class="sxs-lookup"><span data-stu-id="152c9-367">See Also</span></span>  
 [<span data-ttu-id="152c9-368">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="152c9-368">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
