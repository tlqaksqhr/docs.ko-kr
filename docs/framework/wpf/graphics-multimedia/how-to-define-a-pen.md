---
title: "방법: 펜 정의"
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
- pens [WPF], defining
- creating [WPF], pens
ms.assetid: 7a4f2900-cdf9-49de-84e0-ba5d0ded4d33
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 02a3bef369f5bdd70588f3934e4199d7d4c703f7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-a-pen"></a><span data-ttu-id="2297f-102">방법: 펜 정의</span><span class="sxs-lookup"><span data-stu-id="2297f-102">How to: Define a Pen</span></span>
<span data-ttu-id="2297f-103">이 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Pen> 셰이프를 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2297f-103">This example shows how use a <xref:System.Windows.Media.Pen> to outline a shape.</span></span> <span data-ttu-id="2297f-104">간단한 만들려면 <xref:System.Windows.Media.Pen>를 지정 하면 해당 <xref:System.Windows.Media.Pen.Thickness%2A> 및 <xref:System.Windows.Media.Pen.Brush%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="2297f-104">To create a simple <xref:System.Windows.Media.Pen>, you need only specify its <xref:System.Windows.Media.Pen.Thickness%2A> and <xref:System.Windows.Media.Pen.Brush%2A>.</span></span> <span data-ttu-id="2297f-105">지정 하 여 보다 복잡 한 펜을 만들 수 있습니다는 <xref:System.Windows.Media.Pen.DashStyle%2A>, <xref:System.Windows.Media.Pen.DashCap%2A>, <xref:System.Windows.Media.Pen.LineJoin%2A>, <xref:System.Windows.Media.Pen.StartLineCap%2A>, 및 <xref:System.Windows.Media.Pen.EndLineCap%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="2297f-105">You can create more complex pen's by specifying a <xref:System.Windows.Media.Pen.DashStyle%2A>, <xref:System.Windows.Media.Pen.DashCap%2A>, <xref:System.Windows.Media.Pen.LineJoin%2A>, <xref:System.Windows.Media.Pen.StartLineCap%2A>, and <xref:System.Windows.Media.Pen.EndLineCap%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2297f-106">예</span><span class="sxs-lookup"><span data-stu-id="2297f-106">Example</span></span>  
 <span data-ttu-id="2297f-107">다음 예제에서는 한 <xref:System.Windows.Media.Pen> 에 의해 정의 되는 도형을 설명는 <xref:System.Windows.Media.GeometryDrawing>합니다.</span><span class="sxs-lookup"><span data-stu-id="2297f-107">The following example uses a <xref:System.Windows.Media.Pen> to outline a shape defined by a <xref:System.Windows.Media.GeometryDrawing>.</span></span>  
  
 [!code-csharp[PenExamples_snip#PenExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PenExamples_snip/CSharp/PenExample.cs#penexamplewholepage)]
 [!code-vb[PenExamples_snip#PenExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PenExamples_snip/VisualBasic/PenExample.vb#penexamplewholepage)]  
  
 <span data-ttu-id="2297f-108">![펜으로 만들어진 윤곽선](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple-pen.jpg "graphicsmm_simple_pen")</span><span class="sxs-lookup"><span data-stu-id="2297f-108">![Outlines produces by a Pen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple-pen.jpg "graphicsmm_simple_pen")</span></span>  
<span data-ttu-id="2297f-109">GeometryDrawing</span><span class="sxs-lookup"><span data-stu-id="2297f-109">A GeometryDrawing</span></span>
