---
title: "연습: XAML을 사용하여 단추 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: buttons [WPF]
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5c5efa9f8787e65d59e1b544632e806bf3fbbc81
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-create-a-button-by-using-xaml"></a>연습: XAML을 사용하여 단추 만들기
애니메이션된 단추에서 사용 하기 위해 만드는 방법을 설명 하는이 연습의 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 응용 프로그램입니다. 이 연습에서는 스타일 및 서식 파일을 사용 하 여 코드 재사용 및 단추 선언에서 단추 논리 분리를 허용 하는 사용자 지정된 단추 리소스를 만듭니다. 이 연습은 전체 코드를 작성은 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]합니다.  
  
> [!IMPORTANT]
>  이 연습을 입력 하거나 복사 하 여 응용 프로그램을 만들기 위한 단계를 안내해 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 를 Microsoft [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]합니다. 디자인 도구 (Microsoft Expression Blend) 동일한 응용 프로그램 만들기, 참조를 사용 하는 방법을 알아보려면 않으려면 [Microsoft Expression Blend를 사용 하 여 단추 만들기](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md)합니다.  
  
 다음 그림은 완료 된 단추입니다.  
  
 ![XAML을 사용 하 여 만든 사용자 지정 단추](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")  
  
## <a name="create-basic-buttons"></a>기본 단추 만들기  
 새 프로젝트를 만들고 몇 가지 단추 창에 추가 하 여 시작 하겠습니다.  
  
#### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a>새 WPF 프로젝트를 만들고 창에 단추를 추가 하려면  
  
1.  시작[!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]합니다.  
  
2.  **새 WPF 프로젝트를 만들:** 에 **파일** 메뉴에서 **새로**, 클릭 하 고 **프로젝트**합니다. 찾을 **Windows 응용 프로그램 (WPF)** 템플릿과 "AnimatedButton" 프로젝트 이름을 지정 합니다. 이렇게 하면 응용 프로그램에 대 한 기본 항목이 만들어집니다.  
  
3.  **기본 단추 추가:** 이 연습에 필요한 모든 파일은 서식 파일에서 제공 합니다. 두 번 솔루션 탐색기에서 클릭 하 여 Window1.xaml 파일을 엽니다. 기본적으로는 <xref:System.Windows.Controls.Grid> Window1.xaml의 요소입니다. 제거는 <xref:System.Windows.Controls.Grid> 요소 몇 가지 단추를 추가 하 고는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 페이지를 입력 하거나 복사 Window1.xaml 강조 표시 된 다음 코드를 붙여 넣는 방법:  
  
    ```xaml  
    <Window x:Class="AnimatedButton.Window1"  
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
      Title="AnimatedButton" Height="300" Width="300"   
      Background="Black">   <!-- Buttons arranged vertically inside a StackPanel. -->   <StackPanel HorizontalAlignment="Left">     <Button>Button 1</Button>     <Button>Button 2</Button>     <Button>Button 3</Button>   </StackPanel>  
  
    </Window>  
    ```  
  
     F5 키를 눌러 응용 프로그램을 실행 하려면 다음 그림 처럼 보이는 단추 집합이 표시 됩니다.  
  
     ![세 개의 기본 단추](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")  
  
     기본 단추를 만들었으므로 이제 Window1.xaml 파일에서 작업 완료 됩니다. 이 연습의 나머지 부분에 중점을 둡니다 app.xaml 파일 스타일과 단추에 대 한 템플릿을 정의 합니다.  
  
## <a name="set-basic-properties"></a>기본 속성 설정  
 다음으로,이 단추의 단추 모양 및 레이아웃을 제어 하려면 몇 가지 속성을 설정 해 보겠습니다. 단추의 속성을 개별적으로 설정 하는 대신 전체 응용 프로그램에 대 한 속성 단추를 정의 하려면 리소스를 사용 합니다. 응용 프로그램 리소스는 개념적으로 비슷합니다 외부 [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)] ; 웹 페이지에 대 한 리소스 사항은 보다 훨씬 더 강력 [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)]이 연습의 끝에서 살펴보게 되겠지만, 합니다. 리소스에 대 한 자세한 참조 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)합니다.  
  
#### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a>스타일을 사용 하 여 단추에 기본 속성을 설정 하려면  
  
1.  **사용 블록 정의:** app.xaml 열고 아직 없는 경우 다음 강조 표시 된 태그를 추가 합니다.  
  
    ```xaml  
    <Application x:Class="AnimatedButton.App"  
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
      StartupUri="Window1.xaml"  
      >  
      <Application.Resources>
        <!-- Resources for the entire application can be defined here. -->
      </Application.Resources>  
    </Application>  
    ```  
  
     리소스를 정의 하 여 리소스 범위가 결정 됩니다. 에 대 한 리소스 정의 `Application.Resources` 는 app.xaml 파일에서 파일을 통해 리소스를 응용 프로그램의 모든 위치에서 사용할 수 있습니다. 리소스의 범위를 정의 하는 방법에 대 한 자세한 참조 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)합니다.  
  
2.  **스타일을 만들고 정의 된 기본 속성 값:** 다음 태그를 추가 `Application.Resources` 블록입니다. 이 태그를 만듭니다는 <xref:System.Windows.Style> 응용 프로그램 설정의 모든 단추에 적용 되는 <xref:System.Windows.FrameworkElement.Width%2A> 90으로 단추의 및 <xref:System.Windows.FrameworkElement.Margin%2A> 10:  
  
    ```xaml  
    <Application.Resources>  
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>  
    </Application.Resources>  
    ```  
  
     <xref:System.Windows.Style.TargetType%2A> 속성 스타일 유형의 모든 개체에 적용 되도록 지정 <xref:System.Windows.Controls.Button>합니다. 각 <xref:System.Windows.Setter> 에 대 한 다른 속성 값을 설정 하는 <xref:System.Windows.Style>합니다. 따라서이 시점에서 응용 프로그램에서 모든 단추에 너비 90, 여백 10의 있습니다.  F5 키를 눌러 응용 프로그램을 실행 하는 경우 다음과 같은 창이 표시 됩니다.  
  
     ![너비 90, 여백 10의 사용 하는 단추](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")  
  
     훨씬 더 다양 한 개체를 대상으로 세밀 하 게 조정 하는 방법, 등, 복잡 한 속성 값을 지정 다른 스타일에 대 한 입력으로 스타일을 사용 해도 스타일을 수행할 수 있습니다. 자세한 내용은 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)을 참조하세요.  
  
3.  **스타일 속성 값을 리소스로 설정:** 리소스를 사용 하면 일반적으로 정의 된 개체 및 값을 다시 사용 하는 간단한 방법입니다. 특히 리소스를 사용 하 여 코드를 더욱 모듈화 쉽게 복잡 한 값을 정의 하는 것이 유용 합니다. App.xaml에 강조 표시 된 다음 태그를 추가 합니다.  
  
    ```xaml  
    <Application.Resources>  
      <LinearGradientBrush x:Key="GrayBlueGradientBrush" StartPoint="0,0" EndPoint="1,1">
        <GradientStop Color="DarkGray" Offset="0" />
        <GradientStop Color="#CCCCFF" Offset="0.5" />
        <GradientStop Color="DarkGray" Offset="1" />
      </LinearGradientBrush>  
      <Style TargetType="{x:Type Button}">  
        <Setter Property="Background" Value="{StaticResource GrayBlueGradientBrush}" />  
        <Setter Property="Width" Value="80" />  
        <Setter Property="Margin" Value="10" />  
      </Style>  
    </Application.Resources>  
    ```  
  
     바로 아래에서 `Application.Resources` 블록 "GrayBlueGradientBrush" 라는 리소스를 생성 합니다. 이 리소스는 가로 그라데이션을 정의합니다. 이 리소스는 모든 위치에서 속성 값으로 사용할 수 있습니다 단추 스타일 setter를 포함 하 여 응용 프로그램에는 <xref:System.Windows.Controls.Control.Background%2A> 속성입니다. 모든 단추는 이제는 <xref:System.Windows.Controls.Control.Background%2A> 이 그라데이션의 속성 값입니다.  
  
     F5 키를 눌러 응용 프로그램을 실행합니다. 다음과 같이 표시 됩니다.  
  
     ![그라데이션 배경이 있는 단추](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")  
  
## <a name="create-a-template-that-defines-the-look-of-the-button"></a>단추의 모양을 정의 하는 서식 파일 만들기  
 이 섹션에서는 단추의 모양을 (presentation)를 사용자 지정 하는 템플릿을 만듭니다. 단추 표시 구성 된 사각형 및 기타 구성 요소를 포함 하는 여러 개체의 단추에 고유한 모양을 제공 합니다.  
  
 지금까지 단추의 속성을 변화 하는 응용 프로그램에서 단추가 표시 되는 방법의 제어가 없었습니다. 단추의 모양을를 더 크게 변경 하려면 어떻게 해야 할까요? 템플릿을 사용 하는 개체의 표현 보다 효과적으로 제어할 합니다. 템플릿 스타일 내에서 사용할 수 있으므로 (이 연습에서는 단추)에 스타일에 적용 되는 모든 개체에 템플릿을 적용할 수 있습니다.  
  
#### <a name="to-use-the-template-to-define-the-look-of-the-button"></a>단추의 모양을 정의 하는 템플릿을 사용 하려면  
  
1.  **서식 파일 설정:** 같은 컨트롤 때문에 <xref:System.Windows.Controls.Button> 가 <xref:System.Windows.Controls.Control.Template%2A> 속성을 다른 속성 값에 설정한 것 처럼 템플릿 속성 값을 정의할 수 있습니다는 <xref:System.Windows.Style> 를 사용 하는 <xref:System.Windows.Setter>합니다. 단추 스타일을 강조 표시 된 다음 태그를 추가 합니다.  
  
    ```xaml
    <Application.Resources>  
      <LinearGradientBrush x:Key="GrayBlueGradientBrush"   
        StartPoint="0,0" EndPoint="1,1">  
        <GradientStop Color="DarkGray" Offset="0" />  
        <GradientStop Color="#CCCCFF" Offset="0.5" />  
        <GradientStop Color="DarkGray" Offset="1" />  
      </LinearGradientBrush>  
      <Style TargetType="{x:Type Button}">  
        <Setter Property="Background" Value="{StaticResource GrayBlueGradientBrush}" />  
        <Setter Property="Width" Value="80" />  
        <Setter Property="Margin" Value="10" />  
        <Setter Property="Template">
          <Setter.Value>
            <!-- The button template is defined here. -->
          </Setter.Value>
        </Setter>  
      </Style>  
    </Application.Resources>  
    ```  
  
2.  **단추 표시 변경:** 이 시점에서 서식 파일을 정의 해야 합니다. 강조 표시 된 다음 태그를 추가 합니다. 이 태그 지정 두 <xref:System.Windows.Shapes.Rectangle> 둥근된 가장자리와 요소 뒤에 <xref:System.Windows.Controls.DockPanel>합니다. <xref:System.Windows.Controls.DockPanel> 사용 되는 호스트에는 <xref:System.Windows.Controls.ContentPresenter> 단추의 합니다. A <xref:System.Windows.Controls.ContentPresenter> 단추의 콘텐츠를 표시 합니다. 이 연습에서는 콘텐츠는 텍스트 ("단추 1", "단추 2", "버튼 3"). 모든 템플릿 구성 요소 (사각형 및 <xref:System.Windows.Controls.DockPanel>) 내에 배치 되는 <xref:System.Windows.Controls.Grid>합니다.  
  
    ```xaml  
    <Setter.Value>  
      <ControlTemplate TargetType="Button">
        <Grid Width="{TemplateBinding Width}" Height="{TemplateBinding Height}" ClipToBounds="True">
          <!-- Outer Rectangle with rounded corners. -->
          <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}" RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />
          <!-- Inner Rectangle with rounded corners. -->
          <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Stroke="Transparent" StrokeThickness="20" Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20" />
          <!-- Present Content (text) of the button. -->
          <DockPanel Name="myContentPresenterDockPanel">
            <ContentPresenter x:Name="myContentPresenter" Margin="20" Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
          </DockPanel>
        </Grid>
      </ControlTemplate>  
    </Setter.Value>  
    ```  
  
     F5 키를 눌러 응용 프로그램을 실행합니다. 다음과 같이 표시 됩니다.  
  
     ![](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-4.gif "custom_button_AnimatedButton_4")  
  
3.  **템플릿에 서식 파일에 추가:** 다음는 투명 효과 추가 합니다. 먼저 유리 그라데이션 효과 만드는 리소스를 만듭니다. 이러한 그라데이션 리소스 내에서 추가 된 `Application.Resources` 블록:  
  
    ```xaml  
    <Application.Resources>  
      <GradientStopCollection x:Key="MyGlassGradientStopsResource">     <GradientStop Color="WhiteSmoke" Offset="0.2" />     <GradientStop Color="Transparent" Offset="0.4" />     <GradientStop Color="WhiteSmoke" Offset="0.5" />     <GradientStop Color="Transparent" Offset="0.75" />     <GradientStop Color="WhiteSmoke" Offset="0.9" />     <GradientStop Color="Transparent" Offset="1" />   </GradientStopCollection>   <LinearGradientBrush x:Key="MyGlassBrushResource"     StartPoint="0,0" EndPoint="1,1" Opacity="0.75"     GradientStops="{StaticResource MyGlassGradientStopsResource}" />  
    <!-- Styles and other resources below here. -->  
    ```  
  
     이러한 리소스도 사용 되는 <xref:System.Windows.Shapes.Shape.Fill%2A> 삽입 하는 사각형에 대 한는 <xref:System.Windows.Controls.Grid> 단추 서식 파일의 합니다. 서식 파일에 다음 강조 표시 된 태그를 추가 합니다.  
  
    ```  
    <Setter.Value>  
      <ControlTemplate TargetType="{x:Type Button}">  
        <Grid Width="{TemplateBinding Width}" Height="{TemplateBinding Height}"  
    ClipToBounds="True">  
  
        <!-- Outer Rectangle with rounded corners. -->  
        <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch"   
          VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}"   
          RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />  
  
        <!-- Inner Rectangle with rounded corners. -->  
        <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch"   
          VerticalAlignment="Stretch" Stroke="Transparent" StrokeThickness="20"   
          Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20" />  
  
        <!-- Glass Rectangle -->     <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"       VerticalAlignment="Stretch"       StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"       Fill="{StaticResource MyGlassBrushResource}"       RenderTransformOrigin="0.5,0.5">       <Rectangle.Stroke>         <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">           <LinearGradientBrush.GradientStops>             <GradientStop Offset="0.0" Color="LightBlue" />             <GradientStop Offset="1.0" Color="Gray" />           </LinearGradientBrush.GradientStops>         </LinearGradientBrush>       </Rectangle.Stroke>       <!-- These transforms have no effect as they are declared here.             The reason the transforms are included is to be targets             for animation (see later). -->       <Rectangle.RenderTransform>         <TransformGroup>           <ScaleTransform />           <RotateTransform />         </TransformGroup>       </Rectangle.RenderTransform>       <!-- A BevelBitmapEffect is applied to give the button a             "Beveled" look. -->       <Rectangle.BitmapEffect>         <BevelBitmapEffect />       </Rectangle.BitmapEffect>     </Rectangle>  
  
        <!-- Present Text of the button. -->  
        <DockPanel Name="myContentPresenterDockPanel">  
          <ContentPresenter x:Name="myContentPresenter" Margin="20"   
            Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />  
        </DockPanel>  
      </Grid>  
    </ControlTemplate>  
    </Setter.Value>  
    ```  
  
     다음에 유의 <xref:System.Windows.UIElement.Opacity%2A> 사용 하 여 사각형의는 `x:Name` "glassCube"의 속성은 0으로, 샘플을 실행 하는 경우 표시 되지 않으면 위쪽에 오버레이 투명 효과 사각형 하도록 합니다. 나중에 추가 트리거에 대 한 서식 파일에 단추와 상호 작용할 때 때문입니다. 그러나 나타나면 단추 모양을 지금 변경 하 여는 <xref:System.Windows.UIElement.Opacity%2A> 값을 1로 응용 프로그램을 실행 합니다. 다음 그림을 참조하세요. 다음 단계를 계속 하기 전에 변경 된 <xref:System.Windows.UIElement.Opacity%2A> 다시 0으로 합니다.  
  
     ![XAML을 사용 하 여 만든 사용자 지정 단추](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")  
  
## <a name="create-button-interactivity"></a>단추 대화형 작업 만들기  
 이 섹션에서는 속성 값을 변경 하 고 애니메이션 단추 위로 마우스 포인터를 이동 하 고 클릭과 같은 사용자 작업에 대 한 응답을 실행 하는 이벤트 트리거 및 트리거 속성을 만듭니다.  
  
 대화형 기능 (마우스를 위에 놓았을, 범위 밖으로 마우스 이동, 클릭, 및 등)를 추가 하는 쉬운 방법은 스타일이 나 템플릿 내에 트리거를 정의 하는 것입니다. 만들려는 <xref:System.Windows.Trigger>와 같은 "조건" 속성을 정의 하면: 단추 <xref:System.Windows.UIElement.IsMouseOver%2A> 속성 값이 같지 `true`합니다. 그런 다음 트리거 조건이 true 일 때 발생 하는 setter (동작)을 정의 합니다.  
  
#### <a name="to-create-button-interactivity"></a>단추 대화형 작업을 만들려면  
  
1.  **템플릿 트리거 추가:** 강조 표시 된 태그를 템플릿에 추가 합니다.  
  
    ```  
    <Setter.Value>  
      <ControlTemplate TargetType="{x:Type Button}">  
        <Grid Width="{TemplateBinding Width}"   
          Height="{TemplateBinding Height}" ClipToBounds="True">  
  
          <!-- Outer Rectangle with rounded corners. -->  
          <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch"   
          VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}"   
          RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />  
  
          <!-- Inner Rectangle with rounded corners. -->  
          <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch"   
            VerticalAlignment="Stretch" Stroke="Transparent"   
            StrokeThickness="20"   
            Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20"   
          />  
  
          <!-- Glass Rectangle -->  
          <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"  
            VerticalAlignment="Stretch"  
            StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"  
            Fill="{StaticResource MyGlassBrushResource}"  
            RenderTransformOrigin="0.5,0.5">  
            <Rectangle.Stroke>  
              <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">  
                <LinearGradientBrush.GradientStops>  
                  <GradientStop Offset="0.0" Color="LightBlue" />  
                  <GradientStop Offset="1.0" Color="Gray" />  
                </LinearGradientBrush.GradientStops>  
              </LinearGradientBrush>  
            </Rectangle.Stroke>  
  
            <!-- These transforms have no effect as they   
                 are declared here.   
                 The reason the transforms are included is to be targets   
                 for animation (see later). -->  
            <Rectangle.RenderTransform>  
              <TransformGroup>  
                <ScaleTransform />  
                <RotateTransform />  
              </TransformGroup>  
            </Rectangle.RenderTransform>  
  
              <!-- A BevelBitmapEffect is applied to give the button a   
                   "Beveled" look. -->  
            <Rectangle.BitmapEffect>  
              <BevelBitmapEffect />  
            </Rectangle.BitmapEffect>  
          </Rectangle>  
  
          <!-- Present Text of the button. -->  
          <DockPanel Name="myContentPresenterDockPanel">  
            <ContentPresenter x:Name="myContentPresenter" Margin="20"   
              Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />  
          </DockPanel>  
        </Grid>  
  
        <ControlTemplate.Triggers>       <!-- Set action triggers for the buttons and define            what the button does in response to those triggers. -->     </ControlTemplate.Triggers>  
      </ControlTemplate>  
    </Setter.Value>  
    ```  
  
2.  **속성 트리거 추가:** 강조 표시 된 태그를 추가 `ControlTemplate.Triggers` 블록:  
  
    ```  
    <ControlTemplate.Triggers>  
  
      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>  
  
    <ControlTemplate.Triggers/>  
    ```  
  
     F5 키를 눌러 응용 프로그램을 실행 하 고 단추 위에 마우스 포인터를 실행 하면서 효과 표시 합니다.  
  
3.  **포커스 트리거 추가:** 다음으로, 몇 가지 유사한 setter는 단추 (예: 클릭 한 후) 포커스가 있을 때 경우를 처리 하도록 추가 하겠습니다.  
  
    ```  
    <ControlTemplate.Triggers>  
  
      <!-- Set properties when mouse pointer is over the button. -->  
      <Trigger Property="IsMouseOver" Value="True">  
  
        <!-- Below are three property settings that occur when the   
             condition is met (user mouses over button).  -->  
        <!-- Change the color of the outer rectangle when user          mouses over it. -->  
        <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"  
          Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />  
  
        <!-- Sets the glass opacity to 1, therefore, the          glass "appears" when user mouses over it. -->  
        <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />  
  
        <!-- Makes the text slightly blurry as though you were          looking at it through blurry glass. -->  
        <Setter Property="ContentPresenter.BitmapEffect"       TargetName="myContentPresenter">  
          <Setter.Value>  
            <BlurBitmapEffect Radius="1" />  
          </Setter.Value>  
        </Setter>  
      </Trigger>  
      <!-- Set properties when button has focus. -->   <Trigger Property="IsFocused" Value="true">     <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />     <Setter Property="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />   </Trigger>  
  
    </ControlTemplate.Triggers>  
    ```  
  
     F5 키를 눌러 응용 프로그램을 실행 하 고 단추 중 하나를 클릭 합니다. 포커스를 여전히 있기 때문에 클릭 한 후 단추가 강조 표시 된에 유지 된다는 것을 확인 합니다. 다른 단추를 클릭 하면 마지막이를 손실 하는 동안 새 단추 포커스를 얻습니다.  
  
4.  **에 대 한 애니메이션 추가** <xref:System.Windows.UIElement.MouseEnter> **및** <xref:System.Windows.UIElement.MouseLeave> **:** 다음 일부 애니메이션 트리거를 추가 했습니다. 내에 다음 태그를 추가 `ControlTemplate.Triggers` 블록입니다.  
  
    ```  
    <!-- Animations that start when mouse enters and leaves button. -->  
    <EventTrigger RoutedEvent="Mouse.MouseEnter">  
      <EventTrigger.Actions>  
        <BeginStoryboard Name="mouseEnterBeginStoryboard">  
          <Storyboard>  
          <!-- This animation makes the glass rectangle shrink in the X direction. -->  
            <DoubleAnimation Storyboard.TargetName="glassCube"   
              Storyboard.TargetProperty=  
              "(Rectangle.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleX)"  
              By="-0.1" Duration="0:0:0.5" />  
            <!-- This animation makes the glass rectangle shrink in the Y direction. -->  
            <DoubleAnimation  
            Storyboard.TargetName="glassCube"   
              Storyboard.TargetProperty=  
              "(Rectangle.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleY)"   
              By="-0.1" Duration="0:0:0.5" />  
          </Storyboard>  
        </BeginStoryboard>  
      </EventTrigger.Actions>  
    </EventTrigger>  
    <EventTrigger RoutedEvent="Mouse.MouseLeave">  
      <EventTrigger.Actions>  
        <!-- Stopping the storyboard sets all animated properties back to default. -->  
        <StopStoryboard BeginStoryboardName="mouseEnterBeginStoryboard" />  
      </EventTrigger.Actions>  
    </EventTrigger>  
    ```  
  
     투명 효과 사각형 마우스 포인터를 단추 위로 이동 하 고 포인터를 벗어날 때 원래 크기로 반환 하는 경우 축소 합니다.  
  
     포인터를 단추 위로 이동할 때 트리거되는 두 개의 애니메이션이 (<xref:System.Windows.UIElement.MouseEnter> 이벤트 발생). 이러한 애니메이션 X 및 Y 축 따라 투명 효과 사각형을 축소합니다. 속성으로 것 이므로 <xref:System.Windows.Media.Animation.DoubleAnimation> 요소- <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>합니다. <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 애니메이션 0.5 초 동안, 발생 하도록 지정 하 고 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 10% 씩 축소 하는 투명 효과 지정 합니다.  
  
     두 번째 이벤트 트리거 (<xref:System.Windows.UIElement.MouseLeave>) 첫 번째가 중지 됩니다. 중지 하는 경우는 <xref:System.Windows.Media.Animation.Storyboard>, 모든 애니메이션된 속성이 기본값으로 반환 합니다. 따라서 포인터를 단추 밖를 이동할 때 단추 마크로 다시 단추 위로 마우스 포인터를 이동 하기 전의 하는 방법입니다. 애니메이션에 대 한 자세한 내용은 참조 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)합니다.  
  
5.  **추가 단추를 클릭에 대 한 애니메이션:** 마지막 단계는 사용자가 단추를 클릭 하는 경우에 대 한 트리거를 추가 하는 것입니다. 내에 다음 태그를 추가 `ControlTemplate.Triggers` 블록:  
  
    ```  
    <!-- Animation fires when button is clicked, causing glass to spin.  -->  
    <EventTrigger RoutedEvent="Button.Click">  
      <EventTrigger.Actions>  
        <BeginStoryboard>  
          <Storyboard>  
            <DoubleAnimation Storyboard.TargetName="glassCube"   
              Storyboard.TargetProperty=  
              "(Rectangle.RenderTransform).(TransformGroup.Children)[1].(RotateTransform.Angle)"   
              By="360" Duration="0:0:0.5" />  
          </Storyboard>  
        </BeginStoryboard>  
      </EventTrigger.Actions>  
    </EventTrigger>  
    ```  
  
     F5 키를 눌러 응용 프로그램을 실행 하 고 단추 중 하나를 클릭 합니다. 단추를 클릭할 때 투명 효과 사각형 회전 합니다.  
  
## <a name="summary"></a>요약  
 이 연습에서는 다음 연습을 수행 합니다.  
  
-   대상으로 한 <xref:System.Windows.Style> 개체 유형 (<xref:System.Windows.Controls.Button>).  
  
-   사용 하 여 전체 응용 프로그램에 있는 단추의 기본 속성을 제어는 <xref:System.Windows.Style>합니다.  
  
-   만든 리소스의 속성 값에 사용할 그라데이션 같은 <xref:System.Windows.Style> setter입니다.  
  
-   단추에 템플릿을 적용 하 여 전체 응용 프로그램에서 단추 모양을 사용자 지정 합니다.  
  
-   사용자 작업에 대 한 응답으로 단추에 대 한 동작을 사용자 지정 (같은 <xref:System.Windows.UIElement.MouseEnter>, <xref:System.Windows.UIElement.MouseLeave>, 및 <xref:System.Windows.Controls.Primitives.ButtonBase.Click>) 애니메이션 효과 포함 하는 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft Expression Blend를 사용하여 단추 만들기](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md)  
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [단색 및 그라데이션을 사용한 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [비트맵 효과 개요](../../../../docs/framework/wpf/graphics-multimedia/bitmap-effects-overview.md)
