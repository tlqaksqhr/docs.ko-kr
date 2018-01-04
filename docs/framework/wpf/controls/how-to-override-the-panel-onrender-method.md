---
title: "방법: Panel의 OnRender 메서드 재정의"
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
f1_keywords:
- overriding OnRender method
- Panel control, overriding OnRender method
- OnRender method
- controls, Panel, overriding OnRender method
helpviewer_keywords:
- overriding OnRender method of Panel control [WPF]
- OnRender method [WPF], overriding
- Panel control [WPF], overriding OnRender method
ms.assetid: 57397834-a085-4e36-90ab-416fad98f341
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 958595cdfa521b372270d6283c7134ef0ba0ef79
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-override-the-panel-onrender-method"></a><span data-ttu-id="56867-102">방법: Panel의 OnRender 메서드 재정의</span><span class="sxs-lookup"><span data-stu-id="56867-102">How to: Override the Panel OnRender Method</span></span>
<span data-ttu-id="56867-103">재정의 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Panel.OnRender%2A> 방식의 <xref:System.Windows.Controls.Panel> 레이아웃 요소를 사용자 지정 그래픽 효과 추가 하기 위해 합니다.</span><span class="sxs-lookup"><span data-stu-id="56867-103">This example shows how to override the <xref:System.Windows.Controls.Panel.OnRender%2A> method of <xref:System.Windows.Controls.Panel> in order to add custom graphical effects to a layout element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56867-104">예</span><span class="sxs-lookup"><span data-stu-id="56867-104">Example</span></span>  
 <span data-ttu-id="56867-105">사용 된 <xref:System.Windows.Controls.Panel.OnRender%2A> 그래픽 효과 렌더링된 된 패널 요소를 추가 하기 위해 메서드.</span><span class="sxs-lookup"><span data-stu-id="56867-105">Use the <xref:System.Windows.Controls.Panel.OnRender%2A> method in order to add graphical effects to a rendered panel element.</span></span> <span data-ttu-id="56867-106">예를 들어 사용자 지정 테두리 또는 배경 효과 추가 하려면이 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56867-106">For example, you can use this method to add custom border or background effects.</span></span> <span data-ttu-id="56867-107">A <xref:System.Windows.Media.DrawingContext> 개체 도형, 텍스트, 이미지 또는 비디오를 그리기 위한 메서드를 제공 하는 인수로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56867-107">A <xref:System.Windows.Media.DrawingContext> object is passed as an argument, which provides methods for drawing shapes, text, images, or videos.</span></span> <span data-ttu-id="56867-108">결과적으로,이 방법은 패널 개체의 사용자 지정 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="56867-108">As a result, this method is useful for customization of a panel object.</span></span>  
  
 [!code-csharp[LightWeightCustomPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LightWeightCustomPanel/CSharp/OffsetPanel.cs#1)]
 [!code-vb[LightWeightCustomPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/LightWeightCustomPanel/visualbasic/offsetpanel.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="56867-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="56867-109">See Also</span></span>  
 <xref:System.Windows.Controls.Panel>  
 [<span data-ttu-id="56867-110">패널 개요</span><span class="sxs-lookup"><span data-stu-id="56867-110">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="56867-111">방사형 패널 사용자 지정 예제</span><span class="sxs-lookup"><span data-stu-id="56867-111">Custom Radial Panel Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159982)  
 [<span data-ttu-id="56867-112">방법 항목</span><span class="sxs-lookup"><span data-stu-id="56867-112">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/panel-how-to-topics.md)
