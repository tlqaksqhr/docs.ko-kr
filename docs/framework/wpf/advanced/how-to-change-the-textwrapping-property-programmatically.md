---
title: "방법: 프로그래밍 방식으로 TextWrapping 속성 변경"
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
- documents [WPF], changing TextWrapping property programmatically
- TextWrapping property [WPF], changing programmatically
ms.assetid: 30d25554-4c82-4df9-a8d6-35683a4a13bb
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ca87d651f66edba00280a57ca1468af33657a329
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-textwrapping-property-programmatically"></a><span data-ttu-id="dc941-102">방법: 프로그래밍 방식으로 TextWrapping 속성 변경</span><span class="sxs-lookup"><span data-stu-id="dc941-102">How to: Change the TextWrapping Property Programmatically</span></span>
## <a name="example"></a><span data-ttu-id="dc941-103">예</span><span class="sxs-lookup"><span data-stu-id="dc941-103">Example</span></span>  
 <span data-ttu-id="dc941-104">다음 코드 예제에서는의 값을 변경 하는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> 속성 프로그래밍 방식으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc941-104">The following code example shows how to change the value of the <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> property programmatically.</span></span>  
  
 <span data-ttu-id="dc941-105">세 가지 <xref:System.Windows.Controls.Button> 요소 안에 배치 되는 <xref:System.Windows.Controls.StackPanel> 요소에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="dc941-105">Three <xref:System.Windows.Controls.Button> elements are placed within a <xref:System.Windows.Controls.StackPanel> element in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="dc941-106">각 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 에 대 한 이벤트는 <xref:System.Windows.Controls.Button> 를 이벤트 처리기 코드에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc941-106">Each <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event for a <xref:System.Windows.Controls.Button> corresponds with an event handler in the code.</span></span> <span data-ttu-id="dc941-107">이벤트 처리기와 같은 이름을 사용 하 여는 <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> 값에 적용 됩니다 `txt2` 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc941-107">The event handlers use the same name as the <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> value they will apply to `txt2` when the button is clicked.</span></span> <span data-ttu-id="dc941-108">또한 텍스트 `txt1` (한 <xref:System.Windows.Controls.TextBlock> 에 표시 되지는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]) 속성의 변경 내용을 반영 하도록 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc941-108">Also, the text in `txt1` (a <xref:System.Windows.Controls.TextBlock> not shown in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]) is updated to reflect the change in the property.</span></span>  
  
 [!code-xaml[TextWrapProperty#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml#1)]  
  
 [!code-csharp[TextWrapProperty#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextWrapProperty/CSharp/Window1.xaml.cs#2)]
 [!code-vb[TextWrapProperty#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="dc941-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc941-109">See Also</span></span>  
 <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>  
 <xref:System.Windows.TextWrapping>
