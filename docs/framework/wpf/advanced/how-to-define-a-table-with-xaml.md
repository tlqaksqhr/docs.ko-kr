---
title: "방법: XAML로 테이블 정의"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML [WPF], defining tables
- documents [WPF], defining tables with XAML
- tables [WPF], defining with XAML
ms.assetid: 83f2dc58-437e-4cdc-b5dd-0019810c7a85
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b932c7df822edabc5626f20af2bfc1eb3a7f93ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-a-table-with-xaml"></a><span data-ttu-id="8b28c-102">방법: XAML로 테이블 정의</span><span class="sxs-lookup"><span data-stu-id="8b28c-102">How to: Define a Table with XAML</span></span>
<span data-ttu-id="8b28c-103">다음 예제에서는 정의 하는 <xref:System.Windows.Documents.Table> 를 사용 하 여 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="8b28c-103">The following example demonstrates how to define a <xref:System.Windows.Documents.Table> using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  <span data-ttu-id="8b28c-104">예제 테이블에 4 개의 열 (나타내는 <xref:System.Windows.Documents.TableColumn> 요소) 및 여러 행 (나타내는 <xref:System.Windows.Documents.TableRow> 요소) 뿐만 데이터가 포함 된 제목, 머리글 및 바닥글 정보.</span><span class="sxs-lookup"><span data-stu-id="8b28c-104">The example table has four columns (represented by <xref:System.Windows.Documents.TableColumn> elements) and several rows (represented by <xref:System.Windows.Documents.TableRow> elements) containing data as well as title, header, and footer information.</span></span>  <span data-ttu-id="8b28c-105">행에 포함 되어야 합니다는 <xref:System.Windows.Documents.TableRowGroup> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8b28c-105">Rows must be contained in a <xref:System.Windows.Documents.TableRowGroup> element.</span></span>  <span data-ttu-id="8b28c-106">테이블의 각 행은 하나 이상의 셀의 구성 (나타내는 <xref:System.Windows.Documents.TableCell> 요소).</span><span class="sxs-lookup"><span data-stu-id="8b28c-106">Each row in the table is comprised of one or more cells (represented by <xref:System.Windows.Documents.TableCell> elements).</span></span>  <span data-ttu-id="8b28c-107">표 셀의 내용에 포함 되어야 합니다는 <xref:System.Windows.Documents.Block> 요소;이 경우 <xref:System.Windows.Documents.Paragraph> 요소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b28c-107">Content in a table cell must be contained in a <xref:System.Windows.Documents.Block> element; in this case <xref:System.Windows.Documents.Paragraph> elements are used.</span></span>  <span data-ttu-id="8b28c-108">테이블에 하이퍼링크도 호스팅합니다 (나타내는 <xref:System.Windows.Documents.Hyperlink> 요소) 바닥글 행에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b28c-108">The table also hosts a hyperlink (represented by the <xref:System.Windows.Documents.Hyperlink> element) in the footer row.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b28c-109">예</span><span class="sxs-lookup"><span data-stu-id="8b28c-109">Example</span></span>  
 [!code-xaml[TableSnippetsXAML#_TableXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 <span data-ttu-id="8b28c-110">다음 그림에서는 이 예제에 정의된 테이블이 렌더링되는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8b28c-110">The following figure shows how the table defined in this example renders.</span></span>  
  
 <span data-ttu-id="8b28c-111">![렌더링된 테이블.](../../../../docs/framework/wpf/advanced/media/tableeg.png "TableEG")</span><span class="sxs-lookup"><span data-stu-id="8b28c-111">![Rendered table.](../../../../docs/framework/wpf/advanced/media/tableeg.png "TableEG")</span></span>
