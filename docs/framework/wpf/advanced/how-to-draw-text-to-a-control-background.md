---
title: "방법: 컨트롤의 배경에 텍스트 그리기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], drawing text to backgrounds
- text [WPF], drawing to control backgrounds
- drawing [WPF], text to control backgrounds
- backgrounds [WPF], drawing text to
- typography [WPF], drawing text to control backgrounds
ms.assetid: 686d8fba-f61c-4974-a871-c635d67a7f69
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 091be80e055279685c9dba33dd6b6635e64eaff0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-text-to-a-control39s-background"></a><span data-ttu-id="1ce3f-102">방법: 컨트롤의 배경에 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="1ce3f-102">How to: Draw Text to a Control&#39;s Background</span></span>
<span data-ttu-id="1ce3f-103">텍스트 문자열을 변환 하 여 컨트롤의 배경에 직접 텍스트를 그릴 수 있습니다는 <xref:System.Windows.Media.FormattedText> 개체를 다음 개체를 컨트롤의 그리기 <xref:System.Windows.Media.DrawingContext>합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce3f-103">You can draw text directly to the background of a control by converting a text string to a <xref:System.Windows.Media.FormattedText> object, and then drawing the object to the control's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="1ce3f-104">파생 된 개체의 배경 그리기가이 기술을 사용할 수도 있습니다 <xref:System.Windows.Controls.Panel>와 같은 <xref:System.Windows.Controls.Canvas> 및 <xref:System.Windows.Controls.StackPanel>합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce3f-104">You can also use this technique for drawing to the background of objects derived from <xref:System.Windows.Controls.Panel>, such as <xref:System.Windows.Controls.Canvas> and <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
 <span data-ttu-id="1ce3f-105">![텍스트를 배경으로 표시 하는 컨트롤](../../../../docs/framework/wpf/advanced/media/drawtext2background01.png "DrawText2Background01")</span><span class="sxs-lookup"><span data-stu-id="1ce3f-105">![Controls displaying text as background](../../../../docs/framework/wpf/advanced/media/drawtext2background01.png "DrawText2Background01")</span></span>  
<span data-ttu-id="1ce3f-106">사용자 지정 텍스트 배경이 있는 컨트롤의 예</span><span class="sxs-lookup"><span data-stu-id="1ce3f-106">Example of controls with custom text backgrounds</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ce3f-107">예</span><span class="sxs-lookup"><span data-stu-id="1ce3f-107">Example</span></span>  
 <span data-ttu-id="1ce3f-108">컨트롤의 배경에 그리려면 만들 새 <xref:System.Windows.Media.DrawingBrush> 개체 및 개체의 변환 된 텍스트를 그립니다. <xref:System.Windows.Media.DrawingContext>합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce3f-108">To draw to the background of a control, create a new <xref:System.Windows.Media.DrawingBrush> object and draw the converted text to the object's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="1ce3f-109">그런 다음 새 할당 <xref:System.Windows.Media.DrawingBrush> 컨트롤의 배경 속성에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ce3f-109">Then, assign the new <xref:System.Windows.Media.DrawingBrush> to the control's background property.</span></span>  
  
 <span data-ttu-id="1ce3f-110">다음 코드 예제에서는 만드는 방법을 보여 줍니다.는 <xref:System.Windows.Media.FormattedText> 개체와의 배경에 그리기는 <xref:System.Windows.Controls.Label> 및 <xref:System.Windows.Controls.Button> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1ce3f-110">The following code example shows how to create a <xref:System.Windows.Media.FormattedText> object and draw to the background of a <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Button> object.</span></span>  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## <a name="see-also"></a><span data-ttu-id="1ce3f-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1ce3f-111">See Also</span></span>  
 <xref:System.Windows.Media.FormattedText>  
 [<span data-ttu-id="1ce3f-112">서식 있는 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="1ce3f-112">Drawing Formatted Text</span></span>](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)
