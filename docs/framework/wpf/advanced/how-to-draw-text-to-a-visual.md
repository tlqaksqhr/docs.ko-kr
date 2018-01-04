---
title: "방법: 시각적 요소에 텍스트 그리기"
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
- typography [WPF], drawing text to visuals
- visuals [WPF], drawing text to
- text [WPF], drawing to visuals
- drawing [WPF], text to visuals
ms.assetid: fee4003c-e8a6-46ec-babd-2c7f4231a101
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 765d2102bc4466c2b194e03c9688212e04005ca2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-text-to-a-visual"></a><span data-ttu-id="29b73-102">방법: 시각적 요소에 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="29b73-102">How to: Draw Text to a Visual</span></span>
<span data-ttu-id="29b73-103">텍스트를 그리는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Media.DrawingVisual> 를 사용 하는 <xref:System.Windows.Media.DrawingContext> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="29b73-103">The following example shows how to draw text to a <xref:System.Windows.Media.DrawingVisual> using a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="29b73-104">그리기 컨텍스트 호출에서 반환 되는 <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> 의 메서드는 <xref:System.Windows.Media.DrawingVisual> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="29b73-104">A drawing context is returned by calling the <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> method of a <xref:System.Windows.Media.DrawingVisual> object.</span></span> <span data-ttu-id="29b73-105">그리기 컨텍스트에 그래픽 및 텍스트를 그릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29b73-105">You can draw graphics and text into a drawing context.</span></span>  
  
 <span data-ttu-id="29b73-106">텍스트를 그리는 그리기 컨텍스트에 사용 하 여는 <xref:System.Windows.Media.DrawingContext.DrawText%2A> 의 메서드는 <xref:System.Windows.Media.DrawingContext> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="29b73-106">To draw text into the drawing context, use the <xref:System.Windows.Media.DrawingContext.DrawText%2A> method of a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="29b73-107">내용을 그리기 컨텍스트에 그리기 작업을 완료 하는 경우 호출의 <xref:System.Windows.Media.DrawingContext.Close%2A> 메서드를 그리기 컨텍스트에 닫고 내용을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="29b73-107">When you are finished drawing content into the drawing context, call the <xref:System.Windows.Media.DrawingContext.Close%2A> method to close the drawing context and persist the content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29b73-108">예</span><span class="sxs-lookup"><span data-stu-id="29b73-108">Example</span></span>  
 [!code-csharp[DrawingVisualSample#110](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
>  <span data-ttu-id="29b73-109">위의 코드 예제가 발췌된 전체 코드 샘플을 보려면 [DrawingVisuals를 사용하여 적중 테스트 샘플](http://go.microsoft.com/fwlink/?LinkID=159994)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="29b73-109">For the complete code sample from which the preceding code example was extracted, see [Hit Test Using DrawingVisuals Sample](http://go.microsoft.com/fwlink/?LinkID=159994).</span></span>
