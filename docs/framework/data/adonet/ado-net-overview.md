---
title: "ADO.NET 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ee3bc1d8-11db-4be4-89eb-c708cf04117d
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: ae25f03a091d3a9705a2e445fec948d8c5e15e0f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="adonet-overview"></a><span data-ttu-id="648e7-102">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="648e7-102">ADO.NET Overview</span></span>
<span data-ttu-id="648e7-103">ADO.NET은 OLE DB 및 ODBC를 통해 노출되는 데이터 소스, SQL Server 및 XML과 같은 데이터 소스에 대한 일관성 있는 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="648e7-103">ADO.NET provides consistent access to data sources such as SQL Server and XML, and to data sources exposed through OLE DB and ODBC.</span></span> <span data-ttu-id="648e7-104">데이터 공유 소비자 응용 프로그램은 ADO.NET을 통해 이러한 데이터 소스에 연결하여 포함된 데이터를 검색, 처리 및 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="648e7-104">Data-sharing consumer applications can use ADO.NET to connect to these data sources and retrieve, handle, and update the data that they contain.</span></span>  
  
 <span data-ttu-id="648e7-105">ADO.NET은 데이터 조작에 따른 데이터 액세스를 각각의 구성 요소로 구분하여 개별적으로 또는 차례대로 사용할 수 있게 해 줍니다.</span><span class="sxs-lookup"><span data-stu-id="648e7-105">ADO.NET separates data access from data manipulation into discrete components that can be used separately or in tandem.</span></span> <span data-ttu-id="648e7-106">ADO.NET에는 데이터베이스에 연결하고 명령을 실행하며 결과를 검색하는 데 사용되는 .NET Framework 데이터 공급자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="648e7-106">ADO.NET includes .NET Framework data providers for connecting to a database, executing commands, and retrieving results.</span></span> <span data-ttu-id="648e7-107">검색된 결과는 곧바로 처리되거나 ADO.NET <xref:System.Data.DataSet> 개체에 저장되어 특별한 방식으로 사용자에게 노출되거나 여러 소스의 데이터와 함께 사용되거나 계층 간에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="648e7-107">Those results are either processed directly, placed in an ADO.NET <xref:System.Data.DataSet> object in order to be exposed to the user in an ad hoc manner, combined with data from multiple sources, or passed between tiers.</span></span> <span data-ttu-id="648e7-108">`DataSet` 개체는 또한 .NET Framework 데이터 공급자를 독립적으로 사용하여 응용 프로그램에 로컬인 데이터 또는 XML에서 가져온 데이터를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="648e7-108">The `DataSet` object can also be used independently of a .NET Framework data provider to manage data local to the application or sourced from XML.</span></span>  
  
 <span data-ttu-id="648e7-109">ADO.NET 클래스는 System.Data.dll에 있으며 System.Xml.dll에 있는 XML 클래스와 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="648e7-109">The ADO.NET classes are found in System.Data.dll, and are integrated with the XML classes found in System.Xml.dll.</span></span> <span data-ttu-id="648e7-110">데이터베이스에 연결 하는 샘플 코드에서 데이터를 검색 및 콘솔 창에 해당 데이터를 표시 한 참조 [ADO.NET 코드 예제에서는](../../../../docs/framework/data/adonet/ado-net-code-examples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="648e7-110">For sample code that connects to a database, retrieves data from it, and then displays that data in a console window, see [ADO.NET Code Examples](../../../../docs/framework/data/adonet/ado-net-code-examples.md).</span></span>  
  
 <span data-ttu-id="648e7-111">ADO.NET은 관리 코드를 작성하는 개발자에게 ADO(ActiveX Data Objects)에서 네이티브 COM(Component Object Model) 개발자를 대상으로 제공하는 기능과 유사한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="648e7-111">ADO.NET provides functionality to developers who write managed code similar to the functionality provided to native component object model (COM) developers by ActiveX Data Objects (ADO).</span></span> <span data-ttu-id="648e7-112">.NET 응용 프로그램에서 데이터에 액세스할 때 ADO가 아니라 ADO.NET을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="648e7-112">We recommend that you use ADO.NET, not ADO, for accessing data in your .NET applications.</span></span>  
  
 <span data-ttu-id="648e7-113">ADO.NET은 .NET Framework 내에서 가장 직접적인 데이터 액세스 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="648e7-113">ADO.NET provides the most direct method of data access within the .NET Framework.</span></span> <span data-ttu-id="648e7-114">응용 프로그램의 기본 저장소 모델 대신 개념적 모델에 대해 작동 하는 데 더 높은 수준의 추상화에 대 한 참조는 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="648e7-114">For a higher-level abstraction that allows applications to work against a conceptual model instead of the underlying storage model, see the [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md).</span></span>  
  
 <span data-ttu-id="648e7-115">**개인정보취급방침**: System.Data.dll, System.Data.Design.dll, System.Data.OracleClient.dll, System.Data.SqlXml.dll, System.Data.Linq.dll, System.Data.SqlServerCe.dll 및 System.Data.DataSetExtensions.dll 어셈블리는 그렇지 않습니다 사용자의 개인 데이터와 private이 아닌 데이터를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="648e7-115">**Privacy Statement**: The System.Data.dll, System.Data.Design.dll, System.Data.OracleClient.dll, System.Data.SqlXml.dll, System.Data.Linq.dll, System.Data.SqlServerCe.dll, and System.Data.DataSetExtensions.dll assemblies do not distinguish between a user's private data and non-private data.</span></span>  <span data-ttu-id="648e7-116">이러한 어셈블리는 사용자의 개인 데이터를 수집, 저장 및 전송하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="648e7-116">These assemblies do not collect, store, or transport any user's private data.</span></span> <span data-ttu-id="648e7-117">하지만 타사 응용 프로그램에서 이러한 어셈블리를 사용하여 사용자의 개인 데이터를 수집, 저장 및 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="648e7-117">However, third-party applications might collect, store, or transport a user's private data using these assemblies.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="648e7-118">단원 내용</span><span class="sxs-lookup"><span data-stu-id="648e7-118">In This Section</span></span>  
 [<span data-ttu-id="648e7-119">ADO.NET 아키텍처</span><span class="sxs-lookup"><span data-stu-id="648e7-119">ADO.NET Architecture</span></span>](../../../../docs/framework/data/adonet/ado-net-architecture.md)  
 <span data-ttu-id="648e7-120">ADO.NET의 구조와 구성 요소에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="648e7-120">Provides an overview of the architecture and components of ADO.NET.</span></span>  
  
 [<span data-ttu-id="648e7-121">ADO.NET 기술 옵션 및 지침</span><span class="sxs-lookup"><span data-stu-id="648e7-121">ADO.NET Technology Options and Guidelines</span></span>](../../../../docs/framework/data/adonet/ado-net-technology-options-and-guidelines.md)  
 <span data-ttu-id="648e7-122">엔터티 데이터 플랫폼에 포함된 제품과 기술에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="648e7-122">Describes the products and technologies included with the Entity Data Platform.</span></span>  
  
 [<span data-ttu-id="648e7-123">LINQ 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="648e7-123">LINQ and ADO.NET</span></span>](../../../../docs/framework/data/adonet/linq-and-ado-net.md)  
 <span data-ttu-id="648e7-124">LINQ(Language-Integrated Query)가 ADO.NET에 어떻게 구현되었는지 설명하고 관련 항목에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="648e7-124">Describes how Language-Integrated Query (LINQ) is implemented in ADO.NET and provides links to relevant topics.</span></span>  
  
 [<span data-ttu-id="648e7-125">.NET framework 데이터 공급자</span><span class="sxs-lookup"><span data-stu-id="648e7-125">.NET Framework Data Providers</span></span>](../../../../docs/framework/data/adonet/data-providers.md)  
 <span data-ttu-id="648e7-126">ADO.NET에 포함된 하나 이상의 .NET Framework 데이터 공급자에 대한 디자인 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="648e7-126">Provides an overview of the design of the .NET Framework data provider and of the .NET Framework data providers that are included with ADO.NET.</span></span>  
  
 [<span data-ttu-id="648e7-127">ADO.NET 데이터 집합</span><span class="sxs-lookup"><span data-stu-id="648e7-127">ADO.NET DataSets</span></span>](../../../../docs/framework/data/adonet/ado-net-datasets.md)  
 <span data-ttu-id="648e7-128">`DataSet` 디자인 및 구성 요소의 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="648e7-128">Provides an overview of the `DataSet` design and components.</span></span>  
  
 [<span data-ttu-id="648e7-129">ADO.NET에서 Side-by-side-실행</span><span class="sxs-lookup"><span data-stu-id="648e7-129">Side-by-Side Execution in ADO.NET</span></span>](../../../../docs/framework/data/adonet/side-by-side-execution.md)  
 <span data-ttu-id="648e7-130">ADO.NET 버전의 차이를 설명하고 이 차이가 side-by-side 실행 및 응용 프로그램 호환성에 미치는 영향에 대해 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="648e7-130">Discusses differences in ADO.NET versions and their effect on side-by-side execution and application compatibility.</span></span>  
  
 [<span data-ttu-id="648e7-131">ADO.NET 코드 예제</span><span class="sxs-lookup"><span data-stu-id="648e7-131">ADO.NET Code Examples</span></span>](../../../../docs/framework/data/adonet/ado-net-code-examples.md)  
 <span data-ttu-id="648e7-132">ADO.NET 데이터 공급자를 사용하여 데이터를 검색하는 코드 샘플을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="648e7-132">Provides code samples that retrieve data using the ADO.NET data providers.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="648e7-133">관련 단원</span><span class="sxs-lookup"><span data-stu-id="648e7-133">Related Sections</span></span>  
 [<span data-ttu-id="648e7-134">ADO.NET의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="648e7-134">What's New in ADO.NET</span></span>](../../../../docs/framework/data/adonet/whats-new.md)  
 <span data-ttu-id="648e7-135">[!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]에 새로 추가된 기능을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="648e7-135">Introduces features that are new in [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].</span></span>  
  
 [<span data-ttu-id="648e7-136">ADO.NET 응용 프로그램 보안</span><span class="sxs-lookup"><span data-stu-id="648e7-136">Securing ADO.NET Applications</span></span>](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 <span data-ttu-id="648e7-137">ADO.NET을 사용할 때 보안 코드를 작성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="648e7-137">Describes secure coding practices when using ADO.NET.</span></span>  
  
 [<span data-ttu-id="648e7-138">ADO.NET에서 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="648e7-138">Data Type Mappings in ADO.NET</span></span>](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)  
 <span data-ttu-id="648e7-139">.NET Framework 데이터 형식과 .NET Framework 데이터 공급자 간의 데이터 형식 매핑에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="648e7-139">Describes data type mappings between .NET Framework data types and the .NET Framework data providers.</span></span>  
  
 [<span data-ttu-id="648e7-140">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="648e7-140">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 <span data-ttu-id="648e7-141">데이터 소스에 연결하고, 데이터를 검색하고, 데이터를 수정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="648e7-141">Describes how to connect to a data source, retrieve data, and modify data.</span></span> <span data-ttu-id="648e7-142">여기에는 `DataReaders` 및 `DataAdapters`가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="648e7-142">This includes `DataReaders` and `DataAdapters`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="648e7-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="648e7-143">See Also</span></span>  
 [<span data-ttu-id="648e7-144">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="648e7-144">ADO.NET</span></span>](../../../../docs/framework/data/adonet/index.md)  
 [<span data-ttu-id="648e7-145">Visual Studio에서 데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="648e7-145">Accessing data in Visual Studio</span></span>](/visualstudio/data-tools/accessing-data-in-visual-studio)  
 [<span data-ttu-id="648e7-146">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="648e7-146">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
