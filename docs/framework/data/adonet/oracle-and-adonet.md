---
title: "Oracle 및 ADO.NET"
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
ms.assetid: 8ee8e389-53cf-45cf-80bd-1df63ef34f2e
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: c615c985f885734800b471ee31451cfb8a4c8500
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="oracle-and-adonet"></a><span data-ttu-id="00c22-102">Oracle 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="00c22-102">Oracle and ADO.NET</span></span>
> [!NOTE]
>  <span data-ttu-id="00c22-103"><xref:System.Data.OracleClient>의 형식은 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="00c22-103">The types in <xref:System.Data.OracleClient> are deprecated.</span></span> <span data-ttu-id="00c22-104">이 형식은 현재 버전의 .NET Framework에서 계속 지원되지만 향후 릴리스에서 제거될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="00c22-104">The types remain supported in the current version of.NET Framework but will be removed in a future release.</span></span> <span data-ttu-id="00c22-105">타사 Oracle 공급자를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="00c22-105">Microsoft recommends that you use a third-party Oracle provider.</span></span>  
  
 <span data-ttu-id="00c22-106">이 단원에서는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle과 관련된 기능 및 동작에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00c22-106">This section describes features and behaviors that are specific to the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle.</span></span>  
  
 <span data-ttu-id="00c22-107">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle에서는 Oracle Client 소프트웨어에서 제공하는 OCI(Oracle Call Interface)를 사용하여 Oracle 데이터베이스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00c22-107">The [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle provides access to an Oracle database using the Oracle Call Interface (OCI) as provided by Oracle Client software.</span></span> <span data-ttu-id="00c22-108">이 데이터 공급자의 기능은 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], OLE DB 및 ODBC용 [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] 데이터 공급자의 기능과 유사하게 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="00c22-108">The functionality of the data provider is designed to be similar to that of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data providers for [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)], OLE DB, and ODBC.</span></span>  
  
 <span data-ttu-id="00c22-109">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle을 사용하려면 다음과 같이 응용 프로그램에서 <xref:System.Data.OracleClient> 네임스페이스를 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00c22-109">To use the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle, an application must reference the <xref:System.Data.OracleClient> namespace as follows:</span></span>  
  
```vb  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data.OracleClient;  
```  
  
 <span data-ttu-id="00c22-110">또한 코드를 컴파일할 때 DLL에 대한 참조를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00c22-110">You also must include a reference to the DLL when you compile your code.</span></span> <span data-ttu-id="00c22-111">예를 들어, C# 프로그램을 컴파일하는 경우 명령줄에 다음을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00c22-111">For example, if you are compiling a C# program, your command line should include:</span></span>  
  
```  
csc /r:System.Data.OracleClient.dll  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="00c22-112">단원 내용</span><span class="sxs-lookup"><span data-stu-id="00c22-112">In This Section</span></span>  
 [<span data-ttu-id="00c22-113">시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="00c22-113">System Requirements</span></span>](../../../../docs/framework/data/adonet/system-requirements-for-the-dotnet-data-provider-for-oracle.md)  
 <span data-ttu-id="00c22-114">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle을 사용하는 데 필요한 요구 사항 및 사용 과정에서 발생하는 몇 가지 알려진 문제점에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00c22-114">Describes requirements for using the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle, and describes a number of issues to be aware when using it.</span></span>  
  
 [<span data-ttu-id="00c22-115">Oracle Bfile</span><span class="sxs-lookup"><span data-stu-id="00c22-115">Oracle BFILEs</span></span>](../../../../docs/framework/data/adonet/oracle-bfiles.md)  
 <span data-ttu-id="00c22-116">Oracle BFILE 데이터 형식 작업에 사용되는 <xref:System.Data.OracleClient.OracleBFile> 클래스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00c22-116">Describes the <xref:System.Data.OracleClient.OracleBFile> class, which is used to work with the Oracle BFILE data type.</span></span>  
  
 [<span data-ttu-id="00c22-117">Oracle Lob</span><span class="sxs-lookup"><span data-stu-id="00c22-117">Oracle LOBs</span></span>](../../../../docs/framework/data/adonet/oracle-lobs.md)  
 <span data-ttu-id="00c22-118">Oracle LOB 데이터 형식 작업에 사용되는 <xref:System.Data.OracleClient.OracleLob> 클래스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00c22-118">Describes the <xref:System.Data.OracleClient.OracleLob> class, which is used to work with Oracle LOB data types.</span></span>  
  
 [<span data-ttu-id="00c22-119">Oracle REF Cursor</span><span class="sxs-lookup"><span data-stu-id="00c22-119">Oracle REF CURSORs</span></span>](../../../../docs/framework/data/adonet/oracle-ref-cursors.md)  
 <span data-ttu-id="00c22-120">Oracle REF CURSOR 데이터 형식 지원에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00c22-120">Describes support for the Oracle REF CURSOR data type.</span></span>  
  
 [<span data-ttu-id="00c22-121">OracleTypes</span><span class="sxs-lookup"><span data-stu-id="00c22-121">OracleTypes</span></span>](../../../../docs/framework/data/adonet/oracletypes.md)  
 <span data-ttu-id="00c22-122"><xref:System.Data.OracleClient.OracleNumber> 및 <xref:System.Data.OracleClient.OracleString>을 비롯하여 Oracle 데이터 형식 작업에 사용할 수 있는 구조에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00c22-122">Describes structures you can use to work with Oracle data types, including <xref:System.Data.OracleClient.OracleNumber> and <xref:System.Data.OracleClient.OracleString>.</span></span>  
  
 [<span data-ttu-id="00c22-123">Oracle 시퀀스</span><span class="sxs-lookup"><span data-stu-id="00c22-123">Oracle Sequences</span></span>](../../../../docs/framework/data/adonet/oracle-sequences.md)  
 <span data-ttu-id="00c22-124">서버에서 생성한 Oracle 시퀀스 키 값을 검색하는 지원 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00c22-124">Describes support for retrieving the server-generated key Oracle Sequence values.</span></span>  
  
 [<span data-ttu-id="00c22-125">Oracle 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="00c22-125">Oracle Data Type Mappings</span></span>](../../../../docs/framework/data/adonet/oracle-data-type-mappings.md)  
 <span data-ttu-id="00c22-126">Oracle 데이터 형식과 <xref:System.Data.OracleClient.OracleDataReader>에 대한 해당 데이터 형식의 매핑이 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00c22-126">Lists Oracle data types and their mappings to the <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 [<span data-ttu-id="00c22-127">Oracle 분산 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="00c22-127">Oracle Distributed Transactions</span></span>](../../../../docs/framework/data/adonet/oracle-distributed-transactions.md)  
 <span data-ttu-id="00c22-128"><xref:System.Data.OracleClient.OracleConnection> 개체에서 트랜잭션이 활성화되어 있다고 판단할 경우 기존 분산 트랜잭션에 자동으로 인리스트먼트하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00c22-128">Describes how the <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="00c22-129">관련 단원</span><span class="sxs-lookup"><span data-stu-id="00c22-129">Related Sections</span></span>  
 [<span data-ttu-id="00c22-130">ADO.NET 응용 프로그램 보안</span><span class="sxs-lookup"><span data-stu-id="00c22-130">Securing ADO.NET Applications</span></span>](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 <span data-ttu-id="00c22-131">[!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]을 사용할 때 보안 코드를 작성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00c22-131">Describes secure coding practices when using [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].</span></span>  
  
 [<span data-ttu-id="00c22-132">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="00c22-132">DataSets, DataTables, and DataViews</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 <span data-ttu-id="00c22-133">`DataSets`, 형식화된 `DataSets`, `DataTables` 및 `DataViews`를 만들고 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00c22-133">Describes how to create and use `DataSets`, typed `DataSets`, `DataTables`, and `DataViews`.</span></span>  
  
 [<span data-ttu-id="00c22-134">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="00c22-134">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 <span data-ttu-id="00c22-135">ADO.NET에서 데이터로 작업하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00c22-135">Describes how to work with data in ADO.NET.</span></span>  
  
 [<span data-ttu-id="00c22-136">SQL Server 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="00c22-136">SQL Server and ADO.NET</span></span>](../../../../docs/framework/data/adonet/sql/index.md)  
 <span data-ttu-id="00c22-137">[!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] 관련 기능을 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00c22-137">Describes how to work with features and functionality that are specific to [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="00c22-138">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="00c22-138">DbProviderFactories</span></span>](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 <span data-ttu-id="00c22-139">[!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]에서 공급자 독립적인 코드를 쓸 수 있게 하는 일반 클래스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00c22-139">Describes generic classes that allow you to write provider-independent code in [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00c22-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="00c22-140">See Also</span></span>  
 [<span data-ttu-id="00c22-141">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="00c22-141">ADO.NET</span></span>](../../../../docs/framework/data/adonet/index.md)  
 [<span data-ttu-id="00c22-142">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="00c22-142">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
