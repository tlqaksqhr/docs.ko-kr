---
title: "방법: 캔버스 위치 지정 속성 가져오기 또는 설정"
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
helpviewer_keywords: Canvas control [WPF], setting positioning properties
ms.assetid: 1636b950-2b5a-4507-8a10-c5034cc58b1c
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2b2f20754c8425149f73f10af773604539125adb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-get-or-set-canvas-positioning-properties"></a>방법: 캔버스 위치 지정 속성 가져오기 또는 설정
위치 지정 메서드를 사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Canvas> 요소 자식 콘텐츠를 배치 합니다. 콘텐츠를 사용 하 여이 예제는 <xref:System.Windows.Controls.ListBoxItem> 를 나타내는 값을 값의 인스턴스로 변환 위치 지정 <xref:System.Double>, 위치 지정에 대 한 필수 인수는 합니다. 값 한 다음 다시 문자열로 변환 되어에 텍스트로 표시 되는 <xref:System.Windows.Controls.TextBlock> 사용 하 여 요소는 <xref:System.Windows.Controls.Canvas.GetLeft%2A> 메서드.  
  
## <a name="example"></a>예제  
 다음 예제에서는 한 <xref:System.Windows.Controls.ListBox> 11 개의 선택 가능한 요소 <xref:System.Windows.Controls.ListBoxItem> 요소입니다. <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> 이벤트 트리거는 `ChangeLeft` 이후 코드 블록이 정의 하는 사용자 지정 메서드입니다.  
  
 각 <xref:System.Windows.Controls.ListBoxItem> 나타냅니다는 <xref:System.Double> 인수 중 하나는 값을 하는 <xref:System.Windows.Controls.Canvas.SetLeft%2A> 방식의 <xref:System.Windows.Controls.Canvas> 허용 합니다. 사용 하려면는 <xref:System.Windows.Controls.ListBoxItem> 의 인스턴스를 나타내는 <xref:System.Double>를 먼저 변환 해야는 <xref:System.Windows.Controls.ListBoxItem> 을 올바른 데이터 형식입니다.  
  
 [!code-xaml[CanvasPositioningProperties#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml#1)]  
  
 사용자는 <xref:System.Windows.Controls.ListBox> 호출 선택 항목을는 `ChangeLeft` 사용자 지정 메서드입니다. 이 메서드는 전달는 <xref:System.Windows.Controls.ListBoxItem> 에 <xref:System.Windows.LengthConverter> 을 변환 하는 개체는 <xref:System.Windows.Controls.ContentControl.Content%2A> 의 <xref:System.Windows.Controls.ListBoxItem> 의 인스턴스로 <xref:System.Double> (이 값으로 변환 된 이미 사라졌는지는 <xref:System.String> 를 사용 하 여는 <xref:System.Windows.Controls.Control.ToString%2A> 방법)입니다. 이 값은 다음에 다시 전달 되는 <xref:System.Windows.Controls.Canvas.SetLeft%2A> 및 <xref:System.Windows.Controls.Canvas.GetLeft%2A> 의 메서드 <xref:System.Windows.Controls.Canvas> 의 위치를 변경 하기 위해는 `text1` 개체입니다.  
  
 [!code-csharp[CanvasPositioningProperties#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml.cs#2)]
 [!code-vb[CanvasPositioningProperties#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasPositioningProperties/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.Canvas>  
 <xref:System.Windows.Controls.ListBoxItem>  
 <xref:System.Windows.LengthConverter>  
 [패널 개요](../../../../docs/framework/wpf/controls/panels-overview.md)
