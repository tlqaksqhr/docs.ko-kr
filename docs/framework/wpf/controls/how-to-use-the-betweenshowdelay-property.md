---
title: "방법: BetweenShowDelay 속성 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ToolTip control [WPF], BetweenShowDelay time property
- BetweenShowDelay time property [WPF]
ms.assetid: 984ea76d-f2a2-4326-a02e-f97ec3d036d6
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dca6dc7c6238ef4accc921818090237d17ce1cbd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-the-betweenshowdelay-property"></a>방법: BetweenShowDelay 속성 사용
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> 도구 설명 신속 하 게 표시 되도록 시간 속성-거의 없거나 전혀 없이 지연 되어 — 사용자로 이동 하면 마우스 포인터 한 도구 설명에서 직접 다른 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> 속성이 1 초인 (1000 밀리초)로 설정 되어 및 <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> 모두의 도구 설명에 대 한 2 초 (2000 밀리초)로 설정 된 <xref:System.Windows.Shapes.Ellipse> 컨트롤입니다. 타원 중 하나에 대 한 도구 설명을 표시 하 고 다음 마우스 포인터를 이동 다른 타원에 일시 중지 하 고 2 초 내에 두 번째 타원의 도구 설명 바로 표시 합니다.  
  
 다음 시나리오 중 하나에서 <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> 적용 되 고 표시 될 때까지 1 초에 두 번째 타원은 도구 설명에 이르게:  
  
-   두 번째 단추는 시간을 이동 하는 데 걸리는 경우 2 초 이상.  
  
-   도구 설명은 첫 번째 타원은 시간 간격의 시작 부분에 표시 되지 않습니다.  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
[!code-xaml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.ToolTip>  
 <xref:System.Windows.Controls.ToolTipService>  
 [방법 항목](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)  
 [도구 설명 개요](../../../../docs/framework/wpf/controls/tooltip-overview.md)
