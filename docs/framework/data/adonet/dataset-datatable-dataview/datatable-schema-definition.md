---
title: "DataTable 스키마 정의"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: efbcdda4-f5a9-421d-8be2-4c194c74552f
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: be5969bf8653512da27785479ac7feae1f6c09a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="datatable-schema-definition"></a><span data-ttu-id="c1b8a-102">DataTable 스키마 정의</span><span class="sxs-lookup"><span data-stu-id="c1b8a-102">DataTable Schema Definition</span></span>
<span data-ttu-id="c1b8a-103">테이블의 스키마나 구조는 열이나 제약 조건에 의해 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1b8a-103">The schema, or structure, of a table is represented by columns and constraints.</span></span> <span data-ttu-id="c1b8a-104"><xref:System.Data.DataTable>의 스키마는 <xref:System.Data.DataColumn> 개체를 비롯하여 <xref:System.Data.ForeignKeyConstraint> 및 <xref:System.Data.UniqueConstraint> 개체를 사용하여 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c1b8a-104">You define the schema of a <xref:System.Data.DataTable> using <xref:System.Data.DataColumn> objects as well as <xref:System.Data.ForeignKeyConstraint> and <xref:System.Data.UniqueConstraint> objects.</span></span> <span data-ttu-id="c1b8a-105">테이블 열은 데이터 소스 열에 매핑될 수 있습니다. 또한 이 열은 식에서 계산된 값을 포함하며 값을 자동으로 증가시키고 기본 키 값을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1b8a-105">The columns in a table can map to columns in a data source, contain calculated values from expressions, automatically increment their values, or contain primary key values.</span></span>  
  
 <span data-ttu-id="c1b8a-106">테이블의 열, 관계 및 제약 조건을 이름에 따라 참조하는 경우 대/소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="c1b8a-106">References by name to columns, relations, and constraints in a table are case-sensitive.</span></span> <span data-ttu-id="c1b8a-107">따라서 이름이 동일한 열, 관계 또는 제약 조건이 테이블에 두 개 이상 존재할 수 있지만, 대/소문자는 다르게 표기됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1b8a-107">Two or more columns, relations, or constraints can therefore exist in a table that have the same name, but that differ in case.</span></span> <span data-ttu-id="c1b8a-108">예를 들어 할 수 있습니다 **Col1** 및 **col1**합니다.</span><span class="sxs-lookup"><span data-stu-id="c1b8a-108">For example, you can have **Col1** and **col1**.</span></span> <span data-ttu-id="c1b8a-109">이러한 경우 이름에 따라 열을 참조하려면 열 이름의 대/소문자가 정확하게 일치해야 하며, 그렇지 않으면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1b8a-109">In such as case, a reference to one of the columns by name must match the case of the column name exactly; otherwise an exception is thrown.</span></span> <span data-ttu-id="c1b8a-110">예를 들어 경우 테이블 **myTable** 열이 포함 **Col1** 및 **col1**, 참조할 **Col1** 를 이름으로  **myTable.Columns["Col1"]**, 및 **col1** 으로 **myTable.Columns["col1"]**합니다.</span><span class="sxs-lookup"><span data-stu-id="c1b8a-110">For example, if the table **myTable** contains the columns **Col1** and **col1**, you would reference **Col1** by name as **myTable.Columns["Col1"]**, and **col1** as **myTable.Columns["col1"]**.</span></span> <span data-ttu-id="c1b8a-111">으로 열 중 하나를 참조 하려고 **myTable.Columns["COL1"]** 하면 예외가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1b8a-111">Attempting to reference either of the columns as **myTable.Columns["COL1"]** would generate an exception.</span></span>  
  
 <span data-ttu-id="c1b8a-112">특정 이름의 열, 관계 또는 제약 조건이 하나만 있으면 대/소문자 구분 규칙이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1b8a-112">The case-sensitivity rule does not apply if only one column, relation, or constraint  with a particular name exists.</span></span> <span data-ttu-id="c1b8a-113">즉, 테이블에 있는 기타 열, 관계 또는 제약 조건 개체의 이름이 특정한 열, 관계 또는 제약 조건 개체의 이름과 일치하지 않더라도 이름에 따라 대/소문자 구분 없이 해당 개체를 참조할 수 있으며, 예외가 throw되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1b8a-113">That is, if no other column, relation, or constraint object in the table matches the name of that particular column, relation, or constraint object, you may reference the object by name using any case, and no exception is thrown.</span></span> <span data-ttu-id="c1b8a-114">예를 들어 테이블에만 **Col1**를 사용 하 여 참조할 수 **내 합니다. 열 ["COL1"]**합니다.</span><span class="sxs-lookup"><span data-stu-id="c1b8a-114">For example, if the table has only **Col1**, you can reference it using **my.Columns["COL1"]**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1b8a-115"><xref:System.Data.DataTable.CaseSensitive%2A> 의 속성은 **DataTable** 이 동작에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1b8a-115">The <xref:System.Data.DataTable.CaseSensitive%2A> property of the **DataTable** does not affect this behavior.</span></span> <span data-ttu-id="c1b8a-116">**CaseSensitive** 속성이 데이터 테이블 및 영향을 줌 정렬, 검색, 필터링, 제약 조건 및 등을 강제 적용에 속하지만 열, 관계 및 제약 조건에 대 한 참조에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1b8a-116">The **CaseSensitive** property applies to the data in a table and affects sorting, searching, filtering, enforcing constraints, and so on, but not to references to the columns, relations, and constraints.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c1b8a-117">단원 내용</span><span class="sxs-lookup"><span data-stu-id="c1b8a-117">In This Section</span></span>  
 [<span data-ttu-id="c1b8a-118">DataTable에 열 추가</span><span class="sxs-lookup"><span data-stu-id="c1b8a-118">Adding Columns to a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-columns-to-a-datatable.md)  
 <span data-ttu-id="c1b8a-119">사용 하 여 테이블의 열을 정의 하는 방법을 설명 **DataColumn** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c1b8a-119">Describes how to define the columns of a table using **DataColumn** objects.</span></span>  
  
 [<span data-ttu-id="c1b8a-120">식 열 만들기</span><span class="sxs-lookup"><span data-stu-id="c1b8a-120">Creating Expression Columns</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-expression-columns.md)  
 <span data-ttu-id="c1b8a-121">에 대해 설명 방법을 **식** 행의 다른 열에서 값을 기반으로 하는 값을 계산 열의 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1b8a-121">Explains how the **Expression** property of a column can be used to calculate values based on the values from other columns in the row.</span></span>  
  
 [<span data-ttu-id="c1b8a-122">AutoIncrement 열 만들기</span><span class="sxs-lookup"><span data-stu-id="c1b8a-122">Creating AutoIncrement Columns</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md)  
 <span data-ttu-id="c1b8a-123">숫자 값을 자동으로 증가시켜 행마다 열 값이 고유하도록 열을 설정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c1b8a-123">Describes how a column can be set to automatically increment numerical values to ensure a unique column value per row.</span></span>  
  
 [<span data-ttu-id="c1b8a-124">기본 키 정의</span><span class="sxs-lookup"><span data-stu-id="c1b8a-124">Defining Primary Keys</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md)  
 <span data-ttu-id="c1b8a-125">하나 이상에서 테이블의 기본 키를 지정 하는 방법에 설명 **DataColumn** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c1b8a-125">Describes how to specify the primary key of a table from one or more **DataColumn** objects.</span></span>  
  
 [<span data-ttu-id="c1b8a-126">DataTable 제약 조건</span><span class="sxs-lookup"><span data-stu-id="c1b8a-126">DataTable Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md)  
 <span data-ttu-id="c1b8a-127">테이블에서 열의 외래 키와 UNIQUE 제약 조건을 정의하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c1b8a-127">Describes how to define foreign key and unique constraints for columns in a table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1b8a-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c1b8a-128">See Also</span></span>  
 [<span data-ttu-id="c1b8a-129">DataTable</span><span class="sxs-lookup"><span data-stu-id="c1b8a-129">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="c1b8a-130">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="c1b8a-130">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
