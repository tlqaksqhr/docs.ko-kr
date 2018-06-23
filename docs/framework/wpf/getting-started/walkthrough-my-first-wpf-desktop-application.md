---
title: Visual Studio에서 WPF 응용 프로그램 만들기
ms.date: 04/12/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 876bf9bf952aa9591a9ccbe51baaca9c5c71388e
ms.sourcegitcommit: c217b067985905cb21eafc5dd9a83568d7ff4e45
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/22/2018
ms.locfileid: "36314778"
---
# <a name="walkthrough-my-first-wpf-desktop-application"></a>연습: 내 첫 WPF 데스크톱 응용 프로그램

이 문서에서는 대부분의 WPF 응용 프로그램에 공통 된 요소를 포함 하는 간단한 Windows Presentation Foundation (WPF) 응용 프로그램을 개발 하는 방법을 보여 줍니다: 응용 프로그램 태그 XAML (Extensible Language) 태그, 코드 숨김, 응용 프로그램 정의 컨트롤, 레이아웃, 데이터 바인딩 및 스타일.

이 연습에서는 다음 단계를 포함 합니다.

- XAML을 사용 하 여 응용 프로그램의 UI (사용자 인터페이스) 모양 디자인 합니다.

- 응용 프로그램의 동작을 작성 하기 위해 코드를 작성 합니다.

- 응용 프로그램을 관리 하려면 응용 프로그램 정을 만듭니다.

- 컨트롤을 추가 하 고 응용 프로그램 UI를 작성 하는 레이아웃을 만듭니다.

- 응용 프로그램의 UI 전체에서 일관 된 모양에 대 한 스타일을 만듭니다.

- 데이터를 모두 UI 데이터를 채우고 데이터 및 동기화 UI를 유지 하도록 UI를 바인딩하십시오.

이 연습에서는 끝날 때까지 독립 실행형 사용자가 선택한 사용자에 대 한 경비 보고서를 볼 수 있도록 하는 Windows 응용 프로그램 작성 합니다. 응용 프로그램은 브라우저 스타일 창에서 호스트 되는 여러 WPF 페이지로 구성 됩니다.

> [!TIP]
> 이 연습에 사용 되는 샘플 코드는 Visual Basic 및 C#에서 사용할 수 있는 [WPF 응용 프로그램 빌드 소개](http://go.microsoft.com/fwlink/?LinkID=160008)합니다.

## <a name="prerequisites"></a>전제 조건

- Visual Studio 2012 이상

Visual Studio의 최신 버전을 설치 하는 방법에 대 한 자세한 내용은 참조 [Visual Studio 설치](/visualstudio/install/install-visual-studio)합니다.

## <a name="create-the-application-project"></a>응용 프로그램 프로젝트 만들기

첫 번째 단계는 응용 프로그램 정의 두 페이지 및 이미지를 포함 하 여 응용 프로그램 인프라를 만드는 것입니다.

1. Visual Basic 또는 Visual C# 라는에서 새 WPF 응용 프로그램 프로젝트를 만들 **ExpenseIt**:

   1. Visual Studio를 열고 선택 **파일** > **새로** > **프로젝트**합니다.

      **새 프로젝트** 대화 상자가 열립니다.

   2. 아래는 **설치 됨** 범주를 확장 한 다음는 **Visual C#** 또는 **Visual Basic** 노드를 선택한 후 **클래식 Windows 데스크톱**합니다.

   3. 선택 된 **WPF 응용 프로그램 (.NET Framework)** 서식 파일입니다. 이름을 입력 **ExpenseIt** 선택한 후 **확인**합니다.

      ![새 프로젝트 대화 상자를 선택 하는 WPF 응용 프로그램](media/new-project-dialog.png)

      Visual Studio 프로젝트를 만들고 이라는 기본 응용 프로그램 창에 대 한 디자이너를 엽니다 **MainWindow.xaml**합니다.

   > [!NOTE]
   > 이 연습에서는 <xref:System.Windows.Controls.DataGrid> 이상.NET Framework 4에서에서 사용할 수 있는 컨트롤입니다. 프로젝트의 대상.NET Framework 4 있는지 이상 이어야 합니다. 자세한 내용은 [방법: 한 버전의 .NET Framework를 대상으로 지정](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework)을 참조하세요.

2. 열기 *Application.xaml* (Visual Basic) 또는 *App.xaml* (C#).

    이 XAML 파일에는 WPF 응용 프로그램 및 모든 응용 프로그램 리소스 정의합니다. 또한 자동으로 표시 되는 UI를 지정 하려면이 파일을 사용 하면 응용 프로그램 시작; 이 경우 *MainWindow.xaml*합니다.

    XAML은 Visual Basic에서 다음과 같이 표시 됩니다.

    [!code-xaml[ExpenseIt#1_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    C#에서는 다음과 같이 나타납니다.

    [!code-xaml[ExpenseIt#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. 열기 *MainWindow.xaml*합니다.

    이 XAML 파일은 응용 프로그램의 주 창이 하 고 페이지에서 만든 콘텐츠를 표시 합니다. <xref:System.Windows.Window> 클래스 제목, 크기 또는 아이콘을 같은 창, 속성을 정의 하며, 닫기 또는 숨기기 등의 이벤트를 처리 합니다.

4. 변경 된 <xref:System.Windows.Window> 요소를 한 <xref:System.Windows.Navigation.NavigationWindow>다음 XAML에 나타난 것 처럼:

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   이 앱은 사용자 입력에 따라 다른 콘텐츠를 탐색 합니다. 이 인해 주 <xref:System.Windows.Window> 를 변경 해야 하는 <xref:System.Windows.Navigation.NavigationWindow>합니다. <xref:System.Windows.Navigation.NavigationWindow> 모든 속성을 상속 <xref:System.Windows.Window>합니다. <xref:System.Windows.Navigation.NavigationWindow> 의 인스턴스를 만들고 XAML 파일의 요소는 <xref:System.Windows.Navigation.NavigationWindow> 클래스입니다. 자세한 내용은 참조 [탐색 개요](../../../../docs/framework/wpf/app-development/navigation-overview.md)합니다.

5. 다음 속성을 변경한는 <xref:System.Windows.Navigation.NavigationWindow> 요소:

    - 설정의 <xref:System.Windows.Window.Title%2A> 속성을 "ExpenseIt"입니다.

    - 설정의 <xref:System.Windows.FrameworkElement.Width%2A> 속성을 500 픽셀로 합니다.

    - 설정의 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 350 픽셀로 합니다.

    - 제거는 <xref:System.Windows.Controls.Grid> 간에 요소는 <xref:System.Windows.Navigation.NavigationWindow> 태그입니다.

    XAML은 Visual Basic에서 다음과 같이 표시 됩니다.

    [!code-xaml[ExpenseIt#2_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    C#에서는 다음과 같이 나타납니다.

    [!code-xaml[ExpenseIt#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

6. 열기 *MainWindow.xaml.vb* 또는 *MainWindow.xaml.cs*합니다.

    이 파일에 선언 된 이벤트를 처리 하는 코드를 포함 하는 코드 숨김 파일은 *MainWindow.xaml*합니다. 이 파일에는 XAML에 정의된 창의 부분 클래스가 포함되어 있습니다.

7. C#을 사용 하는 경우 변경 된 `MainWindow` 클래스에서 파생 되도록 <xref:System.Windows.Navigation.NavigationWindow>합니다. (Visual basic에서는이 XAML에서 창을 변경할.)

   코드는 다음과 같이 표시 됩니다.

   [!code-csharp[ExpenseIt#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml.cs#3)]
   [!code-vb[ExpenseIt#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml.vb#3)]

   > [!TIP]
   > C# 및 Visual Basic에서 사이는 샘플 코드의 코드 언어를 설정/해제할 수는 **언어** 드롭 다운이 문서의 오른쪽 상단에 있습니다.

## <a name="add-files-to-the-application"></a>응용 프로그램에 파일 추가

이 섹션에서는 응용 프로그램에 두 페이지와 이미지를 추가합니다.

1. 새 WPF 페이지 프로젝트에 추가 하 고 이름을 *ExpenseItHome.xaml*:

   1. **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭는 **ExpenseIt** 프로젝트 노드를 선택 하 고 **추가** > **페이지**합니다.

   1. 에 **새 항목 추가** 대화 상자에서는 **페이지 (WPF)** 템플릿을 이미 선택 되어 있습니다. 이름을 입력 **ExpenseItHome**를 선택한 후 **추가**합니다.

    이 페이지에는 응용 프로그램을 시작할 때 표시 되는 첫 번째 페이지가입니다. 에 대 한 경비 보고서를 표시 하려면를 선택 하는 사람 목록이 표시 됩니다.

2. *ExpenseItHome.xaml*을 엽니다.

3. 설정의 <xref:System.Windows.Controls.Page.Title%2A> "ExpenseIt-홈"에 있습니다.

    XAML은 Visual Basic에서 다음과 같이 표시 됩니다.

    [!code-xaml[ExpenseIt#6_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    C#에서는 다음과 같이 나타납니다.

    [!code-xaml[ExpenseIt#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

4. 열기 *MainWindow.xaml*합니다.

5. 설정의 <xref:System.Windows.Navigation.NavigationWindow.Source%2A> 속성에는 <xref:System.Windows.Navigation.NavigationWindow> "ExpenseItHome.xaml"를 합니다.

    이렇게 하면 *ExpenseItHome.xaml* 이 응용 프로그램을 시작할 때 열리는 첫 페이지로 설정됩니다. XAML은 Visual Basic에서 다음과 같이 표시 됩니다.

    [!code-xaml[ExpenseIt#7_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    C#에서는 다음과 같이 나타납니다.

    [!code-xaml[ExpenseIt#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > 설정할 수도 있습니다는 **소스** 속성에는 **기타** 의 범주는 **속성** 창.
   >
   > ![속성 창에서 source 속성](media/properties-source.png)

6. 프로젝트에 다른 새 WPF 페이지를 추가 하 고 이름을 *ExpenseReportPage.xaml*::

   1. **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭는 **ExpenseIt** 프로젝트 노드를 선택 하 고 **추가** > **페이지**합니다.

   1. 에 **새 항목 추가** 대화 상자에서는 **페이지 (WPF)** 템플릿을 이미 선택 되어 있습니다. 이름을 입력 **ExpenseReportPage**를 선택한 후 **추가**합니다.

    이 페이지에서 선택 된 사람에 대 한 경비 보고서에 표시 됩니다는 **ExpenseItHome** 페이지.

7. *ExpenseReportPage.xaml*을 엽니다.

8. 설정의 <xref:System.Windows.Controls.Page.Title%2A> "ExpenseIt-View Expense"에 있습니다.

    XAML은 Visual Basic에서 다음과 같이 표시 됩니다.

    [!code-xaml[ExpenseIt#4_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    C#에서는 다음과 같이 나타납니다.

    [!code-xaml[ExpenseIt#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

9. 열기 *ExpenseItHome.xaml.vb* 및 *ExpenseReportPage.xaml.vb*, 또는 *ExpenseItHome.xaml.cs* 및 *ExpenseReportPage.xaml.cs*.

    새 페이지 파일을 만들면 Visual Studio 자동으로 만듭니다는 *코드 숨김* 파일입니다. 이러한 코드 숨김 파일은 사용자 입력에 응답하기 위한 논리를 처리합니다.

    코드에 대 한 다음과 같이 표시 됩니다 **ExpenseItHome**:

    [!code-csharp[ExpenseIt#2_5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]
    [!code-vb[ExpenseIt#2_5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    및에 대 한 다음과 같은 **ExpenseReportPage**:

    [!code-csharp[ExpenseIt#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]
    [!code-vb[ExpenseIt#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

10. 명명 된 이미지를 추가 *watermark.png* 프로젝트에 있습니다. 사용자 고유의 이미지를 만들, 샘플 코드에서 파일을 복사 하거나 가져올 수 있습니다 [여기](https://github.com/dotnet/docs/blob/master/docs/framework/wpf/getting-started/media/watermark.png)합니다.

   1. 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **추가** > **기존 항목**, 하거나 키를 눌러 **Shift**+**Alt** + **A**합니다.

   2. 에 **기존 항목 추가** 대화 상자에서 다음을 선택 하 고 사용할 하려는 이미지 파일을 찾은 **추가**합니다.

## <a name="build-and-run-the-application"></a>응용 프로그램 빌드 및 실행

1. 키를 눌러를 빌드하고 응용 프로그램을 실행 하려면 **F5** 선택 또는 **디버깅 시작** 에서 **디버그** 메뉴.

    다음 그림에 나와 있는 응용 프로그램의 <xref:System.Windows.Navigation.NavigationWindow> 단추:

    ![ExpenseIt 샘플 스크린샷](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure1.png)

2. Visual Studio로 되돌아가려면 응용 프로그램을 닫습니다.

## <a name="create-the-layout"></a>레이아웃 만들기

레이아웃 UI 요소를 배치 하는 순서가 지정 된 방법을 제공 하 고 UI의 크기를 조정할 때 해당 요소의 위치와 크기를 관리할 수 있습니다. 일반적으로 다음 레이아웃 컨트롤 중 하나를 사용하여 레이아웃을 만듭니다.

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.DockPanel>
- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.VirtualizingStackPanel>
- <xref:System.Windows.Controls.WrapPanel>

이러한 레이아웃 컨트롤은 각각 자식 요소의 특수 레이아웃 형식을 지원합니다. ExpenseIt 페이지는 크기를 조정할 수 있으며, 각 페이지의 요소는 다른 요소와 함께 가로 및 세로 방향으로 정렬됩니다. 따라서는 <xref:System.Windows.Controls.Grid> 는 응용 프로그램에 대 한 적합 한 레이아웃 요소입니다.

> [!TIP]
> 에 대 한 자세한 내용은 <xref:System.Windows.Controls.Panel> 요소 참조 [패널 개요](../../../../docs/framework/wpf/controls/panels-overview.md)합니다. 레이아웃에 대 한 자세한 내용은 참조 [레이아웃](../../../../docs/framework/wpf/advanced/layout.md)합니다.

섹션에는 단일 열 테이블을 만들면 행 3 개와 10 픽셀 여백 행 및 열 정의를 추가 하 여는 <xref:System.Windows.Controls.Grid> 에 *ExpenseItHome.xaml*합니다.

1. *ExpenseItHome.xaml*을 엽니다.

2. 설정의 <xref:System.Windows.FrameworkElement.Margin%2A> 속성에는 <xref:System.Windows.Controls.Grid> "10,0,10,10" 왼쪽, 위쪽, 오른쪽 및 아래쪽 여백에 해당 하는 요소:

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > 설정할 수도 있습니다는 **여백** 값에 **속성** 창 아래에서 **레이아웃** 범주:
   >
   > ![속성 창에서 여백 값](media/properties-margin.png)

3. 추가 사이 다음 XAML은 <xref:System.Windows.Controls.Grid> 행 및 열 정의를 만드는 태그:

    [!code-xaml[ExpenseIt#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    <xref:System.Windows.Controls.RowDefinition.Height%2A> 로 설정 된 두 개의 행 <xref:System.Windows.GridLength.Auto%2A>, 즉, 행 크기는 행의 콘텐츠에 따라 결정 합니다. 기본 <xref:System.Windows.Controls.RowDefinition.Height%2A> 은 <xref:System.Windows.GridUnitType.Star> 크기 조정, 행 높이가 사용 가능한 공간에 대 한 가중치 임을 의미 합니다. 예를 들어 두 개의 행이 있으면는 <xref:System.Windows.Controls.RowDefinition.Height%2A> 의 "*"를 사용 가능한 공간 중 절반 높이 각각.

    프로그램 <xref:System.Windows.Controls.Grid> 이제 다음 XAML 같이 표시 합니다.

    [!code-xaml[ExpenseIt#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a>컨트롤 추가

이 섹션에서는 홈 페이지는 사용자에 대 한 경비 보고서를 표시 하도록 선택할 수 있는 직원의 목록을 표시 하도록 UI를 업데이트 합니다. 컨트롤은 사용자가 응용 프로그램과 상호 작용할 수 있게 하는 UI 개체입니다. 자세한 내용은 [컨트롤](../../../../docs/framework/wpf/controls/index.md)을 참조하세요.

이 UI를 만들려면 다음 요소를 추가 합니다 *ExpenseItHome.xaml*:

- <xref:System.Windows.Controls.ListBox> (목록에 대해 사용자).
- <xref:System.Windows.Controls.Label> (예: 목록 헤더의 경우).
- <xref:System.Windows.Controls.Button> (클릭 하 여 목록에서 선택 되어 있는 사람에 대 한 경비 보고서를 볼 수)입니다.

각 컨트롤의 행에 배치 되는 <xref:System.Windows.Controls.Grid> 설정 하 여는 <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> 연결 된 속성입니다. 연결 된 속성에 대 한 자세한 내용은 참조 [연결 된 속성 개요](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)합니다.

1. *ExpenseItHome.xaml*을 엽니다.

2. 다음 xaml 위치 사이 <xref:System.Windows.Controls.Grid> 태그:

   [!code-xaml[ExpenseIt#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > 끌어서 컨트롤을 만들 수도 있습니다는 **도구 상자** 창 디자인 창 및 해당 속성 설정이 **속성** 창.

3. 응용 프로그램을 빌드 및 실행합니다.

다음 그림은 방금 만든 컨트롤을 보여 줍니다.

![ExpenseIt 샘플 스크린샷](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure2.png)

## <a name="add-an-image-and-a-title"></a>이미지와 제목을 추가 합니다.

이 섹션에서는 이미지 및 페이지 제목을 사용 하 여 홈 페이지 UI를 업데이트 합니다.

1. *ExpenseItHome.xaml*을 엽니다.

2. 다른 열을 추가 하는 <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> 고정 된 <xref:System.Windows.Controls.ColumnDefinition.Width%2A> 230 픽셀인:

    [!code-xaml[ExpenseIt#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11)]

3. 다른 행을 추가 하 고 <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, 총 4 개 행의:

    [!code-xaml[ExpenseIt#11b](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11b)]

4. 두 번째 열을 설정 하 여 컨트롤을 이동는 <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> 속성을 각각의 세 가지 컨트롤 (테두리, 목록 상자에서 및 단추)에서 1로 합니다.

5. 증가 시켜 각 컨트롤을 한 행 아래로 이동 합니다. 해당 <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> 값을 1 씩 합니다.

   이제 세 가지 컨트롤에 대 한 XAML은 다음과 같습니다.

    [!code-xaml[ExpenseIt#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

6. 설정의 <xref:System.Windows.Controls.Panel.Background%2A> 의 <xref:System.Windows.Controls.Grid> 되도록는 *watermark.png* 사이 다음 XAML 위치를 추가 하 여 이미지 파일의 `<Grid>` 및 `</Grid>` 태그:

    [!code-xaml[ExpenseIt#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

7. 전에 <xref:System.Windows.Controls.Border> 요소를 추가 <xref:System.Windows.Controls.Label> 콘텐츠로 "경비 보고서 보기"입니다. 페이지의 제목입니다.

    [!code-xaml[ExpenseIt#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

8. 응용 프로그램을 빌드 및 실행합니다.

다음 그림에서는 방금 추가한 작업의 결과 보여 줍니다.

![ExpenseIt 샘플 스크린샷](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure3.png)

## <a name="add-code-to-handle-events"></a>이벤트를 처리 하는 코드 추가

1. *ExpenseItHome.xaml*을 엽니다.

2. 추가 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 를 이벤트 처리기는 <xref:System.Windows.Controls.Button> 요소입니다. 자세한 내용은 참조 [하는 방법: 간단한 이벤트 처리기를 만들](http://msdn.microsoft.com/library/b1456e07-9dec-4354-99cf-18666b64f480)합니다.

    [!code-xaml[ExpenseIt#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

3. *ExpenseItHome.xaml.vb* 또는 *ExpenseItHome.xaml.cs*를 엽니다.

4. 다음 코드를 추가 하는 `ExpenseItHome` 클래스 단추를 추가 하려면 클릭 이벤트 처리기입니다. 이벤트 처리기 열립니다는 **ExpenseReportPage** 페이지.

    [!code-csharp[ExpenseIt#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a>ExpenseReportPage에 대 한 UI 만들기

*ExpenseReportPage.xaml* 경비 보고서에 선택 되어 있는 사람의 표시는 **ExpenseItHome** 페이지. 이 섹션에서는 컨트롤 하의 UI를 만들고 **ExpenseReportPage**합니다. 또한 배경 추가 하 고 다양 한 UI 요소에 색 채우기 합니다.

1. *ExpenseReportPage.xaml*을 엽니다.

2. 다음 xaml 간에 <xref:System.Windows.Controls.Grid> 태그:

    [!code-xaml[ExpenseIt#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    이 UI는 비슷합니다 *ExpenseItHome.xaml*보고서 데이터에 표시 되는 점을 제외 하 고는 <xref:System.Windows.Controls.DataGrid>합니다.

3. 응용 프로그램을 빌드 및 실행합니다.

    > [!NOTE]
    > 오류가 발생 하는 경우는 <xref:System.Windows.Controls.DataGrid> 찾을 수 없습니다 또는 존재 하지 않거나, 프로젝트의 대상.NET Framework 4 이상 있는지 확인 합니다. 자세한 내용은 [방법: 한 버전의 .NET Framework를 대상으로 지정](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework)을 참조하세요.

4. 선택 된 **보기** 단추입니다.

    경비 보고서 페이지가 나타납니다. 또한 탐색 단추를 사용할 수 있는지 확인 하십시오.

다음 그림에 추가 UI 요소를 보여 줍니다. *ExpenseReportPage.xaml*합니다.

![ExpenseIt 샘플 스크린샷](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure4.png)

## <a name="style-controls"></a>스타일 컨트롤

다양 한 요소의 모양을 종종 UI에 같은 종류의 모든 요소에 대해 동일 합니다. UI를 사용 하 여 [스타일](../../../../docs/framework/wpf/controls/styling-and-templating.md) 을 통해 여러 요소에서 모양을 다시 사용할 수 있습니다. 다시 사용 가능한 스타일 XAML 만들기 및 관리를 간소화할 수 있습니다. 이 섹션에서는 이전 단계에서 정의된 요소별 특성을 스타일로 바꿉니다.

1. 열기 *Application.xaml* 또는 *App.xaml*합니다.

2. 다음 xaml 간에 <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> 태그:

    [!code-xaml[ExpenseIt#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    이 XAML은 다음 스타일을 추가합니다.

    - `headerTextStyle`: 페이지 제목 <xref:System.Windows.Controls.Label>의 형식을 지정합니다.

    - `labelStyle`: <xref:System.Windows.Controls.Label> 컨트롤의 형식을 지정합니다.

    - `columnHeaderStyle`: <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>의 형식을 지정합니다.

    - `listHeaderStyle`: 목록 헤더 <xref:System.Windows.Controls.Border> 컨트롤의 형식을 지정합니다.

    - `listHeaderTextStyle`: 목록 머리글의 서식을 지정 하려면 다음을 수행 합니다 <xref:System.Windows.Controls.Label>합니다.

    - `buttonStyle`: 형식을 지정 하는 <xref:System.Windows.Controls.Button> ExpenseItHome.xaml에 합니다.

    스타일은 리소스와의 자식을 <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> 속성 요소입니다. 이 위치에서 스타일은 응용 프로그램의 모든 요소에 적용됩니다. .NET Framework 응용 프로그램의 리소스 사용의 예를 들어 참조 [사용 하 여 응용 프로그램 리소스](../../../../docs/framework/wpf/advanced/how-to-use-application-resources.md)합니다.

3. *ExpenseItHome.xaml*을 엽니다.

4. 사이 있는 모든 대체에서 <xref:System.Windows.Controls.Grid> 다음 XAML 사용 하 여 요소:

    [!code-xaml[ExpenseIt#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    스타일을 적용하면 각 컨트롤의 모양을 정의하는 <xref:System.Windows.VerticalAlignment> 및 <xref:System.Windows.Media.FontFamily> 와 같은 속성이 제거되고 바뀝니다. 예를 들어는 `headerTextStyle` "보기 경비 보고서"에 적용할 <xref:System.Windows.Controls.Label>합니다.

5. *ExpenseReportPage.xaml*을 엽니다.

6. 사이 있는 모든 대체에서 <xref:System.Windows.Controls.Grid> 다음 XAML 사용 하 여 요소:

    [!code-xaml[ExpenseIt#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    이렇게 하면 <xref:System.Windows.Controls.Label> 및 <xref:System.Windows.Controls.Border> 요소에 스타일이 추가됩니다.

## <a name="bind-data-to-a-control"></a>컨트롤에 데이터 바인딩

이 섹션에서는 다양 한 컨트롤에 바인딩된 XML 데이터를 만듭니다.

1. *ExpenseItHome.xaml*을 엽니다.

2. 에서는 여 <xref:System.Windows.Controls.Grid> 요소를 만들려면 다음 xaml는 <xref:System.Windows.Data.XmlDataProvider> 각 사용자에 대 한 데이터를 포함 하:

    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]
    [!code-xaml[ExpenseIt#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#23)]
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]

    으로 데이터가 생성 되었는지는 <xref:System.Windows.Controls.Grid> 리소스입니다. 일반적으로 파일로 로드되지만 편의상 데이터가 인라인으로 추가됩니다.

3. 내에서 `<Grid.Resources>` 요소를 다음 추가 <xref:System.Windows.DataTemplate>의 데이터를 표시 하는 방법을 정의 하는 <xref:System.Windows.Controls.ListBox>:

    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]
    [!code-xaml[ExpenseIt#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#24)]
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]

    데이터 템플릿에 대 한 자세한 내용은 참조 [데이터 템플릿 개요](../../../../docs/framework/wpf/data/data-templating-overview.md)합니다.

4. 기존 항목 바꾸기 <xref:System.Windows.Controls.ListBox> 다음 XAML로:

    [!code-xaml[ExpenseIt#25](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    이 XAML 바인딩하는 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 의 속성은 <xref:System.Windows.Controls.ListBox> 데이터 원본에으로 데이터 템플릿을 적용 하 고는 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>합니다.

## <a name="connect-data-to-controls"></a>컨트롤에 데이터 연결

선택한 이름을 검색 하는 코드를 다음으로 추가 된 **ExpenseItHome** 페이지의 생성자에 전달 하 고 **ExpenseReportPage**합니다. **ExpenseReportPage** 은 컨트롤의 정의 전달 된 항목을 가진 데이터 컨텍스트가 해당 설정에 *ExpenseReportPage.xaml* 에 바인딩합니다.

1. *ExpenseReportPage.xaml.vb* 또는 *ExpenseReportPage.xaml.cs*를 엽니다.

2. 선택한 사람의 비용 보고서 데이터를 전달할 수 있도록 개체를 사용하는 생성자를 추가합니다.

    [!code-csharp[ExpenseIt#26](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. *ExpenseItHome.xaml.vb* 또는 *ExpenseItHome.xaml.cs*를 엽니다.

4. 변경 된 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 선택한 사람의 경비 보고서 데이터를 전달 하 여 새 생성자를 호출 하도록 이벤트 처리기입니다.

    [!code-csharp[ExpenseIt#27](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a>데이터 서식 파일을 사용 하 여 스타일 데이터

이 섹션에서는 데이터 템플릿을 사용 하 여 데이터 바인딩된 목록의 각 항목에에서 대 한 UI를 업데이트 합니다.

1. *ExpenseReportPage.xaml*을 엽니다.

2. "Name" 및 "부서"의 내용이 바인딩 <xref:System.Windows.Controls.Label> 요소를 사용 하는 적절 한 데이터 원본 속성입니다. 데이터 바인딩에 대 한 자세한 내용은 참조 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)합니다.

    [!code-xaml[ExpenseIt#31](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. 에서는 여는 <xref:System.Windows.Controls.Grid> 요소인 경비 보고서 데이터를 표시 하는 방법을 정의 하는 다음 데이터 템플릿을 추가 합니다.

    [!code-xaml[ExpenseIt#30](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. 에 템플릿을 적용는 <xref:System.Windows.Controls.DataGrid> 비용 표시 하는 열 데이터를 보고 합니다.

    [!code-xaml[ExpenseIt#32](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. 응용 프로그램을 빌드 및 실행합니다.

6. 사용자를 선택한 다음 선택에서 **보기** 단추입니다.

다음 그림에서는 컨트롤, 레이아웃, 스타일, 데이터 바인딩 및 데이터 템플릿이 적용 된 ExpenseIt 응용 프로그램의 두 페이지를 보여 줍니다.

![ExpenseIt 샘플 스크린샷](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure5.png)

> [!NOTE]
> 이 샘플은 WPF의 특정 기능을 보여 및 보안, 지역화 및 내게 필요한 옵션 등을 위한 모든 모범 사례를 준수 하지 않습니다. WPF 및.NET Framework 응용 프로그램 개발 모범 사례의 포괄적인 적용 범위에 대 한 다음 항목을 참조 합니다.
>
> - [액세스 가능성](../../../../docs/framework/ui-automation/accessibility-best-practices.md)
>
> - [보안](../../../../docs/framework/wpf/security-wpf.md)
>
> - [WPF 전역화 및 지역화](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)
>
> - [WPF 성능](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a>다음 단계

이 연습에서는 다양 한 Windows Presentation Foundation (WPF)를 사용 하 여 UI를 만드는 방법 배웠습니다. 이제는 데이터 바인딩된.NET Framework 응용 프로그램의 구성 요소에 대 한 기본적인 이해 하 고 있어야 합니다. WPF 아키텍처 및 프로그래밍 모델에 대한 자세한 내용은 다음 항목을 참조하세요.

- [WPF 아키텍처](../../../../docs/framework/wpf/advanced/wpf-architecture.md)
- [XAML 개요 (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
- [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
- [레이아웃](../../../../docs/framework/wpf/advanced/layout.md)

응용 프로그램을 만드는 방법에 대한 자세한 내용은 다음 항목을 참조하세요.

- [응용 프로그램 개발](../../../../docs/framework/wpf/app-development/index.md)
- [컨트롤](../../../../docs/framework/wpf/controls/index.md)
- [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [그래픽 및 멀티미디어](../../../../docs/framework/wpf/graphics-multimedia/index.md)
- [WPF의 문서](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)

## <a name="see-also"></a>참고자료

- [개요 패널](../../../../docs/framework/wpf/controls/panels-overview.md)
- [데이터 템플릿 개요](../../../../docs/framework/wpf/data/data-templating-overview.md)
- [WPF 응용 프로그램 빌드](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)
- [스타일 및 템플릿](../../../../docs/framework/wpf/controls/styles-and-templates.md)
