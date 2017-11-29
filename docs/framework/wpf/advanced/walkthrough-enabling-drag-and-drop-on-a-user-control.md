---
title: "연습: 사용자 정의 컨트롤에서 끌어서 놓기 사용"
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
- walkthrough [WPF], drag-and-drop
- drag-and-drop [WPF], walkthrough
ms.assetid: cc844419-1a77-4906-95d9-060d79107fc7
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 360b453b2a25b6822485f18cc81cb43e313949eb
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="walkthrough-enabling-drag-and-drop-on-a-user-control"></a>연습: 사용자 정의 컨트롤에서 끌어서 놓기 사용
이 연습에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 끌어서 놓기 데이터 전송에 참가할 수 있는 사용자 지정 사용자 정의 컨트롤을 만드는 방법을 보여 줍니다.  
  
 이 연습에서는 사용자 지정 WPF 만들어집니다 <xref:System.Windows.Controls.UserControl> 원 모양을 나타내는입니다. 컨트롤에서 끌어서 놓기를 통해 데이터 전송을 활성화하는 기능을 구현합니다. 예를 들어 한 원 컨트롤에서 다른 원 컨트롤로 끌면 채우기 색 데이터가 소스 원에서 대상 원으로 복사됩니다. 원 컨트롤을 끌어서 놓으면는 <xref:System.Windows.Controls.TextBox>, 채우기 색의 문자열 표현에 복사 되는 <xref:System.Windows.Controls.TextBox>합니다. 두 개의 패널 컨트롤을 포함 하는 작은 응용 프로그램 만들어집니다 및 <xref:System.Windows.Controls.TextBox> 끌어서 놓기 기능을 테스트 합니다. 패널이 끌어 놓은 원 데이터를 처리하여 한 패널의 자식 컬렉션에서 다른 패널로 원을 이동하거나 복사할 수 있도록 하는 코드를 작성합니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   사용자 지정 사용자 정의 컨트롤 만들기  
  
-   사용자 정의 컨트롤을 끌기 소스로 사용할 수 있도록 설정  
  
-   사용자 정의 컨트롤을 놓기 대상으로 사용할 수 있도록 설정  
  
-   패널이 사용자 정의 컨트롤에서 놓은 데이터를 받을 수 있도록 설정  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   Visual Studio 2010  
  
## <a name="creating-the-application-project"></a>응용 프로그램 프로젝트 만들기  
 이 섹션에서는 두 개의 패널에 있는 주 페이지를 포함 하는 응용 프로그램 인프라를 만들어집니다 및 <xref:System.Windows.Controls.TextBox>합니다.  
  
### <a name="to-create-the-project"></a>프로젝트를 만들려면  
  
1.  Visual Basic 또는 Visual C#에서 `DragDropExample`이라는 새 WPF 응용 프로그램 프로젝트를 만듭니다. 자세한 내용은 [방법: 새 WPF 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/en-us/1f6aea7a-33e1-4d3f-8555-1daa42e95d82)를 참조하세요.  
  
2.  MainWindow.xaml을 엽니다.  
  
3.  여는 태그와 닫는 사이 다음 태그를 추가 <xref:System.Windows.Controls.Grid> 태그입니다.  
  
     이 태그는 테스트 응용 프로그램에 대한 사용자 인터페이스를 만듭니다.  
  
     [!code-xaml[DragDropWalkthrough#PanelsStep1XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]  
  
## <a name="adding-a-new-user-control-to-the-project"></a>프로젝트에 새 사용자 정의 컨트롤 추가  
 이 섹션에서는 프로젝트에 새 사용자 정의 컨트롤을 추가합니다.  
  
### <a name="to-add-a-new-user-control"></a>새 사용자 정의 컨트롤을 추가하려면  
  
1.  [프로젝트] 메뉴에서 **사용자 정의 컨트롤 추가**를 선택합니다.  
  
2.  [새 항목 추가] 대화 상자에서 이름을 `Circle.xaml`로 변경하고 **추가**를 클릭합니다.  
  
     Circle.xaml과 해당 코드 숨김이 프로젝트에 추가됩니다.  
  
3.  Circle.xaml을 엽니다.  
  
     이 파일에는 사용자 정의 컨트롤의 사용자 인터페이스 요소가 포함됩니다.  
  
4.  루트에 다음 태그를 추가 <xref:System.Windows.Controls.Grid> UI로 파란색 원 있는 간단한 사용자 정의 컨트롤을 만들 수 있습니다.  
  
     [!code-xaml[DragDropWalkthrough#EllipseXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]  
  
5.  Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.  
  
6.  C#에서는 기본 생성자 뒤에 다음 코드를 추가하여 복사 생성자를 만듭니다. Visual Basic에서는 다음 코드를 추가하여 기본 생성자와 복사 생성자를 모두 만듭니다.  
  
     사용자 정의 컨트롤을 복사할 수 있도록 하려면 코드 숨김 파일에서 복사 생성자 메서드를 추가합니다. 간단한 원 사용자 정의 컨트롤에서 사용자 정의 컨트롤의 채우기와 크기만 복사합니다.  
  
     [!code-csharp[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]  
  
### <a name="to-add-the-user-control-to-the-main-window"></a>주 창에 사용자 정의 컨트롤을 추가하려면  
  
1.  MainWindow.xaml을 엽니다.  
  
2.  다음 XAML을 여는 추가 <xref:System.Windows.Window> 태그를 현재 응용 프로그램에 대 한 XML 네임 스페이스 참조를 만듭니다.  
  
    ```  
    xmlns:local="clr-namespace:DragDropExample"  
    ```  
  
3.  첫 번째 범위에서 <xref:System.Windows.Controls.StackPanel>, 첫 번째 패널에서 원 사용자 정의 컨트롤의 두 인스턴스를 만들고 다음 XAML을 추가 합니다.  
  
     [!code-xaml[DragDropWalkthrough#CirclesXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]  
  
     패널에 대한 전체 XAML은 다음과 같습니다.  
  
     [!code-xaml[DragDropWalkthrough#PanelsStep2XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]  
  
## <a name="implementing-drag-source-events-in-the-user-control"></a>사용자 정의 컨트롤에서 끌기 소스 이벤트 구현  
 이 섹션에서을 재정의 하는 <xref:System.Windows.UIElement.OnMouseMove%2A> 메서드와 끌어서 놓기 작업을 시작 합니다.  
  
 끌기 시작 된 경우 (마우스 단추를 누르면 및 마우스를 이동)에 전송 될 데이터 패키지는 <xref:System.Windows.DataObject>합니다. 이 경우 원 컨트롤은 채우기 색의 문자열 표현, 높이의 double 표현과 자신의 복사본이라는 세 개의 데이터 항목을 패키지합니다.  
  
### <a name="to-initiate-a-drag-and-drop-operation"></a>끌어서 놓기 작업을 시작하려면  
  
1.  Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.  
  
2.  다음 추가 <xref:System.Windows.UIElement.OnMouseMove%2A> 클래스에 대 한 처리를 제공 하는 재정의 <xref:System.Windows.UIElement.MouseMove> 이벤트입니다.  
  
     [!code-csharp[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]  
  
     이 <xref:System.Windows.UIElement.OnMouseMove%2A> 재정의 다음 작업을 수행 합니다.  
  
    -   마우스를 이동하는 동안 마우스 왼쪽 단추를 눌렀는지 여부를 확인합니다.  
  
    -   패키지를 원형 데이터를 한 <xref:System.Windows.DataObject>합니다. 이 경우 원 컨트롤은 채우기 색의 문자열 표현, 높이의 double 표현과 자신의 복사본이라는 세 개의 데이터 항목을 패키지합니다.  
  
    -   정적 호출 <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> 메서드 끌어서 놓기 작업을 시작 합니다. 다음 세 가지 매개 변수를 전달 된 <xref:System.Windows.DragDrop.DoDragDrop%2A> 메서드:  
  
        -   `dragSource` – 이 컨트롤에 대한 참조입니다.  
  
        -   `data`– <xref:System.Windows.DataObject> 이전 코드에서 생성 합니다.  
  
        -   `allowedEffects`– 허용 된 끌어서 놓기 작업으로, <xref:System.Windows.DragDropEffects.Copy> 또는 <xref:System.Windows.DragDropEffects.Move>합니다.  
  
3.  F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.  
  
4.  원 컨트롤 중 하나를 클릭 하 고 다른 원 패널 위로 끕니다 및 <xref:System.Windows.Controls.TextBox>합니다. 위로 끌 때는 <xref:System.Windows.Controls.TextBox>, 커서 변경을 이동 하려면 빈를 나타냅니다.  
  
5.  원 위로 끌어 하는 동안는 <xref:System.Windows.Controls.TextBox>, CTRL 키를 누릅니다. 복사를 나타내기 위해 커서가 어떻게 변경되는지 확인합니다.  
  
6.  끌어서 놓기에 원은 <xref:System.Windows.Controls.TextBox>합니다. 원의 채우기 색의 문자열 표현에 추가 되는 <xref:System.Windows.Controls.TextBox>합니다.  
  
     ![원 채우기 색의 문자열 표현](../../../../docs/framework/wpf/advanced/media/dragdrop-colorstring.png "DragDrop_ColorString")  
  
 기본적으로 커서는 끌어서 놓기 작업 중 데이터 놓기의 결과를 나타내도록 변경됩니다. 처리 하 여 사용자에 게 제공 되는 피드백을 사용자 지정할 수는 <xref:System.Windows.UIElement.GiveFeedback> 이벤트 및 다른 커서를 설정 합니다.  
  
### <a name="to-give-feedback-to-the-user"></a>사용자에게 피드백을 제공하려면  
  
1.  Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.  
  
2.  다음 추가 <xref:System.Windows.UIElement.OnGiveFeedback%2A> 클래스에 대 한 처리를 제공 하는 재정의 <xref:System.Windows.UIElement.GiveFeedback> 이벤트입니다.  
  
     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]  
  
     이 <xref:System.Windows.UIElement.OnGiveFeedback%2A> 재정의 다음 작업을 수행 합니다.  
  
    -   확인 된 <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> 놓기 대상에 설정 된 값을 <xref:System.Windows.UIElement.DragOver> 이벤트 처리기입니다.  
  
    -   설정에 따라 사용자 지정 커서는 <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> 값입니다. 커서는 데이터 놓기의 결과에 대한 시각적 피드백을 사용자에게 제공하기 위한 것입니다.  
  
3.  F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.  
  
4.  다른 원 패널을 통해 제어 원 중 하나는 끌어서 및 <xref:System.Windows.Controls.TextBox>합니다. 커서에 지정 된 사용자 지정 커서 이제 됩니다는 <xref:System.Windows.UIElement.OnGiveFeedback%2A> 재정의 합니다.  
  
     ![사용자 지정 커서로 끌어서 놓기](../../../../docs/framework/wpf/advanced/media/dragdrop-customcursor.png "DragDrop_CustomCursor")  
  
5.  텍스트 선택 `green` 에서 <xref:System.Windows.Controls.TextBox>합니다.  
  
6.  `green` 텍스트를 원 컨트롤로 끕니다. 기본 커서가 끌어서 놓기 작업의 결과를 나타내도록 표시되는지 확인합니다. 피드백 커서는 항상 끌기 소스에 의해 설정됩니다.  
  
## <a name="implementing-drop-target-events-in-the-user-control"></a>사용자 정의 컨트롤에서 놓기 대상 이벤트 구현  
 이 섹션에서는 사용자 정의 컨트롤이 놓기 대상이 되도록 지정하고, 사용자 정의 컨트롤을 놓기 대상으로 사용할 수 있도록 설정하는 메서드를 재정의하며, 대상에 끌어 놓은 데이터를 처리합니다.  
  
### <a name="to-enable-the-user-control-to-be-a-drop-target"></a>사용자 정의 컨트롤을 놓기 대상으로 사용할 수 있도록 설정하려면  
  
1.  Circle.xaml을 엽니다.  
  
2.  여에서 <xref:System.Windows.Controls.UserControl> 태그, 추가 <xref:System.Windows.UIElement.AllowDrop%2A> 속성으로 설정 하 고 `true`합니다.  
  
     [!code-xaml[DragDropWalkthrough#UCTagXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]  
  
 <xref:System.Windows.UIElement.OnDrop%2A> 메서드를 호출한 경우는 <xref:System.Windows.UIElement.AllowDrop%2A> 속성이 `true` Circle 사용자 정의 컨트롤에서 끌기 소스에서 데이터를 삭제 하 고 있습니다. 이 메서드에서는 끌어 놓은 데이터를 처리하고 해당 데이터를 원에 적용합니다.  
  
### <a name="to-process-the-dropped-data"></a>끌어 놓은 데이터를 처리하려면  
  
1.  Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.  
  
2.  다음 추가 <xref:System.Windows.UIElement.OnDrop%2A> 클래스에 대 한 처리를 제공 하는 재정의 <xref:System.Windows.UIElement.Drop> 이벤트입니다.  
  
     [!code-csharp[DragDropWalkthrough#OnDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]  
  
     이 <xref:System.Windows.UIElement.OnDrop%2A> 재정의 다음 작업을 수행 합니다.  
  
    -   사용 하 여는 <xref:System.Windows.DataObject.GetDataPresent%2A> 메서드를 끌어온된 데이터 문자열 개체가 포함 되어 있는지 확인 합니다.  
  
    -   사용 하 여는 <xref:System.Windows.DataObject.GetData%2A> 메서드를 제공 하는 경우 문자열 데이터를 추출 합니다.  
  
    -   사용 하 여 한 <xref:System.Windows.Media.BrushConverter> 문자열을 변환 하려고 하는 <xref:System.Windows.Media.Brush>합니다.  
  
    -   브러시를 적용 하는 변환이 성공한 경우의 <xref:System.Windows.Shapes.Shape.Fill%2A> 의 <xref:System.Windows.Shapes.Ellipse> 원 컨트롤의 UI를 제공 하는 합니다.  
  
    -   표시는 <xref:System.Windows.UIElement.Drop> 이벤트를 처리 합니다. 이 이벤트를 수신하는 다른 요소가 원 사용자 정의 컨트롤에서 해당 이벤트를 처리했음을 알 수 있도록 놓기 이벤트를 처리된 것으로 표시해야 합니다.  
  
3.  F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.  
  
4.  텍스트 선택 `green` 에 <xref:System.Windows.Controls.TextBox>합니다.  
  
5.  텍스트를 원 컨트롤로 끌어서 놓습니다. 원이 파란색에서 녹색으로 바뀝니다.  
  
     ![문자열을 브러시로 변환](../../../../docs/framework/wpf/advanced/media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")  
  
6.  텍스트 입력 `green` 에 <xref:System.Windows.Controls.TextBox>합니다.  
  
7.  텍스트 선택 `gre` 에 <xref:System.Windows.Controls.TextBox>합니다.  
  
8.  이 텍스트를 원 컨트롤로 끌어서 놓습니다. 놓기가 허용됨을 나타내도록 커서가 변경되지만 `gre`가 유효한 색이 아니기 때문에 원의 색은 변경되지 않습니다.  
  
9. 녹색 원 컨트롤에서 끌어서 파란색 원 컨트롤에 놓습니다. 원이 파란색에서 녹색으로 바뀝니다. 어떤 커서가 표시 되는지 여부에 따라 달라 집니다는 <xref:System.Windows.Controls.TextBox> 원 끌기 원본인 또는 합니다.  
  
 설정의 <xref:System.Windows.UIElement.AllowDrop%2A> 속성을 `true` 요소를 놓기 대상이 될 수 있도록 하는 전송 된 데이터를 처리 합니다. 그러나 더 나은 사용자 환경을 제공 하려면 처리 해야는 <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, 및 <xref:System.Windows.UIElement.DragOver> 이벤트입니다. 이러한 이벤트에서 데이터를 놓기 전에 검사를 수행하고 사용자에게 추가 피드백을 제공할 수 있습니다.  
  
 데이터를 원 사용자 정의 컨트롤로 끌면 컨트롤에서 끌고 있는 데이터를 처리할 수 있는지 여부를 끌기 소스에 알려야 합니다. 컨트롤에서 데이터 처리 방법을 알지 못하는 경우 놓기를 거부해야 합니다. 이 위해 처리 합니다는 <xref:System.Windows.UIElement.DragOver> 이벤트 집합과 <xref:System.Windows.DragEventArgs.Effects%2A> 속성입니다.  
  
### <a name="to-verify-that-the-data-drop-is-allowed"></a>데이터 놓기가 허용되는지 확인하려면  
  
1.  Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.  
  
2.  다음 추가 <xref:System.Windows.UIElement.OnDragOver%2A> 클래스에 대 한 처리를 제공 하는 재정의 <xref:System.Windows.UIElement.DragOver> 이벤트입니다.  
  
     [!code-csharp[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]  
  
     이 <xref:System.Windows.UIElement.OnDragOver%2A> 재정의 다음 작업을 수행 합니다.  
  
    -   <xref:System.Windows.DragEventArgs.Effects%2A> 속성을 <xref:System.Windows.DragDropEffects.None>로 설정합니다.  
  
    -   수행 되는 동일한 검사를 수행 합니다.는 <xref:System.Windows.UIElement.OnDrop%2A> Circle 사용자 정의 컨트롤 끌어온된 데이터를 처리할 수 있는지 여부를 결정 하는 메서드.  
  
    -   사용자 정의 컨트롤에서 데이터를 처리할 수 있지만 하는 경우 설정의 <xref:System.Windows.DragEventArgs.Effects%2A> 속성을 <xref:System.Windows.DragDropEffects.Copy> 또는 <xref:System.Windows.DragDropEffects.Move>합니다.  
  
3.  F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.  
  
4.  텍스트 선택 `gre` 에 <xref:System.Windows.Controls.TextBox>합니다.  
  
5.  텍스트를 원 컨트롤로 끕니다. `gre`가 유효한 색이 아니므로 놓기가 허용되지 않음을 나타내도록 커서가 변경됩니다.  
  
 놓기 작업의 미리 보기를 적용하여 사용자 환경을 더욱 향상시킬 수 있습니다. Circle 사용자 정의 컨트롤에 대 한 재정의 하는 <xref:System.Windows.UIElement.OnDragEnter%2A> 및 <xref:System.Windows.UIElement.OnDragLeave%2A> 메서드. 데이터를 현재 백그라운드 컨트롤 위로 끌 때 <xref:System.Windows.Shapes.Shape.Fill%2A> 자리 표시자 변수에 저장 됩니다. 문자열이 다음는 브러시 속성으로 변환 되 고 적용할는 <xref:System.Windows.Shapes.Ellipse> 원의 제공 하는 UI입니다. 데이터를 놓지 원래 않고 원을 밖으로 끌 경우 <xref:System.Windows.Shapes.Shape.Fill%2A> 값 원에 다시 적용 됩니다.  
  
### <a name="to-preview-the-effects-of-the-drag-and-drop-operation"></a>끌어서 놓기 작업의 결과를 미리 보려면  
  
1.  Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.  
  
2.  Circle 클래스에서 private 선언 <xref:System.Windows.Media.Brush> 라는 변수 `_previousFill` 되도록 초기화 및 `null`합니다.  
  
     [!code-csharp[DragDropWalkthrough#Brush](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]  
  
3.  다음 추가 <xref:System.Windows.UIElement.OnDragEnter%2A> 클래스에 대 한 처리를 제공 하는 재정의 <xref:System.Windows.UIElement.DragEnter> 이벤트입니다.  
  
     [!code-csharp[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]  
  
     이 <xref:System.Windows.UIElement.OnDragEnter%2A> 재정의 다음 작업을 수행 합니다.  
  
    -   저장는 <xref:System.Windows.Shapes.Shape.Fill%2A> 의 속성은 <xref:System.Windows.Shapes.Ellipse> 에 `_previousFill` 변수입니다.  
  
    -   수행 되는 동일한 검사를 수행 합니다.는 <xref:System.Windows.UIElement.OnDrop%2A> 데이터를 변환할 수 있는지 여부를 확인 하는 <xref:System.Windows.Media.Brush>합니다.  
  
    -   데이터가 변환 되는 유효한 <xref:System.Windows.Media.Brush>, 되 게 적용 되는 <xref:System.Windows.Shapes.Shape.Fill%2A> 의 <xref:System.Windows.Shapes.Ellipse>합니다.  
  
4.  다음 추가 <xref:System.Windows.UIElement.OnDragLeave%2A> 클래스에 대 한 처리를 제공 하는 재정의 <xref:System.Windows.UIElement.DragLeave> 이벤트입니다.  
  
     [!code-csharp[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]  
  
     이 <xref:System.Windows.UIElement.OnDragLeave%2A> 재정의 다음 작업을 수행 합니다.  
  
    -   적용 되는 <xref:System.Windows.Media.Brush> 에 저장는 `_previousFill` 변수를 <xref:System.Windows.Shapes.Shape.Fill%2A> 의 <xref:System.Windows.Shapes.Ellipse> Circle 사용자 정의 컨트롤의 UI를 제공 하는 합니다.  
  
5.  F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.  
  
6.  텍스트 선택 `green` 에 <xref:System.Windows.Controls.TextBox>합니다.  
  
7.  텍스트를 놓지 않고 원 컨트롤 위로 끕니다. 원이 파란색에서 녹색으로 바뀝니다.  
  
     ![끌어서 놓기 작업의 결과 미리 보기](../../../../docs/framework/wpf/advanced/media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")  
  
8.  원 컨트롤에서 멀리 텍스트를 끕니다. 원이 녹색에서 다시 파란색으로 바뀝니다.  
  
## <a name="enabling-a-panel-to-receive-dropped-data"></a>패널이 끌어 놓은 데이터를 수신할 수 있도록 설정  
 이 섹션에서는 원 사용자 정의 컨트롤을 호스트하는 패널이 끌어 온 원 데이터의 놓기 대상 역할을 하도록 설정합니다. 패널 간에 원을 이동하거나, Ctrl 키를 누른 상태로 원을 끌어서 놓아 원 컨트롤의 복사본을 만들 수 있도록 하는 코드를 구현합니다.  
  
### <a name="to-enable-the-panel-to-be-a-drop-target"></a>패널을 놓기 대상으로 사용할 수 있도록 설정하려면  
  
1.  MainWindow.xaml을 엽니다.  
  
2.  다음 xaml 각에 나와 있는 것 처럼는 <xref:System.Windows.Controls.StackPanel> 컨트롤에 대 한 처리기를 추가 <xref:System.Windows.UIElement.DragOver> 및 <xref:System.Windows.UIElement.Drop> 이벤트입니다. 이름에서 <xref:System.Windows.UIElement.DragOver> 이벤트 처리기 `panel_DragOver`, 이름을 지정 하 고는 <xref:System.Windows.UIElement.Drop> 이벤트 처리기 `panel_Drop`합니다.  
  
     [!code-xaml[DragDropWalkthrough#PanelsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]  
  
3.  MainWindows.xaml.cs 또는 MainWindow.xaml.vb를 엽니다.  
  
4.  다음 코드에 대 한 추가 <xref:System.Windows.UIElement.DragOver> 이벤트 처리기입니다.  
  
     [!code-csharp[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]  
  
     이 <xref:System.Windows.UIElement.DragOver> 이벤트 처리기는 다음 작업을 수행 합니다.  
  
    -   "개체" 데이터에 패키지 끌어온된 데이터에 포함 되어 있는지 확인는 <xref:System.Windows.DataObject> 원 사용자 컨트롤에 대 한 호출에서 전달 <xref:System.Windows.DragDrop.DoDragDrop%2A>합니다.  
  
    -   "Object" 데이터가 있는 경우 Ctrl 키를 눌렀는지 여부를 확인합니다.  
  
    -   CTRL 키를 누를 경우 설정의 <xref:System.Windows.DragEventArgs.Effects%2A> 속성을 <xref:System.Windows.DragDropEffects.Copy>합니다. 그렇지 않으면, 설정 된 <xref:System.Windows.DragEventArgs.Effects%2A> 속성을 <xref:System.Windows.DragDropEffects.Move>합니다.  
  
5.  다음 코드에 대 한 추가 <xref:System.Windows.UIElement.Drop> 이벤트 처리기입니다.  
  
     [!code-csharp[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]  
  
     이 <xref:System.Windows.UIElement.Drop> 이벤트 처리기는 다음 작업을 수행 합니다.  
  
    -   확인 여부는 <xref:System.Windows.UIElement.Drop> 이벤트가 이미 처리 되었습니다. 예를 들어, 다른 원이 삭제 되 면 Circle 있는 핸들의 <xref:System.Windows.UIElement.Drop> 이벤트를 원하지 않는 Circle도 처리에 포함 된 패널입니다.  
  
    -   경우는 <xref:System.Windows.UIElement.Drop> 이벤트 처리 되지 않으면 검사 CTRL 키를 누르면 여부.  
  
    -   CTRL 키를 누른 경우는 <xref:System.Windows.UIElement.Drop> 발생 하는지 원의 복사본 제어에 추가 하는 <xref:System.Windows.Controls.Panel.Children%2A> 의 컬렉션은 <xref:System.Windows.Controls.StackPanel>합니다.  
  
    -   CTRL 키를 누르지에서 원 이동는 <xref:System.Windows.Controls.Panel.Children%2A> 에 부모 컨트롤의 컬렉션은 <xref:System.Windows.Controls.Panel.Children%2A> 에서 삭제 된 패널의 컬렉션입니다.  
  
    -   설정의 <xref:System.Windows.DragEventArgs.Effects%2A> 알리기 위해 속성은 <xref:System.Windows.DragDrop.DoDragDrop%2A> 메서드 이동 또는 복사 작업을 수행 하는지 여부입니다.  
  
6.  F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.  
  
7.  텍스트 선택 `green` 에서 <xref:System.Windows.Controls.TextBox>합니다.  
  
8.  텍스트를 원 컨트롤로 끌어서 놓습니다.  
  
9. 왼쪽 패널에서 오른쪽 패널로 원 컨트롤을 끌어서 놓습니다. 원에서 제거 되는 <xref:System.Windows.Controls.Panel.Children%2A> 왼쪽된 패널의 컬렉션 오른쪽 panel의 Children 컬렉션에 추가 합니다.  
  
10. 원 컨트롤이 있는 패널에서 다른 패널로 원 컨트롤을 끌고 Ctrl 키를 누른 채 놓습니다. Circle이 복사 되 고 복사본에 추가 됩니다는 <xref:System.Windows.Controls.Panel.Children%2A> 받는 패널의 컬렉션입니다.  
  
     ![Ctrl 키를 누른 채 원 끌기](../../../../docs/framework/wpf/advanced/media/dragdrop-paneldrop.png "DragDrop_PanelDrop")  
  
## <a name="see-also"></a>참고 항목  
 [끌어서 놓기 개요](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)
