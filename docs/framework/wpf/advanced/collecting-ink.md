---
title: "잉크 수집"
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
- ink [WPF], collecting
- InkCanvas element [WPF]
- properties [WPF], DrawingAttributes
- collecting digital ink [WPF]
- digital ink [WPF], collecting
- properties [WPF], DefaultDrawingAttributes
- DefaultDrawingAttributes property [WPF]
ms.assetid: 66a3129d-9577-43eb-acbd-56c147282016
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 81ed657de0c0e4d07fcb10b099cbf5e5c80a71fc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="collecting-ink"></a>잉크 수집
[Windows Presentation Foundation](../../../../docs/framework/wpf/index.md) 플랫폼은 기능의 핵심 요소로서 디지털 잉크를 수집합니다. 이 항목에서는 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]에서 잉크를 수집하는 방법에 대해 설명합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 다음에 나오는 예제를 사용하려면 먼저 [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)]와 [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]를 설치해야 합니다. 또한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]용 응용 프로그램을 작성하는 방법을 알고 있어야 합니다. 시작 하는 방법에 대 한 자세한 내용은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], 참조 [연습: 내 첫 WPF 데스크톱 응용 프로그램](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)합니다.  
  
## <a name="using-the-inkcanvas-element"></a>InkCanvas 요소 사용  
 <xref:System.Windows.Controls.InkCanvas> 요소에 잉크를 수집 하는 가장 쉬운 방법은 제공 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]합니다. <xref:System.Windows.Controls.InkCanvas> 요소는 비슷합니다는 [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/microsoft.ink.inkoverlay\(v=vs.90\).aspx) 에서 개체는 [!INCLUDE[TLA2#tla_tpclssdk](../../../../includes/tla2sharptla-tpclssdk-md.md)] 및 이전 버전입니다.  
  
 사용 하 여 프로그램 <xref:System.Windows.Controls.InkCanvas> 요소를 수신 및 잉크 입력을 표시 합니다. 일반적으로 스타일러스를 사용하여 잉크를 입력합니다.이 스타일러스는 디지타이저와 상호 작용하여 잉크 스트로크를 생성합니다. 또한 스타일러스 대신 마우스를 사용할 수도 있습니다. 생성된 된 스트로크도 표현 됩니다 <xref:System.Windows.Ink.Stroke> , 이러한 개체를 프로그래밍 방식으로 및 사용자가 입력 조작할 수 있습니다. <xref:System.Windows.Controls.InkCanvas> 선택, 수정 또는 삭제는 기존 수 있도록 <xref:System.Windows.Ink.Stroke>합니다.  
  
 XAML을 사용하면 트리에 `InkCanvas` 요소를 추가하는 것처럼 쉽게 잉크 컬렉션을 설정할 수 있습니다. 다음 예제에서는 추가 <xref:System.Windows.Controls.InkCanvas> 을 기본값 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 에서 만든 프로젝트 [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)]합니다.  
  
 [!code-xaml[DigitalInkTopics#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]  
  
 `InkCanvas` 요소는 자식 요소를 포함할 수도 있으므로 거의 모든 형식의 XAML 요소에 잉크 주석 기능을 추가할 수 있습니다. 예를 들어 잉크 기능에 텍스트 요소를 추가 하려면 단순히 자식으로 만듭니다의 <xref:System.Windows.Controls.InkCanvas>합니다.  
  
 [!code-xaml[DigitalInkTopics#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]  
  
 잉크로 이미지를 표시하기 위한 지원 기능을 추가하는 것도 매우 쉽습니다.  
  
 [!code-xaml[DigitalInkTopics#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]  
  
### <a name="inkcollection-modes"></a>InkCollection 모드  
 <xref:System.Windows.Controls.InkCanvas> 다양 한 입력을 통해 모드 지원을 제공 해당 <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> 속성입니다.  
  
### <a name="manipulating-ink"></a>잉크 조작  
 <xref:System.Windows.Controls.InkCanvas> 많은 잉크 편집 작업에 대 한 지원을 제공 합니다. 예를 들어 <xref:System.Windows.Controls.InkCanvas> 요소에 기능을 추가 하는 데 필요한 추가 코드 없이 지원 펜 백 지웁니다.  
  
#### <a name="selection"></a>선택  
 선택 모드를 설정 하는 작업은 설정으로는 <xref:System.Windows.Controls.InkCanvasEditingMode> 속성을 **선택**합니다. 값에 따라 편집 모드를 설정 하는 다음 코드는 <xref:System.Windows.Forms.CheckBox>:  
  
 [!code-csharp[DigitalInkTopics#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
 [!code-vb[DigitalInkTopics#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]  
  
#### <a name="drawingattributes"></a>DrawingAttributes  
 사용 된 <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> 잉크 스트로크의 모양을 변경할 속성입니다. 예를 들어,는 <xref:System.Windows.Ink.DrawingAttributes.Color%2A> 소속 <xref:System.Windows.Ink.DrawingAttributes> 는 렌더링 된 색을 설정 <xref:System.Windows.Ink.Stroke>합니다. 다음 예제에서는 선택한 스트로크의 색을 빨강으로 변경합니다.  
  
 [!code-csharp[DigitalInkTopics#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
 [!code-vb[DigitalInkTopics#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]  
  
### <a name="defaultdrawingattributes"></a>DefaultDrawingAttributes  
 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> 속성은 높이, 너비 및에 만들어질 선의 색 같은 속성에 대 한 액세스를 제공는 <xref:System.Windows.Controls.InkCanvas>합니다. 변경 하면는 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>에 입력 한 모든 이후 스트로크는 <xref:System.Windows.Controls.InkCanvas> 새로운 속성 값으로 렌더링 됩니다.  
  
 수정할 뿐 아니라는 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> 코드 숨김 파일에 XAML 구문을 지정 하는 데 사용할 수 있습니다 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> 속성입니다. 다음 XAML 코드에 설정 하는 방법을 보여 줍니다는 <xref:System.Windows.Ink.DrawingAttributes.Color%2A> 속성입니다. 이 코드를 사용하려면 Visual Studio 2005에서 "HelloInkCanvas"라는 새 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프로젝트를 만듭니다. Window1.xaml 파일의 코드를 다음 코드로 바꿉니다.  
  
 [!code-xaml[HelloInkCanvas#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]  
  
 그런 다음 코드 숨김 파일의 Window1 클래스 내에 다음 단추 이벤트 처리기를 추가합니다.  
  
 [!code-csharp[HelloInkCanvas#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]  
  
 이 코드를 복사한 후 Microsoft Visual Studio 2005에서 **F5** 키를 눌러 디버거에서 프로그램을 실행합니다.  
  
 알림 방법을 <xref:System.Windows.Controls.StackPanel> 단추 위쪽에 배치 합니다.는 <xref:System.Windows.Controls.InkCanvas>합니다. 단추의 위에 잉크 하려고 하면는 <xref:System.Windows.Controls.InkCanvas> 수집 하 고 단추 뒤 잉크를 렌더링 합니다. 형제는 단추가 때문에 이것이 <xref:System.Windows.Controls.InkCanvas> 자식이 아니라 합니다. 또한 단추가 z 순서에서 더 앞서기 때문에 잉크가 단추 뒤에서 렌더링됩니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Ink.DrawingAttributes>  
 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>  
 <xref:System.Windows.Ink>
