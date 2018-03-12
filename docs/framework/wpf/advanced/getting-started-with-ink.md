---
title: "잉크 시작"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- procedural code in lieu of XAML [WPF]
- gradient brush [WPF], animating colors of
- XAML [WPF], procedural code in lieu of
- animation [WPF], gradient brush colors
- brushes [WPF], animating colors of
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 74227ebe815e971087569ff39ac0a3479c1b0d14
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2018
---
# <a name="getting-started-with-ink"></a>잉크 시작
디지털 잉크 응용 프로그램에 통합 하는 것이 이전 보다 더 쉽습니다. 잉크가 발전 하 고 완벽 한 통합을 위한 프로그래밍의 COM 및 Windows Forms 메서드를 자연스럽 게 구축 되는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]합니다. 별도 Sdk 또는 런타임 라이브러리를 설치할 필요가 없습니다.  
  
## <a name="prerequisites"></a>전제 조건  
 다음 예제를 사용 하려면 먼저 설치 해야 Microsoft Visual Studio 2005 및 [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]합니다. 또한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]용 응용 프로그램을 작성하는 방법을 알고 있어야 합니다. 시작 하는 방법에 대 한 자세한 내용은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], 참조 [연습: 내 첫 WPF 데스크톱 응용 프로그램](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)합니다.  
  
## <a name="quick-start"></a>빠른 시작  
 이 섹션에서는 간단한을 작성 하는 데 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 잉크를 수집 하는 응용 프로그램입니다.  
  
 그렇게 이미 하지 않은 경우 Microsoft Visual Studio 2005를 설치 및 [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)]합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램 일반적으로 전에 컴파일되어야 볼 수 공백으로만 구성 된 경우에 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]합니다. 그러나는 [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)] 응용 프로그램이 포함 된, XamlPad 구현 과정을 가속화 하도록 디자인 된는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-UI를 기반으로 합니다. 보고 하 여 마다 개별적으로 처음 몇 가지 샘플이이 문서에서는 해당 응용 프로그램을 사용할 수 있습니다. 만드는 과정에서 컴파일된 응용 프로그램 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 이 문서의 뒷부분에서 설명 합니다.  
  
 XAMLPad를 실행 하려면 클릭는 **시작** 메뉴에서 **모든 프로그램**, 가리킨 **Microsoft Windows SDK**, 가리킨 **도구**를 클릭 하 고 **XAMLPad**합니다. XAMLPad는 렌더링 창에서 코드 창에서 작성 된 XAML 코드를 렌더링 합니다. XAML 코드를 편집할 수 있으며 변경 내용이 즉시 렌더링 창에 표시 합니다.  
  
#### <a name="got-ink"></a>잉크 사용  
 첫 번째를 시작 하려면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 잉크를 지 원하는 응용 프로그램:  
  
1.  Open Microsoft Visual Studio 2005  
  
2.  새 **Windows 응용 프로그램 (WPF)**  
  
3.  형식 `<InkCanvas/>` 사이 `<Grid>` 태그  
  
4.  키를 눌러 **F5** 디버거에서 응용 프로그램을 시작 하려면  
  
5.  스타일러스 또는 마우스를 사용 하 여, 작성 **hello world** 창에서  
  
 잉크 해당 하는 12 키 입력으로는 "hello world" 응용 프로그램을 작성 했습니다!  
  
#### <a name="spice-up-your-application"></a>응용 프로그램 꾸미기  
 일부 기능을 사용 하겠습니다는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]합니다.  열기 사이 있는 모든 대체 \<창 > 태그와 닫는 \</Window > 태그를 다음 태그로 그라데이션 브러시 백그라운드 프로그램 잉크 표면에 얻으려고 합니다.  
  
 [!code-xaml[DigitalInkTopics#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#1)]  
[!code-xaml[DigitalInkTopics#1a](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#1a)]  
  
#### <a name="using-animation"></a>애니메이션을 사용 하 여  
 쉽도록 애니메이션 그라데이션 브러시의 색을 적용 해 보겠습니다. 다음 추가 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 닫은 후 `</InkCanvas>` 태그 닫히기 전까지 `</Page>` 태그입니다.  
  
 [!code-xaml[DigitalInkTopics#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#2)]  
  
#### <a name="adding-some-code-behind-the-xaml"></a>XAML 뒤에 있는 일부 코드를 추가합니다.  
 XAML을 사용 하면 매우 쉽게 사용자 인터페이스를 디자인 하려면, 실제 응용 프로그램 이벤트를 처리 하는 코드를 추가 해야 합니다. 잉크 마우스에서 마우스 단추 클릭에 대 한 응답에서을 확대 하는 간단한 예제는 다음과 같습니다.  
  
 설정의 `MouseRightButtonUp` 처리기에 프로그램 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]:  
  
 [!code-xaml[DigitalInkTopics#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]  
  
 Visual Studio의 솔루션 탐색기에서 Windows1.xaml를 확장 하 고 코드 숨김 파일 Window1.xaml.cs 또는 Visual Basic을 사용 하는 경우 Window1.xaml.vb를 엽니다. 다음 이벤트 처리기 코드를 추가 합니다.  
  
 [!code-csharp[DigitalInkTopics#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
 [!code-vb[DigitalInkTopics#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]  
  
 이제 응용 프로그램을 실행 합니다. 잉크를 추가한 다음 마우스 오른쪽 단추로 클릭 하거나 스타일러스로 키를 눌러 보류 동작을 수행 합니다.  
  
#### <a name="using-procedural-code-instead-of-xaml"></a>프로시저 코드를 사용 하 여 XAML 대신  
 모든 액세스할 수 있습니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프로시저 코드의 기능입니다. 여기서는 "Hello 잉크 World" 응용 프로그램에 대 한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 하나를 사용 하지 않는 하 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 전혀 합니다. Visual Studio에서 빈 콘솔 응용 프로그램에 아래 코드를 붙여 넣습니다. PresentationCore, PresentationFramework, 및 WindowsBase 어셈블리에 대 한 참조를 추가 하 고 키를 눌러 응용 프로그램을 빌드합니다 **F5**:  
  
 [!code-csharp[InkCanvasConsoleApp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
 [!code-vb[InkCanvasConsoleApp#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]  
  
## <a name="see-also"></a>참고 항목  
 [디지털 잉크](../../../../docs/framework/wpf/advanced/digital-ink.md)  
 [잉크 수집](../../../../docs/framework/wpf/advanced/collecting-ink.md)  
 [필기 인식](../../../../docs/framework/wpf/advanced/handwriting-recognition.md)  
 [잉크 저장](../../../../docs/framework/wpf/advanced/storing-ink.md)
