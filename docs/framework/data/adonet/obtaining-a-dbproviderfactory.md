---
title: "DbProviderFactory 가져오기"
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
ms.assetid: a16e4a4d-6a5b-45db-8635-19570e4572ae
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: d230a122cbc02521c8d300d96cdd074bd7faa979
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="obtaining-a-dbproviderfactory"></a><span data-ttu-id="93d3a-102">DbProviderFactory 가져오기</span><span class="sxs-lookup"><span data-stu-id="93d3a-102">Obtaining a DbProviderFactory</span></span>
<span data-ttu-id="93d3a-103"><xref:System.Data.Common.DbProviderFactory>를 가져오는 프로세스에서는 데이터 공급자에 대한 정보가 <xref:System.Data.Common.DbProviderFactories> 클래스에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="93d3a-103">The process of obtaining a <xref:System.Data.Common.DbProviderFactory> involves passing information about a data provider to the <xref:System.Data.Common.DbProviderFactories> class.</span></span> <span data-ttu-id="93d3a-104"><xref:System.Data.Common.DbProviderFactories.GetFactory%2A> 메서드는 이 정보를 기반으로 하여 강력한 형식의 공급자 팩터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="93d3a-104">Based on this information, the <xref:System.Data.Common.DbProviderFactories.GetFactory%2A> method creates a strongly typed provider factory.</span></span> <span data-ttu-id="93d3a-105">예를 들어 <xref:System.Data.SqlClient.SqlClientFactory>를 만들려면 공급자 이름을 "System.Data.SqlClient"로 지정하는 문자열을 `GetFactory`에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="93d3a-105">For example, to create a <xref:System.Data.SqlClient.SqlClientFactory>, you can pass `GetFactory` a string with the provider name specified as "System.Data.SqlClient".</span></span> <span data-ttu-id="93d3a-106">`GetFactory`의 다른 오버로드는 <xref:System.Data.DataRow>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="93d3a-106">The other overload of `GetFactory` takes a <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="93d3a-107">공급자 팩터리를 만든 후에는 해당 메서드를 사용하여 다른 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93d3a-107">Once you create the provider factory, you can then use its methods to create additional objects.</span></span> <span data-ttu-id="93d3a-108">`SqlClientFactory`의 메서드로는 <xref:System.Data.SqlClient.SqlClientFactory.CreateConnection%2A>, <xref:System.Data.SqlClient.SqlClientFactory.CreateCommand%2A> 및 <xref:System.Data.SqlClient.SqlClientFactory.CreateDataAdapter%2A>가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93d3a-108">Some of the methods of a `SqlClientFactory` include <xref:System.Data.SqlClient.SqlClientFactory.CreateConnection%2A>, <xref:System.Data.SqlClient.SqlClientFactory.CreateCommand%2A>, and <xref:System.Data.SqlClient.SqlClientFactory.CreateDataAdapter%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93d3a-109">.NET Framework <xref:System.Data.OracleClient.OracleClientFactory>, <xref:System.Data.Odbc.OdbcFactory> 및 <xref:System.Data.OleDb.OleDbFactory> 클래스도 이와 유사한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="93d3a-109">The .NET Framework <xref:System.Data.OracleClient.OracleClientFactory>, <xref:System.Data.Odbc.OdbcFactory>, and <xref:System.Data.OleDb.OleDbFactory> classes also provide similar functionality.</span></span>  
  
## <a name="registering-dbproviderfactories"></a><span data-ttu-id="93d3a-110">DbProviderFactories 등록</span><span class="sxs-lookup"><span data-stu-id="93d3a-110">Registering DbProviderFactories</span></span>  
 <span data-ttu-id="93d3a-111">팩터리 기반의 클래스를 지 원하는 각.NET Framework 데이터 공급자에 대 한 구성 정보를 등록는 **DbProviderFactories** 의 섹션은 **machine.config** 로컬 컴퓨터의 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="93d3a-111">Each .NET Framework data provider that supports a factory-based class registers configuration information in the **DbProviderFactories** section of the **machine.config** file on the local computer.</span></span> <span data-ttu-id="93d3a-112">다음 구성 파일 조각에서는 <xref:System.Data.SqlClient>의 구문과 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="93d3a-112">The following configuration file fragment shows the syntax and format for <xref:System.Data.SqlClient>.</span></span>  
  
```xml  
<system.data>  
  <DbProviderFactories>  
    <add name="SqlClient Data Provider"  
     invariant="System.Data.SqlClient"   
     description=".Net Framework Data Provider for SqlServer"   
     type="System.Data.SqlClient.SqlClientFactory, System.Data,   
     Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
    />  
  </DbProviderFactories>  
</system.data>  
```  
  
 <span data-ttu-id="93d3a-113">**고정** 특성 기본 데이터 공급자를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="93d3a-113">The **invariant** attribute identifies the underlying data provider.</span></span> <span data-ttu-id="93d3a-114">세 부분으로 이루어진 이 명명 구문은 새 팩터리를 만들 때뿐만 아니라 공급자 이름 및 관련된 연결 문자열을 런타임에 검색할 수 있도록 응용 프로그램 구성 파일에서 공급자를 식별하는 데도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="93d3a-114">This three-part naming syntax is also used when creating a new factory and for identifying the provider in an application configuration file so that the provider name, along with its associated connection string, can be retrieved at run time.</span></span>  
  
## <a name="retrieving-provider-information"></a><span data-ttu-id="93d3a-115">공급자 정보 검색</span><span class="sxs-lookup"><span data-stu-id="93d3a-115">Retrieving Provider Information</span></span>  
 <span data-ttu-id="93d3a-116"><xref:System.Data.Common.DbProviderFactories.GetFactoryClasses%2A> 메서드를 사용하면 로컬 컴퓨터에 설치되어 있는 데이터 공급자에 대한 모든 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93d3a-116">You can retrieve information about all of the data providers installed on the local computer by using the <xref:System.Data.Common.DbProviderFactories.GetFactoryClasses%2A> method.</span></span> <span data-ttu-id="93d3a-117">반환 된 <xref:System.Data.DataTable> 라는 **DbProviderFactories** 다음 표에 설명 된 열을 포함 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="93d3a-117">It returns a <xref:System.Data.DataTable> named **DbProviderFactories** that contains the columns described in the following table.</span></span>  
  
|<span data-ttu-id="93d3a-118">열 서수</span><span class="sxs-lookup"><span data-stu-id="93d3a-118">Column ordinal</span></span>|<span data-ttu-id="93d3a-119">열 이름</span><span class="sxs-lookup"><span data-stu-id="93d3a-119">Column name</span></span>|<span data-ttu-id="93d3a-120">예제 출력</span><span class="sxs-lookup"><span data-stu-id="93d3a-120">Example output</span></span>|<span data-ttu-id="93d3a-121">설명</span><span class="sxs-lookup"><span data-stu-id="93d3a-121">Description</span></span>|  
|--------------------|-----------------|--------------------|-----------------|  
|<span data-ttu-id="93d3a-122">0</span><span class="sxs-lookup"><span data-stu-id="93d3a-122">0</span></span>|<span data-ttu-id="93d3a-123">**Name**</span><span class="sxs-lookup"><span data-stu-id="93d3a-123">**Name**</span></span>|<span data-ttu-id="93d3a-124">SqlClient Data Provider</span><span class="sxs-lookup"><span data-stu-id="93d3a-124">SqlClient Data Provider</span></span>|<span data-ttu-id="93d3a-125">읽을 수 있는 데이터 공급자 이름</span><span class="sxs-lookup"><span data-stu-id="93d3a-125">Readable name for the data provider</span></span>|  
|<span data-ttu-id="93d3a-126">1</span><span class="sxs-lookup"><span data-stu-id="93d3a-126">1</span></span>|<span data-ttu-id="93d3a-127">**설명**</span><span class="sxs-lookup"><span data-stu-id="93d3a-127">**Description**</span></span>|<span data-ttu-id="93d3a-128">.Net Framework Data Provider for SqlServer</span><span class="sxs-lookup"><span data-stu-id="93d3a-128">.Net Framework Data Provider for SqlServer</span></span>|<span data-ttu-id="93d3a-129">읽을 수 있는 데이터 공급자 설명</span><span class="sxs-lookup"><span data-stu-id="93d3a-129">Readable description of the data provider</span></span>|  
|<span data-ttu-id="93d3a-130">2</span><span class="sxs-lookup"><span data-stu-id="93d3a-130">2</span></span>|<span data-ttu-id="93d3a-131">**InvariantName**</span><span class="sxs-lookup"><span data-stu-id="93d3a-131">**InvariantName**</span></span>|<span data-ttu-id="93d3a-132">System.Data.SqlClient</span><span class="sxs-lookup"><span data-stu-id="93d3a-132">System.Data.SqlClient</span></span>|<span data-ttu-id="93d3a-133">데이터 공급자를 프로그래밍 방식으로 참조하는 데 사용할 수 있는 이름</span><span class="sxs-lookup"><span data-stu-id="93d3a-133">Name that can be used programmatically to refer to the data provider</span></span>|  
|<span data-ttu-id="93d3a-134">3</span><span class="sxs-lookup"><span data-stu-id="93d3a-134">3</span></span>|<span data-ttu-id="93d3a-135">**AssemblyQualifiedName**</span><span class="sxs-lookup"><span data-stu-id="93d3a-135">**AssemblyQualifiedName**</span></span>|<span data-ttu-id="93d3a-136">System.Data.SqlClient.SqlClientFactory, System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089</span><span class="sxs-lookup"><span data-stu-id="93d3a-136">System.Data.SqlClient.SqlClientFactory, System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089</span></span>|<span data-ttu-id="93d3a-137">개체를 인스턴스화하는 데 충분한 정보가 포함된 팩터리 클래스의 정규화된 이름</span><span class="sxs-lookup"><span data-stu-id="93d3a-137">Fully qualified name of the factory class, which contains enough information to instantiate the object</span></span>|  
  
 <span data-ttu-id="93d3a-138">이 `DataTable`을 사용하면 런타임에 사용자가 <xref:System.Data.DataRow>를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93d3a-138">This `DataTable` can be used to enable a user to select a <xref:System.Data.DataRow> at run time.</span></span> <span data-ttu-id="93d3a-139">그런 다음 선택한 `DataRow`를 <xref:System.Data.Common.DbProviderFactories.GetFactory%2A> 메서드에 전달하여 강력한 형식의 <xref:System.Data.Common.DbProviderFactory>를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93d3a-139">The selected `DataRow` can then be passed to the <xref:System.Data.Common.DbProviderFactories.GetFactory%2A> method to create a strongly typed <xref:System.Data.Common.DbProviderFactory>.</span></span> <span data-ttu-id="93d3a-140">선택한 <xref:System.Data.DataRow>를 `GetFactory` 메서드에 전달하면 원하는 `DbProviderFactory` 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93d3a-140">A selected <xref:System.Data.DataRow> can be passed to the `GetFactory` method to create the desired `DbProviderFactory` object.</span></span>  
  
## <a name="listing-the-installed-provider-factory-classes"></a><span data-ttu-id="93d3a-141">설치되어 있는 공급자 팩터리 클래스 나열</span><span class="sxs-lookup"><span data-stu-id="93d3a-141">Listing the Installed Provider Factory Classes</span></span>  
 <span data-ttu-id="93d3a-142">이 예제에서는 <xref:System.Data.Common.DbProviderFactories.GetFactoryClasses%2A> 메서드를 사용하여 설치되어 있는 공급자에 대한 정보가 포함된 <xref:System.Data.DataTable>을 반환하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="93d3a-142">This example demonstrates how to use the <xref:System.Data.Common.DbProviderFactories.GetFactoryClasses%2A> method to return a <xref:System.Data.DataTable> containing information about the installed providers.</span></span> <span data-ttu-id="93d3a-143">이 코드는 `DataTable`의 각 행을 반복하여 현재 설치되어 있는 각 공급자에 대한 정보를 콘솔 창에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="93d3a-143">The code iterates through each row in the `DataTable`, displaying information for each installed provider in the console window.</span></span>  
  
 [!code-csharp[DataWorks DbProviderFactories#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories/VB/source.vb#1)]  
  
## <a name="using-application-configuration-files-to-store-factory-information"></a><span data-ttu-id="93d3a-144">응용 프로그램 구성 파일을 사용하여 팩터리 정보 저장</span><span class="sxs-lookup"><span data-stu-id="93d3a-144">Using Application Configuration Files to Store Factory Information</span></span>  
 <span data-ttu-id="93d3a-145">팩터리로 작업에 사용 되는 디자인 패턴와 같은 응용 프로그램 구성 파일에서 공급자 및 연결 문자열 정보를 저장 하는 과정이 수반 됩니다 **app.config** Windows 응용 프로그램에 대 한 및 **web.config**  ASP.NET 응용 프로그램에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="93d3a-145">The design pattern used for working with factories entails storing provider and connection string information in an application configuration file, such as **app.config** for a Windows application, and **web.config** for an ASP.NET application.</span></span>  
  
 <span data-ttu-id="93d3a-146">다음 구성 파일 조각에서는 SQL Server에서 Northwind 데이터베이스에 연결하는 데 필요한 "NorthwindSQL" 및 Access/Jet에서 Northwind 데이터베이스에 연결하는 데 필요한 "NorthwindAccess"라는 두 가지 명명된 연결 문자열을 저장하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="93d3a-146">The following configuration file fragment demonstrates how to save two named connection strings, "NorthwindSQL" for a connection to the Northwind database in SQL Server, and "NorthwindAccess" for a connection to the Northwind database in Access/Jet.</span></span> <span data-ttu-id="93d3a-147">**고정** 이름에 사용 되는 **providerName** 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="93d3a-147">The **invariant** name is used for the **providerName** attribute.</span></span>  
  
```xml  
<configuration>  
  <connectionStrings>  
    <clear/>  
    <add name="NorthwindSQL"   
     providerName="System.Data.SqlClient"   
     connectionString=  
     "Data Source=MSSQL1;Initial Catalog=Northwind;Integrated Security=true"  
    />  
  
    <add name="NorthwindAccess"   
     providerName="System.Data.OleDb"   
     connectionString=  
     "Provider=Microsoft.Jet.OLEDB.4.0;Data Source=C:\Data\Northwind.mdb;"  
    />  
  </connectionStrings>  
</configuration>  
```  
  
### <a name="retrieving-a-connection-string-by-provider-name"></a><span data-ttu-id="93d3a-148">공급자 이름을 사용하여 연결 문자열 검색</span><span class="sxs-lookup"><span data-stu-id="93d3a-148">Retrieving a Connection String by Provider Name</span></span>  
 <span data-ttu-id="93d3a-149">공급자 팩터리를 만들려면 연결 문자열뿐만 아니라 공급자 이름도 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93d3a-149">In order to create a provider factory, you must supply a connection string as well as the provider name.</span></span> <span data-ttu-id="93d3a-150">고정 형식으로 공급자 이름을 전달 하 여 응용 프로그램 구성 파일에서 연결 문자열을 검색 하는 방법을 보여 주는이 예제 "*System.Data.ProviderName*"입니다.</span><span class="sxs-lookup"><span data-stu-id="93d3a-150">This example demonstrates how to retrieve a connection string from an application configuration file by passing the provider name in the invariant format "*System.Data.ProviderName*".</span></span> <span data-ttu-id="93d3a-151">이 코드는 <xref:System.Configuration.ConnectionStringSettingsCollection>을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="93d3a-151">The code iterates through the <xref:System.Configuration.ConnectionStringSettingsCollection>.</span></span> <span data-ttu-id="93d3a-152">메서드가 성공하면 <xref:System.Configuration.ConnectionStringSettings.ProviderName%2A>이 반환되고, 그렇지 않으면 `null`(Visual Basic의 경우에는 `Nothing`)이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="93d3a-152">It returns the <xref:System.Configuration.ConnectionStringSettings.ProviderName%2A> on success; otherwise `null` (`Nothing` in Visual Basic).</span></span> <span data-ttu-id="93d3a-153">공급자에 대한 항목이 여러 개 있으면 응용 프로그램 구성 파일에서 찾은 첫 번째 항목이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="93d3a-153">If there are multiple entries for a provider, the first one found is returned.</span></span> <span data-ttu-id="93d3a-154">자세한 내용과 예제 구성 파일에서 연결 문자열을 검색 하는 참조 [연결 문자열 및 구성 파일](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="93d3a-154">For more information and examples of retrieving connection strings from configuration files, see [Connection Strings and Configuration Files](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93d3a-155">코드를 실행하려면 `System.Configuration.dll`에 대한 참조가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="93d3a-155">A reference to `System.Configuration.dll` is required in order for the code to run.</span></span>  
  
 [!code-csharp[DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider/VB/source.vb#1)]  
  
## <a name="creating-the-dbproviderfactory-and-dbconnection"></a><span data-ttu-id="93d3a-156">DbProviderFactory 및 DbConnection 만들기</span><span class="sxs-lookup"><span data-stu-id="93d3a-156">Creating the DbProviderFactory and DbConnection</span></span>  
 <span data-ttu-id="93d3a-157">만드는 방법을 보여 주는이 예제는 <xref:System.Data.Common.DbProviderFactory> 및 <xref:System.Data.Common.DbConnection> 형식에서 공급자 이름을 전달 하 여 "*System.Data.ProviderName*" 및 연결 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="93d3a-157">This example demonstrates how to create a <xref:System.Data.Common.DbProviderFactory> and <xref:System.Data.Common.DbConnection> object by passing it the provider name in the format "*System.Data.ProviderName*" and a connection string.</span></span> <span data-ttu-id="93d3a-158">메서드가 성공하면 `DbConnection` 개체가 반환되고, 오류가 발생하면 `null` (Visual Basic의 경우에는 `Nothing`)이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="93d3a-158">A `DbConnection` object is returned on success; `null` (`Nothing` in Visual Basic) on any error.</span></span>  
  
 <span data-ttu-id="93d3a-159">이 코드는 `DbProviderFactory`를 호출하여 <xref:System.Data.Common.DbProviderFactories.GetFactory%2A>를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="93d3a-159">The code obtains the `DbProviderFactory` by calling <xref:System.Data.Common.DbProviderFactories.GetFactory%2A>.</span></span> <span data-ttu-id="93d3a-160">그러면 <xref:System.Data.Common.DbProviderFactory.CreateConnection%2A> 메서드가 <xref:System.Data.Common.DbConnection> 개체를 만들고 <xref:System.Data.Common.DbConnection.ConnectionString%2A> 속성이 연결 문자열에 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="93d3a-160">Then the <xref:System.Data.Common.DbProviderFactory.CreateConnection%2A> method creates the <xref:System.Data.Common.DbConnection> object and the <xref:System.Data.Common.DbConnection.ConnectionString%2A> property is set to the connection string.</span></span>  
  
 [!code-csharp[DataWorks DbProviderFactories.GetFactory#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.GetFactory/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.GetFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.GetFactory/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="93d3a-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="93d3a-161">See Also</span></span>  
 [<span data-ttu-id="93d3a-162">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="93d3a-162">DbProviderFactories</span></span>](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 [<span data-ttu-id="93d3a-163">연결 문자열</span><span class="sxs-lookup"><span data-stu-id="93d3a-163">Connection Strings</span></span>](../../../../docs/framework/data/adonet/connection-strings.md)  
 [<span data-ttu-id="93d3a-164">구성 클래스를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="93d3a-164">Using the Configuration Classes</span></span>](http://msdn.microsoft.com/library/98d2b386-baf6-4a17-974b-76e3b4c87acc)  
 [<span data-ttu-id="93d3a-165">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="93d3a-165">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
