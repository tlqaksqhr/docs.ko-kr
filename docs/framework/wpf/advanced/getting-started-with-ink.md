---
title: "잉크 시작 | Microsoft Docs"
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
  - "애니메이션, 그라데이션 브러시 색"
  - "브러시, 색에 애니메이션 적용"
  - "그라데이션 브러시, 색에 애니메이션 적용"
  - "XAML 대신 프로시저 코드"
  - "XAML, 대신 프로시저 코드"
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 잉크 시작
응용 프로그램에 디지털 잉크 기능을 통합하는 것이 훨씬 쉬워졌습니다.  잉크는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]와의 완벽한 통합을 위해 자연스럽게 프로그래밍 방식의 COM 및 Windows Forms 메서드로 발전했습니다.  따라서 별도로 SDK나 런타임 라이브러리를 설치할 필요가 없습니다.  
  
## 사전 요구 사항  
 다음 예제를 사용하려면 먼저 Microsoft Visual Studio 2005와 [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]를 설치해야 합니다.  또한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]용 응용 프로그램을 작성하는 방법을 알고 있어야 합니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 시작하는 방법에 대한 자세한 내용은 [연습: WPF 시작](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)을 참조하십시오.  
  
## 퀵 스타트  
 이 단원에는 잉크를 수집하는 간단한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램을 작성하는 방법에 대한 유용한 정보가 나와 있습니다.  
  
 아직 Microsoft Visual Studio 2005 및 [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)]를 설치하지 않았다면 지금 설치하십시오.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램은 대개 컴파일해야만 볼 수 있습니다. 이것은 응용 프로그램이 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]만으로 구성된 경우에도 마찬가지입니다.  하지만 [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)]에는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 기반 UI를 구현하는 프로세스를 빠르게 처리할 수 있도록 디자인된 응용 프로그램인 XamlPad가 포함되어 있습니다.  이 응용 프로그램을 사용하면 이 문서의 앞부분에 있는 몇 가지 샘플을 보고 샘플을 사용하여 실습해 볼 수 있습니다.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 컴파일된 응용 프로그램을 만드는 프로세스에 대해서는 이 문서의 뒷부분에서 다룹니다.  
  
 XAMLPad를 시작하려면 **시작** 메뉴를 클릭하고 **모든 프로그램**, **Microsoft Windows SDK**, **도구**를 차례로 가리킨 다음 **XAMLPad**를 클릭합니다.  XAMLPad는 코드 창에서 작성한 XAML 코드를 렌더링 창에서 렌더링합니다.  XAML 코드를 편집하면 렌더링 창에 변경 사항이 즉시 나타납니다.  
  
#### 잉크 사용  
 잉크를 지원하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램을 처음으로 만들어서 시작하려면 다음과 같이 하십시오.  
  
1.  Microsoft Visual Studio 2005를 엽니다.  
  
2.  새 **Windows 응용 프로그램\(WPF\)**을 만듭니다.  
  
3.  `<Grid>` 태그 사이에 `<InkCanvas/>`를 입력합니다.  
  
4.  **F5** 키를 눌러 디버거에서 응용 프로그램을 시작합니다.  
  
5.  스타일러스나 마우스를 사용하여 창에 hello world를 씁니다.  
  
 "hello world"에 대한 잉크 응용 프로그램을 12번의 키 입력만으로 만들었습니다.  
  
#### 응용 프로그램 꾸미기  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 몇 가지 기능을 이용해 보겠습니다.  여는 \<Window\> 태그와 닫는 \<\/Window\> 태그 사이에 있는 모든 요소를 다음 태그로 교체하여 잉크 기능으로 그려지는 표면에 그라데이션 브러시 배경을 추가합니다.  
  
 [!code-xml[DigitalInkTopics#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#1)]  
[!code-xml[DigitalInkTopics#1a](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#1a)]  
  
#### 애니메이션 사용  
 재미를 위해 그라데이션 브러시의 색에 애니메이션 효과를 추가해 봅니다.  닫는 `</InkCanvas>` 태그와 닫는 `</Page>` 태그 사이에 다음과 같은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 추가합니다.  
  
 [!code-xml[DigitalInkTopics#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#2)]  
  
#### XAML에 몇 가지 코드 추가  
 XAML을 사용하면 사용자 인터페이스를 매우 쉽게 디자인할 수 있지만 실제 응용 프로그램에는 이벤트를 처리하는 코드를 추가해야 합니다.  다음은 마우스 오른쪽 단추를 클릭하여 잉크를 확대하는 단순한 예제입니다.  
  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 `MouseRightButtonUp` 처리기를 설정합니다.  
  
 [!code-xml[DigitalInkTopics#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]  
  
 Visual Studio의 솔루션 탐색기에서 Windows1.xaml을 확장하고 코드 숨김 파일인 Window1.xaml.cs\(Visual Basic을 사용하는 경우 Window1.xaml.vb\)를 엽니다.  다음 이벤트 처리기 코드를 추가합니다.  
  
 [!code-csharp[DigitalInkTopics#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
 [!code-vb[DigitalInkTopics#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]  
  
 이제 응용 프로그램을 실행합니다.  잉크를 추가한 후 마우스 오른쪽 단추로 잉크를 클릭하거나 스타일러스로 이와 동등한 누르고 있기 동작을 수행합니다.  
  
#### XAML 대신 프로시저 코드 사용  
 프로시저 코드에서 모든 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기능에 액세스할 수 있습니다.  다음은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 전혀 사용하지 않는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]용 "Hello Ink World" 응용 프로그램입니다.  Visual Studio에서 다음 코드를 빈 콘솔 응용 프로그램에 붙여 넣습니다.  PresentationCore, PresentationFramework 및 WindowsBase 어셈블리에 대한 참조를 추가하고 **F5** 키를 눌러 응용 프로그램을 빌드합니다.  
  
 [!code-csharp[InkCanvasConsoleApp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
 [!code-vb[InkCanvasConsoleApp#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]  
  
## 참고 항목  
 [디지털 잉크](../../../../docs/framework/wpf/advanced/digital-ink.md)   
 [잉크 수집](../../../../docs/framework/wpf/advanced/collecting-ink.md)   
 [필기 인식](../../../../docs/framework/wpf/advanced/handwriting-recognition.md)   
 [잉크 저장](../../../../docs/framework/wpf/advanced/storing-ink.md)