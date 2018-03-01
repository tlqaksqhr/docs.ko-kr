---
title: "방법: GridSplitter 표시"
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
- GridSplitter control [WPF], ensuring visibility of
ms.assetid: 0a62a964-89c8-48f0-9023-5df721a8cf47
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0b7587a093b2b43856a05693bb785a0465211782
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-sure-that-a-gridsplitter-is-visible"></a><span data-ttu-id="4ea46-102">방법: GridSplitter 표시</span><span class="sxs-lookup"><span data-stu-id="4ea46-102">How to: Make Sure That a GridSplitter Is Visible</span></span>
<span data-ttu-id="4ea46-103">있는지 확인 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.GridSplitter> 컨트롤에서 다른 컨트롤에 의해 숨겨지지 않은 <xref:System.Windows.Controls.Grid>합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea46-103">This example shows how to make sure a <xref:System.Windows.Controls.GridSplitter> control is not hidden by the other controls in a <xref:System.Windows.Controls.Grid>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ea46-104">예</span><span class="sxs-lookup"><span data-stu-id="4ea46-104">Example</span></span>  
 <span data-ttu-id="4ea46-105"><xref:System.Windows.Controls.Panel.Children%2A> 의 <xref:System.Windows.Controls.Grid> 컨트롤 태그 또는 코드에서 정의 된 순서 대로 렌더링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ea46-105">The <xref:System.Windows.Controls.Panel.Children%2A> of a <xref:System.Windows.Controls.Grid> control are rendered in the order that they are defined in markup or code.</span></span> <span data-ttu-id="4ea46-106"><xref:System.Windows.Controls.GridSplitter>마지막 요소로 정의 하지 않는 경우 다른 컨트롤에서 컨트롤을 숨길 수 있습니다는 <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션 또는 경우 제공 하는 다른 컨트롤에 더 높은 <xref:System.Windows.Controls.Panel.ZIndexProperty>합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea46-106"><xref:System.Windows.Controls.GridSplitter> controls can be hidden by other controls if you do not define them as the last elements in the <xref:System.Windows.Controls.Panel.Children%2A> collection or if you give other controls a higher <xref:System.Windows.Controls.Panel.ZIndexProperty>.</span></span>  
  
 <span data-ttu-id="4ea46-107">방지 하기 위해 숨겨진 <xref:System.Windows.Controls.GridSplitter> 컨트롤을 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea46-107">To prevent hidden <xref:System.Windows.Controls.GridSplitter> controls, do one of the following.</span></span>  
  
-   <span data-ttu-id="4ea46-108">다음 사항을 확인 <xref:System.Windows.Controls.GridSplitter> 컨트롤은 마지막 <xref:System.Windows.Controls.Panel.Children%2A> 에 추가 <xref:System.Windows.Controls.Grid>합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea46-108">Make sure that <xref:System.Windows.Controls.GridSplitter> controls are the last <xref:System.Windows.Controls.Panel.Children%2A> added to the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="4ea46-109">다음 예제와 <xref:System.Windows.Controls.GridSplitter> 에서 마지막 요소로 <xref:System.Windows.Controls.Panel.Children%2A> 의 컬렉션은 <xref:System.Windows.Controls.Grid>합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea46-109">The following example shows the <xref:System.Windows.Controls.GridSplitter> as the last element in the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.Grid>.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterLastChild](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterlastchild)]  
  
-   <span data-ttu-id="4ea46-110">설정의 <xref:System.Windows.Controls.Panel.ZIndexProperty> 에 <xref:System.Windows.Controls.GridSplitter> 숨길 수 있는 컨트롤 보다 길어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea46-110">Set the <xref:System.Windows.Controls.Panel.ZIndexProperty> on the <xref:System.Windows.Controls.GridSplitter> to be higher than a control that would otherwise hide it.</span></span> <span data-ttu-id="4ea46-111">다음 예제에서는 <xref:System.Windows.Controls.GridSplitter> 더 높은 제어 <xref:System.Windows.Controls.Panel.ZIndexProperty> 보다는 <xref:System.Windows.Controls.Button> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea46-111">The following example gives the <xref:System.Windows.Controls.GridSplitter> control a higher <xref:System.Windows.Controls.Panel.ZIndexProperty> than the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterZIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterzindex)]  
  
-   <span data-ttu-id="4ea46-112">숨길 수 있는 컨트롤의 여백을 설정는 <xref:System.Windows.Controls.GridSplitter> 있도록는 <xref:System.Windows.Controls.GridSplitter> 노출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ea46-112">Set margins on the control that would otherwise hide the <xref:System.Windows.Controls.GridSplitter> so that the <xref:System.Windows.Controls.GridSplitter> is exposed.</span></span> <span data-ttu-id="4ea46-113">다음 예제에서는 겹쳐져 컨트롤과 숨기기에 여백을 설정 하는 <xref:System.Windows.Controls.GridSplitter>합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea46-113">The following example sets margins on a control that would otherwise overlay and hide the <xref:System.Windows.Controls.GridSplitter>.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterMargin](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplittermargin)]  
  
## <a name="see-also"></a><span data-ttu-id="4ea46-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4ea46-114">See Also</span></span>  
 <xref:System.Windows.Controls.GridSplitter>  
 [<span data-ttu-id="4ea46-115">방법 항목</span><span class="sxs-lookup"><span data-stu-id="4ea46-115">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)
