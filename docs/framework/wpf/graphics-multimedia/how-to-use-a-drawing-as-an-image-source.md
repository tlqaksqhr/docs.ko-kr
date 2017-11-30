---
title: "방법: 그림을 이미지 소스로 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [WPF], drawings [WPF], as image sources
- image sources [WPF], drawings
- drawings [WPF], as image sources
ms.assetid: dcf71c7b-9e86-4b8e-8e39-0d0ce0389ef4
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0e100bc29afb17a37bc0c66621261347bea6d210
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-drawing-as-an-image-source"></a><span data-ttu-id="cf763-102">방법: 그림을 이미지 소스로 사용</span><span class="sxs-lookup"><span data-stu-id="cf763-102">How to: Use a Drawing as an Image Source</span></span>
<span data-ttu-id="cf763-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Drawing> 로 <xref:System.Windows.Controls.Image.Source%2A> 에 대 한 프로그램 <xref:System.Windows.Controls.Image> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf763-103">This example shows how to use a <xref:System.Windows.Media.Drawing> as the <xref:System.Windows.Controls.Image.Source%2A> for an <xref:System.Windows.Controls.Image> control.</span></span> <span data-ttu-id="cf763-104">표시 하는 <xref:System.Windows.Media.Drawing> 와 <xref:System.Windows.Controls.Image> 컨트롤을 사용 하 여는 <xref:System.Windows.Media.DrawingImage> 로 <xref:System.Windows.Controls.Image> 컨트롤의 <xref:System.Windows.Controls.Image.Source%2A> 설정는 <xref:System.Windows.Media.DrawingImage> 개체의 <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> 속성을 표시 하려는 드로잉을 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf763-104">To display a <xref:System.Windows.Media.Drawing> with an <xref:System.Windows.Controls.Image> control, use a <xref:System.Windows.Media.DrawingImage> as the <xref:System.Windows.Controls.Image> control's <xref:System.Windows.Controls.Image.Source%2A> and set the <xref:System.Windows.Media.DrawingImage> object's <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> property to the drawing you want to display.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf763-105">예제</span><span class="sxs-lookup"><span data-stu-id="cf763-105">Example</span></span>  
 <span data-ttu-id="cf763-106">다음 예제에서는 <xref:System.Windows.Media.DrawingImage> 및 <xref:System.Windows.Controls.Image> 컨트롤을 표시 한 <xref:System.Windows.Media.GeometryDrawing>합니다.</span><span class="sxs-lookup"><span data-stu-id="cf763-106">The following example uses a <xref:System.Windows.Media.DrawingImage> and an <xref:System.Windows.Controls.Image> control to display a <xref:System.Windows.Media.GeometryDrawing>.</span></span> <span data-ttu-id="cf763-107">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="cf763-107">This example produces the following output:</span></span>  
  
 <span data-ttu-id="cf763-108">![개의 GeometryDrawing](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span><span class="sxs-lookup"><span data-stu-id="cf763-108">![A GeometryDrawing of two ellipses](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span></span>  
<span data-ttu-id="cf763-109">DrawingImage</span><span class="sxs-lookup"><span data-stu-id="cf763-109">A DrawingImage</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="cf763-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf763-110">See Also</span></span>  
 <xref:System.Windows.Freezable.Freeze%2A>  
 [<span data-ttu-id="cf763-111">ImageDrawing을 사용하여 이미지 그리기</span><span class="sxs-lookup"><span data-stu-id="cf763-111">Draw an Image Using ImageDrawing</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-draw-an-image-using-imagedrawing.md)  
 [<span data-ttu-id="cf763-112">Drawing 개체 개요</span><span class="sxs-lookup"><span data-stu-id="cf763-112">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="cf763-113">Freezable 개체 개요</span><span class="sxs-lookup"><span data-stu-id="cf763-113">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="cf763-114">PresentationOptions:Freeze 특성</span><span class="sxs-lookup"><span data-stu-id="cf763-114">PresentationOptions:Freeze Attribute</span></span>](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)
