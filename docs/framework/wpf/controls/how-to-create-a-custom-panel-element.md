---
title: "방법: 사용자 지정 패널 요소 만들기"
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
- Panel control [WPF]
- custom Panel elements [WPF]
ms.assetid: e0df4f1e-8c07-4e86-89a3-e22acfffdc2a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7e7cca5b6f7a0d5085e70c4ab6ac33ff83b75217
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-custom-panel-element"></a><span data-ttu-id="d592d-102">방법: 사용자 지정 패널 요소 만들기</span><span class="sxs-lookup"><span data-stu-id="d592d-102">How to: Create a Custom Panel Element</span></span>
## <a name="example"></a><span data-ttu-id="d592d-103">예제</span><span class="sxs-lookup"><span data-stu-id="d592d-103">Example</span></span>  
 <span data-ttu-id="d592d-104">기본 레이아웃 동작을 재정의 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Panel> 요소에서 파생 된 사용자 지정 레이아웃 요소를 만들고 <xref:System.Windows.Controls.Panel>합니다.</span><span class="sxs-lookup"><span data-stu-id="d592d-104">This example shows how to override the default layout behavior of the <xref:System.Windows.Controls.Panel> element and create custom layout elements that are derived from <xref:System.Windows.Controls.Panel>.</span></span>  
  
 <span data-ttu-id="d592d-105">이 예제에서는 간단한 사용자 지정 정의 <xref:System.Windows.Controls.Panel> 라는 요소 `PlotPanel`, 자식 요소에 따라 두 하드 코드 된 x 및 y 좌표를 배치 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="d592d-105">The example defines a simple custom <xref:System.Windows.Controls.Panel> element called `PlotPanel`, which positions child elements according to two hard-coded x- and y-coordinates.</span></span> <span data-ttu-id="d592d-106">이 예제에서는 `x` 및 `y` 으로 설정 되어 `50`; 따라서 모든 자식 요소를 x 축과 y 해당 위치에 배치 축 합니다.</span><span class="sxs-lookup"><span data-stu-id="d592d-106">In this example, `x` and `y` are both set to `50`; therefore, all child elements are positioned at that location on the x and y axes.</span></span>  
  
 <span data-ttu-id="d592d-107">사용자 지정을 구현 하려면 <xref:System.Windows.Controls.Panel> 동작을 사용 하 여는 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 및 <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="d592d-107">To implement custom <xref:System.Windows.Controls.Panel> behaviors, the example uses the <xref:System.Windows.FrameworkElement.MeasureOverride%2A> and <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> methods.</span></span> <span data-ttu-id="d592d-108">각 메서드가 반환 하는 <xref:System.Windows.Size> 배치 하 고 자식 요소를 렌더링 하는 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="d592d-108">Each method returns the <xref:System.Windows.Size> data that is necessary to position and render child elements.</span></span>  
  
 [!code-cpp[PlotPanel#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d592d-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d592d-109">See Also</span></span>  
 <xref:System.Windows.Controls.Panel>  
 [<span data-ttu-id="d592d-110">패널 개요</span><span class="sxs-lookup"><span data-stu-id="d592d-110">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="d592d-111">사용자 지정 콘텐츠 줄 바꿈 패널 예제 만들기</span><span class="sxs-lookup"><span data-stu-id="d592d-111">Create a Custom Content-Wrapping Panel Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159979)
