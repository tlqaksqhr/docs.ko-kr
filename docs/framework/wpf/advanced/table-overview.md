---
title: 테이블 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flow content elements [WPF], Table
- documents [WPF], tables
- tables [WPF]
ms.assetid: 5e1105f4-8fc4-473a-ba55-88c8e71386e6
ms.openlocfilehash: 631a14ae8eb17713186f7db66700026cc476024e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33549372"
---
# <a name="table-overview"></a><span data-ttu-id="0bc57-102">테이블 개요</span><span class="sxs-lookup"><span data-stu-id="0bc57-102">Table Overview</span></span>
<span data-ttu-id="0bc57-103"><xref:System.Windows.Documents.Table> 유동 문서 콘텐츠 그리드 기반 프레젠테이션을 지 원하는 블록 수준 요소가입니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-103"><xref:System.Windows.Documents.Table> is a block level element that supports grid-based presentation of Flow document content.</span></span> <span data-ttu-id="0bc57-104">이 요소의 유연성 덕분에 이 요소는 매우 유용하지만 이해하고 제대로 사용하기가 더 복잡합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-104">The flexibility of this element makes it very useful, but also makes it more complicated to understand and use correctly.</span></span>  
  
 <span data-ttu-id="0bc57-105">이 항목에는 다음과 같은 섹션이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-105">This topic contains the following sections.</span></span>  
  
-   [<span data-ttu-id="0bc57-106">테이블 기본 사항</span><span class="sxs-lookup"><span data-stu-id="0bc57-106">Table Basics</span></span>](#table_basics)  
  
-   [<span data-ttu-id="0bc57-107">Table은 Grid와 어떻게 다를까요?</span><span class="sxs-lookup"><span data-stu-id="0bc57-107">How is Table Different then Grid?</span></span>](#table_vs_Grid)  
  
-   [<span data-ttu-id="0bc57-108">기본 테이블 구조</span><span class="sxs-lookup"><span data-stu-id="0bc57-108">Basic Table Structure</span></span>](#basic_table_structure)  
  
-   [<span data-ttu-id="0bc57-109">테이블 포함</span><span class="sxs-lookup"><span data-stu-id="0bc57-109">Table Containment</span></span>](#table_containment)  
  
-   [<span data-ttu-id="0bc57-110">행 그룹</span><span class="sxs-lookup"><span data-stu-id="0bc57-110">Row Groupings</span></span>](#row_groupings)  
  
-   [<span data-ttu-id="0bc57-111">백그라운드 렌더링 우선 순위</span><span class="sxs-lookup"><span data-stu-id="0bc57-111">Background Rendering Precedence</span></span>](#rendering_precedence)  
  
-   [<span data-ttu-id="0bc57-112">행 및 열 확장</span><span class="sxs-lookup"><span data-stu-id="0bc57-112">Spanning Rows or Columns</span></span>](#spanning_rows_or_columns)  
  
-   [<span data-ttu-id="0bc57-113">코드로 테이블 빌드</span><span class="sxs-lookup"><span data-stu-id="0bc57-113">Building a Table With Code</span></span>](#building_a_table_with_code)  
  
-   <span data-ttu-id="0bc57-114">[관련 항목]</span><span class="sxs-lookup"><span data-stu-id="0bc57-114">[Related Topics]</span></span> 
  
<a name="table_basics"></a>   
## <a name="table-basics"></a><span data-ttu-id="0bc57-115">테이블 기본 사항</span><span class="sxs-lookup"><span data-stu-id="0bc57-115">Table Basics</span></span>  
  
<a name="table_vs_Grid"></a>   
### <a name="how-is-table-different-then-grid"></a><span data-ttu-id="0bc57-116">Table은 Grid와 어떻게 다를까요?</span><span class="sxs-lookup"><span data-stu-id="0bc57-116">How is Table Different then Grid?</span></span>  
 <span data-ttu-id="0bc57-117"><xref:System.Windows.Documents.Table> 및 <xref:System.Windows.Controls.Grid> 공통 된 기능을 공유 하지만 각는 다양 한 시나리오에 가장 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-117"><xref:System.Windows.Documents.Table> and <xref:System.Windows.Controls.Grid> share some common functionality, but each is best suited for different scenarios.</span></span> <span data-ttu-id="0bc57-118">A <xref:System.Windows.Documents.Table> 유동 콘텐츠 내에서 사용 하도록 설계 되었습니다 (참조 [흐름 문서 개요](../../../../docs/framework/wpf/advanced/flow-document-overview.md) 유동 콘텐츠에 대 한 자세한 내용은).</span><span class="sxs-lookup"><span data-stu-id="0bc57-118">A <xref:System.Windows.Documents.Table> is designed for use within flow content (see [Flow Document Overview](../../../../docs/framework/wpf/advanced/flow-document-overview.md) for more information on flow content).</span></span> <span data-ttu-id="0bc57-119">그리드는 폼 내부에서 사용하는 것이 적합합니다(기본적으로 유동 콘텐츠 외부의 모든 위치).</span><span class="sxs-lookup"><span data-stu-id="0bc57-119">Grids are best used inside of forms (basically anywhere outside of flow content).</span></span> <span data-ttu-id="0bc57-120">내에서 한 <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Table> 지원 유동 콘텐츠 동작 하는 동안 콘텐츠 선택, 페이지 매김 및 열 흐름 변경 등는 <xref:System.Windows.Controls.Grid> 는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-120">Within a <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Table> supports flow content behaviors like pagination, column reflow, and content selection while a <xref:System.Windows.Controls.Grid> does not.</span></span> <span data-ttu-id="0bc57-121">A <xref:System.Windows.Controls.Grid> 반면에 외부에 <xref:System.Windows.Documents.FlowDocument> 비롯 한 여러 가지 이유로 <xref:System.Windows.Controls.Grid> 행 및 열 인덱스에 따라 요소를 추가 <xref:System.Windows.Documents.Table> 는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-121">A <xref:System.Windows.Controls.Grid> on the other hand is best used outside of a <xref:System.Windows.Documents.FlowDocument> for many reasons including <xref:System.Windows.Controls.Grid> adds elements based on a row and column index, <xref:System.Windows.Documents.Table> does not.</span></span> <span data-ttu-id="0bc57-122"><xref:System.Windows.Controls.Grid> 자식 콘텐츠를 단일 "셀"에 존재 하는 요소가 둘 이상 허용 층으로 요소를 사용 하면</span><span class="sxs-lookup"><span data-stu-id="0bc57-122">The <xref:System.Windows.Controls.Grid> element allows layering of child content, allowing more than one element to exist within a single "cell."</span></span> <span data-ttu-id="0bc57-123"><xref:System.Windows.Documents.Table> 레이어 링을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-123"><xref:System.Windows.Documents.Table> does not support layering.</span></span> <span data-ttu-id="0bc57-124">자식 요소는 <xref:System.Windows.Controls.Grid> 절대 해당 "셀" 경계 영역을 기준으로 배치 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-124">Child elements of a <xref:System.Windows.Controls.Grid> can be absolutely positioned relative to the area of their "cell" boundaries.</span></span> <span data-ttu-id="0bc57-125"><xref:System.Windows.Documents.Table> 이 기능을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-125"><xref:System.Windows.Documents.Table> does not support this feature.</span></span> <span data-ttu-id="0bc57-126">마지막으로, 한 <xref:System.Windows.Controls.Grid> 적은 리소스가 필요 없으면 <xref:System.Windows.Documents.Table> 하므로 사용 하 여 것이 좋습니다는 <xref:System.Windows.Controls.Grid> 성능 향상을 위해 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-126">Finally, a <xref:System.Windows.Controls.Grid> requires less resources then a <xref:System.Windows.Documents.Table> so consider using a <xref:System.Windows.Controls.Grid> to improve performance.</span></span>  
  
<a name="basic_table_structure"></a>   
### <a name="basic-table-structure"></a><span data-ttu-id="0bc57-127">기본 테이블 구조</span><span class="sxs-lookup"><span data-stu-id="0bc57-127">Basic Table Structure</span></span>  
 <span data-ttu-id="0bc57-128"><xref:System.Windows.Documents.Table> 열으로 구성 된 그리드 기반 프레젠테이션을 제공 (나타내는 <xref:System.Windows.Documents.TableColumn> 요소)와 행 (나타내는 <xref:System.Windows.Documents.TableRow> 요소).</span><span class="sxs-lookup"><span data-stu-id="0bc57-128"><xref:System.Windows.Documents.Table> provides a grid-based presentation consisting of columns (represented by <xref:System.Windows.Documents.TableColumn> elements) and rows (represented by <xref:System.Windows.Documents.TableRow> elements).</span></span> <span data-ttu-id="0bc57-129"><xref:System.Windows.Documents.TableColumn> 요소 콘텐츠를 호스트 하지 마세요. 단순히 열과 열의 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-129"><xref:System.Windows.Documents.TableColumn> elements do not host content; they simply define columns and characteristics of columns.</span></span> <span data-ttu-id="0bc57-130"><xref:System.Windows.Documents.TableRow> 요소에서 호스트 되어야 합니다는 <xref:System.Windows.Documents.TableRowGroup> 테이블에 대 한 행의 그룹화를 정의 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-130"><xref:System.Windows.Documents.TableRow> elements must be hosted in a <xref:System.Windows.Documents.TableRowGroup> element, which defines a grouping of rows for the table.</span></span> <span data-ttu-id="0bc57-131"><xref:System.Windows.Documents.TableCell> 테이블에 의해 표시 되는 실제 콘텐츠를 포함 하는 요소에서 호스트 되어야 합니다는 <xref:System.Windows.Documents.TableRow> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-131"><xref:System.Windows.Documents.TableCell> elements, which contain the actual content to be presented by the table, must be hosted in a <xref:System.Windows.Documents.TableRow> element.</span></span> <span data-ttu-id="0bc57-132"><xref:System.Windows.Documents.TableCell> 파생 된 요소를 하나만 있습니다 <xref:System.Windows.Documents.Block>합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-132"><xref:System.Windows.Documents.TableCell> may only contain elements that derive from <xref:System.Windows.Documents.Block>.</span></span>  <span data-ttu-id="0bc57-133">에 대 한 올바른 자식 요소는 <xref:System.Windows.Documents.TableCell> 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-133">Valid child elements for a <xref:System.Windows.Documents.TableCell> include.</span></span>  
  
-   <xref:System.Windows.Documents.BlockUIContainer>  
  
-   <xref:System.Windows.Documents.List>  
  
-   <xref:System.Windows.Documents.Paragraph>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.Table>  
  
> [!NOTE]
>  <span data-ttu-id="0bc57-134"><xref:System.Windows.Documents.TableCell> 요소 직접 텍스트 콘텐츠를 호스팅하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-134"><xref:System.Windows.Documents.TableCell> elements may not directly host text content.</span></span> <span data-ttu-id="0bc57-135">콘텐츠 요소와 같은 흐름에 대 한 포함 규칙에 대 한 자세한 내용은 <xref:System.Windows.Documents.TableCell>, 참조 [흐름 문서 개요](../../../../docs/framework/wpf/advanced/flow-document-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-135">For more information about the containment rules for flow content elements like <xref:System.Windows.Documents.TableCell>, see [Flow Document Overview](../../../../docs/framework/wpf/advanced/flow-document-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0bc57-136"><xref:System.Windows.Documents.Table> 비슷합니다는 <xref:System.Windows.Controls.Grid> 요소 하지만 더 많은 기능이 있으며, 따라서 큰 리소스 오버 헤드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-136"><xref:System.Windows.Documents.Table> is similar to the <xref:System.Windows.Controls.Grid> element but has more capabilities and, therefore, requires greater resource overhead.</span></span>  
  
 <span data-ttu-id="0bc57-137">다음 예제에서는 간단한 2 x 3 테이블에 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-137">The following example defines a simple 2 x 3 table with [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)].</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_BasicLayout](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_basiclayout)]  
  
 <span data-ttu-id="0bc57-138">다음 그림은 이 예제에서 렌더링하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-138">The following figure shows how this example renders.</span></span>  
  
 <span data-ttu-id="0bc57-139">![스크린샷: 기본 테이블 렌더링](../../../../docs/framework/wpf/advanced/media/basictablerrender.png "BasicTablerRender")</span><span class="sxs-lookup"><span data-stu-id="0bc57-139">![Screenshot: Render a basic table](../../../../docs/framework/wpf/advanced/media/basictablerrender.png "BasicTablerRender")</span></span>  
  
<a name="table_containment"></a>   
### <a name="table-containment"></a><span data-ttu-id="0bc57-140">테이블 포함</span><span class="sxs-lookup"><span data-stu-id="0bc57-140">Table Containment</span></span>  
 <span data-ttu-id="0bc57-141"><xref:System.Windows.Documents.Table> 파생 되는 <xref:System.Windows.Documents.Block> 요소에 대 한 일반적인 규칙을 준수 <xref:System.Windows.Documents.Block> 수준 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-141"><xref:System.Windows.Documents.Table> derives from the <xref:System.Windows.Documents.Block> element, and adheres to the common rules for <xref:System.Windows.Documents.Block> level elements.</span></span>  <span data-ttu-id="0bc57-142">A <xref:System.Windows.Documents.Table> 요소 중 다음과 같은 요소가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-142">A <xref:System.Windows.Documents.Table> element may be contained by any of the following elements:</span></span>  
  
-   <xref:System.Windows.Documents.FlowDocument>  
  
-   <xref:System.Windows.Documents.TableCell>  
  
-   <xref:System.Windows.Controls.ListBoxItem>  
  
-   <xref:System.Windows.Controls.ListViewItem>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.Floater>  
  
-   <xref:System.Windows.Documents.Figure>  
  
<a name="row_groupings"></a>   
### <a name="row-groupings"></a><span data-ttu-id="0bc57-143">행 그룹</span><span class="sxs-lookup"><span data-stu-id="0bc57-143">Row Groupings</span></span>  
 <span data-ttu-id="0bc57-144"><xref:System.Windows.Documents.TableRowGroup> 요소는 테이블 내에서 행을 임의로 그룹화 하는 방법을 제공 합니다; 테이블의 모든 행은 행 그룹에 속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-144">The <xref:System.Windows.Documents.TableRowGroup> element provides a way to arbitrarily group rows within a table; every row in a table must belong to a row grouping.</span></span>  <span data-ttu-id="0bc57-145">행 그룹 내의 행은 보통 공통 의도를 공유하고 그룹으로 스타일을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-145">Rows within a row group often share a common intent, and may be styled as a group.</span></span>  <span data-ttu-id="0bc57-146">행 그룹은 공통적으로 제목, 헤더 및 바닥글 행과 같은 특수 용도 행을 테이블에 포함된 기본 콘텐츠에서 구분하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-146">A common use for row groupings is to separate special-purpose rows, such as a title, header, and footer rows, from the primary content contained by the table.</span></span>  
  
 <span data-ttu-id="0bc57-147">다음 예제에서는 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] 스타일의 머리글 및 바닥글 행이 있는 테이블을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-147">The following example uses [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] to define a table with styled header and footer rows.</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_RowGroups](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_rowgroups)]  
  
 <span data-ttu-id="0bc57-148">다음 그림은 이 예제에서 렌더링하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-148">The following figure shows how this example renders.</span></span>  
  
 <span data-ttu-id="0bc57-149">![스크린샷: 테이블 행 그룹](../../../../docs/framework/wpf/advanced/media/table-rowgroups.png "Table_RowGroups")</span><span class="sxs-lookup"><span data-stu-id="0bc57-149">![Screenshot: Table row groups](../../../../docs/framework/wpf/advanced/media/table-rowgroups.png "Table_RowGroups")</span></span>  
  
<a name="rendering_precedence"></a>   
### <a name="background-rendering-precedence"></a><span data-ttu-id="0bc57-150">백그라운드 렌더링 우선 순위</span><span class="sxs-lookup"><span data-stu-id="0bc57-150">Background Rendering Precedence</span></span>  
 <span data-ttu-id="0bc57-151">테이블 요소는 다음 순서로 렌더링됩니다(최저부터 최고까지 z 순서).</span><span class="sxs-lookup"><span data-stu-id="0bc57-151">Table elements render in the following order (z-order from lowest to highest).</span></span> <span data-ttu-id="0bc57-152">이 순서는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-152">This order cannot be changed.</span></span> <span data-ttu-id="0bc57-153">예를 들어 설정된 순서를 재정의하는 데 사용할 수 있는 다음 요소에 대한 "Z 순서" 속성은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-153">For example, there is no "Z-order" property for these elements that you can use to override this established order.</span></span>  
  
1.  <xref:System.Windows.Documents.Table>  
  
2.  <xref:System.Windows.Documents.TableColumn>  
  
3.  <xref:System.Windows.Documents.TableRowGroup>  
  
4.  <xref:System.Windows.Documents.TableRow>  
  
5.  <xref:System.Windows.Documents.TableCell>  
  
 <span data-ttu-id="0bc57-154">테이블에서 이러한 각 요소의 배경색을 정의하는 다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-154">Consider the following example, which defines background colors for each of these elements within a table.</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_ZOrder](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_zorder)]  
  
 <span data-ttu-id="0bc57-155">다음 그림은 이 예제가 렌더링되는 방법을 보여 줍니다(배경색만 표시).</span><span class="sxs-lookup"><span data-stu-id="0bc57-155">The following figure shows how this example renders (showing background colors only).</span></span>  
  
 <span data-ttu-id="0bc57-156">![스크린샷: 테이블 z 순서](../../../../docs/framework/wpf/advanced/media/table-zorder.png "Table_ZOrder")</span><span class="sxs-lookup"><span data-stu-id="0bc57-156">![Screenshot: Table z&#45;order](../../../../docs/framework/wpf/advanced/media/table-zorder.png "Table_ZOrder")</span></span>  
  
<a name="spanning_rows_or_columns"></a>   
### <a name="spanning-rows-or-columns"></a><span data-ttu-id="0bc57-157">행 및 열 확장</span><span class="sxs-lookup"><span data-stu-id="0bc57-157">Spanning Rows or Columns</span></span>  
 <span data-ttu-id="0bc57-158">사용 하 여 여러 행 이나 열에 걸쳐 표 셀을 구성할 수 있습니다는 <xref:System.Windows.Documents.TableCell.RowSpan%2A> 또는 <xref:System.Windows.Documents.TableCell.ColumnSpan%2A> 특성에 각각 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-158">Table cells may be configured to span multiple rows or columns by using the <xref:System.Windows.Documents.TableCell.RowSpan%2A> or <xref:System.Windows.Documents.TableCell.ColumnSpan%2A> attributes, respectively.</span></span>  
  
 <span data-ttu-id="0bc57-159">셀이 세 개의 열에 걸쳐 있는 다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-159">Consider the following example, in which a cell spans three columns.</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_ColumnSpan](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_columnspan)]  
  
 <span data-ttu-id="0bc57-160">다음 그림은 이 예제에서 렌더링하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-160">The following figure shows how this example renders.</span></span>  
  
 <span data-ttu-id="0bc57-161">![스크린샷: 세 열에 걸친 셀](../../../../docs/framework/wpf/advanced/media/table-columnspan.png "Table_ColumnSpan")</span><span class="sxs-lookup"><span data-stu-id="0bc57-161">![Screenshot: Cell spanning all three columns](../../../../docs/framework/wpf/advanced/media/table-columnspan.png "Table_ColumnSpan")</span></span>  
  
<a name="building_a_table_with_code"></a>   
## <a name="building-a-table-with-code"></a><span data-ttu-id="0bc57-162">코드로 테이블 빌드</span><span class="sxs-lookup"><span data-stu-id="0bc57-162">Building a Table With Code</span></span>  
 <span data-ttu-id="0bc57-163">다음 예제에서는 프로그래밍 방식으로 만드는 방법을 보여는 <xref:System.Windows.Documents.Table> 콘텐츠를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-163">The following examples show how to programmatically create a <xref:System.Windows.Documents.Table> and populate it with content.</span></span> <span data-ttu-id="0bc57-164">테이블의 내용이 5 개의 행에 할당 됩니다 (나타내는 <xref:System.Windows.Documents.TableRow> 에 포함 된 개체는 <xref:System.Windows.Documents.Table.RowGroups%2A> 개체)와 6 개의 열 (나타내는 <xref:System.Windows.Documents.TableColumn> 개체).</span><span class="sxs-lookup"><span data-stu-id="0bc57-164">The contents of the table are apportioned into five rows (represented by <xref:System.Windows.Documents.TableRow> objects contained in a <xref:System.Windows.Documents.Table.RowGroups%2A> object) and six columns (represented by <xref:System.Windows.Documents.TableColumn> objects).</span></span> <span data-ttu-id="0bc57-165">행은 전체 테이블의 제목을 지정하는 제목 행, 테이블의 데이터 열을 설명하는 헤더 행 및 요약 정보가 포함된 바닥글 행 등의 여러 다른 프레젠테이션 용도로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-165">The rows are used for different presentation purposes, including a title row intended to title the entire table, a header row to describe the columns of data in the table, and a footer row with summary information.</span></span>  <span data-ttu-id="0bc57-166">“제목”, “헤더” 및 “바닥글” 행의 개념은 테이블에 고유한 것이 아니며, 여러 다른 특성이 있는 행일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-166">Note that the notion of "title", "header", and "footer" rows are not inherent to the table; these are simply rows with different characteristics.</span></span> <span data-ttu-id="0bc57-167">테이블 셀에 텍스트, 이미지 또는 기타 거의 모든 구성 될 수 있습니다는 실제 콘텐츠를 포함할 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-167">Table cells contain the actual content, which can be comprised of text, images, or nearly any other [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] element.</span></span>  
  
 <span data-ttu-id="0bc57-168">첫째, 한 <xref:System.Windows.Documents.FlowDocument> 만들어집니다 호스트에는 <xref:System.Windows.Documents.Table>, 및 새 <xref:System.Windows.Documents.Table> 만들어지고의 내용에 추가 <xref:System.Windows.Documents.FlowDocument>합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-168">First, a <xref:System.Windows.Documents.FlowDocument> is created to host the <xref:System.Windows.Documents.Table>, and a new <xref:System.Windows.Documents.Table> is created and added to the contents of the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
 <span data-ttu-id="0bc57-169">다음은 6 개의 <xref:System.Windows.Documents.TableColumn> 개체 생성 되 고 테이블의 추가 <xref:System.Windows.Documents.Table.Columns%2A> 서식이 적용 된 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-169">Next, six <xref:System.Windows.Documents.TableColumn> objects are created and added to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection, with some formatting applied.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0bc57-170">테이블의 <xref:System.Windows.Documents.Table.Columns%2A> 컬렉션 표준 인덱스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-170">Note that the table's <xref:System.Windows.Documents.Table.Columns%2A> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
 <span data-ttu-id="0bc57-171">다음으로 제목 행을 만들어 서식이 적용된 테이블에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-171">Next, a title row is created and added to the table with some formatting applied.</span></span>  <span data-ttu-id="0bc57-172">제목 행은 테이블의 6개 열에 모두 걸친 단일 셀을 포함하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-172">The title row happens to contain a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
 <span data-ttu-id="0bc57-173">다음으로 헤더 행을 만들어 테이블에 추가하고, 헤더 행의 셀을 만들어 콘텐츠로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-173">Next, a header row is created and added to the table, and the cells in the header row are created and populated with content.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
 <span data-ttu-id="0bc57-174">다음으로 데이터 행을 만들어 테이블에 추가하고, 이 행의 셀을 만들어 콘텐츠로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-174">Next, a row for data is created and added to the table, and the cells in this row are created and populated with content.</span></span>  <span data-ttu-id="0bc57-175">이 행을 작성하는 것은 헤더 행을 작성하는 것과 비슷합니다. 단, 약간 다른 서식이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-175">Building this row is similar to building the header row, with slightly different formatting applied.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
 <span data-ttu-id="0bc57-176">마지막으로 바닥글 행을 만들어 추가하고 서식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-176">Finally, a footer row is created, added, and formatted.</span></span>  <span data-ttu-id="0bc57-177">제목 행과 마찬가지로 바닥글에는 테이블의 6개 열에 모두 걸친 단일 셀이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc57-177">Like the title row, the footer contains a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a><span data-ttu-id="0bc57-178">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0bc57-178">See Also</span></span>  
 [<span data-ttu-id="0bc57-179">유동 문서 개요</span><span class="sxs-lookup"><span data-stu-id="0bc57-179">Flow Document Overview</span></span>](../../../../docs/framework/wpf/advanced/flow-document-overview.md)  
 [<span data-ttu-id="0bc57-180">XAML로 테이블 정의</span><span class="sxs-lookup"><span data-stu-id="0bc57-180">Define a Table with XAML</span></span>](../../../../docs/framework/wpf/advanced/how-to-define-a-table-with-xaml.md)  
 [<span data-ttu-id="0bc57-181">WPF의 문서</span><span class="sxs-lookup"><span data-stu-id="0bc57-181">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="0bc57-182">유동 콘텐츠 요소 사용</span><span class="sxs-lookup"><span data-stu-id="0bc57-182">Use Flow Content Elements</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-flow-content-elements.md)
