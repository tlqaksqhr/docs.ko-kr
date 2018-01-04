---
title: "방법: ScrollViewer가 있는 Expander 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], Expander
- ScrollViewer control [WPF], with Expander control
- Expander control [WPF], creating
- controls [WPF], ScrollViewer
ms.assetid: 2ad124d2-2406-4157-aaf2-64e067298f01
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a2066ccce28138cfecf4e0b4574d45783a9ba4ca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-an-expander-with-a-scrollviewer"></a><span data-ttu-id="f2a1f-102">방법: ScrollViewer가 있는 Expander 만들기</span><span class="sxs-lookup"><span data-stu-id="f2a1f-102">How to: Create an Expander with a ScrollViewer</span></span>
<span data-ttu-id="f2a1f-103">만드는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Expander> 이미지, 텍스트 등의 복잡 한 콘텐츠를 포함 하는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="f2a1f-103">This example shows how to create an <xref:System.Windows.Controls.Expander> control that contains complex content, such as an image and text.</span></span> <span data-ttu-id="f2a1f-104">이 예제에서는 또한의 콘텐츠를 둘러싸는 <xref:System.Windows.Controls.Expander> 에 <xref:System.Windows.Controls.ScrollViewer> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2a1f-104">The example also encloses the content of the <xref:System.Windows.Controls.Expander> in a <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2a1f-105">예</span><span class="sxs-lookup"><span data-stu-id="f2a1f-105">Example</span></span>  
 <span data-ttu-id="f2a1f-106">만드는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Controls.Expander>합니다.</span><span class="sxs-lookup"><span data-stu-id="f2a1f-106">The following example shows how to create an <xref:System.Windows.Controls.Expander>.</span></span> <span data-ttu-id="f2a1f-107">이 예제에서는 사용는 <xref:System.Windows.Controls.Primitives.BulletDecorator> 제어를 정의 하기 위해 이미지 및 텍스트를 포함 하는 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="f2a1f-107">The example uses a <xref:System.Windows.Controls.Primitives.BulletDecorator> control, which contains an image and text, in order to define the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>.</span></span> <span data-ttu-id="f2a1f-108">A <xref:System.Windows.Controls.ScrollViewer> 컨트롤은 확장 된 콘텐츠를 스크롤 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2a1f-108">A <xref:System.Windows.Controls.ScrollViewer> control provides a method for scrolling the expanded content.</span></span>  
  
 <span data-ttu-id="f2a1f-109">이 예제에서는 설정 하는 <xref:System.Windows.FrameworkElement.Height%2A> 속성에는 <xref:System.Windows.Controls.ScrollViewer> 대신 콘텐츠에 대.</span><span class="sxs-lookup"><span data-stu-id="f2a1f-109">Note that the example sets the <xref:System.Windows.FrameworkElement.Height%2A> property on the <xref:System.Windows.Controls.ScrollViewer> instead of on the content.</span></span> <span data-ttu-id="f2a1f-110">경우는 <xref:System.Windows.FrameworkElement.Height%2A> 를 콘텐츠에 설정의 <xref:System.Windows.Controls.ScrollViewer> 사용자 콘텐츠를 스크롤할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f2a1f-110">If the <xref:System.Windows.FrameworkElement.Height%2A> is set on the content, the <xref:System.Windows.Controls.ScrollViewer> does not allow the user to scroll the content.</span></span> <span data-ttu-id="f2a1f-111"><xref:System.Windows.FrameworkElement.Width%2A> 속성이에 설정 되는 <xref:System.Windows.Controls.Expander> 컨트롤과이 설정에 적용 됩니다는 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 및 확장 된 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="f2a1f-111">The <xref:System.Windows.FrameworkElement.Width%2A> property is set on the <xref:System.Windows.Controls.Expander> control and this setting applies to the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and the expanded content.</span></span>  
  
 [!code-xaml[ExpanderRichContent#CreateExpander](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#createexpander)]  
  
 [!code-csharp[ExpanderRichContent#CreateExpanderCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#createexpandercode)]  
  
## <a name="see-also"></a><span data-ttu-id="f2a1f-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f2a1f-112">See Also</span></span>  
 <xref:System.Windows.Controls.Expander>  
 [<span data-ttu-id="f2a1f-113">Expander 개요</span><span class="sxs-lookup"><span data-stu-id="f2a1f-113">Expander Overview</span></span>](../../../../docs/framework/wpf/controls/expander-overview.md)  
 [<span data-ttu-id="f2a1f-114">방법 항목</span><span class="sxs-lookup"><span data-stu-id="f2a1f-114">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/expander-how-to-topics.md)
