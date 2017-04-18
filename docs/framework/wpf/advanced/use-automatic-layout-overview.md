---
title: "자동 레이아웃 사용 개요 | Microsoft Docs"
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
  - "자동 레이아웃"
  - "레이아웃, 자동"
ms.assetid: 6fed9264-18bb-4d05-8867-1fe356c6f687
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 자동 레이아웃 사용 개요
이 항목에서는 지역화할 수 있는 [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)]를 사용하여 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램을 작성하는 방법에 대한 개발자용 지침을 소개합니다.  이전에는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]의 지역화 작업이 시간이 많이 소요되는 프로세스였습니다.  이전에는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]가 조정되는 각 언어에 대해 픽셀 단위의 조정이 필요했지만  이제는 올바른 디자인 및 코딩 표준을 사용하여 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]를 생성할 때 지역화 작업자가 크기 및 위치 조정 작업을 보다 적게 수행할 수 있게 되었습니다.  보다 쉽게 크기 및 위치를 조정할 수 있는 응용 프로그램을 작성하는 방법을 자동 레이아웃이라고 하며 이는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램 디자인을 통해 구현할 수 있습니다.  
  
 이 항목에는 다음 단원이 포함되어 있습니다.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
-   [자동 레이아웃 사용의 이점](#advantages_of_autolayout)  
  
-   [자동 레이아웃 및 컨트롤](#autolayout_controls)  
  
-   [자동 레이아웃 및 코딩 표준](#autolayout_coding)  
  
-   [자동 레이아웃 및 모눈](#autolay_grids)  
  
-   [IsSharedSizeScope 속성을 사용한 자동 레이아웃 및 모눈](#autolay_grids_issharedsizescope)  
  
-   [관련 항목](#seeAlsoToggle)  
  
<a name="advantages_of_autolayout"></a>   
## 자동 레이아웃 사용의 이점  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프레젠테이션 시스템은 강력하고 유연하므로 서로 다른 언어의 요구 사항을 충족시킬 수 있도록 조정될 수 있는 응용 프로그램에서의 요소 레이아웃 기능을 제공합니다.  다음 목록에서는 일부 자동 레이아웃의 장점을 보여 줍니다.  
  
-   [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]가 모든 언어에서 잘 표시됩니다.  
  
-   텍스트가 변환된 후 컨트롤의 위치와 크기를 다시 조정할 필요가 줄어듭니다.  
  
-   창 크기를 다시 조정할 필요가 줄어듭니다.  
  
-   [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 레이아웃이 모든 언어에서 적절하게 렌더링됩니다.  
  
-   문자열을 변환하는 정도로만 지역화를 수행할 수 있습니다.  
  
<a name="autolayout_controls"></a>   
## 자동 레이아웃 및 컨트롤  
 자동 레이아웃을 통해 응용 프로그램은 컨트롤 크기를 자동으로 조정할 수 있습니다.  예를 들어 컨트롤은 문자열 길이를 수용하도록 변경될 수 있습니다.  이러한 기능을 통해 지역화 작업자는 문자열을 변환할 때, 변환된 텍스트에 맞게 컨트롤 크기를 다시 조정하지 않아도 됩니다.  다음 예제에서는 영어 콘텐츠의 단추를 만듭니다.  
  
 [!code-xml[LocalizationBtn_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
 이 예제에서 스페인어 단추를 만들려면 텍스트를 변경하기만 하면 됩니다.  다음 예제를 참조하십시오.  
  
 [!code-xml[LocalizationBtn#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 다음 그래픽에서는 코드 샘플의 출력을 보여 줍니다.  
  
 ![텍스트가 여러 언어로 표시되는 동일한 단추](../../../../docs/framework/wpf/advanced/media/globalizationbutton.png "GlobalizationButton")  
자동으로 크기를 조정할 수 있는 단추  
  
<a name="autolayout_coding"></a>   
## 자동 레이아웃 및 코딩 표준  
 자동 레이아웃 방법을 사용하려면 완전히 지역화할 수 있는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 생성할 수 있는 코딩 및 디자인 표준\/규칙 집합이 필요합니다.  다음 지침은 자동 레이아웃 코딩에 도움이 됩니다.  
  
|코딩 표준|설명|  
|-----------|--------|  
|절대 위치를 사용하지 않습니다.|-   <xref:System.Windows.Controls.Canvas>는 요소를 절대 위치에 배치하므로 사용하지 않습니다.<br />-   <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.StackPanel> 및 <xref:System.Windows.Controls.Grid>를 사용하여 컨트롤을 배치합니다.<br />-   다양한 패널 형식에 대한 설명은 [Panel 개요](../../../../docs/framework/wpf/controls/panels-overview.md)를 참조하십시오.|  
|창에 고정 크기를 설정하지 않습니다.|-   <xref:System.Windows.Window.SizeToContent%2A>를 사용합니다.<br />-   예를 들면 다음과 같습니다.<br /><br /> [!code-xml[LocalizationGrid#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#2)]|  
|<xref:System.Windows.FrameworkElement.FlowDirection%2A>를 추가합니다.|<ul><li>응용 프로그램의 루트 요소에 <xref:System.Windows.FrameworkElement.FlowDirection%2A>을 추가합니다.</li><li>[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 간단한 방법으로 가로, 양방향 및 세로 레이아웃을 지원합니다.  프레젠테이션 프레임워크에서 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 속성을 사용하여 레이아웃을 정의할 수 있습니다.  흐름 방향 패턴은 다음과 같습니다.<br /><br /> <ul><li><xref:System.Windows.FlowDirection>\(LrTb\) \- 라틴어, 동아시아 언어 등을 위한 가로 레이아웃</li><li><xref:System.Windows.FlowDirection>\(RlTb\) \- 아랍어, 히브리어 등을 위한 양방향 레이아웃</li></ul></li></ul>|  
|실제 글꼴 대신 합성 글꼴을 사용합니다.|<ul><li>합성 글꼴을 사용하면 <xref:System.Windows.Controls.Control.FontFamily%2A> 속성을 지역화할 필요가 없습니다.</li><li>개발자는 다음 글꼴 중 하나를 사용하거나 자체 글꼴을 만들 수 있습니다.<br /><br /> <ul><li>Global User Interface</li><li>Global San Serif</li><li>Global Serif</li></ul></li></ul>|  
|xml:lang을 추가합니다.|-   `xml:lang` 특성을 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]의 루트 요소에 추가합니다. 예를 들어 영어 응용 프로그램에는 `xml:lang="en-US"`를 추가합니다.<br />-   합성 글꼴은 `xml:lang`를 통해 사용할 글꼴을 결정하므로 이 속성을 설정하여 다국어 시나리오를 지원합니다.|  
  
<a name="autolay_grids"></a>   
## 자동 레이아웃 및 모눈  
 <xref:System.Windows.Controls.Grid> 요소는 개발자가 요소 위치를 지정하는 데 사용할 수 있으므로 자동 레이아웃에 유용합니다.  <xref:System.Windows.Controls.Grid> 컨트롤을 사용하면 열 및 행 정렬을 사용하여 자식 요소 간에 사용 가능한 공간을 분배할 수 있습니다.  [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 요소는 여러 셀에 걸쳐 배치될 수 있으며 모눈 안에 모눈을 사용할 수 있습니다.  모눈은 복잡한 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 만들고 배치하는 데 사용할 수 있으므로 유용합니다.  다음 예제에서는 모눈을 사용하여 일부 단추 및 텍스트를 배치하는 방법을 보여 줍니다.  셀의 높이와 너비가 <xref:System.Windows.GridUnitType>로 설정되어 있으므로 이미지가 있는 단추를 포함하는 셀은 이미지에 맞춰 조정됩니다.  
  
 [!code-xml[LocalizationGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 다음 그래픽에서는 이전 코드에서 만든 모눈을 보여 줍니다.  
  
 ![표 예제](../../../../docs/framework/wpf/advanced/media/glob-grid.png "glob\_grid")  
모눈  
  
<a name="autolay_grids_issharedsizescope"></a>   
## IsSharedSizeScope 속성을 사용한 자동 레이아웃 및 모눈  
 <xref:System.Windows.Controls.Grid> 요소는 지역화할 수 있는 응용 프로그램에서 콘텐츠에 맞게 조정되는 컨트롤을 만드는 데 유용합니다.  그러나 콘텐츠에 관계없이 특정 크기로 컨트롤을 유지하려는 경우도 있습니다.  예를 들어 "확인", "취소" 및 "찾아보기" 단추가 있는 경우 콘텐츠에 맞게 단추 크기를 조정할 필요가 없을 것입니다.  이 경우 <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=fullName> 연결된 속성을 사용하면 여러 모눈 요소 간에 동일한 크기를 공유할 수 있습니다.  다음 예제에서는 여러 <xref:System.Windows.Controls.Grid> 요소 간에 열과 행 크기 조정 데이터를 공유하는 방법을 보여 줍니다.  
  
 [!code-xml[gridIssharedsizescopeProp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 **참고** 완전한 코드 샘플은 [모눈 간 크기 조정 속성 공유](../../../../docs/framework/wpf/controls/how-to-share-sizing-properties-between-grids.md)를 참조하십시오.  
  
## 참고 항목  
 [WPF의 전역화](../../../../docs/framework/wpf/advanced/globalization-for-wpf.md)   
 [자동 레이아웃을 사용하여 단추 만들기](../../../../docs/framework/wpf/advanced/how-to-use-automatic-layout-to-create-a-button.md)   
 [자동 레이아웃에 Grid 사용](../../../../docs/framework/wpf/advanced/how-to-use-a-grid-for-automatic-layout.md)