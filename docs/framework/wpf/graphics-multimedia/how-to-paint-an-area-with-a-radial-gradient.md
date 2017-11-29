---
title: "방법: 방사형 그라데이션으로 영역 그리기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with radial gradients
- radial gradients [WPF], painting with
- painting [WPF], with radial gradients
ms.assetid: b5d0fc8a-8986-4796-b003-a75b41a48928
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 55b707e4738a77a8fb093071ef6f5105b2200c16
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-paint-an-area-with-a-radial-gradient"></a><span data-ttu-id="cd832-102">방법: 방사형 그라데이션으로 영역 그리기</span><span class="sxs-lookup"><span data-stu-id="cd832-102">How to: Paint an Area with a Radial Gradient</span></span>
<span data-ttu-id="cd832-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.RadialGradientBrush> 방사형 그라데이션으로 영역을 그리는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="cd832-103">This example shows how to use the <xref:System.Windows.Media.RadialGradientBrush> class to paint an area with a radial gradient.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd832-104">예제</span><span class="sxs-lookup"><span data-stu-id="cd832-104">Example</span></span>  
 <span data-ttu-id="cd832-105">다음 예제에서는 한 <xref:System.Windows.Media.RadialGradientBrush> 노란색에서 파랑 라임 녹색으로 빨간색으로 전환 되는 방사형 그라데이션으로 여 사각형을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="cd832-105">The following example uses a <xref:System.Windows.Media.RadialGradientBrush> to paint a rectangle with a radial gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xaml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 <span data-ttu-id="cd832-106">다음 그림에서는 앞의 예제에서 그라데이션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cd832-106">The following illustration shows the gradient from the preceding example.</span></span> <span data-ttu-id="cd832-107">그라데이션의 중지 강조 표시 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cd832-107">The gradient's stops have been highlighted.</span></span>  
  
 <span data-ttu-id="cd832-108">![방사형 그라데이션의 그라데이션 중지점](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops")</span><span class="sxs-lookup"><span data-stu-id="cd832-108">![Gradient stops in a radial gradient](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cd832-109">이 항목의 예제는 제어점을 설정 하기 위한 기본 좌표계를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd832-109">The examples in this topic use the default coordinate system for setting control points.</span></span> <span data-ttu-id="cd832-110">경계 상자를 기준으로 기본 좌표계가: 0은 경계 상자의 0 %1의 경계 상자 100%를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd832-110">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="cd832-111">이 좌표 시스템을 설정 하 여 변경할 수 있습니다는 <xref:System.Windows.Media.GradientBrush.MappingMode%2A> 속성 값을 <xref:System.Windows.Media.BrushMappingMode.Absolute>합니다.</span><span class="sxs-lookup"><span data-stu-id="cd832-111">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span> <span data-ttu-id="cd832-112">절대 좌표계는 경계 상자를 기준으로 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd832-112">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="cd832-113">값은 로컬 공간에서 직접 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd832-113">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="cd832-114">에 대 한 추가 <xref:System.Windows.Media.RadialGradientBrush> 예제를 보려면 참조는 [브러시 샘플](http://go.microsoft.com/fwlink/?LinkID=159973)합니다.</span><span class="sxs-lookup"><span data-stu-id="cd832-114">For additional <xref:System.Windows.Media.RadialGradientBrush> examples, see the [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="cd832-115">그라데이션 및 브러시의 다른 형식에 대 한 자세한 내용은 참조 [단색 및 그라데이션 개요 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cd832-115">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span></span>
