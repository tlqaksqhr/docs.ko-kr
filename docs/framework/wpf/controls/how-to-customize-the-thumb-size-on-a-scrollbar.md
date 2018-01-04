---
title: "방법: ScrollBar의 Thumb 크기 사용자 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ScrollBar control [WPF]
- customizing thumb size [WPF]
- thumb size [WPF]
ms.assetid: fa32b866-5ca1-4e73-85e7-2ac64b80d194
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e88a7afb9c98179fbcb4a67217edd411d4fe9567
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-customize-the-thumb-size-on-a-scrollbar"></a><span data-ttu-id="36e53-102">방법: ScrollBar의 Thumb 크기 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="36e53-102">How to: Customize the Thumb Size on a ScrollBar</span></span>
<span data-ttu-id="36e53-103">이 항목에서는 설정 하는 방법에 설명 된 <xref:System.Windows.Controls.Primitives.Thumb> 의 <xref:System.Windows.Controls.Primitives.ScrollBar> 최소 크기를 지정 하는 방법 및 고정된 크기는 <xref:System.Windows.Controls.Primitives.Thumb> 의 <xref:System.Windows.Controls.Primitives.ScrollBar>합니다.</span><span class="sxs-lookup"><span data-stu-id="36e53-103">This topic explains how to set the <xref:System.Windows.Controls.Primitives.Thumb> of a <xref:System.Windows.Controls.Primitives.ScrollBar> to a fixed size and how to specify a minimum size for the <xref:System.Windows.Controls.Primitives.Thumb> of a <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36e53-104">예</span><span class="sxs-lookup"><span data-stu-id="36e53-104">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="36e53-105">설명</span><span class="sxs-lookup"><span data-stu-id="36e53-105">Description</span></span>  
 <span data-ttu-id="36e53-106">다음 예제에서는 한 <xref:System.Windows.Controls.Primitives.ScrollBar> 올려진는 <xref:System.Windows.Controls.Primitives.Thumb> 고정 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="36e53-106">The following example creates a <xref:System.Windows.Controls.Primitives.ScrollBar> that has a <xref:System.Windows.Controls.Primitives.Thumb> with a fixed size.</span></span> <span data-ttu-id="36e53-107">예제에서는 <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> 속성은 <xref:System.Windows.Controls.Primitives.Thumb> 를 <xref:System.Double.NaN> 의 높이 설정 하 고는 <xref:System.Windows.Controls.Primitives.Thumb>합니다.</span><span class="sxs-lookup"><span data-stu-id="36e53-107">The example sets the <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> property of the <xref:System.Windows.Controls.Primitives.Thumb> to <xref:System.Double.NaN> and sets the height of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  <span data-ttu-id="36e53-108">가로 만들려면 <xref:System.Windows.Controls.Primitives.ScrollBar> 와 <xref:System.Windows.Controls.Primitives.Thumb> 고정된 폭을의 너비를 설정는 <xref:System.Windows.Controls.Primitives.Thumb>합니다.</span><span class="sxs-lookup"><span data-stu-id="36e53-108">To create a horizontal <xref:System.Windows.Controls.Primitives.ScrollBar> with a <xref:System.Windows.Controls.Primitives.Thumb> that has a fixed width, set the width of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="36e53-109">코드</span><span class="sxs-lookup"><span data-stu-id="36e53-109">Code</span></span>  
 [!code-xaml[ScrollBarCustomThumbSize#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#1)]  
  
## <a name="description"></a><span data-ttu-id="36e53-110">설명</span><span class="sxs-lookup"><span data-stu-id="36e53-110">Description</span></span>  
 <span data-ttu-id="36e53-111">다음 예제에서는 한 <xref:System.Windows.Controls.Primitives.ScrollBar> 올려진는 <xref:System.Windows.Controls.Primitives.Thumb> 최소 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="36e53-111">The following example creates a <xref:System.Windows.Controls.Primitives.ScrollBar> that has a <xref:System.Windows.Controls.Primitives.Thumb> with a minimum size.</span></span> <span data-ttu-id="36e53-112">값을 설정 하는 예제 <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="36e53-112">The example sets the value of <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>.</span></span> <span data-ttu-id="36e53-113">가로 만들려면 <xref:System.Windows.Controls.Primitives.ScrollBar> 와 <xref:System.Windows.Controls.Primitives.Thumb> 최소 너비, 설정는 <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="36e53-113">To create a horizontal <xref:System.Windows.Controls.Primitives.ScrollBar> with a <xref:System.Windows.Controls.Primitives.Thumb> that has a minimum width, set the <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="36e53-114">코드</span><span class="sxs-lookup"><span data-stu-id="36e53-114">Code</span></span>  
 [!code-xaml[ScrollBarCustomThumbSize#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#2)]  
  
## <a name="see-also"></a><span data-ttu-id="36e53-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="36e53-115">See Also</span></span>  
 [<span data-ttu-id="36e53-116">ScrollBar 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="36e53-116">ScrollBar Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/scrollbar-styles-and-templates.md)
