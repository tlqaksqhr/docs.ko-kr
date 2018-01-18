---
title: "DataSet, DataTable 및 DataView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6d4c4b69-8919-4224-8a65-6cca1c61b48f
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: fb8cf2c9f763ea32bb7c7907111fea80e542a7f7
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="datasets-datatables-and-dataviews"></a><span data-ttu-id="6ad02-102">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="6ad02-102">DataSets, DataTables, and DataViews</span></span>
<span data-ttu-id="6ad02-103">ADO.NET <xref:System.Data.DataSet>은 포함된 데이터 소스에 관계없이 일관성 있는 관계형 프로그래밍 모델을 제공하는 데이터의 메모리 상주 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="6ad02-103">The ADO.NET <xref:System.Data.DataSet> is a memory-resident representation of data that provides a consistent relational programming model regardless of the source of the data it contains.</span></span> <span data-ttu-id="6ad02-104"><xref:System.Data.DataSet>은 데이터를 포함하고 제약하며 데이터의 순서를 지정하는 테이블과 각 테이블 간의 관계를 포함하는 데이터의 완전한 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6ad02-104">A <xref:System.Data.DataSet> represents a complete set of data including the tables that contain, order, and constrain the data, as well as the relationships between the tables.</span></span>  
  
 <span data-ttu-id="6ad02-105"><xref:System.Data.DataSet>을 사용하는 방법은 여러 가지가 있으며, 각 방법은 독립적으로 또는 조합하여 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ad02-105">There are several ways of working with a <xref:System.Data.DataSet>, which can be applied independently or in combination.</span></span> <span data-ttu-id="6ad02-106">다음과 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ad02-106">You can:</span></span>  
  
-   <span data-ttu-id="6ad02-107"><xref:System.Data.DataTable> 내에 프로그래밍 방식으로 <xref:System.Data.DataRelation>, <xref:System.Data.Constraint> 및 <xref:System.Data.DataSet>를 만들고 각 테이블을 데이터로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="6ad02-107">Programmatically create a <xref:System.Data.DataTable>, <xref:System.Data.DataRelation>, and <xref:System.Data.Constraint> within a <xref:System.Data.DataSet> and populate the tables with data.</span></span>  
  
-   <span data-ttu-id="6ad02-108"><xref:System.Data.DataSet>를 사용하여 기존 관계형 데이터 소스의 데이터 테이블로 `DataAdapter`을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="6ad02-108">Populate the <xref:System.Data.DataSet> with tables of data from an existing relational data source using a `DataAdapter`.</span></span>  
  
-   <span data-ttu-id="6ad02-109">XML을 사용하여 <xref:System.Data.DataSet> 내용을 로드하고 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad02-109">Load and persist the <xref:System.Data.DataSet> contents using XML.</span></span> <span data-ttu-id="6ad02-110">자세한 내용은 [데이터 집합에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ad02-110">For more information, see [Using XML in a DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).</span></span>  
  
 <span data-ttu-id="6ad02-111">또한 XML Web services를 사용하여 강력한 형식의 <xref:System.Data.DataSet>을 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ad02-111">A strongly typed <xref:System.Data.DataSet> can also be transported using an XML Web service.</span></span> <span data-ttu-id="6ad02-112"><xref:System.Data.DataSet>의 디자인은 XML Web services를 사용하는 데이터 전송에 가장 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad02-112">The design of the <xref:System.Data.DataSet> makes it ideal for transporting data using XML Web services.</span></span> <span data-ttu-id="6ad02-113">XML Web services에 대한 개요는 [XML Web services 개요](http://msdn.microsoft.com/en-us/9db0c7b8-bca6-462b-9be5-f5f9a7f05a4d)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ad02-113">For an overview of XML Web services, see [XML Web Services Overview](http://msdn.microsoft.com/en-us/9db0c7b8-bca6-462b-9be5-f5f9a7f05a4d).</span></span> <span data-ttu-id="6ad02-114">XML Web services에서 <xref:System.Data.DataSet>를 사용하는 예제는 [Consuming a DataSet from an XML Web Service](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/consuming-a-dataset-from-an-xml-web-service.md)(XML Web services에서 데이터 집합 사용)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ad02-114">For an example of consuming a <xref:System.Data.DataSet> from an XML Web service, see [Consuming a DataSet from an XML Web Service](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/consuming-a-dataset-from-an-xml-web-service.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6ad02-115">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="6ad02-115">In This Section</span></span>  
 [<span data-ttu-id="6ad02-116">데이터 집합 만들기</span><span class="sxs-lookup"><span data-stu-id="6ad02-116">Creating a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-dataset.md)  
 <span data-ttu-id="6ad02-117"><xref:System.Data.DataSet>의 인스턴스를 만들기 위한 구문에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad02-117">Describes the syntax for creating an instance of a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="6ad02-118">데이터 집합에 DataTable 추가</span><span class="sxs-lookup"><span data-stu-id="6ad02-118">Adding a DataTable to a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-a-datatable-to-a-dataset.md)  
 <span data-ttu-id="6ad02-119">테이블과 열을 만들어 <xref:System.Data.DataSet>에 추가하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad02-119">Describes how to create and add tables and columns to a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="6ad02-120">DataRelation 추가</span><span class="sxs-lookup"><span data-stu-id="6ad02-120">Adding DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)  
 <span data-ttu-id="6ad02-121"><xref:System.Data.DataSet>에 있는 테이블 사이의 관계를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad02-121">Describes how to create relations between tables in a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="6ad02-122">DataRelation 탐색</span><span class="sxs-lookup"><span data-stu-id="6ad02-122">Navigating DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datarelations.md)  
 <span data-ttu-id="6ad02-123"><xref:System.Data.DataSet>에 있는 테이블 사이의 관계를 사용하여 부모-자식 관계의 자식 또는 부모 행을 반환하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad02-123">Describes how to use the relations between tables in a <xref:System.Data.DataSet> to return the child or parent rows of a parent-child relationship.</span></span>  
  
 [<span data-ttu-id="6ad02-124">데이터 집합 콘텐츠 병합</span><span class="sxs-lookup"><span data-stu-id="6ad02-124">Merging DataSet Contents</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/merging-dataset-contents.md)  
 <span data-ttu-id="6ad02-125">하나의 <xref:System.Data.DataSet>, <xref:System.Data.DataTable> 또는 <xref:System.Data.DataRow> 배열의 내용을 다른 <xref:System.Data.DataSet>으로 병합하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad02-125">Describes how to merge the contents of one <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, or <xref:System.Data.DataRow> array into another <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="6ad02-126">데이터 집합 콘텐츠 복사</span><span class="sxs-lookup"><span data-stu-id="6ad02-126">Copying DataSet Contents</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/copying-dataset-contents.md)  
 <span data-ttu-id="6ad02-127">스키마 및 지정한 데이터를 포함하는 <xref:System.Data.DataSet>의 복사본을 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad02-127">Describes how to create a copy of a <xref:System.Data.DataSet> that can contain schema as well as specified data.</span></span>  
  
 [<span data-ttu-id="6ad02-128">데이터 집합 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="6ad02-128">Handling DataSet Events</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-dataset-events.md)  
 <span data-ttu-id="6ad02-129"><xref:System.Data.DataSet>의 이벤트와 해당 이벤트를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad02-129">Describes the events of a <xref:System.Data.DataSet> and how to use them.</span></span>  
  
 [<span data-ttu-id="6ad02-130">형식화된 데이터 집합</span><span class="sxs-lookup"><span data-stu-id="6ad02-130">Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 <span data-ttu-id="6ad02-131">형식화된 <xref:System.Data.DataSet>의 정의와 이를 만들어 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad02-131">Discusses what a typed <xref:System.Data.DataSet> is and how to create and use it.</span></span>  
  
 [<span data-ttu-id="6ad02-132">DataTable</span><span class="sxs-lookup"><span data-stu-id="6ad02-132">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 <span data-ttu-id="6ad02-133"><xref:System.Data.DataTable>을 만들고 스키마를 정의하며 데이터를 조작하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad02-133">Describes how to create a <xref:System.Data.DataTable>, define the schema, and manipulate data.</span></span>  
  
 [<span data-ttu-id="6ad02-134">DataTableReader</span><span class="sxs-lookup"><span data-stu-id="6ad02-134">DataTableReaders</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)  
 <span data-ttu-id="6ad02-135"><xref:System.Data.DataTableReader>를 만들고 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad02-135">Describes how to create and use a <xref:System.Data.DataTableReader>.</span></span>  
  
 [<span data-ttu-id="6ad02-136">DataView</span><span class="sxs-lookup"><span data-stu-id="6ad02-136">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 <span data-ttu-id="6ad02-137">`DataViews`를 만들고 작업하는 방법과 <xref:System.Data.DataView> 이벤트를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad02-137">Describes how to create and work with `DataViews` and work with <xref:System.Data.DataView> events.</span></span>  
  
 [<span data-ttu-id="6ad02-138">데이터 집합에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="6ad02-138">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 <span data-ttu-id="6ad02-139"><xref:System.Data.DataSet>의 내용을 로드하여 XML 데이터로 유지하는 것을 포함하여 <xref:System.Data.DataSet>이 데이터 소스로서 XML과 상호 작용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad02-139">Describes how the <xref:System.Data.DataSet> interacts with XML as a data source, including loading and persisting the contents of a <xref:System.Data.DataSet> as XML data.</span></span>  
  
 [<span data-ttu-id="6ad02-140">XML Web services에서 데이터 집합 사용</span><span class="sxs-lookup"><span data-stu-id="6ad02-140">Consuming a DataSet from an XML Web Service</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/consuming-a-dataset-from-an-xml-web-service.md)  
 <span data-ttu-id="6ad02-141"><xref:System.Data.DataSet>을 사용하여 데이터를 전송하는 XML Web services를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad02-141">Describes how to create an XML Web service that uses a <xref:System.Data.DataSet> to transport data.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6ad02-142">관련 단원</span><span class="sxs-lookup"><span data-stu-id="6ad02-142">Related Sections</span></span>  
 [<span data-ttu-id="6ad02-143">ADO.NET의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="6ad02-143">What's New in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/whats-new.md)  
 <span data-ttu-id="6ad02-144">ADO.NET에 새로 추가된 기능을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad02-144">Introduces features that are new in ADO.NET.</span></span>  
  
 [<span data-ttu-id="6ad02-145">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="6ad02-145">ADO.NET Overview</span></span>](../../../../../docs/framework/data/adonet/ado-net-overview.md)  
 <span data-ttu-id="6ad02-146">ADO.NET의 디자인 및 구성 요소에 대해 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad02-146">Provides an introduction to the design and components of ADO.NET.</span></span>  
  
 [<span data-ttu-id="6ad02-147">DataAdapter에서 데이터 집합 채우기</span><span class="sxs-lookup"><span data-stu-id="6ad02-147">Populating a DataSet from a DataAdapter</span></span>](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 <span data-ttu-id="6ad02-148">데이터 원본의 데이터가 있는 **데이터 집합**을 로드하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad02-148">Describes how to load a **DataSet** with data from a data source.</span></span>  
  
 [<span data-ttu-id="6ad02-149">DataAdapter로 데이터 원본 업데이트</span><span class="sxs-lookup"><span data-stu-id="6ad02-149">Updating Data Sources with DataAdapters</span></span>](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 <span data-ttu-id="6ad02-150">**데이터 집합**의 데이터에 대한 변경 사항을 다시 데이터 원본에 적용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad02-150">Describes how to resolve changes to the data in a **DataSet** back to the data source.</span></span>  
  
 [<span data-ttu-id="6ad02-151">데이터 집합에 기존 제약 조건 추가</span><span class="sxs-lookup"><span data-stu-id="6ad02-151">Adding Existing Constraints to a DataSet</span></span>](../../../../../docs/framework/data/adonet/adding-existing-constraints-to-a-dataset.md)  
 <span data-ttu-id="6ad02-152">데이터 원본의 기본 키 정보로 **데이터 집합**을 채우는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad02-152">Describes how to populate a **DataSet** with primary key information from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ad02-153">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6ad02-153">See Also</span></span>  
 [<span data-ttu-id="6ad02-154">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6ad02-154">ADO.NET</span></span>](../../../../../docs/framework/data/adonet/index.md)  
 [<span data-ttu-id="6ad02-155">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="6ad02-155">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
