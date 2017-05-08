---
title: "잉크 수집 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "디지털 잉크 수집"
  - "DefaultDrawingAttributes 속성"
  - "디지털 잉크, 수집"
  - "DrawingAttributes 속성"
  - "잉크, 수집"
  - "InkCanvas 요소"
  - "속성, DefaultDrawingAttributes"
  - "속성, DrawingAttributes"
ms.assetid: 66a3129d-9577-43eb-acbd-56c147282016
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 잉크 수집
[Windows Presentation Foundation](../../../../docs/framework/wpf/index.md) 플랫폼에서는 디지털 잉크 수집을 핵심 기능으로 제공합니다.  이 항목에서는 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]에서 잉크를 수집하는 방법에 대해 설명합니다.  
  
## 사전 요구 사항  
 다음 예제를 사용하려면 먼저 [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)]와 [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]를 설치해야 합니다.  또한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]용 응용 프로그램을 작성하는 방법을 알고 있어야 합니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 시작하는 방법에 대한 자세한 내용은 [연습: WPF 시작](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)을 참조하십시오.  
  
## InkCanvas 요소 사용  
 <xref:System.Windows.Controls.InkCanvas> 요소는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 잉크를 수집할 수 있는 가장 쉬운 방법을 제공합니다.  <xref:System.Windows.Controls.InkCanvas> 요소는 [!INCLUDE[TLA2#tla_tpclssdk](../../../../includes/tla2sharptla-tpclssdk-md.md)] 및 이전 버전의 <xref:Microsoft.Ink.InkOverlay> 개체와 비슷합니다.  
  
 잉크 입력을 받아서 표시하려면 <xref:System.Windows.Controls.InkCanvas> 요소를 사용합니다.  일반적으로 잉크 입력 시에는 잉크 스트로크를 생성하기 위해 디지타이저와 상호 작용하는 스타일러스가 사용됩니다.  스타일러스 대신 마우스를 사용할 수도 있습니다.  생성된 스트로크는 <xref:System.Windows.Ink.Stroke> 개체로 나타나며 프로그래밍 방식과 사용자 입력을 통해 조작할 수 있습니다.  <xref:System.Windows.Controls.InkCanvas>를 사용하면 기존 <xref:System.Windows.Ink.Stroke>를 선택, 수정 또는 삭제할 수 있습니다.  
  
 XAML을 사용하는 경우 트리에 `InkCanvas` 요소를 추가하기만 하면 잉크 수집을 간편하게 설정할 수 있습니다.  다음 예제에서는 [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)]에서 만들어진 기본 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프로젝트에 <xref:System.Windows.Controls.InkCanvas>를 추가합니다.  
  
 [!code-xml[DigitalInkTopics#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]  
  
 `InkCanvas` 요소는 자식 요소를 포함할 수 있으므로 거의 모든 형식의 XAML 요소에 잉크 주석 기능을 추가할 수 있습니다.  예를 들어 텍스트 요소에 잉크 기능을 추가하려는 경우 텍스트 요소를 <xref:System.Windows.Controls.InkCanvas>의 자식으로 설정하기만 하면 됩니다.  
  
 [!code-xml[DigitalInkTopics#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]  
  
 잉크를 사용한 이미지 표시 지원 기능을 추가하는 것도 간단합니다.  
  
 [!code-xml[DigitalInkTopics#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]  
  
### InkCollection 모드  
 <xref:System.Windows.Controls.InkCanvas>는 해당 <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> 속성을 통해 다양한 입력 모드를 지원합니다.  
  
### 잉크 조작  
 <xref:System.Windows.Controls.InkCanvas>는 많은 잉크 편집 작업을 지원합니다.  예를 들어 <xref:System.Windows.Controls.InkCanvas>는 펜 뒤쪽으로 지우기 기능을 지원하며 이 기능을 요소에 추가하는 데 추가 코드는 필요하지 않습니다.  
  
#### 선택 영역  
 선택 모드를 설정할 때는 <xref:System.Windows.Controls.InkCanvasEditingMode> 속성을 **Select**로 설정하기만 하면 됩니다.  다음 코드에서는 <xref:System.Windows.Forms.CheckBox> 값을 기준으로 편집 모드를 설정합니다.  
  
 [!code-csharp[DigitalInkTopics#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
 [!code-vb[DigitalInkTopics#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]  
  
#### DrawingAttributes  
 잉크 스트로크의 모양을 변경하려면 <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> 속성을 사용합니다.  예를 들어 <xref:System.Windows.Ink.DrawingAttributes>의 <xref:System.Windows.Ink.DrawingAttributes.Color%2A> 멤버는 렌더링된 <xref:System.Windows.Ink.Stroke>의 색을 설정합니다.  다음 예제에서는 선택된 스트로크의 색을 빨간색으로 변경합니다.  
  
 [!code-csharp[DigitalInkTopics#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
 [!code-vb[DigitalInkTopics#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]  
  
### DefaultDrawingAttributes  
 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> 속성을 사용하면 <xref:System.Windows.Controls.InkCanvas>에서 생성되는 스트로크의 높이, 너비, 색 등의 속성에 액세스할 수 있습니다.  한번 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>를 변경하면 이후에 <xref:System.Windows.Controls.InkCanvas>에 입력되는 모든 스트로크가 새 속성 값을 사용하여 렌더링됩니다.  
  
 코드 숨김 파일에서 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>를 수정할 수 있을 뿐만 아니라 XAML 구문을 사용하여 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> 속성을 지정할 수도 있습니다.  다음 XAML 코드 예제에서는 <xref:System.Windows.Ink.DrawingAttributes.Color%2A> 속성을 설정하는 방법을 보여 줍니다.  이 코드를 사용하려면 Visual Studio 2005에서 "HelloInkCanvas"라는 새 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프로젝트를 만든 다음  Window1.xaml 파일의 코드를 다음 코드로 바꿉니다.  
  
 [!code-xml[HelloInkCanvas#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]  
  
 그런 다음에는 코드 숨김 파일의 Window1 클래스 내에 다음 단추 이벤트 처리기를 추가합니다.  
  
 [!code-csharp[HelloInkCanvas#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]  
  
 이 코드를 복사한 후 Microsoft Visual Studio 2005에서 **F5** 키를 눌러 디버거에서 프로그램을 실행합니다.  
  
 <xref:System.Windows.Controls.StackPanel>은 <xref:System.Windows.Controls.InkCanvas> 위에 단추를 배치합니다.  사용자가 단추 위에 잉크로 그리려고 하면 <xref:System.Windows.Controls.InkCanvas>가 단추 뒤에서 잉크를 수집하여 렌더링합니다.  이는 단추가 <xref:System.Windows.Controls.InkCanvas>의 자식이 아니라 형제이기 때문입니다.  뿐만 아니라 z 순서에서 단추가 잉크보다 위에 있으므로 잉크가 단추 뒤에서 렌더링됩니다.  
  
## 참고 항목  
 <xref:System.Windows.Ink.DrawingAttributes>   
 <xref:System.Windows.InkCanvas.DefaultDrawingAttributes%2A>   
 <xref:System.Windows.Ink>