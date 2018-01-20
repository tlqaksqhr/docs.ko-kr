---
title: "데이터 보기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0fe5dfa2-c1cd-435f-90b6-b4dd2e3ef34b
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 5b79461a6fc3314ca4178e0f9b1cff1c468cc3e6
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="dataviews"></a><span data-ttu-id="ac506-102">데이터 보기</span><span class="sxs-lookup"><span data-stu-id="ac506-102">DataViews</span></span>
<span data-ttu-id="ac506-103"><xref:System.Data.DataView>는 데이터 바인딩 응용 프로그램에서 자주 사용되는 기능으로, 이 기능을 사용하면 <xref:System.Data.DataTable>에 저장되어 있는 데이터에 대해 서로 다른 뷰를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac506-103">A <xref:System.Data.DataView> enables you to create different views of the data stored in a <xref:System.Data.DataTable>, a capability that is often used in data-binding applications.</span></span> <span data-ttu-id="ac506-104">사용 하는 **DataView**를 여러 정렬 순서로 테이블의 데이터를 노출할 수 있습니다 및 행 상태 또는 필터 식을 기준으로 데이터를 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac506-104">Using a **DataView**, you can expose the data in a table with different sort orders, and you can filter the data by row state or based on a filter expression.</span></span>  
  
 <span data-ttu-id="ac506-105">A **DataView** 제공 데이터 원본에 대 한 동적 뷰 **DataTable**: 콘텐츠, 정렬 및 구성원 나타나는 순서 대로 변경 내용을 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac506-105">A **DataView** provides a dynamic view of data in the underlying **DataTable**: the content, ordering, and membership reflect changes as they occur.</span></span> <span data-ttu-id="ac506-106">이 동작은에서 **선택** 의 메서드는 **DataTable**, 반환 하는 <xref:System.Data.DataRow> 배열 테이블에서 특정 필터 및/또는 정렬 순서에 따라: thiscontent 변경 내용이 반영 되는 기본 테이블을 하지만 해당 멤버 및 순서 지정 정적인 상태로 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac506-106">This behavior differs from the **Select** method of the **DataTable**, which returns a <xref:System.Data.DataRow> array from a table based on a particular filter and/or sort order: thiscontent reflects changes to the underlying table, but its membership and ordering remain static.</span></span> <span data-ttu-id="ac506-107">동적 기능은 **DataView** 데이터 바인딩 응용 프로그램에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac506-107">The dynamic capabilities of the **DataView** make it ideal for data-binding applications.</span></span>  
  
 <span data-ttu-id="ac506-108">A **DataView** 단일 집합이 있는 여러 가지 정렬 및 필터링 기준을 적용할 수 있습니다는 데이터베이스 뷰와 매우 유사 하 게 데이터에 대 한 동적 뷰를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac506-108">A **DataView** provides you with a dynamic view of a single set of data, much like a database view, to which you can apply different sorting and filtering criteria.</span></span> <span data-ttu-id="ac506-109">그러나 데이터베이스 뷰와 달리는 **DataView** 테이블로 취급 될 수 없고 및 조인 된 테이블의 뷰를 제공할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ac506-109">Unlike a database view, however, a **DataView** cannot be treated as a table and cannot provide a view of joined tables.</span></span> <span data-ttu-id="ac506-110">또한 소스 테이블에 있는 열을 제외하거나 계산을 통해 만들어지는 열과 같이 소스 테이블에 없는 열을 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ac506-110">You also cannot exclude columns that exist in the source table, nor can you append columns, such as computational columns, that do not exist in the source table.</span></span>  
  
 <span data-ttu-id="ac506-111">사용할 수 있습니다는 <xref:System.Data.DataView.DataViewManager%2A> 에 있는 모든 테이블에 대 한 뷰 설정을 관리할 수는 **DataSet**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac506-111">You can use a <xref:System.Data.DataView.DataViewManager%2A> to manage view settings for all the tables in a **DataSet**.</span></span> <span data-ttu-id="ac506-112">**DataViewManager** 각 테이블에 대 한 기본 뷰 설정을 관리할 수 있는 편리한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac506-112">The **DataViewManager** provides you with a convenient way to manage default view settings for each table.</span></span> <span data-ttu-id="ac506-113">컨트롤의 둘 이상의 테이블을 바인딩하는 경우는 **DataSet**바인딩할는 **DataViewManager** 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ac506-113">When binding a control to more than one table of a **DataSet**, binding to a **DataViewManager** is the ideal choice.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ac506-114">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="ac506-114">In This Section</span></span>  
 [<span data-ttu-id="ac506-115">DataView 만들기</span><span class="sxs-lookup"><span data-stu-id="ac506-115">Creating a DataView</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-dataview.md)  
 <span data-ttu-id="ac506-116">만드는 방법에 설명 된 **DataView** 에 대 한는 **DataTable**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac506-116">Describes how to create a **DataView** for a **DataTable**.</span></span>  
  
 [<span data-ttu-id="ac506-117">데이터 정렬 및 필터링</span><span class="sxs-lookup"><span data-stu-id="ac506-117">Sorting and Filtering Data</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)  
 <span data-ttu-id="ac506-118">속성을 설정 하는 방법에 설명 된 **DataView** 특정 정렬 순서로 데이터를 반환 하거나 특정 필터 조건에 맞는 데이터 행의 하위 집합을 반환 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac506-118">Describes how to set the properties of a **DataView** to return subsets of data rows meeting specific filter criteria, or to return data in a particular sort order.</span></span>  
  
 [<span data-ttu-id="ac506-119">DataRow 및 DataRowView</span><span class="sxs-lookup"><span data-stu-id="ac506-119">DataRows and DataRowViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datarows-and-datarowviews.md)  
 <span data-ttu-id="ac506-120">에 의해 노출 된 데이터에 액세스 하는 방법에 설명 된 **DataView**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac506-120">Describes how to access the data exposed by the **DataView**.</span></span>  
  
 [<span data-ttu-id="ac506-121">행 찾기</span><span class="sxs-lookup"><span data-stu-id="ac506-121">Finding Rows</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md)  
 <span data-ttu-id="ac506-122">특정 행을 확인 하는 방법에 설명 된 **DataView**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac506-122">Describes how to find a particular row in a **DataView**.</span></span>  
  
 [<span data-ttu-id="ac506-123">ChildView 및 관계</span><span class="sxs-lookup"><span data-stu-id="ac506-123">ChildViews and Relations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/childviews-and-relations.md)  
 <span data-ttu-id="ac506-124">사용 하 여 부모-자식 관계에서 데이터의 뷰를 만드는 방법에 설명 된 **DataView**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac506-124">Describes how to create views of data from a parent-child relationship using a **DataView**.</span></span>  
  
 [<span data-ttu-id="ac506-125">데이터 보기 수정</span><span class="sxs-lookup"><span data-stu-id="ac506-125">Modifying DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/modifying-dataviews.md)  
 <span data-ttu-id="ac506-126">내부에서 데이터를 수정 하는 방법을 설명 **DataTable** 통해는 **DataView**, 업데이트 활성화 또는 비활성화를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac506-126">Describes how to modify the data in the underlying **DataTable** via the **DataView**, including enabling or disabling updates.</span></span>  
  
 [<span data-ttu-id="ac506-127">DataView 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="ac506-127">Handling DataView Events</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-dataview-events.md)  
 <span data-ttu-id="ac506-128">사용 하는 방법에 설명는 **ListChanged** 이벤트 알림을 받을 때 내용 또는 순서가 **DataView** 업데이트 되 고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac506-128">Describes how to use the **ListChanged** event to receive notification when the contents or order of a **DataView** is being updated.</span></span>  
  
 [<span data-ttu-id="ac506-129">데이터 보기 관리</span><span class="sxs-lookup"><span data-stu-id="ac506-129">Managing DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/managing-dataviews.md)  
 <span data-ttu-id="ac506-130">사용 하는 방법에 설명는 **DataViewManager** 관리할 **DataView** 의 각 테이블에 대 한 설정을 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac506-130">Describes how to use a **DataViewManager** to manage **DataView** settings for each table in a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ac506-131">관련 단원</span><span class="sxs-lookup"><span data-stu-id="ac506-131">Related Sections</span></span>  
 [<span data-ttu-id="ac506-132">ASP.NET 웹 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="ac506-132">ASP.NET Web Applications</span></span>](http://msdn.microsoft.com/library/a812d7b7-049e-4234-a4c2-6acf690301f6)  
 <span data-ttu-id="ac506-133">ASP.NET 응용 프로그램, Web Forms 및 Web Services를 만들기 위한 개요 및 자세한 단계별 절차를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ac506-133">Provides overviews and detailed, step-by-step procedures for creating ASP.NET applications, Web Forms, and Web Services.</span></span>  
  
 [<span data-ttu-id="ac506-134">Windows 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="ac506-134">Windows Applications</span></span>](http://msdn.microsoft.com/library/a6bb2180-09b1-4738-b9fd-7fb05fc92f23)  
 <span data-ttu-id="ac506-135">Windows Forms 및 콘솔 응용 프로그램 작업에 대한 자세한 내용을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ac506-135">Provides detailed information about working with Windows Forms and console applications.</span></span>  
  
 [<span data-ttu-id="ac506-136">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="ac506-136">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 <span data-ttu-id="ac506-137">설명의 **DataSet** 개체와 사용 하 여 응용 프로그램 데이터를 관리 하는 방법을 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac506-137">Describes the **DataSet** object and how you can use it to manage application data.</span></span>  
  
 [<span data-ttu-id="ac506-138">DataTable</span><span class="sxs-lookup"><span data-stu-id="ac506-138">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 <span data-ttu-id="ac506-139">설명의 **DataTable** 개체와 사용 하 여 단독으로 또는의 일부로 응용 프로그램 데이터를 관리 하는 방법을 **DataSet**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac506-139">Describes the **DataTable** object and how you can use it to manage application data by itself or as part of a **DataSet**.</span></span>  
  
 [<span data-ttu-id="ac506-140">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ac506-140">ADO.NET</span></span>](../../../../../docs/framework/data/adonet/index.md)  
 <span data-ttu-id="ac506-141">ADO.NET 아키텍처 및 구성 요소에 대해 설명하고, ADO.NET을 사용하여 기존 데이터 소스에 액세스하고 응용 프로그램 데이터를 관리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ac506-141">Describes the ADO.NET architecture and components, and how to use ADO.NET to access existing data sources and manage application data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac506-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ac506-142">See Also</span></span>  
 [<span data-ttu-id="ac506-143">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="ac506-143">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
