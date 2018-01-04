---
title: "방법: 프로그래밍 방식으로 표 작성"
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
helpviewer_keywords: tables [WPF], creating programmatically
ms.assetid: e3ca88f3-6e94-4b61-82fc-42104c10b761
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fca6a304ea12dd90a71f8718fed5f1595f4cd4b3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-build-a-table-programmatically"></a><span data-ttu-id="e58dc-102">방법: 프로그래밍 방식으로 표 작성</span><span class="sxs-lookup"><span data-stu-id="e58dc-102">How to: Build a Table Programmatically</span></span>
<span data-ttu-id="e58dc-103">다음 예제에서는 프로그래밍 방식으로 만드는 방법을 보여는 <xref:System.Windows.Documents.Table> 콘텐츠를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="e58dc-103">The following examples show how to programmatically create a <xref:System.Windows.Documents.Table> and populate it with content.</span></span> <span data-ttu-id="e58dc-104">테이블의 내용이 5 개의 행에 할당 됩니다 (나타내는 <xref:System.Windows.Documents.TableRow> 에 포함 된 개체는 <xref:System.Windows.Documents.Table.RowGroups%2A> 개체)와 6 개의 열 (나타내는 <xref:System.Windows.Documents.TableColumn> 개체).</span><span class="sxs-lookup"><span data-stu-id="e58dc-104">The contents of the table are apportioned into five rows (represented by <xref:System.Windows.Documents.TableRow> objects contained in a <xref:System.Windows.Documents.Table.RowGroups%2A> object) and six columns (represented by <xref:System.Windows.Documents.TableColumn> objects).</span></span> <span data-ttu-id="e58dc-105">행은 전체 테이블의 제목을 지정하는 제목 행, 테이블의 데이터 열을 설명하는 헤더 행 및 요약 정보가 포함된 바닥글 행 등의 여러 다른 프레젠테이션 용도로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e58dc-105">The rows are used for different presentation purposes, including a title row intended to title the entire table, a header row to describe the columns of data in the table, and a footer row with summary information.</span></span>  <span data-ttu-id="e58dc-106">“제목”, “헤더” 및 “바닥글” 행의 개념은 테이블에 고유한 것이 아니며, 여러 다른 특성이 있는 행일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="e58dc-106">Note that the notion of "title", "header", and "footer" rows are not inherent to the table; these are simply rows with different characteristics.</span></span> <span data-ttu-id="e58dc-107">테이블 셀에 텍스트, 이미지 또는 기타 거의 모든 구성 될 수 있습니다는 실제 콘텐츠를 포함할 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e58dc-107">Table cells contain the actual content, which can be comprised of text, images, or nearly any other [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e58dc-108">예</span><span class="sxs-lookup"><span data-stu-id="e58dc-108">Example</span></span>  
 <span data-ttu-id="e58dc-109">첫째, 한 <xref:System.Windows.Documents.FlowDocument> 만들어집니다 호스트에는 <xref:System.Windows.Documents.Table>, 및 새 <xref:System.Windows.Documents.Table> 만들어지고의 내용에 추가 <xref:System.Windows.Documents.FlowDocument>합니다.</span><span class="sxs-lookup"><span data-stu-id="e58dc-109">First, a <xref:System.Windows.Documents.FlowDocument> is created to host the <xref:System.Windows.Documents.Table>, and a new <xref:System.Windows.Documents.Table> is created and added to the contents of the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
## <a name="example"></a><span data-ttu-id="e58dc-110">예</span><span class="sxs-lookup"><span data-stu-id="e58dc-110">Example</span></span>  
 <span data-ttu-id="e58dc-111">다음은 6 개의 <xref:System.Windows.Documents.TableColumn> 개체 생성 되 고 테이블의 추가 <xref:System.Windows.Documents.Table.Columns%2A> 서식이 적용 된 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="e58dc-111">Next, six <xref:System.Windows.Documents.TableColumn> objects are created and added to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection, with some formatting applied.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e58dc-112">테이블의 <xref:System.Windows.Documents.Table.Columns%2A> 컬렉션 표준 인덱스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e58dc-112">Note that the table's <xref:System.Windows.Documents.Table.Columns%2A> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
## <a name="example"></a><span data-ttu-id="e58dc-113">예</span><span class="sxs-lookup"><span data-stu-id="e58dc-113">Example</span></span>  
 <span data-ttu-id="e58dc-114">다음으로 제목 행을 만들어 서식이 적용된 테이블에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e58dc-114">Next, a title row is created and added to the table with some formatting applied.</span></span>  <span data-ttu-id="e58dc-115">제목 행은 테이블의 6개 열에 모두 걸친 단일 셀을 포함하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e58dc-115">The title row happens to contain a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
## <a name="example"></a><span data-ttu-id="e58dc-116">예</span><span class="sxs-lookup"><span data-stu-id="e58dc-116">Example</span></span>  
 <span data-ttu-id="e58dc-117">다음으로 헤더 행을 만들어 테이블에 추가하고, 헤더 행의 셀을 만들어 콘텐츠로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="e58dc-117">Next, a header row is created and added to the table, and the cells in the header row are created and populated with content.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
## <a name="example"></a><span data-ttu-id="e58dc-118">예</span><span class="sxs-lookup"><span data-stu-id="e58dc-118">Example</span></span>  
 <span data-ttu-id="e58dc-119">다음으로 데이터 행을 만들어 테이블에 추가하고, 이 행의 셀을 만들어 콘텐츠로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="e58dc-119">Next, a row for data is created and added to the table, and the cells in this row are created and populated with content.</span></span>  <span data-ttu-id="e58dc-120">이 행을 작성하는 것은 헤더 행을 작성하는 것과 비슷합니다. 단, 약간 다른 서식이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e58dc-120">Building this row is similar to building the header row, with slightly different formatting applied.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
## <a name="example"></a><span data-ttu-id="e58dc-121">예</span><span class="sxs-lookup"><span data-stu-id="e58dc-121">Example</span></span>  
 <span data-ttu-id="e58dc-122">마지막으로 바닥글 행을 만들어 추가하고 서식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e58dc-122">Finally, a footer row is created, added, and formatted.</span></span>  <span data-ttu-id="e58dc-123">제목 행과 마찬가지로 바닥글에는 테이블의 6개 열에 모두 걸친 단일 셀이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e58dc-123">Like the title row, the footer contains a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a><span data-ttu-id="e58dc-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e58dc-124">See Also</span></span>  
 [<span data-ttu-id="e58dc-125">테이블 개요</span><span class="sxs-lookup"><span data-stu-id="e58dc-125">Table Overview</span></span>](../../../../docs/framework/wpf/advanced/table-overview.md)
