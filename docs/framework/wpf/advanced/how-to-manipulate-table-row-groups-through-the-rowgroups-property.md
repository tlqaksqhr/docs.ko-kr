---
title: "방법: 테이블 &#39; 조작 Rowgroup 속성을 통해 s 행 그룹"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- row groups [WPF], manipulating through RowGroups property
- RowGroups property [WPF], manipulating row groups
- documents [WPF], manipulating row groups through RowGroups property
- properties [WPF], RowGroups [WPF], manipulating row groups
ms.assetid: ea61440f-08ae-44ed-b314-5716aaaae3ed
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f084819c3a5c39ea9d94a5741f8fb4a005d6040c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-manipulate-a-table39s-row-groups-through-the-rowgroups-property"></a><span data-ttu-id="7368e-102">방법: 테이블 &#39; 조작 Rowgroup 속성을 통해 s 행 그룹</span><span class="sxs-lookup"><span data-stu-id="7368e-102">How to: Manipulate a Table&#39;s Row Groups through the RowGroups Property</span></span>
<span data-ttu-id="7368e-103">이 예제에서는 통해 테이블의 행 그룹에서 수행할 수 있는 보다 일반적인 작업 중 일부는 <xref:System.Windows.Documents.Table.RowGroups%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="7368e-103">This example demonstrates some of the more common operations that can be performed on a table's row groups through the <xref:System.Windows.Documents.Table.RowGroups%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7368e-104">예</span><span class="sxs-lookup"><span data-stu-id="7368e-104">Example</span></span>  
 <span data-ttu-id="7368e-105">다음 예제에서는 새 테이블을 만들고 다음 사용 하 여는 <xref:System.Windows.Documents.TableRowGroupCollection.Add%2A> 을 테이블의 열을 추가 하는 방법을 <xref:System.Windows.Documents.Table.RowGroups%2A> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="7368e-105">The following example creates a new table and then uses the <xref:System.Windows.Documents.TableRowGroupCollection.Add%2A> method to add columns to the table's <xref:System.Windows.Documents.Table.RowGroups%2A> collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Add](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_add)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Add](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_add)]  
  
## <a name="example"></a><span data-ttu-id="7368e-106">예</span><span class="sxs-lookup"><span data-stu-id="7368e-106">Example</span></span>  
 <span data-ttu-id="7368e-107">다음 예제에서는 새 삽입 <xref:System.Windows.Documents.TableRowGroup>합니다.</span><span class="sxs-lookup"><span data-stu-id="7368e-107">The following example inserts a new <xref:System.Windows.Documents.TableRowGroup>.</span></span>  <span data-ttu-id="7368e-108">인덱스 위치 0, 새로운 첫 번째 행에 새 열을 삽입 하는 테이블의 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="7368e-108">The new column is inserted at index position 0, making it the new first row group in the table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7368e-109"><xref:System.Windows.Documents.TableRowGroupCollection> 컬렉션 표준 인덱스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7368e-109">The <xref:System.Windows.Documents.TableRowGroupCollection> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Insert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_insert)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Insert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_insert)]  
  
## <a name="example"></a><span data-ttu-id="7368e-110">예</span><span class="sxs-lookup"><span data-stu-id="7368e-110">Example</span></span>  
 <span data-ttu-id="7368e-111">다음 예제에서는 특정 행이 여러 개 추가 <xref:System.Windows.Documents.TableRowGroup> (인덱스에 의해 지정 됨) 테이블에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7368e-111">The following example adds several rows to a particular <xref:System.Windows.Documents.TableRowGroup> (specified by index) in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_AddRows](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_addrows)]
 [!code-vb[TableSnippets2#_Table_RowGroups_AddRows](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_addrows)]  
  
## <a name="example"></a><span data-ttu-id="7368e-112">예</span><span class="sxs-lookup"><span data-stu-id="7368e-112">Example</span></span>  
 <span data-ttu-id="7368e-113">다음 예에서는 테이블에 첫 번째 행 그룹의 행에 몇 가지 임의의 속성에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="7368e-113">The following example accesses some arbitrary properties on rows in the first row group in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_ManipRows](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_maniprows)]
 [!code-vb[TableSnippets2#_Table_RowGroups_ManipRows](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_maniprows)]  
  
## <a name="example"></a><span data-ttu-id="7368e-114">예</span><span class="sxs-lookup"><span data-stu-id="7368e-114">Example</span></span>  
 <span data-ttu-id="7368e-115">다음 예제에서는 특정 여러 셀 추가 <xref:System.Windows.Documents.TableRow> (인덱스에 의해 지정 됨) 테이블에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7368e-115">The following example adds several cells to a particular <xref:System.Windows.Documents.TableRow> (specified by index) in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_AddCells](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_addcells)]
 [!code-vb[TableSnippets2#_Table_RowGroups_AddCells](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_addcells)]  
  
## <a name="example"></a><span data-ttu-id="7368e-116">예</span><span class="sxs-lookup"><span data-stu-id="7368e-116">Example</span></span>  
 <span data-ttu-id="7368e-117">다음 예제에서는 일부 임의의 메서드 및 속성의 첫 번째 행 그룹에서 첫 번째 행의 셀에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="7368e-117">The following example access some arbitrary methods and properties on cells in the first row in the first row group.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_ManipCells](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_manipcells)]
 [!code-vb[TableSnippets2#_Table_RowGroups_ManipCells](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_manipcells)]  
  
## <a name="example"></a><span data-ttu-id="7368e-118">예</span><span class="sxs-lookup"><span data-stu-id="7368e-118">Example</span></span>  
 <span data-ttu-id="7368e-119">다음 예제에서는 수를 반환 합니다. <xref:System.Windows.Documents.TableRowGroup> 요소 테이블에서 호스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="7368e-119">The following example returns the number of <xref:System.Windows.Documents.TableRowGroup> elements hosted by the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Count](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_count)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Count](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_count)]  
  
## <a name="example"></a><span data-ttu-id="7368e-120">예</span><span class="sxs-lookup"><span data-stu-id="7368e-120">Example</span></span>  
 <span data-ttu-id="7368e-121">다음 예제에서는 참조에 의해 특정 행 그룹을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7368e-121">The following example removes a particular row group by reference.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_DelRef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_delref)]
 [!code-vb[TableSnippets2#_Table_RowGroups_DelRef](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_delref)]  
  
## <a name="example"></a><span data-ttu-id="7368e-122">예</span><span class="sxs-lookup"><span data-stu-id="7368e-122">Example</span></span>  
 <span data-ttu-id="7368e-123">다음 예에서는 인덱스에 의해 특정 행 그룹을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7368e-123">The following example removes a particular row group by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_DelIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_delindex)]
 [!code-vb[TableSnippets2#_Table_RowGroups_DelIndex](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_delindex)]  
  
## <a name="example"></a><span data-ttu-id="7368e-124">예</span><span class="sxs-lookup"><span data-stu-id="7368e-124">Example</span></span>  
 <span data-ttu-id="7368e-125">다음 예에서는 테이블의 행 그룹 컬렉션에서 모든 행 그룹을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7368e-125">The following example removes all row groups from the table's row groups collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Clear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_clear)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Clear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_clear)]  
  
## <a name="see-also"></a><span data-ttu-id="7368e-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7368e-126">See Also</span></span>  
 [<span data-ttu-id="7368e-127">방법: 유동 콘텐츠 요소를 인라인 처리 속성을 통해 조작</span><span class="sxs-lookup"><span data-stu-id="7368e-127">How-to: Manipulate Flow Content Elements through the Inlines Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)  
 [<span data-ttu-id="7368e-128">Blocks 속성을 통한 FlowDocument 조작</span><span class="sxs-lookup"><span data-stu-id="7368e-128">Manipulate a FlowDocument through the Blocks Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)  
 [<span data-ttu-id="7368e-129">Columns 속성을 통해 테이블의 열 조작</span><span class="sxs-lookup"><span data-stu-id="7368e-129">Manipulate a Table's Columns through the Columns Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)
