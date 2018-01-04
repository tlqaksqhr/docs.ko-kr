---
title: "방법: 현재 위치에서 요소가 회전하도록 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ae76d33a30853107cbecf0749230aefce77a866d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-an-element-spin-in-place"></a><span data-ttu-id="43216-102">방법: 현재 위치에서 요소가 회전하도록 만들기</span><span class="sxs-lookup"><span data-stu-id="43216-102">How to: Make an Element Spin in Place</span></span>
<span data-ttu-id="43216-103">요소를 사용 하 여 회전 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.RotateTransform> 및 <xref:System.Windows.Media.Animation.DoubleAnimation>합니다.</span><span class="sxs-lookup"><span data-stu-id="43216-103">This example shows how to make an element spin by using a <xref:System.Windows.Media.RotateTransform> and a <xref:System.Windows.Media.Animation.DoubleAnimation>.</span></span>  
  
 <span data-ttu-id="43216-104">다음 예제에서는 적용는 <xref:System.Windows.Media.RotateTransform> 에 <xref:System.Windows.UIElement.RenderTransform%2A> 요소의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="43216-104">The following example applies the <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span> <span data-ttu-id="43216-105">이 예제에서는 사용는 <xref:System.Windows.Media.Animation.DoubleAnimation> 애니메이션 효과를 줄의 <xref:System.Windows.Media.RotateTransform.Angle%2A> 의 <xref:System.Windows.Media.RotateTransform>합니다.</span><span class="sxs-lookup"><span data-stu-id="43216-105">The example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.Media.RotateTransform.Angle%2A> of the <xref:System.Windows.Media.RotateTransform>.</span></span> <span data-ttu-id="43216-106">이 예제에서는 요소를 현재 위치에서 회전을 하려면 설정는 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 점 (0.5, 0.5)는 요소의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="43216-106">To make the element spin in place, the example sets the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property of the element to the point (0.5, 0.5).</span></span>  
  
## <a name="example"></a><span data-ttu-id="43216-107">예</span><span class="sxs-lookup"><span data-stu-id="43216-107">Example</span></span>  
 [!code-xaml[transformanimations_snip#11](../../../../samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 <span data-ttu-id="43216-108">더 많은 변환 예제를 포함 하는 전체 샘플을 참조 하십시오. [2 차원 변환은 샘플](http://go.microsoft.com/fwlink/?LinkID=158252)합니다.</span><span class="sxs-lookup"><span data-stu-id="43216-108">For the complete sample, which includes more transformation examples, see [2-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43216-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="43216-109">See Also</span></span>  
 [<span data-ttu-id="43216-110">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="43216-110">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="43216-111">Transform 개요</span><span class="sxs-lookup"><span data-stu-id="43216-111">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
