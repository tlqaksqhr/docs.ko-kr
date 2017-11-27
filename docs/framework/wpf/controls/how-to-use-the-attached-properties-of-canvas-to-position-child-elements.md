---
title: "방법: Canvas의 연결된 속성을 사용하여 자식 요소 배치"
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
- cpp
helpviewer_keywords:
- attached properties [WPF Designer]
- Canvas control [WPF], attached properties
ms.assetid: 48f1d25d-3820-4107-a4cc-d6c1e5664a44
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 85ee852c868f26937494d5d340d2db4210224754
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-the-attached-properties-of-canvas-to-position-child-elements"></a><span data-ttu-id="516e0-102">방법: Canvas의 연결된 속성을 사용하여 자식 요소 배치</span><span class="sxs-lookup"><span data-stu-id="516e0-102">How to: Use the Attached Properties of Canvas to Position Child Elements</span></span>
<span data-ttu-id="516e0-103">연결된 된 속성을 사용 하는 방법을 보여 주는이 예제 <xref:System.Windows.Controls.Canvas> 자식 요소의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="516e0-103">This example shows how to use the attached properties of <xref:System.Windows.Controls.Canvas> to position child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="516e0-104">예제</span><span class="sxs-lookup"><span data-stu-id="516e0-104">Example</span></span>  
 <span data-ttu-id="516e0-105">다음 예제에서는 4 개의 <xref:System.Windows.Controls.Button> 부모의 자식 요소로 요소 <xref:System.Windows.Controls.Canvas>합니다.</span><span class="sxs-lookup"><span data-stu-id="516e0-105">The following example adds four <xref:System.Windows.Controls.Button> elements as child elements of a parent <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="516e0-106">이 고유한 연결 된 속성을 각 자식 요소 <xref:System.Windows.Controls.Canvas>: <xref:System.Windows.Controls.Canvas.Bottom%2A>, <xref:System.Windows.Controls.Canvas.Left%2A>, <xref:System.Windows.Controls.Canvas.Right%2A>, 및 <xref:System.Windows.Controls.Canvas.Top%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="516e0-106">Each child element represents a distinct attached property of <xref:System.Windows.Controls.Canvas>: <xref:System.Windows.Controls.Canvas.Bottom%2A>, <xref:System.Windows.Controls.Canvas.Left%2A>, <xref:System.Windows.Controls.Canvas.Right%2A>, and <xref:System.Windows.Controls.Canvas.Top%2A>.</span></span> <span data-ttu-id="516e0-107">각 <xref:System.Windows.Controls.Button> 에서 부모에 상대적인 배치 <xref:System.Windows.Controls.Canvas> 할당된 된 속성 값에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="516e0-107">Each <xref:System.Windows.Controls.Button> is positioned relative to the parent <xref:System.Windows.Controls.Canvas> and according to its assigned property value.</span></span>  
  
 [!code-cpp[CanvasAttachedProperties#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/CanvasAttachedProperties/CPP/CanvasAttachedProps.cpp#1)]
 [!code-csharp[CanvasAttachedProperties#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasAttachedProperties/CSharp/CanvasAttachedProps.cs#1)]
 [!code-vb[CanvasAttachedProperties#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasAttachedProperties/VisualBasic/CanvasAttachedProps.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="516e0-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="516e0-108">See Also</span></span>  
 <xref:System.Windows.Controls.Canvas>  
 <xref:System.Windows.Controls.Canvas.Bottom%2A>  
 <xref:System.Windows.Controls.Canvas.Left%2A>  
 <xref:System.Windows.Controls.Canvas.Right%2A>  
 <xref:System.Windows.Controls.Canvas.Top%2A>  
 <xref:System.Windows.Controls.Button>  
 [<span data-ttu-id="516e0-109">패널 개요</span><span class="sxs-lookup"><span data-stu-id="516e0-109">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="516e0-110">방법 항목</span><span class="sxs-lookup"><span data-stu-id="516e0-110">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/canvas-how-to-topics.md)  
 [<span data-ttu-id="516e0-111">연결된 속성 개요</span><span class="sxs-lookup"><span data-stu-id="516e0-111">Attached Properties Overview</span></span>](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)
