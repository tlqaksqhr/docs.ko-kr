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
ms.workload: dotnet
ms.openlocfilehash: 5eacc5435e259c20c25b64d6e82c33d07338602a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-custom-panel-element"></a>방법: 사용자 지정 패널 요소 만들기
## <a name="example"></a>예  
 기본 레이아웃 동작을 재정의 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Panel> 요소에서 파생 된 사용자 지정 레이아웃 요소를 만들고 <xref:System.Windows.Controls.Panel>합니다.  
  
 이 예제에서는 간단한 사용자 지정 정의 <xref:System.Windows.Controls.Panel> 라는 요소 `PlotPanel`, 자식 요소에 따라 두 하드 코드 된 x 및 y 좌표를 배치 하 합니다. 이 예제에서는 `x` 및 `y` 으로 설정 되어 `50`; 따라서 모든 자식 요소를 x 축과 y 해당 위치에 배치 축 합니다.  
  
 사용자 지정을 구현 하려면 <xref:System.Windows.Controls.Panel> 동작을 사용 하 여는 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 및 <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 메서드. 각 메서드가 반환 하는 <xref:System.Windows.Size> 배치 하 고 자식 요소를 렌더링 하는 데이터입니다.  
  
 [!code-cpp[PlotPanel#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.Panel>  
 [패널 개요](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [사용자 지정 콘텐츠 줄 바꿈 패널 예제 만들기](http://go.microsoft.com/fwlink/?LinkID=159979)
