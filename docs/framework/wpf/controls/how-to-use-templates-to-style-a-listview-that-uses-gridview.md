---
title: "방법: 템플릿을 사용하여 GridView 사용 ListView의 스타일 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 94bf964b-96c8-4bdf-a0c3-f5271b7cb565
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9abc19ca14cf512deff898f5f20d23870b8b7847
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-templates-to-style-a-listview-that-uses-gridview"></a><span data-ttu-id="59ea4-102">방법: 템플릿을 사용하여 GridView 사용 ListView의 스타일 지정</span><span class="sxs-lookup"><span data-stu-id="59ea4-102">How to: Use Templates to Style a ListView That Uses GridView</span></span>
<span data-ttu-id="59ea4-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.DataTemplate> 및 <xref:System.Windows.Style> 의 모양을 지정 하는 개체는 <xref:System.Windows.Controls.ListView> 컨트롤을 사용 하는 <xref:System.Windows.Controls.GridView> 보기 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="59ea4-103">This example shows how to use the <xref:System.Windows.DataTemplate> and <xref:System.Windows.Style> objects to specify the appearance of a <xref:System.Windows.Controls.ListView> control that uses a <xref:System.Windows.Controls.GridView> view mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59ea4-104">예</span><span class="sxs-lookup"><span data-stu-id="59ea4-104">Example</span></span>  
 <span data-ttu-id="59ea4-105">다음 예제에 나온 <xref:System.Windows.Style> 및 <xref:System.Windows.DataTemplate> 에 대 한 열 머리글의 모양을 사용자 지정 하는 개체는 <xref:System.Windows.Controls.GridViewColumn>합니다.</span><span class="sxs-lookup"><span data-stu-id="59ea4-105">The following examples show <xref:System.Windows.Style> and <xref:System.Windows.DataTemplate> objects that customize the appearance of a column header for a <xref:System.Windows.Controls.GridViewColumn>.</span></span>  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheaderstyle)]  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheadertemplate)]  
  
 <span data-ttu-id="59ea4-106">이 방법을 사용 하는 방법을 보여 주는 다음 예제 <xref:System.Windows.Style> 및 <xref:System.Windows.DataTemplate> 설정 하는 개체는 <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> 및 <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> 의 속성을 <xref:System.Windows.Controls.GridViewColumn>합니다.</span><span class="sxs-lookup"><span data-stu-id="59ea4-106">The following example shows how to use these <xref:System.Windows.Style> and <xref:System.Windows.DataTemplate> objects to set the <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> and <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> properties of a <xref:System.Windows.Controls.GridViewColumn>.</span></span> <span data-ttu-id="59ea4-107"><xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> 속성은 열 셀의 내용을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="59ea4-107">The <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property defines the content of the column cells.</span></span>  
  
 [!code-xaml[ListViewTemplate#GridViewColumnTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcolumntemplate)]  
  
 <span data-ttu-id="59ea4-108"><xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> 및 <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> 의 열 머리글 모양을 사용자 지정 하는 데 사용할 수 있는 여러 속성 중 두는 <xref:System.Windows.Controls.GridView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="59ea4-108">The <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> and <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> are only two of several properties that you can use to customize column header appearance for a <xref:System.Windows.Controls.GridView> control.</span></span> <span data-ttu-id="59ea4-109">자세한 내용은 [GridView 열 헤더 스타일 및 템플릿 개요](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="59ea4-109">For more information, see [GridView Column Header Styles and Templates Overview](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md).</span></span>  
  
 <span data-ttu-id="59ea4-110">다음 예제에서는 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.DataTemplate> 에 있는 셀의 모양을 사용자 지정 하는 <xref:System.Windows.Controls.GridViewColumn>합니다.</span><span class="sxs-lookup"><span data-stu-id="59ea4-110">The following example shows how to define a <xref:System.Windows.DataTemplate> that customizes the appearance of the cells in a <xref:System.Windows.Controls.GridViewColumn>.</span></span>  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 <span data-ttu-id="59ea4-111">다음 예제에서는이 사용 하는 방법을 보여 줍니다 <xref:System.Windows.DataTemplate> 의 콘텐츠를 정의 하는 <xref:System.Windows.Controls.GridViewColumn> 셀입니다.</span><span class="sxs-lookup"><span data-stu-id="59ea4-111">The following example shows how to use this <xref:System.Windows.DataTemplate> to define the content of a <xref:System.Windows.Controls.GridViewColumn> cell.</span></span> <span data-ttu-id="59ea4-112">이 서식 파일 대신 사용 되는 <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> 이전에 표시 되는 속성 <xref:System.Windows.Controls.GridViewColumn> 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="59ea4-112">This template is used instead of the <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property that is shown in the previous <xref:System.Windows.Controls.GridViewColumn> example.</span></span>  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
## <a name="see-also"></a><span data-ttu-id="59ea4-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59ea4-113">See Also</span></span>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="59ea4-114">GridView 개요</span><span class="sxs-lookup"><span data-stu-id="59ea4-114">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)  
 [<span data-ttu-id="59ea4-115">방법 항목</span><span class="sxs-lookup"><span data-stu-id="59ea4-115">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="59ea4-116">ListView 개요</span><span class="sxs-lookup"><span data-stu-id="59ea4-116">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)
