---
title: "방법: Drawing에 GuidelineSet 적용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GuidelineSet property [WPF], applying to drawings
- graphics [WPF], GuidelineSet property
ms.assetid: 45f3e0b4-8820-45a7-b865-b8ea5b17b0c8
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dd8d93d128c03cb9ee482860603e5734e96c6fc2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-apply-a-guidelineset-to-a-drawing"></a><span data-ttu-id="0f902-102">방법: Drawing에 GuidelineSet 적용</span><span class="sxs-lookup"><span data-stu-id="0f902-102">How to: Apply a GuidelineSet to a Drawing</span></span>
<span data-ttu-id="0f902-103">적용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.GuidelineSet> 에 <xref:System.Windows.Media.DrawingGroup>합니다.</span><span class="sxs-lookup"><span data-stu-id="0f902-103">This example shows how to apply a <xref:System.Windows.Media.GuidelineSet> to a <xref:System.Windows.Media.DrawingGroup>.</span></span>  
  
 <span data-ttu-id="0f902-104"><xref:System.Windows.Media.DrawingGroup> 클래스의 유일한 형식인 <xref:System.Windows.Media.Drawing> 올려진는 <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0f902-104">The <xref:System.Windows.Media.DrawingGroup> class is the only type of <xref:System.Windows.Media.Drawing> that has a <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> property.</span></span> <span data-ttu-id="0f902-105">적용 하는 <xref:System.Windows.Media.GuidelineSet> 를 다른 유형의 <xref:System.Windows.Media.Drawing>에 추가 <xref:System.Windows.Media.DrawingGroup> 다음 적용는 <xref:System.Windows.Media.GuidelineSet> 에 프로그램 <xref:System.Windows.Media.DrawingGroup>합니다.</span><span class="sxs-lookup"><span data-stu-id="0f902-105">To apply a <xref:System.Windows.Media.GuidelineSet> to another type of <xref:System.Windows.Media.Drawing>, add it to a <xref:System.Windows.Media.DrawingGroup> and then apply the <xref:System.Windows.Media.GuidelineSet> to your <xref:System.Windows.Media.DrawingGroup>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f902-106">예제</span><span class="sxs-lookup"><span data-stu-id="0f902-106">Example</span></span>  
 <span data-ttu-id="0f902-107">다음 예제에서는 두 개의 <xref:System.Windows.Media.DrawingGroup> 거의 동일한; 유일한 차이점은 개체: 두 번째 <xref:System.Windows.Media.DrawingGroup> 에 <xref:System.Windows.Media.GuidelineSet> 첫 번째 되지 않는다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0f902-107">The following example creates two <xref:System.Windows.Media.DrawingGroup> objects that are almost identical; the only difference is: the second <xref:System.Windows.Media.DrawingGroup> has a <xref:System.Windows.Media.GuidelineSet> and the first does not.</span></span>  
  
 <span data-ttu-id="0f902-108">다음 그림에서는 예제의 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0f902-108">The following illustration shows the output from the example.</span></span> <span data-ttu-id="0f902-109">둘 사이의 차이점은 렌더링 하므로 <xref:System.Windows.Media.DrawingGroup> 개체는 여러, 그리기의 일부를 확대 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f902-109">Because the rendering difference between the two <xref:System.Windows.Media.DrawingGroup> objects is so subtle, portions of the drawings are enlarged.</span></span>  
  
 <span data-ttu-id="0f902-110">![GuidelineSet이 있는 DrawingGroup과 없는 DrawingGroup](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")</span><span class="sxs-lookup"><span data-stu-id="0f902-110">![A DrawingGroup with and without a GuidelineSet](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupGuidelineSetExample.cs#graphicsmmdrawinggroupguidelinesetexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupGuidelineSetExample.xaml#graphicsmmdrawinggroupguidelinesetexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="0f902-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0f902-111">See Also</span></span>  
 <xref:System.Windows.Media.DrawingGroup>  
 <xref:System.Windows.Media.GuidelineSet>  
 [<span data-ttu-id="0f902-112">Drawing 개체 개요</span><span class="sxs-lookup"><span data-stu-id="0f902-112">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
