---
title: "ADO.NET에서 데이터 형식 매핑"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4afab94-ada6-4c77-a73c-41f17bae6b5a
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 45061ed18d5854092db4a8d90bc18d48e2e6e6db
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="data-type-mappings-in-adonet"></a><span data-ttu-id="bc2dc-102">ADO.NET에서 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="bc2dc-102">Data Type Mappings in ADO.NET</span></span>
<span data-ttu-id="bc2dc-103">.NET Framework는 런타임에 형식이 선언, 사용 및 관리되는 방법을 정의하는 공용 형식 시스템을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc2dc-103">The .NET Framework is based on the common type system, which defines how types are declared, used, and managed in the runtime.</span></span> <span data-ttu-id="bc2dc-104">.NET Framework는 값 형식과 참조 형식으로 구성되며, 두 형식 모두 <xref:System.Object> 기본 형식에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc2dc-104">It consists of both value types and reference types, which all derive from the <xref:System.Object> base type.</span></span> <span data-ttu-id="bc2dc-105">데이터 소스로 작업할 경우 데이터 형식을 명시적으로 지정하지 않으면 데이터 공급자에서 데이터 형식이 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc2dc-105">When working with a data source, the data type is inferred from the data provider if it is not explicitly specified.</span></span> <span data-ttu-id="bc2dc-106">예를 들어 <xref:System.Data.DataSet> 개체는 모든 데이터 소스에 대해 독립적입니다.</span><span class="sxs-lookup"><span data-stu-id="bc2dc-106">For example, a <xref:System.Data.DataSet> object is independent of any specific data source.</span></span> <span data-ttu-id="bc2dc-107">`DataSet`의 데이터는 데이터 소스에서 검색되며 변경 내용은 `DataAdapter`를 사용하여 데이터 소스에 다시 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc2dc-107">Data in a `DataSet` is retrieved from a data source, and changes are persisted back to the data source by using a `DataAdapter`.</span></span> <span data-ttu-id="bc2dc-108">즉, `DataAdapter`가 <xref:System.Data.DataTable>의 `DataSet`을 데이터 소스의 값으로 채울 때 `DataTable` 열의 결과 데이터 형식은 데이터 소스에 연결하는 데 사용되는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 데이터 공급자별 형식이 아닌, [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="bc2dc-108">This means that when a `DataAdapter` fills a <xref:System.Data.DataTable> in a `DataSet` with values from a data source, the resulting data types of the columns in the `DataTable` are [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] types, instead of types specific to the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data provider that is used to connect to the data source.</span></span>  
  
 <span data-ttu-id="bc2dc-109">마찬가지로 `DataReader`가 데이터 소스의 값을 반환할 때 결과 값은 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 형식의 지역 변수에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc2dc-109">Likewise, when a `DataReader` returns a value from a data source, the resulting value is stored in a local variable that has a [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] type.</span></span> <span data-ttu-id="bc2dc-110">`Fill`의 `DataAdapter` 작업과 `Get`의 `DataReader` 메서드 모두에서 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 형식은 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 데이터 공급자로부터 반환된 값에서 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc2dc-110">For both the `Fill` operations of the `DataAdapter` and the `Get` methods of the `DataReader`, the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] type is inferred from the value returned from the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data provider.</span></span>  
  
 <span data-ttu-id="bc2dc-111">반환되는 값의 형식을 알고 있는 경우에는 유추되는 데이터 형식을 사용하는 대신 `DataReader`의 형식화된 접근자 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc2dc-111">Instead of relying on the inferred data type, you can use the typed accessor methods of the `DataReader` when you know the specific type of the value being returned.</span></span> <span data-ttu-id="bc2dc-112">형식화된 접근자 메서드는 값을 특정 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 형식으로 반환하여 추가로 형식을 변환할 필요가 없도록 하므로 더 나은 성능을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc2dc-112">Typed accessor methods give you better performance by returning a value as a specific [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] type, which eliminates the need for additional type conversion.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc2dc-113">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 데이터 공급자 데이터 형식의 Null 값은 `DBNull.Value`로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc2dc-113">Null values for [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data provider data types are represented by `DBNull.Value`.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bc2dc-114">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="bc2dc-114">In This Section</span></span>  
 [<span data-ttu-id="bc2dc-115">SQL Server 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="bc2dc-115">SQL Server Data Type Mappings</span></span>](../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 <span data-ttu-id="bc2dc-116"><xref:System.Data.SqlClient>의 유추된 데이터 형식 매핑과 데이터 접근자 메서드 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bc2dc-116">Lists inferred data type mappings and data accessor methods for <xref:System.Data.SqlClient>.</span></span>  
  
 [<span data-ttu-id="bc2dc-117">OLE DB 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="bc2dc-117">OLE DB Data Type Mappings</span></span>](../../../../docs/framework/data/adonet/ole-db-data-type-mappings.md)  
 <span data-ttu-id="bc2dc-118"><xref:System.Data.OleDb>의 유추된 데이터 형식 매핑과 데이터 접근자 메서드 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bc2dc-118">Lists inferred data type mappings and data accessor methods for <xref:System.Data.OleDb>.</span></span>  
  
 [<span data-ttu-id="bc2dc-119">ODBC 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="bc2dc-119">ODBC Data Type Mappings</span></span>](../../../../docs/framework/data/adonet/odbc-data-type-mappings.md)  
 <span data-ttu-id="bc2dc-120"><xref:System.Data.Odbc>의 유추된 데이터 형식 매핑과 데이터 접근자 메서드 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bc2dc-120">Lists inferred data type mappings and data accessor methods for <xref:System.Data.Odbc>.</span></span>  
  
 [<span data-ttu-id="bc2dc-121">Oracle 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="bc2dc-121">Oracle Data Type Mappings</span></span>](../../../../docs/framework/data/adonet/oracle-data-type-mappings.md)  
 <span data-ttu-id="bc2dc-122"><xref:System.Data.OracleClient>의 유추된 데이터 형식 매핑과 데이터 접근자 메서드 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bc2dc-122">Lists inferred data type mappings and data accessor methods for <xref:System.Data.OracleClient>.</span></span>  
  
 [<span data-ttu-id="bc2dc-123">부동 소수점 숫자</span><span class="sxs-lookup"><span data-stu-id="bc2dc-123">Floating-Point Numbers</span></span>](../../../../docs/framework/data/adonet/floating-point-numbers.md)  
 <span data-ttu-id="bc2dc-124">개발자가 부동 소수점 숫자를 사용할 때 자주 발생하는 문제에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bc2dc-124">Describes issues that developers frequently encounter when working with floating-point numbers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc2dc-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bc2dc-125">See Also</span></span>  
 [<span data-ttu-id="bc2dc-126">SQL Server 데이터 형식 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="bc2dc-126">SQL Server Data Types and ADO.NET</span></span>](../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [<span data-ttu-id="bc2dc-127">매개 변수 및 매개 변수 데이터 형식 구성</span><span class="sxs-lookup"><span data-stu-id="bc2dc-127">Configuring Parameters and Parameter Data Types</span></span>](../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 [<span data-ttu-id="bc2dc-128">데이터베이스 스키마 정보 검색</span><span class="sxs-lookup"><span data-stu-id="bc2dc-128">Retrieving Database Schema Information</span></span>](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 [<span data-ttu-id="bc2dc-129">공용 형식 시스템</span><span class="sxs-lookup"><span data-stu-id="bc2dc-129">Common Type System</span></span>](../../../../docs/standard/base-types/common-type-system.md)  
 [<span data-ttu-id="bc2dc-130">형식 변환</span><span class="sxs-lookup"><span data-stu-id="bc2dc-130">Converting Types</span></span>](http://msdn.microsoft.com/en-us/6038316e-bdaf-4f55-8006-407f591ce156)  
 [<span data-ttu-id="bc2dc-131">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="bc2dc-131">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
