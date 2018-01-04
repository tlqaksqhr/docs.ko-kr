---
title: "방법: GridSplitter로 열 크기 조정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- grid columns [WPF], resizing
- GridSplitter control [WPF], resizing grid columns
- resizing grid columns [WPF]
ms.assetid: 47b20fe6-7adc-4aa6-9693-b4e184eef74b
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d68d829e5543b1c299668493c11b62ccb11d81af
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-resize-columns-with-a-gridsplitter"></a><span data-ttu-id="87997-102">방법: GridSplitter로 열 크기 조정</span><span class="sxs-lookup"><span data-stu-id="87997-102">How to: Resize Columns with a GridSplitter</span></span>
<span data-ttu-id="87997-103">이 예제에는 세로 만드는 방법을 보여 줍니다 <xref:System.Windows.Controls.GridSplitter> 의 두 열 사이의 간격을 재배포 하려면는 <xref:System.Windows.Controls.Grid> 의 크기를 변경 하지 않고는 <xref:System.Windows.Controls.Grid>합니다.</span><span class="sxs-lookup"><span data-stu-id="87997-103">This example shows how to create a vertical <xref:System.Windows.Controls.GridSplitter> in order to redistribute the space between two columns in a <xref:System.Windows.Controls.Grid> without changing the dimensions of the <xref:System.Windows.Controls.Grid>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87997-104">예</span><span class="sxs-lookup"><span data-stu-id="87997-104">Example</span></span>  
 <span data-ttu-id="87997-105">**열의 가장자리를 오버레이하는 GridSplitter를 만드는 방법**</span><span class="sxs-lookup"><span data-stu-id="87997-105">**How to create a GridSplitter that overlays the edge of a column**</span></span>  
  
 <span data-ttu-id="87997-106">지정 하는 <xref:System.Windows.Controls.GridSplitter> 에 인접 한 열 크기를 조정 하는 <xref:System.Windows.Controls.Grid>설정는 <xref:System.Windows.Controls.Grid.Column%2A> 크기를 조정할 열 중 하나에 연결 된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="87997-106">To specify a <xref:System.Windows.Controls.GridSplitter> that resizes adjacent columns in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Column%2A> attached property to one of the columns that you want to resize.</span></span> <span data-ttu-id="87997-107">경우에 <xref:System.Windows.Controls.Grid> 에 둘 이상의 행이 설정는 <xref:System.Windows.Controls.Grid.RowSpan%2A> 연결 된 속성의 행 수입니다.</span><span class="sxs-lookup"><span data-stu-id="87997-107">If your <xref:System.Windows.Controls.Grid> has more than one row, set the <xref:System.Windows.Controls.Grid.RowSpan%2A> attached property to the number of rows.</span></span> <span data-ttu-id="87997-108">다음 설정의 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 속성을 <xref:System.Windows.HorizontalAlignment.Left> 또는 <xref:System.Windows.HorizontalAlignment.Right> (설정한 어떤 맞춤 크기를 조정 하려면 두 개의 열에 따라 다름).</span><span class="sxs-lookup"><span data-stu-id="87997-108">Then set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property to <xref:System.Windows.HorizontalAlignment.Left> or <xref:System.Windows.HorizontalAlignment.Right> (which alignment you set depends on which two columns you want to resize).</span></span> <span data-ttu-id="87997-109">마지막으로 설정 된 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 속성을 <xref:System.Windows.VerticalAlignment.Stretch>합니다.</span><span class="sxs-lookup"><span data-stu-id="87997-109">Finally, set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> property to <xref:System.Windows.VerticalAlignment.Stretch>.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterColumnOverlay](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplittercolumnoverlay)]  
  
 <span data-ttu-id="87997-110">A <xref:System.Windows.Controls.GridSplitter> 고유한 열가지고 있지 않은 다른 컨트롤에 의해 가려질 수 있습니다는 <xref:System.Windows.Controls.Grid>합니다.</span><span class="sxs-lookup"><span data-stu-id="87997-110">A <xref:System.Windows.Controls.GridSplitter> that does not have its own column may be obscured by other controls in the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="87997-111">이 문제를 방지하는 방법에 대한 자세한 내용은 [Make Sure That a GridSplitter Is Visible](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md)(GridSplitter가 표시되는지 확인)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="87997-111">For more information about how to prevent this issue, see [Make Sure That a GridSplitter Is Visible](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md).</span></span>  
  
 <span data-ttu-id="87997-112">**열을 차지하는 GridSplitter를 만드는 방법**</span><span class="sxs-lookup"><span data-stu-id="87997-112">**How to create a GridSplitter that occupies a column**</span></span>  
  
 <span data-ttu-id="87997-113">지정 하는 <xref:System.Windows.Controls.GridSplitter> 에 열을 차지 하는 <xref:System.Windows.Controls.Grid>로 설정는 <xref:System.Windows.Controls.Grid.Column%2A> 크기를 조정할 열 중 하나에 연결 된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="87997-113">To specify a <xref:System.Windows.Controls.GridSplitter> that occupies a column in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Column%2A> attached property to one of the columns that you want to resize.</span></span> <span data-ttu-id="87997-114">눈금에 둘 이상의 행을 있으면 설정 하는 <xref:System.Windows.Controls.Grid.RowSpan%2A> 연결 된 속성의 행 수입니다.</span><span class="sxs-lookup"><span data-stu-id="87997-114">If your Grid has more than one row, set the <xref:System.Windows.Controls.Grid.RowSpan%2A> attached property to the number of rows.</span></span> <span data-ttu-id="87997-115">다음 설정는 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 를 <xref:System.Windows.HorizontalAlignment.Center>설정는 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 속성을 <xref:System.Windows.VerticalAlignment.Stretch>, 설정 및는 <xref:System.Windows.Controls.ColumnDefinition.Width%2A> 포함 하는 열의 <xref:System.Windows.Controls.GridSplitter> 를 <xref:System.Windows.GridLength.Auto%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="87997-115">Then set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> to <xref:System.Windows.HorizontalAlignment.Center>, set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> property to <xref:System.Windows.VerticalAlignment.Stretch>, and set the <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of the column that contains the <xref:System.Windows.Controls.GridSplitter> to <xref:System.Windows.GridLength.Auto%2A>.</span></span>  
  
 <span data-ttu-id="87997-116">다음 예제에서는 세로 정의 하는 방법을 보여 줍니다 <xref:System.Windows.Controls.GridSplitter> 열 점유 하 고 어느 쪽에 대 한 열 크기를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="87997-116">The following example shows how to define a vertical <xref:System.Windows.Controls.GridSplitter> that occupies a column and resizes the columns on either side of it.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart2)]  
  
## <a name="see-also"></a><span data-ttu-id="87997-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87997-117">See Also</span></span>  
 <xref:System.Windows.Controls.GridSplitter>  
 [<span data-ttu-id="87997-118">방법 항목</span><span class="sxs-lookup"><span data-stu-id="87997-118">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)
