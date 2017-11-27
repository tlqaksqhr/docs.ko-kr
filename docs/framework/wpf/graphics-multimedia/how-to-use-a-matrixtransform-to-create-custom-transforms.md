---
title: "방법: MatrixTransform을 사용하여 사용자 지정 변환 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: graphics [WPF], custom Transforms
ms.assetid: 919381ca-989f-47cf-86b4-1094060236e4
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4995c5d712807e91b27c7afacd6f5b7015cb5898
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-matrixtransform-to-create-custom-transforms"></a><span data-ttu-id="5ecf4-102">방법: MatrixTransform을 사용하여 사용자 지정 변환 만들기</span><span class="sxs-lookup"><span data-stu-id="5ecf4-102">How to: Use a MatrixTransform to Create Custom Transforms</span></span>
<span data-ttu-id="5ecf4-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.MatrixTransform> 변환 (이동)에 위치, 늘이기, 및의 기울이기는 <xref:System.Windows.Controls.Button>합니다.</span><span class="sxs-lookup"><span data-stu-id="5ecf4-103">This example shows how to use a <xref:System.Windows.Media.MatrixTransform> to translate (move) the position, stretch, and skew of a <xref:System.Windows.Controls.Button>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5ecf4-104">사용 하 여는 <xref:System.Windows.Media.MatrixTransform> 클래스에서 제공 하지 않는 사용자 지정 변환을 만들 수는 <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, 또는 <xref:System.Windows.Media.TranslateTransform> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="5ecf4-104">Use the <xref:System.Windows.Media.MatrixTransform> class to create custom transformations that are not provided by the <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, or <xref:System.Windows.Media.TranslateTransform> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ecf4-105">예제</span><span class="sxs-lookup"><span data-stu-id="5ecf4-105">Example</span></span>  
 [!code-xaml[Transforms_snip#MatrixTransform](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MatrixTransformExample.xaml#matrixtransform)]  
  
## <a name="see-also"></a><span data-ttu-id="5ecf4-106">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ecf4-106">See Also</span></span>  
 <xref:System.Windows.Media.MatrixTransform>  
 <xref:System.Windows.Media.Transform>  
 [<span data-ttu-id="5ecf4-107">Transform 개요</span><span class="sxs-lookup"><span data-stu-id="5ecf4-107">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [<span data-ttu-id="5ecf4-108">방법 항목</span><span class="sxs-lookup"><span data-stu-id="5ecf4-108">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)  
 [<span data-ttu-id="5ecf4-109">WPF에서 Shape 및 기본 그리기 개요</span><span class="sxs-lookup"><span data-stu-id="5ecf4-109">Shapes and Basic Drawing in WPF Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
