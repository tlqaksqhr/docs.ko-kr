---
title: "방법: TabControl을 사용하여 세로로 정렬된 탭 표시"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tab pages [Windows Forms], displaying side-aligned tabs
- tabs [Windows Forms], displaying side-aligned tabs
- TabControl control [Windows Forms], displaying side-aligned tabs
ms.assetid: 110d5abd-3ae3-4ded-95bf-778aaac798a0
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0dcbf2cc1aee1333ad5062f2a467adfd0dbe00c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-side-aligned-tabs-with-tabcontrol"></a><span data-ttu-id="68acb-102">방법: TabControl을 사용하여 세로로 정렬된 탭 표시</span><span class="sxs-lookup"><span data-stu-id="68acb-102">How to: Display Side-Aligned Tabs with TabControl</span></span>
<span data-ttu-id="68acb-103"><xref:System.Windows.Forms.TabControl>의 <xref:System.Windows.Forms.TabControl.Alignment%2A> 속성은 가로(컨트롤 위쪽 또는 아래쪽에 가로로)가 아니라 세로로(컨트롤 왼쪽 또는 오른쪽 가장자리에 세로로) 탭 표시를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="68acb-103">The <xref:System.Windows.Forms.TabControl.Alignment%2A> property of <xref:System.Windows.Forms.TabControl> supports displaying tabs vertically (along the left or right edge of the control), as opposed to horizontally (across the top or bottom of the control).</span></span> <span data-ttu-id="68acb-104">시각적 스타일을 사용하는 경우 <xref:System.Windows.Forms.TabPage> 개체의 <xref:System.Windows.Forms.TabPage.Text%2A> 속성이 탭에 표시되지 않으므로 기본적으로 이 세로 표시를 사용하면 사용자 환경이 저하됩니다.</span><span class="sxs-lookup"><span data-stu-id="68acb-104">By default, this vertical display results in a poor user experience, because the <xref:System.Windows.Forms.TabPage.Text%2A> property of the <xref:System.Windows.Forms.TabPage> object does not display in the tab when visual styles are enabled.</span></span> <span data-ttu-id="68acb-105">탭 내의 텍스트 방향을 제어하는 직접적인 방법도 없습니다. <xref:System.Windows.Forms.TabControl>에서 소유자 그리기를 사용하여 이 환경을 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68acb-105">There is also no direct way to control the direction of the text within the tab. You can use owner draw on <xref:System.Windows.Forms.TabControl> to improve this experience.</span></span>  
  
 <span data-ttu-id="68acb-106">다음 절차에서는 "소유자 그리기" 기능을 사용하여 탭 텍스트가 왼쪽에서 오른쪽으로 흐르는 오른쪽 맞춤 탭을 렌더링하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="68acb-106">The following procedure shows how to render right-aligned tabs, with the tab text running from left to right, by using the "owner draw" feature.</span></span>  
  
### <a name="to-display-right-aligned-tabs"></a><span data-ttu-id="68acb-107">오른쪽 맞춤 탭을 표시하려면</span><span class="sxs-lookup"><span data-stu-id="68acb-107">To display right-aligned tabs</span></span>  
  
1.  <span data-ttu-id="68acb-108">폼에 <xref:System.Windows.Forms.TabControl>을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="68acb-108">Add a <xref:System.Windows.Forms.TabControl> to your form.</span></span>  
  
2.  <span data-ttu-id="68acb-109"><xref:System.Windows.Forms.TabControl.Alignment%2A> 속성을 <xref:System.Windows.Forms.TabAlignment.Right>으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="68acb-109">Set the <xref:System.Windows.Forms.TabControl.Alignment%2A> property to <xref:System.Windows.Forms.TabAlignment.Right>.</span></span>  
  
3.  <span data-ttu-id="68acb-110">모든 탭의 너비가 같도록 <xref:System.Windows.Forms.TabControl.SizeMode%2A> 속성을 <xref:System.Windows.Forms.TabSizeMode.Fixed>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="68acb-110">Set the <xref:System.Windows.Forms.TabControl.SizeMode%2A> property to <xref:System.Windows.Forms.TabSizeMode.Fixed>, so that all tabs are the same width.</span></span>  
  
4.  <span data-ttu-id="68acb-111"><xref:System.Windows.Forms.TabControl.ItemSize%2A> 속성을 원하는 탭의 고정 크기로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="68acb-111">Set the <xref:System.Windows.Forms.TabControl.ItemSize%2A> property to the preferred fixed size for the tabs.</span></span> <span data-ttu-id="68acb-112"><xref:System.Windows.Forms.TabControl.ItemSize%2A> 속성은 탭이 오른쪽 맞춤인 경우에도 위쪽에 있는 것처럼 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="68acb-112">Keep in mind that the <xref:System.Windows.Forms.TabControl.ItemSize%2A> property behaves as though the tabs were on top, although they are right-aligned.</span></span> <span data-ttu-id="68acb-113">따라서 탭의 가로 크기를 늘리려면 <xref:System.Drawing.Size.Height%2A> 속성을 변경해야 하고, 탭의 높이를 늘리려면 <xref:System.Drawing.Size.Width%2A> 속성을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68acb-113">As a result, in order to make the tabs wider, you must change the <xref:System.Drawing.Size.Height%2A> property, and in order to make them taller, you must change the <xref:System.Drawing.Size.Width%2A> property.</span></span>  
  
     <span data-ttu-id="68acb-114">아래 코드 예제에서 최상의 결과를 얻으려면 탭의 <xref:System.Drawing.Size.Width%2A>를 25로 설정하고 <xref:System.Drawing.Size.Height%2A>를 100으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="68acb-114">For best result with the code example below, set the <xref:System.Drawing.Size.Width%2A> of the tabs to 25 and the <xref:System.Drawing.Size.Height%2A> to 100.</span></span>  
  
5.  <span data-ttu-id="68acb-115"><xref:System.Windows.Forms.TabControl.DrawMode%2A> 속성을 <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed>으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="68acb-115">Set the <xref:System.Windows.Forms.TabControl.DrawMode%2A> property to <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed>.</span></span>  
  
6.  <span data-ttu-id="68acb-116">텍스트를 왼쪽에서 오른쪽으로 렌더링하는 <xref:System.Windows.Forms.TabControl>의 <xref:System.Windows.Forms.TabControl.DrawItem> 이벤트에 대한 처리기를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="68acb-116">Define a handler for the <xref:System.Windows.Forms.TabControl.DrawItem> event of <xref:System.Windows.Forms.TabControl> that renders the text from left to right.</span></span>  
  
     [!code-csharp[TabControl.RightAlignedTabs#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/TabControl.RightAlignedTabs/CS/Form1.cs#1)]
     [!code-vb[TabControl.RightAlignedTabs#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/TabControl.RightAlignedTabs/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="68acb-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="68acb-117">See Also</span></span>  
 [<span data-ttu-id="68acb-118">TabControl 컨트롤</span><span class="sxs-lookup"><span data-stu-id="68acb-118">TabControl Control</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)
