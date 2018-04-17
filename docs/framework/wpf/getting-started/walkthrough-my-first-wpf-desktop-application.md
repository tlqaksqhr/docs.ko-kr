---
title: '연습: 내 첫 WPF 데스크톱 응용 프로그램'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
caps.latest.revision: 71
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3725e96b514b0204f10f6b5c45ed2bbec1d892de
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-my-first-wpf-desktop-application"></a>연습: 내 첫 WPF 데스크톱 응용 프로그램
이 연습에서는 개발에 대 한 소개는 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 대부분에 공통 된 요소를 포함 하는 응용 프로그램 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램: [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 태그, 코드 숨김, 응용 프로그램 정의 컨트롤, 레이아웃 데이터 바인딩 및 스타일입니다. 
  
이 연습 과정을 안내해 간단한 개발 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 다음 단계를 사용 하 여 응용 프로그램입니다. 
  
-   정의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 응용 프로그램의 모양 디자인 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]합니다. 
  
-   코드를 작성하여 응용 프로그램의 동작 빌드. 
  
-   응용 프로그램 정의를 만들어 응용 프로그램 관리. 
  
-   컨트롤 추가 및 레이아웃은 응용 프로그램을 구성을 만들어 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]합니다. 
  
-   스타일을 만들어 응용 프로그램 전체에서 일관 된 모양을 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]합니다. 
  
-   바인딩는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 둘 다에 대 한 데이터를 채우는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 데이터 및 데이터 유지 및 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 동기화 합니다. 
  
이 연습에서는 끝날 때까지 마치면 독립 실행형 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 사용자가 선택한 사용자에 대 한 경비 보고서를 볼 수 있는 응용 프로그램입니다. 응용 프로그램은 몇 가지 구성 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 브라우저 스타일 창에서 호스트 되는 페이지입니다. 
  
이 연습에 사용 되는 샘플 코드는 둘 다에 사용할 수 있는 [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)] 및 [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] 에서 [WPF 응용 프로그램 빌드 소개](http://go.microsoft.com/fwlink/?LinkID=160008)합니다. 

## <a name="prerequisites"></a>전제 조건  

- [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)] 이상

Visual Studio의 최신 버전을 설치 하는 방법에 대 한 자세한 내용은 참조 [Visual Studio 설치](/visualstudio/install/install-visual-studio)합니다.
  
## <a name="creating-the-application-project"></a>응용 프로그램 프로젝트 만들기  
이 섹션에서는 응용 프로그램 정의, 두 페이지 및 이미지를 포함하는 응용 프로그램 인프라를 만듭니다. 
  
1. Visual Basic 또는 Visual C#에서 `ExpenseIt`이라는 새 WPF 응용 프로그램 프로젝트를 만듭니다. 자세한 내용은 [방법: 새 WPF 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82)를 참조하세요. 
  
    > [!NOTE]
    >  이 연습에서는 <xref:System.Windows.Controls.DataGrid> .NET Framework 4에서 사용할 수 있는 컨트롤입니다. 프로젝트의 대상.NET Framework 4 있는지 이상 이어야 합니다. 자세한 내용은 [방법: 한 버전의 .NET Framework를 대상으로 지정](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework)을 참조하세요. 
  
2. Application.xaml(Visual Basic) 또는 App.xaml(C#)을 엽니다. 
  
     이 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일 정의 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램 및 모든 응용 프로그램 리소스입니다. 또한 지정 하려면이 파일을 사용는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 자동으로 표시 되 응용 프로그램이 시작 됩니다;이 경우 MainWindow.xaml 합니다. 
  
     프로그램 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Visual Basic에서 다음과 같이 표시 됩니다.  
  
    [!code-xaml[ExpenseIt#1_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]  
  
     C#에서는 다음과 같이 나타납니다.  
  
    [!code-xaml[ExpenseIt#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]  
  
3. MainWindow.xaml을 엽니다. 
  
     이 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일은 응용 프로그램의 주 창이 및 페이지에서 만든 콘텐츠를 표시 합니다. <xref:System.Windows.Window> 클래스 제목, 크기 또는 아이콘을 같은 창, 속성을 정의 하며, 닫기 또는 숨기기 등의 이벤트를 처리 합니다. 
  
4. 변경 된 <xref:System.Windows.Window> 요소를 한 <xref:System.Windows.Navigation.NavigationWindow>합니다. 
  
     이 응용 프로그램은 사용자 상호 작용에 따라 다른 콘텐츠를 탐색합니다. 따라서 주 <xref:System.Windows.Window> 를 변경 해야 하는 <xref:System.Windows.Navigation.NavigationWindow>합니다. <xref:System.Windows.Navigation.NavigationWindow> 모든 속성을 상속 <xref:System.Windows.Window>합니다. <xref:System.Windows.Navigation.NavigationWindow> 의 인스턴스를 만들고 XAML 파일의 요소는 <xref:System.Windows.Navigation.NavigationWindow> 클래스입니다. 자세한 내용은 [탐색 개요](../../../../docs/framework/wpf/app-development/navigation-overview.md)를 참조하세요. 
  
5. 다음 속성을 변경한는 <xref:System.Windows.Navigation.NavigationWindow> 요소:  
  
    -   설정의 <xref:System.Windows.Window.Title%2A> 속성을 "ExpenseIt"입니다. 
  
    -   설정의 <xref:System.Windows.FrameworkElement.Width%2A> 속성을 500 픽셀로 합니다. 
  
    -   설정의 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 350 픽셀로 합니다. 
  
    -   제거는 <xref:System.Windows.Controls.Grid> 간에 요소는 <xref:System.Windows.Navigation.NavigationWindow> 태그입니다. 
  
     프로그램 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Visual Basic에서 다음과 같이 표시 됩니다.  
  
    [!code-xaml[ExpenseIt#2_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]  
  
     C#에서는 다음과 같이 나타납니다.  
  
    [!code-xaml[ExpenseIt#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]  
  
6. MainWindow.xaml.vb 또는 MainWindow.xaml.cs를 엽니다. 
  
     이 파일은 MainWindow.xaml에 선언된 이벤트를 처리할 코드를 포함하는 코드 숨김 파일입니다. 이 파일에는 XAML에 정의된 창의 부분 클래스가 포함되어 있습니다. 
  
7. C#을 사용 하는 경우 변경 된 `MainWindow` 클래스에서 파생 되도록 <xref:System.Windows.Navigation.NavigationWindow>합니다. 
  
     Visual Basic에서는 XAML에서 창을 변경하면 자동으로 이와 같이 변경됩니다. 
  
     코드는 다음과 같습니다. 
  
    [!code-csharp[ExpenseIt#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml.cs#3)]
    [!code-vb[ExpenseIt#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml.vb#3)]  
  
## <a name="adding-files-to-the-application"></a>응용 프로그램에 파일 추가  
이 섹션에서는 응용 프로그램에 두 페이지와 이미지를 추가합니다. 
  
1. 프로젝트에 새 페이지 (WPF) 추가 `ExpenseItHome.xaml`합니다. 자세한 내용은 참조 [하는 방법: WPF 프로젝트에 새 항목 추가](http://msdn.microsoft.com/library/17e6b238-fc32-4385-98ef-2f66ca09d9ad)합니다. 
  
     이 페이지는 응용 프로그램이 시작될 때 표시되는 첫 번째 페이지입니다. 이 페이지에서는 사용자가 비용 보고서를 표시할 사람을 선택할 수 있는 사람 목록을 보여줍니다. 
  
2. ExpenseItHome.xaml을 엽니다. 
  
3. 설정의 <xref:System.Windows.Controls.Page.Title%2A> "ExpenseIt-홈"에 있습니다. 
  
     프로그램 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Visual Basic에서 다음과 같이 표시 됩니다.  
  
    [!code-xaml[ExpenseIt#6_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]  
  
     C#에서는 다음과 같이 나타납니다.  
  
    [!code-xaml[ExpenseIt#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]  
  
4. MainWindow.xaml을 엽니다. 
  
5. 설정의 <xref:System.Windows.Navigation.NavigationWindow.Source%2A> 속성에는 <xref:System.Windows.Navigation.NavigationWindow> "ExpenseItHome.xaml"를 합니다. 
  
     이렇게 하면 ExpenseItHome.xaml이 응용 프로그램을 시작할 때 열리는 첫 페이지로 설정됩니다. 프로그램 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Visual Basic에서 다음과 같이 표시 됩니다.  
  
    [!code-xaml[ExpenseIt#7_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]  
  
     C#에서는 다음과 같이 나타납니다.  
  
    [!code-xaml[ExpenseIt#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]  
  
6. 프로젝트에 새 페이지 (WPF) 추가 `ExpenseReportPage.xaml`합니다. 
  
     이 페이지는 ExpenseItHome.xaml에서 선택된 사람의 비용 보고서를 표시합니다. 
  
7. ExpenseReportPage.xaml을 엽니다. 
  
8. 설정의 <xref:System.Windows.Controls.Page.Title%2A> "ExpenseIt-View Expense"에 있습니다. 
  
     프로그램 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Visual Basic에서 다음과 같이 표시 됩니다.  
  
    [!code-xaml[ExpenseIt#4_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]  
  
     C#에서는 다음과 같이 나타납니다.  
  
    [!code-xaml[ExpenseIt#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]  
  
9. ExpenseItHome.xaml.vb 및 ExpenseReportPage.xaml.vb를 열거나 ExpenseItHome.xaml.cs 및 ExpenseReportPage.xaml.cs를 엽니다. 
  
     새 페이지 파일을 만들면 Visual Studio에서 자동으로 코드 숨김 파일을 만듭니다. 이러한 코드 숨김 파일은 사용자 입력에 응답하기 위한 논리를 처리합니다. 
  
     코드는 다음과 같습니다. 
  
    [!code-csharp[ExpenseIt#2_5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]
    [!code-vb[ExpenseIt#2_5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]  
  
    [!code-csharp[ExpenseIt#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]
    [!code-vb[ExpenseIt#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]  
  
10. 명명 된 이미지를 추가 *watermark.png* 프로젝트에 있습니다. 고유 이미지를 만들거나 샘플 코드에서 파일을 복사할 수 있습니다. 자세한 내용은 참조 [하는 방법: 프로젝트에 기존 항목 추가](/previous-versions/visualstudio/visual-studio-2008/9f4t9t92(v=vs.90))합니다. 

## <a name="building-and-running-the-application"></a>빌드 및 응용 프로그램 실행  
이 섹션에서는 응용 프로그램을 빌드하고 실행합니다. 
  
1. F5 키를 누르거나 선택 하 여 응용 프로그램을 실행 하 고 빌드 **디버깅 시작** 에서 **디버그** 메뉴. 
  
     다음 그림에 나와 있는 응용 프로그램의 <xref:System.Windows.Navigation.NavigationWindow> 단추입니다. 
  
     ![ExpenseIt 샘플 스크린샷](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure1.png "GettingStartedFigure1")  
  
2. 돌아가려면 응용 프로그램을 닫고 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]합니다. 
  
## <a name="creating-the-layout"></a>레이아웃 만들기  
레이아웃을 순서 대로 제공 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 요소를 하 고 해당 요소의 위치와 크기를 관리할 수 때는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 크기가 조정 됩니다. 일반적으로 다음 레이아웃 컨트롤 중 하나를 사용하여 레이아웃을 만듭니다.  
  
-   <xref:System.Windows.Controls.Canvas>  
  
-   <xref:System.Windows.Controls.DockPanel>  
  
-   <xref:System.Windows.Controls.Grid>  
  
-   <xref:System.Windows.Controls.StackPanel>  
  
-   <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
-   <xref:System.Windows.Controls.WrapPanel>  
  
이러한 레이아웃 컨트롤은 각각 자식 요소의 특수 레이아웃 형식을 지원합니다. ExpenseIt 페이지는 크기를 조정할 수 있으며, 각 페이지의 요소는 다른 요소와 함께 가로 및 세로 방향으로 정렬됩니다. 따라서는 <xref:System.Windows.Controls.Grid> 는 응용 프로그램에 대 한 적합 한 레이아웃 요소입니다. 
  
> [!NOTE]
>  에 대 한 자세한 내용은 <xref:System.Windows.Controls.Panel> 요소 참조 [패널 개요](../../../../docs/framework/wpf/controls/panels-overview.md)합니다. 레이아웃에 대 한 자세한 내용은 참조 [레이아웃](../../../../docs/framework/wpf/advanced/layout.md)합니다. 
  
섹션에는 단일 열 테이블을 만들면 행 3 개와 10 픽셀 여백 행 및 열 정의를 추가 하 여는 <xref:System.Windows.Controls.Grid> ExpenseItHome.xaml에 있습니다. 
  
1. ExpenseItHome.xaml을 엽니다. 
  
2. 설정의 <xref:System.Windows.FrameworkElement.Margin%2A> 속성에는 <xref:System.Windows.Controls.Grid> 요소 왼쪽, 위쪽, 오른쪽 및 아래쪽 여백에 해당 하는 "10,0,10,10"입니다. 
  
3. 다음 추가 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 사이 <xref:System.Windows.Controls.Grid> 태그 행 및 열 정의 만들 수 있습니다. 
  
    [!code-xaml[ExpenseIt#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]  
  
     <xref:System.Windows.Controls.RowDefinition.Height%2A> 로 설정 된 두 개의 행 <xref:System.Windows.GridLength.Auto%2A> 행의 내용을 기준으로 의미 하는 행을 조정 됩니다. 기본 <xref:System.Windows.Controls.RowDefinition.Height%2A> 은 <xref:System.Windows.GridUnitType.Star> 크기 조정, 행은 사용 가능한 공간에 대 한 가중치 됩니다. 예를 들어 두 행의 높이가 각각 “*”이면 이 두 행은 사용 가능한 공간의 절반에 해당하는 높이를 가지게 됩니다.  
  
     프로그램 <xref:System.Windows.Controls.Grid> 이제 다음 XAML 같이 표시 합니다.  
  
    [!code-xaml[ExpenseIt#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]  
  
## <a name="adding-controls"></a>컨트롤 추가  
이 섹션에서는 홈 페이지 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 경비 보고서는 선택한 개인에 대 한 표시를 사용자에서 선택할 수 직원의 목록을 표시 하도록 업데이트 됩니다. 컨트롤은 사용자가 응용 프로그램과 상호 작용할 수 있게 하는 UI 개체입니다. 자세한 내용은 [컨트롤](../../../../docs/framework/wpf/controls/index.md)을 참조하세요. 
  
만들려는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], ExpenseItHome.xaml에 다음 요소가 추가 됩니다.  
  
-   <xref:System.Windows.Controls.ListBox> (목록에 대해 사용자). 
  
-   <xref:System.Windows.Controls.Label> (예: 목록 헤더의 경우). 
  
-   <xref:System.Windows.Controls.Button> (클릭 하 여 목록에서 선택 되어 있는 사람에 대 한 경비 보고서를 볼 수)입니다. 
  
각 컨트롤의 행에 배치 되는 <xref:System.Windows.Controls.Grid> 설정 하 여는 <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> 연결 된 속성입니다. 연결 된 속성에 대 한 자세한 내용은 참조 [연결 된 속성 개요](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)합니다. 
  
1. ExpenseItHome.xaml을 엽니다. 
  
2. 다음 추가 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 사이 <xref:System.Windows.Controls.Grid> 태그입니다. 
  
    [!code-xaml[ExpenseIt#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]  
  
3. 응용 프로그램을 빌드 및 실행합니다. 
  
다음 그림에서는 이 섹션에서 XAML을 통해 만든 컨트롤을 보여줍니다. 
  
![ExpenseIt 샘플 스크린샷](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure2.png "GettingStartedFigure2")  
  
## <a name="adding-an-image-and-a-title"></a>이미지 및 제목 추가  
이 섹션에서는 홈 페이지 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 이미지 및 페이지 제목으로 업데이트 됩니다. 
  
1. ExpenseItHome.xaml을 엽니다. 
  
2. 다른 열을 추가 하는 <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> 고정 된 <xref:System.Windows.Controls.ColumnDefinition.Width%2A> 230 픽셀인 합니다. 
  
    [!code-xaml[ExpenseIt#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11)]  
  
3. 다른 행을 추가 하는 <xref:System.Windows.Controls.Grid.RowDefinitions%2A>합니다. 
  
    [!code-xaml[ExpenseIt#11b](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11b)]  
  
4. 두 번째 열을 설정 하 여 컨트롤을 이동 <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> 1입니다. 증가 시켜 각 컨트롤을 한 행 아래로 이동는 <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> 1입니다. 
  
    [!code-xaml[ExpenseIt#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]  
  
5. 설정의 <xref:System.Windows.Controls.Panel.Background%2A> 의 <xref:System.Windows.Controls.Grid> watermark.png 이미지 파일이 있습니다. 
  
    [!code-xaml[ExpenseIt#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]  
  
6. 하기 전에 <xref:System.Windows.Controls.Border>, 추가 <xref:System.Windows.Controls.Label> 콘텐츠로 "보기 경비 보고서의" 페이지의 제목입니다. 
  
    [!code-xaml[ExpenseIt#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]  
  
7. 응용 프로그램을 빌드 및 실행합니다. 
  
다음 그림에서는 이 섹션의 결과를 보여줍니다. 
  
![ExpenseIt 샘플 스크린샷](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure3.png "GettingStartedFigure3")  
  
## <a name="adding-code-to-handle-events"></a>이벤트를 처리 하는 코드 추가  
  
1. ExpenseItHome.xaml을 엽니다. 
  
2. 추가 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 를 이벤트 처리기는 <xref:System.Windows.Controls.Button> 요소입니다. 자세한 내용은 참조 [하는 방법: 간단한 이벤트 처리기를 만들](http://msdn.microsoft.com/library/b1456e07-9dec-4354-99cf-18666b64f480)합니다. 
  
    [!code-xaml[ExpenseIt#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]  
  
3. ExpenseItHome.xaml.vb 또는 ExpenseItHome.xaml.cs를 엽니다. 
  
4. 다음 코드를 추가 하는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 인해 ExpenseReportPage.xaml 파일을 탐색 창에서 이벤트 처리기입니다. 
  
    [!code-csharp[ExpenseIt#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]  
  
## <a name="creating-the-ui-for-expensereportpage"></a>ExpenseReportPage의 UI 만들기  
ExpenseReportPage.xaml에서는 ExpenseItHome.xaml에서 선택된 사람의 비용 보고서를 보여줍니다. 이 섹션 컨트롤을 추가 하 고 만듭니다는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ExpenseReportPage.xaml에 대 한 합니다. 이 섹션 배경 및 채우기 색을 다양 한도 추가 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 요소입니다. 
  
1. ExpenseReportPage.xaml을 엽니다. 
  
2. 다음 XAML을 <xref:System.Windows.Controls.Grid> 태그 사이에 추가합니다. 
  
     이 UI는 보고서 데이터에 표시 되는 점을 제외 하 고 ExpenseItHome.xaml에서 만들어진 UI와 유사는 <xref:System.Windows.Controls.DataGrid>합니다. 
  
    [!code-xaml[ExpenseIt#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]  
  
3. 응용 프로그램을 빌드 및 실행합니다. 
  
    > [!NOTE]
    >  오류가 발생 하는 경우는 <xref:System.Windows.Controls.DataGrid> 찾을 수 없습니다 또는 존재 하지 않거나, 프로젝트의 대상.NET Framework 4 이상 있는지 확인 합니다. 자세한 내용은 [방법: 한 버전의 .NET Framework를 대상으로 지정](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework)을 참조하세요. 
  
4. 클릭는 **보기** 단추입니다. 
  
     경비 보고서 페이지가 나타납니다. 
  
다음 그림에서는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ExpenseReportPage.xaml에 추가 된 요소입니다. 뒤로 탐색 단추를 사용할 수 있습니다. 
  
![ExpenseIt 샘플 스크린샷](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure4.png "GettingStartedFigure4")  
  
## <a name="styling-controls"></a>컨트롤 스타일 지정  
다양 한 요소의 모양을 수에 같은 종류의 모든 요소에 대해 동일는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]합니다. [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]에서는 스타일을 사용하여 여러 요소 간에 모양을 다시 사용할 수 있습니다. 다시 사용 가능한 스타일을 단순화 하는 데 도움이 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 생성 및 관리 합니다. 스타일에 대 한 자세한 내용은 참조 [스타일 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)합니다. 이 섹션에서는 이전 단계에서 정의된 요소별 특성을 스타일로 바꿉니다. 
  
1. Application.xaml 또는 App.xaml을 엽니다. 
  
2. 다음 xaml 간에 <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> 태그:  
  
    [!code-xaml[ExpenseIt#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]  
  
     이 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 다음 스타일을 추가 합니다.  
  
    -  `headerTextStyle`: 페이지 제목 <xref:System.Windows.Controls.Label>의 형식을 지정합니다. 
  
    -  `labelStyle`: <xref:System.Windows.Controls.Label> 컨트롤의 형식을 지정합니다. 
  
    -  `columnHeaderStyle`: <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>의 형식을 지정합니다. 
  
    -  `listHeaderStyle`: 목록 헤더 <xref:System.Windows.Controls.Border> 컨트롤의 형식을 지정합니다. 
  
    -  `listHeaderTextStyle`: 목록 머리글의 서식을 지정 하려면 다음을 수행 합니다 <xref:System.Windows.Controls.Label>합니다. 
  
    -  `buttonStyle`: 형식을 지정 하는 <xref:System.Windows.Controls.Button> ExpenseItHome.xaml에 합니다. 
  
     스타일은 리소스와의 자식을 <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> 속성 요소입니다. 이 위치에서 스타일은 응용 프로그램의 모든 요소에 적용됩니다. 리소스를 사용 하는 예제에 대 한 한 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] 응용 프로그램 참조 [사용 하 여 응용 프로그램 리소스](../../../../docs/framework/wpf/advanced/how-to-use-application-resources.md)합니다. 
  
3. ExpenseItHome.xaml을 엽니다. 
  
4. 사이 있는 모든 대체에서 <xref:System.Windows.Controls.Grid> 다음 XAML 사용 하 여 요소입니다. 
  
    [!code-xaml[ExpenseIt#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]  
  
     스타일을 적용하면 각 컨트롤의 모양을 정의하는 <xref:System.Windows.VerticalAlignment> 및 <xref:System.Windows.Media.FontFamily> 와 같은 속성이 제거되고 바뀝니다. 예를 들어는 `headerTextStyle` "보기 경비 보고서"에 적용할 <xref:System.Windows.Controls.Label>합니다. 
  
5. ExpenseReportPage.xaml을 엽니다. 
  
6. 사이 있는 모든 대체에서 <xref:System.Windows.Controls.Grid> 다음 XAML 사용 하 여 요소입니다. 
  
    [!code-xaml[ExpenseIt#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]  
  
     이렇게 하면 <xref:System.Windows.Controls.Label> 및 <xref:System.Windows.Controls.Border> 요소에 스타일이 추가됩니다. 
  
7. 응용 프로그램을 빌드 및 실행합니다. 
  
     추가한 후의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 이 섹션에서는 응용 프로그램에서는 동일한 스타일으로 업데이트 되 고 이전과 동일 합니다. 
  
## <a name="binding-data-to-a-control"></a>컨트롤에 데이터 바인딩  
이 섹션에서는 만듭니다는 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 다양 한 컨트롤에 바인딩되는 데이터입니다. 
  
1. ExpenseItHome.xaml을 엽니다. 
  
2. 에서는 여는 <xref:System.Windows.Controls.Grid> 요소를 만들려면 다음 xaml는 <xref:System.Windows.Data.XmlDataProvider> 각 사용자에 대 한 데이터를 포함 하 합니다. 
  
     으로 데이터가 생성 되었는지는 <xref:System.Windows.Controls.Grid> 리소스입니다. 일반적으로 파일로 로드되지만 편의상 데이터가 인라인으로 추가됩니다. 
  
    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]  
    [!code-xaml[ExpenseIt#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#23)]  
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]  
  
3. 에 <xref:System.Windows.Controls.Grid> 리소스를 다음 추가 <xref:System.Windows.DataTemplate>에 데이터를 표시 하는 방법을 정의 하는 <xref:System.Windows.Controls.ListBox>합니다. 데이터 템플릿에 대한 자세한 내용은 [데이터 템플릿 개요](../../../../docs/framework/wpf/data/data-templating-overview.md)를 참조하세요. 
  
    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]  
    [!code-xaml[ExpenseIt#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#24)]  
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]  
  
4. 기존 항목 바꾸기 <xref:System.Windows.Controls.ListBox> 다음 XAML로 합니다. 
  
    [!code-xaml[ExpenseIt#25](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]  
  
     이 XAML 바인딩하는 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 의 속성은 <xref:System.Windows.Controls.ListBox> 데이터 원본에으로 데이터 템플릿을 적용 하 고는 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>합니다. 
  
## <a name="connecting-data-to-controls"></a>컨트롤에 데이터 연결  
이 섹션에서는 ExpenseItHome.xaml 페이지에 있는 사용자 목록에서 선택한의 생성자에 대 한 참조를 전달 하는 현재 항목을 검색 하는 코드를 작성 `ExpenseReportPage` 인스턴스화하는 동안 합니다. `ExpenseReportPage`는 ExpenseReportPage.xaml에 정의된 컨트롤이 바인딩되는 전달된 항목으로 데이터 컨텍스트를 설정합니다. 
  
1. ExpenseReportPage.xaml.vb 또는 ExpenseReportPage.xaml.cs를 엽니다. 
  
2. 선택한 사람의 비용 보고서 데이터를 전달할 수 있도록 개체를 사용하는 생성자를 추가합니다. 
  
    [!code-csharp[ExpenseIt#26](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]  
  
3. ExpenseItHome.xaml.vb 또는 ExpenseItHome.xaml.cs를 엽니다. 
  
4. 변경 된 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 선택한 사람의 경비 보고서 데이터를 전달 하 여 새 생성자를 호출 하도록 이벤트 처리기입니다. 
  
    [!code-csharp[ExpenseIt#27](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]  
  
## <a name="styling-data-with-data-templates"></a>데이터 서식 파일을 사용 하 여 스타일 데이터  
이 섹션에서는 업데이트는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 데이터 템플릿을 사용 하 여 바인딩된 목록의 데이터의 각 항목에 대 한 합니다. 
  
1. ExpenseReportPage.xaml을 엽니다. 
  
2. "Name" 및 "부서"의 내용이 바인딩 <xref:System.Windows.Controls.Label> 요소를 사용 하는 적절 한 데이터 원본 속성입니다. 데이터 바인딩에 대한 자세한 내용은 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)를 참조하세요. 
  
    [!code-xaml[ExpenseIt#31](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]  
  
3. 에서는 여 <xref:System.Windows.Controls.Grid> 요소인 비용 보고서 데이터를 표시 하는 방법을 정의 하는 다음 데이터 템플릿을 추가 합니다.  
    [!code-xaml[ExpenseIt#30](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]  
  
4. 에 템플릿을 적용는 <xref:System.Windows.Controls.DataGrid> 비용 표시 하는 열 데이터를 보고 합니다. 
  
    [!code-xaml[ExpenseIt#32](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]  
  
5. 응용 프로그램을 빌드 및 실행합니다. 
  
6. 사용자를 선택 하 고 클릭는 **보기** 단추입니다. 
  
 다음 그림에서는 컨트롤, 레이아웃, 스타일, 데이터 바인딩 및 데이터 템플릿이 적용된 ExpenseIt 응용 프로그램의 페이지를 둘 다 보여 줍니다. 
  
 ![ExpenseIt 샘플 스크린샷](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure5.png "GettingStartedFigure5")  
  
## <a name="best-practices"></a>최선의 구현 방법  
이 샘플에서는 WPF의 특정 기능에 대해 설명하므로 응용 프로그램 개발 모범 사례를 따르지 않습니다. 포괄적인 적용 범위에 대 한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 및 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] 적절 하 게 다음 항목을 참조 하는 응용 프로그램 개발 모범 사례:  
  
-   접근성 - [접근성에 대한 유용한 정보](../../../../docs/framework/ui-automation/accessibility-best-practices.md)  
  
-   보안- [보안](../../../../docs/framework/wpf/security-wpf.md)  
  
-   지역화 - [WPF 전역화 및 지역화 개요](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)  
  
-   성능 - [WPF 응용 프로그램 성능 최적화](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
  
## <a name="whats-next"></a>새로운 기능  
이제 만들기에 다양 한 기술을 갖추고 있는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 를 사용 하 여 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]합니다. 데이터 바인딩된의 기본 구성 요소에 잘 이해할 이제 있어야 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] 응용 프로그램입니다. 이 항목은 전체 목록이 아니며 이 항목에 설명된 기술 외의 가능성을 스스로 발견할 수도 있습니다. 
  
 WPF 아키텍처 및 프로그래밍 모델에 대한 자세한 내용은 다음 항목을 참조하세요.  
  
-   [WPF 아키텍처](../../../../docs/framework/wpf/advanced/wpf-architecture.md)  
  
-   [XAML 개요(WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
  
-   [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
  
-   [레이아웃](../../../../docs/framework/wpf/advanced/layout.md)  
  
 응용 프로그램을 만드는 방법에 대한 자세한 내용은 다음 항목을 참조하세요.  
  
-   [응용 프로그램 개발](../../../../docs/framework/wpf/app-development/index.md)  
  
-   [컨트롤](../../../../docs/framework/wpf/controls/index.md)  
  
-   [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)  
  
-   [그래픽 및 멀티미디어](../../../../docs/framework/wpf/graphics-multimedia/index.md)  
  
-   [WPF의 문서](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
  
## <a name="see-also"></a>참고자료  
 [패널 개요](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [데이터 템플릿 개요](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [WPF 응용 프로그램 빌드](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)  
 [스타일 및 템플릿](../../../../docs/framework/wpf/controls/styles-and-templates.md)
