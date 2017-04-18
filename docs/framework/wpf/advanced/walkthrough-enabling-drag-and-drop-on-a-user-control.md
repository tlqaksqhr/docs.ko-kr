---
title: "연습: 사용자 정의 컨트롤에서 끌어서 놓기 사용 | Microsoft Docs"
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
  - "끌어서 놓기[WPF], 연습"
  - "연습[WPF], 끌어서 놓기"
ms.assetid: cc844419-1a77-4906-95d9-060d79107fc7
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 연습: 사용자 정의 컨트롤에서 끌어서 놓기 사용
이 연습에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 끌어서 놓기 데이터 전송이 가능한 사용자 지정 사용자 정의 컨트롤을 만드는 방법을 보여 줍니다.  
  
 이 연습에서는 원 모양을 나타내는 사용자 지정 WPF <xref:System.Windows.Controls.UserControl>을 만듭니다.  이 컨트롤에 끌어서 놓기를 통한 데이터 전송을 가능하게 해 주는 기능을 구현해 봅니다.  예를 들어 한 Circle 컨트롤에서 다른 Circle 컨트롤로 끌 경우 채우기 색 데이터가 소스 Circle에서 대상 Circle로 복사됩니다.  Circle 컨트롤에서 <xref:System.Windows.Controls.TextBox>로 끌 경우에는 채우기 색의 문자열 표현이 <xref:System.Windows.Controls.TextBox>로 복사됩니다.  또한 두 개의 패널 컨트롤과 <xref:System.Windows.Controls.TextBox>가 포함된 작은 응용 프로그램을 만들어 끌어서 놓기 기능을 테스트해 봅니다.  패널에서 놓인 Circle 데이터를 처리할 수 있게 해 주는 코드를 작성합니다. 이 코드를 사용하면 한 패널의 Children 컬렉션에 있는 Circle을 다른 패널로 이동하거나 복사할 수 있습니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   사용자 지정 사용자 정의 컨트롤을 만듭니다.  
  
-   사용자 정의 컨트롤이 끌기 소스가 될 수 있도록 설정합니다.  
  
-   사용자 정의 컨트롤이 놓기 대상이 될 수 있도록 설정합니다.  
  
-   패널이 사용자 정의 컨트롤에서 놓은 데이터를 받을 수 있도록 설정합니다.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   Visual Studio 2010  
  
## 응용 프로그램 프로젝트 만들기  
 이 단원에서는 두 개의 패널과 한 개의 <xref:System.Windows.Controls.TextBox>가 있는 주 페이지를 포함하는 응용 프로그램 인프라를 만듭니다.  
  
### 프로젝트를 만들려면  
  
1.  Visual Basic 또는 Visual C\#에서 `DragDropExample`이라는 새 WPF 응용 프로그램 프로젝트를 만듭니다.  자세한 내용은 [방법: 새 WPF 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/ko-kr/1f6aea7a-33e1-4d3f-8555-1daa42e95d82)를 참조하십시오.  
  
2.  MainWindow.xaml을 엽니다.  
  
3.  <xref:System.Windows.Controls.Grid>의 여는 태그와 닫는 태그 사이에 다음 태그를 추가합니다.  
  
     이 태그는 테스트 응용 프로그램을 위한 사용자 인터페이스를 만듭니다.  
  
     [!code-xml[DragDropWalkthrough#PanelsStep1XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]  
  
## 프로젝트에 새 사용자 정의 컨트롤 추가  
 이 단원에서는 프로젝트에 새 사용자 정의 컨트롤을 추가합니다.  
  
### 새 사용자 정의 컨트롤을 추가하려면  
  
1.  프로젝트 메뉴에서 **사용자 정의 컨트롤 추가**를 선택합니다.  
  
2.  새 항목 추가 대화 상자에서 이름을 `Circle.xaml`로 변경하고 **추가**를 클릭합니다.  
  
     Circle.xaml과 해당 코드 숨김 파일이 프로젝트에 추가됩니다.  
  
3.  Circle.xaml을 엽니다.  
  
     이 파일에는 사용자 정의 컨트롤의 사용자 인터페이스 요소가 포함됩니다.  
  
4.  루트 <xref:System.Windows.Controls.Grid>에 다음 태그를 추가하여 파란색 원이 UI로 포함된 간단한 사용자 정의 컨트롤을 만듭니다.  
  
     [!code-xml[DragDropWalkthrough#EllipseXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]  
  
5.  Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.  
  
6.  C\#에서 기본 생성자 뒤에 다음 코드를 추가하여 복사 생성자를 만듭니다.  Visual Basic에서는 다음 코드를 추가하여 기본 생성자와 복사 생성자를 모두 만듭니다.  
  
     사용자 정의 컨트롤을 복사할 수 있도록 하려면 코드 숨김 파일에 복사 생성자 메서드를 추가합니다.  이 예제의 간단한 Circle 사용자 정의 컨트롤에서는 사용자 정의 컨트롤의 채우기와 크기만 복사합니다.  
  
     [!code-csharp[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]  
  
### 주 창에 사용자 정의 컨트롤을 추가하려면  
  
1.  MainWindow.xaml을 엽니다.  
  
2.  여는 <xref:System.Windows.Window> 태그에 다음 XAML을 추가하여 현재 응용 프로그램에 대한 XML 네임스페이스 참조를 만듭니다.  
  
    ```  
    xmlns:local="clr-namespace:DragDropExample"  
    ```  
  
3.  첫 번째 <xref:System.Windows.Controls.StackPanel>에서 다음 XAML을 추가하여 첫 번째 패널에 Circle 사용자 정의 컨트롤의 인스턴스를 두 개 만듭니다.  
  
     [!code-xml[DragDropWalkthrough#CirclesXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]  
  
     패널의 전체 XAML은 다음과 같습니다.  
  
     [!code-xml[DragDropWalkthrough#PanelsStep2XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]  
  
## 사용자 정의 컨트롤에 끌기 소스 이벤트 구현  
 이 단원에서는 <xref:System.Windows.UIElement.OnMouseMove%2A> 메서드를 재정의하고 끌어서 놓기 작업을 시작합니다.  
  
 마우스 단추를 누른 채 마우스를 이동하는 방법으로 끌기가 시작되면 전송 대상 데이터를 <xref:System.Windows.DataObject>에 패키지합니다.  이 예제의 경우 Circle 컨트롤은 세 개의 데이터 항목, 즉 채우기 색의 문자열 표현, 높이의 double 형식 표현 및 컨트롤 자체의 복사본을 패키지합니다.  
  
### 끌어서 놓기 작업을 시작하려면  
  
1.  Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.  
  
2.  다음과 같은 <xref:System.Windows.UIElement.OnMouseMove%2A> 재정의를 추가하여 <xref:System.Windows.UIElement.MouseMove> 이벤트에 대한 클래스 처리를 제공합니다.  
  
     [!code-csharp[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]  
  
     재정의된 이 <xref:System.Windows.UIElement.OnMouseMove%2A>는 다음 작업을 수행합니다.  
  
    -   마우스 왼쪽 단추를 누른 채 마우스를 이동하고 있는지 여부를 확인합니다.  
  
    -   Circle 데이터를 <xref:System.Windows.DataObject>에 패키지합니다.  이 예제의 경우 Circle 컨트롤은 세 개의 데이터 항목, 즉 채우기 색의 문자열 표현, 높이의 double 형식 표현 및 컨트롤 자체의 복사본을 패키지합니다.  
  
    -   정적 <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=fullName> 메서드를 호출하여 끌어서 놓기 작업을 시작합니다.  <xref:System.Windows.DragDrop.DoDragDrop%2A> 메서드에는 다음 세 개의 매개 변수를 전달합니다.  
  
        -   `dragSource` \- 이 컨트롤에 대한 참조입니다.  
  
        -   `data` \- 이전 코드에서 만든 <xref:System.Windows.DataObject>입니다.  
  
        -   `allowedEffects` \- 허용되는 끌어서 놓기 작업으로, <xref:System.Windows.DragDropEffects> 또는 <xref:System.Windows.DragDropEffects>입니다.  
  
3.  F5 키를 눌러 응용 프로그램을 빌드 및 실행합니다.  
  
4.  Circle 컨트롤 중 하나를 클릭하여 패널, 다른 Circle 및 <xref:System.Windows.Controls.TextBox>로 끕니다.  <xref:System.Windows.Controls.TextBox>로 끌 때는 커서가 이동을 나타내는 커서로 바뀝니다.  
  
5.  Ctrl 키를 누른 채 Circle을 <xref:System.Windows.Controls.TextBox>로 끕니다.  그러면 커서가 복사를 나타내는 커서로 바뀝니다.  
  
6.  Circle을 <xref:System.Windows.Controls.TextBox>로 끌어서 놓습니다.  Circle의 채우기 색에 해당하는 문자열 표현이 <xref:System.Windows.Controls.TextBox>에 추가됩니다.  
  
     ![원의 채우기 색에 대한 문자열 표현](../../../../docs/framework/wpf/advanced/media/dragdrop-colorstring.png "DragDrop\_ColorString")  
  
 기본적으로 끌어서 놓기 작업 중에는 데이터를 놓을 때의 결과를 나타내도록 커서가 바뀝니다.  <xref:System.Windows.UIElement.GiveFeedback> 이벤트를 처리하고 다른 커서를 설정하여 사용자에게 제공되는 피드백을 사용자 지정할 수 있습니다.  
  
### 사용자에게 피드백을 제공하려면  
  
1.  Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.  
  
2.  다음과 같은 <xref:System.Windows.UIElement.OnGiveFeedback%2A> 재정의를 추가하여 <xref:System.Windows.UIElement.GiveFeedback> 이벤트에 대한 클래스 처리를 제공합니다.  
  
     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]  
  
     재정의된 이 <xref:System.Windows.UIElement.OnGiveFeedback%2A>는 다음 작업을 수행합니다.  
  
    -   놓기 대상의 <xref:System.Windows.UIElement.DragOver> 이벤트 처리기에 설정된 <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> 값을 확인합니다.  
  
    -   <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> 값에 따라 사용자 지정 커서를 설정합니다.  이 커서는 데이터를 놓을 때의 결과에 대한 시각적 피드백을 사용자에게 제공하기 위한 것입니다.  
  
3.  F5 키를 눌러 응용 프로그램을 빌드 및 실행합니다.  
  
4.  Circle 컨트롤 중 하나를 패널, 다른 Circle 및 <xref:System.Windows.Controls.TextBox>로 끕니다.  이제 커서가 재정의 <xref:System.Windows.UIElement.OnGiveFeedback%2A>에서 지정한 사용자 지정 커서로 바뀝니다.  
  
     ![사용자 지정 커서로 끌어서 놓기](../../../../docs/framework/wpf/advanced/media/dragdrop-customcursor.png "DragDrop\_CustomCursor")  
  
5.  <xref:System.Windows.Controls.TextBox>에서 `green`이라는 텍스트를 선택합니다.  
  
6.  `green` 텍스트를 Circle 컨트롤로 끕니다.  끌어서 놓기 작업의 결과를 나타내는 기본 커서가 표시됩니다.  피드백 커서는 항상 끌기 소스에서 설정합니다.  
  
## 사용자 정의 컨트롤에 놓기 대상 이벤트 구현  
 이 단원에서는 사용자 정의 컨트롤이 놓기 대상이 되도록 지정하고, 사용자 정의 컨트롤이 놓기 대상이 될 수 있도록 하는 메서드를 재정의하고, 대상에 놓인 데이터를 처리합니다.  
  
### 사용자 정의 컨트롤이 놓기 대상이 될 수 있도록 설정하려면  
  
1.  Circle.xaml을 엽니다.  
  
2.  여는 <xref:System.Windows.Controls.UserControl> 태그에 <xref:System.Windows.UIElement.AllowDrop%2A> 속성을 추가하고 이 속성을 `true`로 설정합니다.  
  
     [!code-xml[DragDropWalkthrough#UCTagXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]  
  
 <xref:System.Windows.UIElement.AllowDrop%2A> 속성이 `true`로 설정된 경우 끌기 소스의 데이터를 Circle 사용자 정의 컨트롤에 놓으면 <xref:System.Windows.UIElement.OnDrop%2A> 메서드가 호출됩니다.  이 메서드에서 Circle에 놓인 데이터를 처리하여 Circle에 적용합니다.  
  
### 놓인 데이터를 처리하려면  
  
1.  Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.  
  
2.  다음과 같은 <xref:System.Windows.UIElement.OnDrop%2A> 재정의를 추가하여 <xref:System.Windows.UIElement.Drop> 이벤트에 대한 클래스 처리를 제공합니다.  
  
     [!code-csharp[DragDropWalkthrough#OnDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]  
  
     재정의된 이 <xref:System.Windows.UIElement.OnDrop%2A>는 다음 작업을 수행합니다.  
  
    -   <xref:System.Windows.DataObject.GetDataPresent%2A> 메서드를 사용하여 끌어온 데이터에 문자열 개체가 포함되어 있는지 확인합니다.  
  
    -   문자열 데이터가 있으면 <xref:System.Windows.DataObject.GetData%2A> 메서드를 사용하여 이 데이터를 추출합니다.  
  
    -   <xref:System.Windows.Media.BrushConverter>를 사용하여 문자열을 <xref:System.Windows.Media.Brush>로 변환합니다.  
  
    -   변환에 성공하면 Circle 컨트롤의 UI를 제공하는 <xref:System.Windows.Shapes.Ellipse>의 <xref:System.Windows.Shapes.Shape.Fill%2A>에 브러시를 적용합니다.  
  
    -   <xref:System.Windows.UIElement.Drop> 이벤트를 처리된 이벤트로 표시합니다.  이 이벤트를 받는 다른 요소에 Circle 사용자 정의 컨트롤이 해당 이벤트를 처리했음을 알리려면 놓기 이벤트를 처리된 이벤트로 표시해야 합니다.  
  
3.  F5 키를 눌러 응용 프로그램을 빌드 및 실행합니다.  
  
4.  <xref:System.Windows.Controls.TextBox>에서 `green`이라는 텍스트를 선택합니다.  
  
5.  이 텍스트를 Circle 컨트롤로 끌어서 놓습니다.  Circle이 파란색에서 녹색으로 바뀝니다.  
  
     ![브러시로 문자열 변환](../../../../docs/framework/wpf/advanced/media/dragdrop-dropgreentext.png "DragDrop\_DropGreenText")  
  
6.  <xref:System.Windows.Controls.TextBox>에 `green`이라는 텍스트를 입력합니다.  
  
7.  <xref:System.Windows.Controls.TextBox>에서 `gre`라는 텍스트를 선택합니다.  
  
8.  이 텍스트를 Circle 컨트롤로 끌어서 놓습니다.  커서가 놓기가 허용됨을 나타내는 커서로 바뀌지만, `gre`가 올바른 색이 아니므로 Circle의 색은 바뀌지 않습니다.  
  
9. 녹색 Circle 컨트롤에서 파란색 Circle 컨트롤로 마우스를 끌어서 놓습니다.  Circle이 파란색에서 녹색으로 바뀝니다.  끌기 소스가 <xref:System.Windows.Controls.TextBox>인지 Circle인지에 따라 어떤 커서가 표시되는지 확인합니다.  
  
 <xref:System.Windows.UIElement.AllowDrop%2A> 속성을 `true`로 설정하고 놓인 데이터를 처리하기만 하면 요소가 놓기 대상이 될 수 있습니다.  그러나 보다 향상된 사용자 환경을 제공하려면 <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave> 및 <xref:System.Windows.UIElement.DragOver> 이벤트도 처리해야 합니다.  이러한 이벤트에서 데이터를 놓기 전에 확인을 수행하고 사용자에게 추가 피드백을 제공할 수 있습니다.  
  
 데이터를 Circle 사용자 정의 컨트롤로 끌면 이 컨트롤에서는 끌고 있는 데이터를 처리할 수 있는지 여부를 끌기 소스에 알려야 합니다.  컨트롤에서 데이터 처리 방법을 알 수 없는 경우에는 놓기를 거부해야 합니다.  이렇게 하려면 <xref:System.Windows.UIElement.DragOver> 이벤트를 처리하고 <xref:System.Windows.DragEventArgs.Effects%2A> 속성을 설정합니다.  
  
### 데이터 놓기가 허용되는지 확인하려면  
  
1.  Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.  
  
2.  다음과 같은 <xref:System.Windows.UIElement.OnDragOver%2A> 재정의를 추가하여 <xref:System.Windows.UIElement.DragOver> 이벤트에 대한 클래스 처리를 제공합니다.  
  
     [!code-csharp[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]  
  
     재정의된 이 <xref:System.Windows.UIElement.OnDragOver%2A>는 다음 작업을 수행합니다.  
  
    -   <xref:System.Windows.DragEventArgs.Effects%2A> 속성을 <xref:System.Windows.DragDropEffects>로 설정합니다.  
  
    -   <xref:System.Windows.UIElement.OnDrop%2A> 메서드에서 수행되는 것과 동일한 확인 작업을 수행하여 Circle 사용자 정의 컨트롤이 끌어온 데이터를 처리할 수 있는지 여부를 확인합니다.  
  
    -   사용자 정의 컨트롤이 데이터를 처리할 수 있으면 <xref:System.Windows.DragEventArgs.Effects%2A> 속성을 <xref:System.Windows.DragDropEffects> 또는 <xref:System.Windows.DragDropEffects>로 설정합니다.  
  
3.  F5 키를 눌러 응용 프로그램을 빌드 및 실행합니다.  
  
4.  <xref:System.Windows.Controls.TextBox>에서 `gre`라는 텍스트를 선택합니다.  
  
5.  이 텍스트를 Circle 컨트롤로 끕니다.  `gre`는 올바른 색이 아니므로 이번에는 커서가 놓기가 허용되지 않음을 나타내는 커서로 바뀝니다.  
  
 놓기 작업의 미리 보기를 적용하여 사용자 환경을 더 향상시킬 수 있습니다.  Circle 사용자 정의 컨트롤의 경우에는 <xref:System.Windows.UIElement.OnDragEnter%2A> 및 <xref:System.Windows.UIElement.OnDragLeave%2A> 메서드를 재정의합니다.  데이터를 컨트롤로 끌면 현재 배경 <xref:System.Windows.Shapes.Shape.Fill%2A>이 자리 표시자 변수에 저장됩니다.  그런 다음 문자열이 브러시로 변환되어 Circle의 UI를 제공하는 <xref:System.Windows.Shapes.Ellipse>에 적용됩니다.  데이터를 놓지 않고 Circle 밖으로 끌면 원래 <xref:System.Windows.Shapes.Shape.Fill%2A> 값이 Circle에 다시 적용됩니다.  
  
### 끌어서 놓기 작업의 결과를 미리 보려면  
  
1.  Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.  
  
2.  Circle 클래스에서 `_previousFill`이라는 전용 <xref:System.Windows.Media.Brush> 변수를 선언하고 이 변수를 `null`로 초기화합니다.  
  
     [!code-csharp[DragDropWalkthrough#Brush](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]  
  
3.  다음과 같은 <xref:System.Windows.UIElement.OnDragEnter%2A> 재정의를 추가하여 <xref:System.Windows.UIElement.DragEnter> 이벤트에 대한 클래스 처리를 제공합니다.  
  
     [!code-csharp[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]  
  
     재정의된 이 <xref:System.Windows.UIElement.OnDragEnter%2A>는 다음 작업을 수행합니다.  
  
    -   <xref:System.Windows.Shapes.Ellipse>의 <xref:System.Windows.Shapes.Shape.Fill%2A> 속성을 `_previousFill` 변수에 저장합니다.  
  
    -   <xref:System.Windows.UIElement.OnDrop%2A> 메서드에서 수행되는 것과 동일한 확인 작업을 수행하여 데이터를 <xref:System.Windows.Media.Brush>로 변환할 수 있는지 여부를 확인합니다.  
  
    -   데이터가 올바른 <xref:System.Windows.Media.Brush>로 변환되면 <xref:System.Windows.Shapes.Ellipse>의 <xref:System.Windows.Shapes.Shape.Fill%2A>에 이 브러시를 적용합니다.  
  
4.  다음과 같은 <xref:System.Windows.UIElement.OnDragLeave%2A> 재정의를 추가하여 <xref:System.Windows.UIElement.DragLeave> 이벤트에 대한 클래스 처리를 제공합니다.  
  
     [!code-csharp[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]  
  
     재정의된 이 <xref:System.Windows.UIElement.OnDragLeave%2A>는 다음 작업을 수행합니다.  
  
    -   Circle 사용자 정의 컨트롤의 UI를 제공하는 <xref:System.Windows.Shapes.Ellipse>의 <xref:System.Windows.Shapes.Shape.Fill%2A>에 `_previousFill` 변수에 저장된 <xref:System.Windows.Media.Brush>를 적용합니다.  
  
5.  F5 키를 눌러 응용 프로그램을 빌드 및 실행합니다.  
  
6.  <xref:System.Windows.Controls.TextBox>에서 `green`이라는 텍스트를 선택합니다.  
  
7.  텍스트를 Circle 컨트롤로 끌어오되 놓지는 않습니다.  Circle이 파란색에서 녹색으로 바뀝니다.  
  
     ![끌어서 놓기 작업의 효과 미리 보기](../../../../docs/framework/wpf/advanced/media/dragdrop-previeweffects.png "DragDrop\_PreviewEffects")  
  
8.  텍스트를 Circle 컨트롤 밖으로 끕니다.  Circle이 녹색에서 다시 파란색으로 바뀝니다.  
  
## 패널이 놓기 대상 데이터를 받을 수 있도록 설정  
 이 단원에서는 Circle 사용자 정의 컨트롤을 호스팅하는 패널이 끌어온 Circle 데이터의 놓기 대상이 될 수 있도록 설정합니다.  Circle을 패널 간에 이동하거나, Ctrl 키를 누른 채 끌어서 놓는 방법으로 Circle 컨트롤의 복사본을 만들 수 있도록 하는 코드를 구현합니다.  
  
### 패널이 놓기 대상이 될 수 있도록 설정하려면  
  
1.  MainWindow.xaml을 엽니다.  
  
2.  다음 XAML과 같이 각 <xref:System.Windows.Controls.StackPanel> 컨트롤에서 <xref:System.Windows.UIElement.DragOver> 및 <xref:System.Windows.UIElement.Drop> 이벤트에 대한 처리기를 추가합니다.  <xref:System.Windows.UIElement.DragOver> 이벤트 처리기의 이름을 `panel_DragOver`로 지정하고, <xref:System.Windows.UIElement.Drop> 이벤트 처리기의 이름을 `panel_Drop`으로 지정합니다.  
  
     [!code-xml[DragDropWalkthrough#PanelsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]  
  
3.  MainWindows.xaml.cs 또는 MainWindows.xaml.vb를 엽니다.  
  
4.  <xref:System.Windows.UIElement.DragOver> 이벤트 처리기에 다음 코드를 추가합니다.  
  
     [!code-csharp[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]  
  
     이 <xref:System.Windows.UIElement.DragOver> 이벤트의 처리기는 다음 작업을 수행합니다.  
  
    -   Circle 사용자 정의 컨트롤이 <xref:system.Windows.DataObject>에 패키지하여 <xref:System.Windows.DragDrop.DoDragDrop%2A> 호출 시 전달한 "개체" 데이터가 끌어온 데이터에 포함되어 있는지 확인합니다.  
  
    -   "개체" 데이터가 있으면 Ctrl 키가 누른 상태인지 확인합니다.  
  
    -   Ctrl 키가 누른 상태이면 <xref:System.Windows.DragEventArgs.Effects%2A> 속성을 <xref:System.Windows.DragDropEffects>로 설정합니다.  그렇지 않으면 <xref:System.Windows.DragEventArgs.Effects%2A> 속성을 <xref:System.Windows.DragDropEffects>로 설정합니다.  
  
5.  <xref:System.Windows.UIElement.Drop> 이벤트 처리기에 다음 코드를 추가합니다.  
  
     [!code-csharp[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]  
  
     이 <xref:System.Windows.UIElement.Drop> 이벤트의 처리기는 다음 작업을 수행합니다.  
  
    -   <xref:System.Windows.UIElement.Drop> 이벤트가 이미 처리되었는지 여부를 확인합니다.  예를 들어 <xref:System.Windows.UIElement.Drop> 이벤트를 처리하는 다른 Circle에 Circle을 놓은 경우에는 이 Circle이 포함된 패널에서도 같은 이벤트를 처리하지 않도록 합니다.  
  
    -   <xref:System.Windows.UIElement.Drop> 이벤트가 처리되지 않은 경우에는 Ctrl 키가 누른 상태인지 확인합니다.  
  
    -   <xref:System.Windows.UIElement.Drop>이 발생할 때 Ctrl 키가 누른 상태이면 Circle 컨트롤의 복사본을 만들어 <xref:System.Windows.Controls.StackPanel>의 <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션에 추가합니다.  
  
    -   Ctrl 키가 누른 상태가 아니면 부모 컨트롤의 <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션에 있는 Circle을 이 컨트롤이 놓인 패널의 <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션으로 이동합니다.  
  
    -   수행된 작업이 이동인지 복사인지를 <xref:System.Windows.DragDrop.DoDragDrop%2A> 메서드에 알리도록 <xref:System.Windows.DragEventArgs.Effects%2A> 속성을 설정합니다.  
  
6.  F5 키를 눌러 응용 프로그램을 빌드 및 실행합니다.  
  
7.  <xref:System.Windows.Controls.TextBox>에서 `green`이라는 텍스트를 선택합니다.  
  
8.  이 텍스트를 Circle 컨트롤로 끌어서 놓습니다.  
  
9. Circle 컨트롤을 왼쪽 패널에서 오른쪽 패널로 끌어서 놓습니다.  이 Circle이 왼쪽 패널의 <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션에서 제거되고 오른쪽 패널의 Children 컬렉션에 추가됩니다.  
  
10. Ctrl 키를 누른 채로 Circle 컨트롤을 현재 패널에서 다른 패널로 끌어서 놓습니다.  이 Circle이 복사되고, 받는 패널의 <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션에 복사본이 추가됩니다.  
  
     ![Ctrl 키를 누른 채 원 끌기](../../../../docs/framework/wpf/advanced/media/dragdrop-paneldrop.png "DragDrop\_PanelDrop")  
  
## 참고 항목  
 [끌어서 놓기 개요](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)