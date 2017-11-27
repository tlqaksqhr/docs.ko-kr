---
title: "방법: 사각형 기하 도형의 모퉁이 둥글게 하기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- corners [WPF], rounding
- RectangleGeometry class [WPF], rounding corners
- graphics [WPF], rounding corners of RectangleGeometry objects [WPF]
- rounding corners of RectangleGeometry objects [WPF]
ms.assetid: 926644bc-1357-4c0b-ac81-694bd090ae87
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4cd857f7ce886095bcbe92ae57c350ce83bb5c7d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-round-the-corners-of-a-rectanglegeometry"></a><span data-ttu-id="fad68-102">방법: 사각형 기하 도형의 모퉁이 둥글게 하기</span><span class="sxs-lookup"><span data-stu-id="fad68-102">How to: Round the Corners of a RectangleGeometry</span></span>
<span data-ttu-id="fad68-103">모퉁이 둥글게 하는 <xref:System.Windows.Media.RectangleGeometry>설정, 해당 <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> 및 <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> 속성을 0 보다 큰 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fad68-103">To round the corners of a <xref:System.Windows.Media.RectangleGeometry>, set its <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> and <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> properties to a value greater than zero.</span></span> <span data-ttu-id="fad68-104">이 값이 클수록 더 둥글게 사각형의 모퉁이입니다.</span><span class="sxs-lookup"><span data-stu-id="fad68-104">The larger the values, the rounder the rectangle's corners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fad68-105">예제</span><span class="sxs-lookup"><span data-stu-id="fad68-105">Example</span></span>  
 <span data-ttu-id="fad68-106">다음 예제에서는 몇 가지 <xref:System.Windows.Media.RectangleGeometry> 서로 다른 개체 <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> 및 <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fad68-106">The following example shows several <xref:System.Windows.Media.RectangleGeometry> objects with different <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> and <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> settings.</span></span> <span data-ttu-id="fad68-107"><xref:System.Windows.Media.RectangleGeometry> 개체를 사용 하 여 표시 <xref:System.Windows.Shapes.Path> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="fad68-107">The <xref:System.Windows.Media.RectangleGeometry> objects are displayed using <xref:System.Windows.Shapes.Path> elements.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRoundedRectangleGeometryExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/RectangleGeometryRoundedCornerExample.xaml#graphicsmmroundedrectanglegeometryexamplewholepage)]  
  
 <span data-ttu-id="fad68-108">![여러 RadiusX &#47;의 사각형 RadiusY 설정](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rounded.png "graphicsmm_rounded")</span><span class="sxs-lookup"><span data-stu-id="fad68-108">![Rectangles with different RadiusX&#47;RadiusY settings](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rounded.png "graphicsmm_rounded")</span></span>  
<span data-ttu-id="fad68-109">모퉁이가 둥근 사각형</span><span class="sxs-lookup"><span data-stu-id="fad68-109">Rectangles with Rounded Corners</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fad68-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fad68-110">See Also</span></span>  
 [<span data-ttu-id="fad68-111">Geometry 개요</span><span class="sxs-lookup"><span data-stu-id="fad68-111">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="fad68-112">복합 도형 만들기</span><span class="sxs-lookup"><span data-stu-id="fad68-112">Create a Composite Shape</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)  
 [<span data-ttu-id="fad68-113">PathGeometry를 사용하여 도형 만들기</span><span class="sxs-lookup"><span data-stu-id="fad68-113">Create a Shape by Using a PathGeometry</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
