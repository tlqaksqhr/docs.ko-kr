---
title: "방법: 시각적 요소의 그리기 콘텐츠 열거"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retrieving the DrawingGroup value of a Visual [WPF]
- enumerating the contents of a Visual [WPF]
ms.assetid: 2974ddb3-2997-4713-8fd2-e93d549c58a8
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5c97926286076149a6eedf34bb70bbc76b2e0d8e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enumerate-drawing-content-of-a-visual"></a><span data-ttu-id="0e360-102">방법: 시각적 요소의 그리기 콘텐츠 열거</span><span class="sxs-lookup"><span data-stu-id="0e360-102">How to: Enumerate Drawing Content of a Visual</span></span>
<span data-ttu-id="0e360-103"><xref:System.Windows.Media.Drawing> 의 내용을 열거 하기 위한 개체 모델을 제공 하는 개체는 <xref:System.Windows.Media.Visual>합니다.</span><span class="sxs-lookup"><span data-stu-id="0e360-103">The <xref:System.Windows.Media.Drawing> object provide an object model for enumerating the contents of a <xref:System.Windows.Media.Visual>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e360-104">예</span><span class="sxs-lookup"><span data-stu-id="0e360-104">Example</span></span>  
 <span data-ttu-id="0e360-105">다음 예제에서는 <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> 를 검색할 메서드는 <xref:System.Windows.Media.DrawingGroup> 값은 <xref:System.Windows.Media.Visual> 고이 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e360-105">The following example uses the <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> method to retrieve the <xref:System.Windows.Media.DrawingGroup> value of a <xref:System.Windows.Media.Visual> and enumerate it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0e360-106">검색 하는 시각적 개체의 내용을 열거 하는 경우 <xref:System.Windows.Media.Drawing> 개체 및 하지 기본 표시에 나타나는 렌더링 데이터의 벡터 그래픽 명령 목록으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e360-106">When you are enumerating the contents of the visual, you are retrieving <xref:System.Windows.Media.Drawing> objects, and not the underlying representation of the render data as a vector graphics instruction list.</span></span> <span data-ttu-id="0e360-107">자세한 내용은 [WPF 그래픽 렌더링 개요](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0e360-107">For more information, see [WPF Graphics Rendering Overview](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a><span data-ttu-id="0e360-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0e360-108">See Also</span></span>  
 <xref:System.Windows.Media.Drawing>  
 <xref:System.Windows.Media.DrawingGroup>  
 <xref:System.Windows.Media.VisualTreeHelper>  
 [<span data-ttu-id="0e360-109">Drawing 개체 개요</span><span class="sxs-lookup"><span data-stu-id="0e360-109">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="0e360-110">WPF 그래픽 렌더링 개요</span><span class="sxs-lookup"><span data-stu-id="0e360-110">WPF Graphics Rendering Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)
