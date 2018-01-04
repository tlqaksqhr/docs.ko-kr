---
title: "GDI+에서 그리기 화면 제한"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, clipping
- clipping [Windows Forms], using GDI+
- GDI+, restricting drawing surface
ms.assetid: 8b5f71d9-d2f0-4540-9c41-740f90fd4c26
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b7834c95959972e7264e1caa2cfc21b190341b21
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="restricting-the-drawing-surface-in-gdi"></a><span data-ttu-id="633d2-102">GDI+에서 그리기 화면 제한</span><span class="sxs-lookup"><span data-stu-id="633d2-102">Restricting the Drawing Surface in GDI+</span></span>
<span data-ttu-id="633d2-103">클리핑은 그리기 특정 사각형 또는 영역을 제한 하는 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="633d2-103">Clipping involves restricting drawing to a certain rectangle or region.</span></span> <span data-ttu-id="633d2-104">다음 그림과 문자열 "Hello" 하트 모양의 영역 잘립니다.</span><span class="sxs-lookup"><span data-stu-id="633d2-104">The following illustration shows the string "Hello" clipped to a heart-shaped region.</span></span>  
  
 <span data-ttu-id="633d2-105">![제한 된 그리기 화면](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art30.gif "AboutGdip02_Art30")</span><span class="sxs-lookup"><span data-stu-id="633d2-105">![Restricted Drawing Surface](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art30.gif "AboutGdip02_Art30")</span></span>  
  
## <a name="clipping-with-regions"></a><span data-ttu-id="633d2-106">클리핑 영역</span><span class="sxs-lookup"><span data-stu-id="633d2-106">Clipping with Regions</span></span>  
 <span data-ttu-id="633d2-107">영역 경로에서 생성 될 수 있습니다 및 클리핑에 대해 개략적으로 설명 된 텍스트를 사용할 수 있도록 경로 문자열의 윤곽을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="633d2-107">Regions can be constructed from paths, and paths can contain the outlines of strings, so you can use outlined text for clipping.</span></span> <span data-ttu-id="633d2-108">다음 그림에는 텍스트 문자열의 내부에 클리핑된 동심 타원의 집합을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="633d2-108">The following illustration shows a set of concentric ellipses clipped to the interior of a string of text.</span></span>  
  
 <span data-ttu-id="633d2-109">![제한 된 그리기 화면](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art31.gif "AboutGdip02_Art31")</span><span class="sxs-lookup"><span data-stu-id="633d2-109">![Restricted Drawing Surface](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art31.gif "AboutGdip02_Art31")</span></span>  
  
 <span data-ttu-id="633d2-110">클리핑을 그리려면 만들기는 <xref:System.Drawing.Graphics> 개체, 설정 해당 <xref:System.Drawing.Graphics.Clip%2A> 속성을 다음의 그리기 메서드를 호출 동일한 <xref:System.Drawing.Graphics> 개체:</span><span class="sxs-lookup"><span data-stu-id="633d2-110">To draw with clipping, create a <xref:System.Drawing.Graphics> object, set its <xref:System.Drawing.Graphics.Clip%2A> property, and then call the drawing methods of that same <xref:System.Drawing.Graphics> object:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#91](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#91)]
 [!code-vb[LinesCurvesAndShapes#91](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#91)]  
  
## <a name="see-also"></a><span data-ttu-id="633d2-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="633d2-111">See Also</span></span>  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Region?displayProperty=nameWithType>  
 [<span data-ttu-id="633d2-112">선, 곡선 및 도형</span><span class="sxs-lookup"><span data-stu-id="633d2-112">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="633d2-113">영역 사용</span><span class="sxs-lookup"><span data-stu-id="633d2-113">Using Regions</span></span>](../../../../docs/framework/winforms/advanced/using-regions.md)
