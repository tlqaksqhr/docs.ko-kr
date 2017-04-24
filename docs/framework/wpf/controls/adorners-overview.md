---
title: "표시기 개요 | Microsoft Docs"
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
  - "표시기[WPF], 표시기 정보"
ms.assetid: 33d4c5c2-2daf-4e45-ba9a-5b673e2b8280
caps.latest.revision: 35
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 34
---
# 표시기 개요
표시기\(adorner\)는 사용자에게 시각적 큐를 제공하기 위해 사용되는 <xref:System.Windows.FrameworkElement>의 특수 형식입니다.  또한 표시기를 사용하여 함수 핸들을 요소에 추가하거나 컨트롤에 대한 상태 정보를 제공할 수 있습니다.  
  
   
  
<a name="about_Adorners"></a>   
## 표시기 정보  
 <xref:System.Windows.Documents.Adorner>는 <xref:System.Windows.UIElement>에 바인딩된 사용자 지정 <xref:System.Windows.FrameworkElement>입니다.  표시기는 항상 표시된 요소 또는 표시된 요소 컬렉션의 맨 위에 있는 렌더링 화면인 <xref:System.Windows.Documents.AdornerLayer>에 렌더링됩니다.  표시기의 렌더링은 표시기가 바인딩된 <xref:System.Windows.UIElement>의 렌더링과 독립적입니다.  표시기는 대개 표시된 요소의 왼쪽 위에 있는 표준 2차원 좌표 원점을 사용하여 해당 표시기가 바인딩되는 요소를 기준으로 배치됩니다.  
  
 표시기의 일반적인 응용 프로그램에서는 다음을 수행합니다.  
  
-   <xref:System.Windows.UIElement>에 사용자가 크기 조정, 회전, 위치 변경과 같은 방법으로 요소를 조작할 수 있는 기능 핸들 추가  
  
-   다양한 상태를 나타내거나 다양한 이벤트에 응답하기 위해 시각적 피드백 제공  
  
-   <xref:System.Windows.UIElement>에 시각적 데코레이션 오버레이  
  
-   <xref:System.Windows.UIElement>의 일부 또는 전체를 시각적으로 마스킹 또는 재정의  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서는 시각적 요소를 표시하기 위한 기본 프레임워크를 제공합니다.  다음 표에서는 개체를 표시할 때 사용되는 기본 형식 및 각 기본 형식의 용도를 보여 줍니다.  다음은 몇 가지 사용법의 예입니다.  
  
|||  
|-|-|  
|<xref:System.Windows.Documents.Adorner>|모든 구체적인 표시기 구현에서 상속하는 추상 기본 클래스입니다.|  
|<xref:System.Windows.Documents.AdornerLayer>|하나 이상의 표시된 요소의 표시기에 대한 렌더링 계층을 나타내는 클래스입니다.|  
|<xref:System.Windows.Documents.AdornerDecorator>|표시기 계층을 요소 컬렉션에 연결할 수 있는 클래스입니다.|  
  
<a name="implement_custom_Adorner"></a>   
## 사용자 지정 표시기 구현  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 제공하는 표시기 프레임워크는 기본적으로 사용자 지정 표시기 만들기를 지원합니다.  사용자 지정 표시기는 추상 <xref:System.Windows.Documents.Adorner> 클래스에서 상속되는 클래스를 구현하여 생성됩니다.  
  
> [!NOTE]
>  <xref:System.Windows.Documents.Adorner>의 부모는 표시되는 요소가 아니라 <xref:System.Windows.Documents.Adorner>를 렌더링하는 <xref:System.Windows.Documents.AdornerLayer>입니다.  
  
 다음 예제에서는 간단한 표시기를 구현하는 클래스를 보여 줍니다.  예제에서 보여 주는 표시기는 원으로 <xref:System.Windows.UIElement>의 모퉁이를 간단하게 표시합니다.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
 다음 이미지에서는 <xref:System.Windows.Controls.TextBox>에 적용된 SimpleCircleAdorner를 보여 줍니다.  
  
 ![표시기 예제: 표시된 TextBox](../../../../docs/framework/wpf/controls/media/adornedtextbox.png "AdornedTextBox")  
  
<a name="rendering_behavior_for_Adorners"></a>   
## 표시기의 렌더링 동작  
 표시기에는 어떠한 고유 렌더링 동작도 포함되지 않으므로 표시기 구현자가 표시기를 렌더링해야 합니다.  일반적으로 렌더링 동작을 구현할 때는 <xref:System.Windows.UIElement.OnRender%2A> 메서드를 재정의하고 필요에 따라 하나 이상의 <xref:System.Windows.Media.DrawingContext> 개체를 사용하여 표시기의 시각적 요소를 렌더링합니다\(위의 예제 참조\).  
  
> [!NOTE]
>  표시기 계층에 배치된 모든 요소는 사용자가 설정한 나머지 스타일의 맨 위에 렌더링됩니다.  즉, 표시기는 항상 맨 위에 표시되며 [Z 순서](GTMT)를 사용하여 재정의할 수 없습니다.  
  
<a name="adorner_events_hittest"></a>   
## 이벤트 및 적중 테스트  
 표시기는 다른 모든 <xref:System.Windows.FrameworkElement>와 같이 입력 이벤트를 받습니다.  표시기의 [Z 순서](GTMT)는 항상 표시기가 표시하는 요소보다 상위에 있기 때문에 표시기는 내부 표시된 요소를 대상으로 하는 <xref:System.Windows.UIElement.Drop> 또는 <xref:System.Windows.UIElement.MouseMove>와 같은 입력 이벤트를 받습니다.  표시기는 특정 입력 이벤트를 수신 대기하고 해당 이벤트를 다시 발생시켜 내부 표시된 요소에 전달할 수 있습니다.  
  
 표시기 아래에 있는 요소의 통과 적중 테스트 기능을 사용하려면 표시기에서 적중 테스트 <xref:System.Windows.UIElement.IsHitTestVisible%2A> 속성을 **false**로 설정해야 합니다.  적중 테스트에 대한 자세한 내용은 다음을 참조하십시오.  
  
 [시각적 계층에서 적중 테스트](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md).  
  
<a name="adorn_single_element"></a>   
## 단일 UIElement 표시  
 표시기를 특정 <xref:System.Windows.UIElement>에 바인딩하려면 다음 단계를 수행합니다.  
  
1.  정적 메서드인 <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>를 호출하여 표시할 <xref:System.Windows.UIElement>의 <xref:System.Windows.Documents.AdornerLayer> 개체를 가져옵니다.  <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>는 지정된 <xref:System.Windows.UIElement>에서 시각적 트리를 검색하여 발견하는 첫 번째 표시기 계층을 반환하며  표시기 계층이 없으면 null을 반환합니다.  
  
2.  <xref:System.Windows.Documents.AdornerLayer.Add%2A> 메서드를 호출하여 대상 <xref:System.Windows.UIElement>에 표시기를 바인딩합니다.  
  
 다음 예제에서는 위의 SimpleCircleAdorner를 *myTextBox*라는 <xref:System.Windows.Controls.TextBox>에 바인딩합니다.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]을 사용하여 표시기를 다른 요소에 바인딩하는 기능은 현재 지원되지 않습니다.  
  
<a name="adorn_children_panel"></a>   
## 패널 자식 표시  
 표시기를 <xref:System.Windows.Controls.Panel> 자식에 바인딩하려면 다음 단계를 수행합니다.  
  
1.  `static` 메서드 <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>를 호출하여 표시될 자식의 요소에 대한 표시기 계층을 찾습니다.  
  
2.  부모 요소의 자식을 열거하고 <xref:System.Windows.Documents.AdornerLayer.Add%2A> 메서드를 호출하여 표시기를 각 자식 요소에 바인딩합니다.  
  
 다음 예제에서는 위의 SimpleCircleAdorner를 *myStackPanel*라는 <xref:System.Windows.Controls.StackPanel>의 자식에 바인딩합니다.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
## 참고 항목  
 <xref:System.Windows.Media.AdornerHitTestResult>   
 [WPF에서 Shape 및 기본 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)   
 [이미지, 그림 및 시각적 표시로 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [Drawing 개체 개요](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/controls/adorners-how-to-topics.md)