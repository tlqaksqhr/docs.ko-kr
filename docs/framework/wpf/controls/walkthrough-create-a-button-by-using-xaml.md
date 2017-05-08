---
title: "연습: XAML을 사용하여 단추 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "단추"
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 연습: XAML을 사용하여 단추 만들기
이 연습에서는 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 응용 프로그램에서 사용할 애니메이션 단추를 만드는 방법에 대해 알아 봅니다.  이 연습에서는 스타일과 템플릿을 사용하여 코드를 다시 사용할 수 있고 단추 논리와 단추 선언을 분리할 수 있는 사용자 지정된 단추 리소스를 만듭니다.  이 연습에서는 전체 코드를 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]로 작성합니다.  
  
> [!IMPORTANT]
>  이 연습에서는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]을 Microsoft [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]에 입력 또는 복사하여 붙여넣는 방법으로 응용 프로그램을 만드는 단계를 안내합니다.  디자인 도구\(Microsoft Expression Blend\)를 사용하여 동일한 응용 프로그램을 만드는 방법을 알고 싶으면 [Microsoft Expression Blend를 사용하여 단추 만들기](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md)를 참조하십시오.  
  
 다음 그림에서는 완료된 단추를 보여 줍니다.  
  
 ![XAML을 사용하여 만든 사용자 지정 단추](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.png "custom\_button\_AnimatedButton\_5")  
  
## 기본 단추 만들기  
 먼저 새 프로젝트를 만들고 창에 몇 개의 단추를 추가합니다.  
  
#### 새 WPF 프로젝트를 만들고 창에 단추를 추가하려면  
  
1.  [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]를 시작합니다.  
  
2.  **새 WPF 프로젝트 만들기:** **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.  **Windows 응용 프로그램\(WPF\)** 템플릿을 찾아서 프로젝트 이름을 "AnimatedButton"으로 지정합니다.  이것으로 응용 프로그램의 기초를 만들었습니다.  
  
3.  **기본 단추 추가.** 이 연습에 필요한 모든 파일은 템플릿에서 제공됩니다.  솔루션 탐색기에서 Window1.xaml 파일을 두 번 클릭하여 엽니다.  기본적으로 Window1.xaml에는 <xref:System.Windows.Controls.Grid> 요소가 있습니다.  <xref:System.Windows.Controls.Grid> 요소를 제거하고 아래의 강조 표시된 코드를 Window1.xaml에 입력 또는 복사하고 붙여 넣어서 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 페이지에 몇 개의 단추를 추가합니다.  
  
    ```  
    <Window x:Class="AnimatedButton.Window1"  
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
      Title="AnimatedButton" Height="300" Width="300"   
      Background="Black">  
  
      <!-- Buttons arranged vertically inside a StackPanel. -->  
      <StackPanel HorizontalAlignment="Left">  
        <Button>Button 1</Button>  
        <Button>Button 2</Button>  
        <Button>Button 3</Button>  
      </StackPanel>  
  
    </Window>  
    ```  
  
     F5 키를 눌러 응용 프로그램을 실행합니다. 다음 그림과 같은 단추 집합이 표시됩니다.  
  
     ![세 개의 기본 단추](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-1.png "custom\_button\_AnimatedButton\_1")  
  
     기본 단추를 만들었으므로 Window1.xaml 파일에서의 작업을 완료했습니다.  이 연습의 나머지 부분에서는 주로 app.xaml 파일에서 단추의 스타일과 템플릿을 정의합니다.  
  
## 기본 속성 설정  
 다음으로 이러한 단추의 일부 속성을 설정하여 단추의 모양과 레이아웃을 조정합니다.  단추의 속성을 개별적으로 설정하지 않고 리소스를 사용하여 전체 응용 프로그램의 단추 속성을 정의합니다.  응용 프로그램 리소스는 개념적으로 웹 페이지의 외부 [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)]와 유사하지만 이 연습을 마치면 알 수 있듯이 리소스가 [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)]보다 기능이 강력합니다.  리소스에 대한 자세한 내용은 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)를 참조하십시오.  
  
#### 스타일을 사용하여 단추의 기본 속성을 설정하려면  
  
1.  **Application.Resources 블록 정의.** app.xaml을 열고 아래의 강조 표시된 태그를 추가합니다\(없는 경우\).  
  
    ```  
    <Application x:Class="AnimatedButton.App"  
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
      StartupUri="Window1.xaml"  
      >  
      <Application.Resources>  
  
        <!-- Resources for the entire application can be   
             defined here. -->  
  
      </Application.Resources>  
    </Application>  
    ```  
  
     리소스 범위는 리소스를 정의하는 위치에 따라 결정됩니다.  리소스를 app.xaml 파일의 `Application.Resoureses`에서 정의하면 응용 프로그램의 아무 위치에서나 리소스를 사용할 수 있습니다.  리소스 범위 정의에 대한 자세한 내용은 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)를 참조하십시오.  
  
2.  **스타일을 만들고 스타일을 사용하여 기본 속성 값 정의.** 아래의 태그를 `Application.Resources` 블록에 추가합니다.  이 태그는 응용 프로그램의 모든 단추에 적용되는 <xref:System.Windows.Style>을 만듭니다. 이 스타일에서는 단추의 <xref:System.Windows.FrameworkElement.Width%2A>를 90으로, <xref:System.Windows.FrameworkElement.Margin%2A>을 10으로 설정합니다.  
  
    ```  
    <Application.Resources>  
  
      <Style TargetType="Button">  
        <Setter Property="Width" Value="90" />  
        <Setter Property="Margin" Value="10" />  
      </Style>  
  
    </Application.Resources>  
    ```  
  
     위의 <xref:System.Windows.Style.TargetType%2A> 속성은 스타일이 모든 <xref:System.Windows.Controls.Button> 개체 형식에 적용되도록 지정합니다.  각 <xref:System.Windows.Setter>는 <xref:System.Windows.Style>의 서로 다른 속성 값을 지정합니다.  따라서 이때 응용 프로그램의 모든 단추의 너비는 90이고 여백은 10입니다.  F5 키를 눌러 응용 프로그램을 실행하면 다음 창이 표시됩니다.  
  
     ![너비 90, 여백 10의 단추](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-2.png "custom\_button\_AnimatedButton\_2")  
  
     이외에도 스타일을 사용하여 대상으로 지정할 개체를 미세 조정하고 복잡한 속성 값을 지정하는 등의 다양한 작업을 수행할 수 있으며 스타일을 다른 스타일의 입력으로 사용할 수도 있습니다.  자세한 내용은 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)을 참조하십시오.  
  
3.  **스타일 속성 값을 리소스로 설정.** 리소스를 사용하면 일반적으로 정의되어 있는 개체 및 값을 쉽게 다시 사용할 수 있습니다.  특히 리소스를 사용하여 코드를 모듈식으로 만들면 복잡한 값을 쉽게 정의할 수 있습니다.  아래의 강조 표시된 태그를 app.xaml에 추가합니다.  
  
    ```  
    <Application.Resources>  
  
      <LinearGradientBrush x:Key="GrayBlueGradientBrush"   
        StartPoint="0,0" EndPoint="1,1">  
        <GradientStop Color="DarkGray" Offset="0" />  
        <GradientStop Color="#CCCCFF" Offset="0.5" />  
        <GradientStop Color="DarkGray" Offset="1" />  
      </LinearGradientBrush>  
  
      <Style TargetType="{x:Type Button}">  
        <Setter Property="Background"   
          Value="{StaticResource GrayBlueGradientBrush}" />  
        <Setter Property="Width" Value="80" />  
        <Setter Property="Margin" Value="10" />  
      </Style>  
  
    </Application.Resources>  
    ```  
  
     `Application.Resources` 블록 바로 아래에서 "GrayBlueGradientBrush"라는 리소스를 만들었습니다.  이 리소스에서는 가로 그라데이션을 정의합니다.  <xref:System.Windows.Controls.Control.Background%2A> 속성의 단추 스타일 setter 내부를 비롯해 응용 프로그램의 모든 위치에서 이 리소스를 속성 값으로 사용할 수 있습니다.  이제 모든 단추가 이 그라데이션의 <xref:System.Windows.Controls.Control.Background%2A> 속성 값을 가집니다.  
  
     F5 키를 눌러 응용 프로그램을 실행합니다.  다음과 같이 표시됩니다.  
  
     ![그라데이션 배경이 있는 단추](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-3.png "custom\_button\_AnimatedButton\_3")  
  
## 단추의 모양을 정의하는 템플릿 만들기  
 이 단원에서는 단추의 모양\(표시\)을 사용자 지정하는 템플릿을 만듭니다.  단추 표시는 직사각형을 비롯한 여러 개체와 단추에 고유한 모양을 부여하는 기타 구성 요소로 이루어집니다.  
  
 지금까지 응용 프로그램에서 단추가 표시되는 모양을 제어하려면 단추의 속성을 변경하는 방법밖에 없었습니다.  단추의 모양을 근본적으로 변경하려는 경우에는 어떻게 합니까?  템플릿을 사용하면 개체 표시를 보다 효과적으로 제어할 수 있습니다.  템플릿은 스타일 내에서 사용할 수 있으므로 스타일이 적용되는 모든 개체\(이 연습의 경우에는 단추\)에 템플릿을 적용할 수 있습니다.  
  
#### 템플릿을 사용하여 단추 모양을 정의하려면  
  
1.  **템플릿 설정.** <xref:System.Windows.Controls.Button>과 같은 컨트롤에는 <xref:System.Windows.Controls.Control.Template%2A> 속성이 있으므로 <xref:System.Windows.Style>에서 <xref:System.Windows.Setter>를 사용하여 설정하는 다른 속성 값처럼 템플릿 속성 값을 정의할 수 있습니다.  아래의 강조 표시된 태그를 단추 스타일에 추가합니다.  
  
    ```  
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
  
2.  **단추 표시 변경.** 이제 템플릿을 정의해야 합니다.  다음의 강조 표시된 태그를 추가합니다.  이 태그에서는 모퉁이가 둥근 두 개의 <xref:System.Windows.Shapes.Rectangle> 요소와 <xref:System.Windows.Controls.DockPanel> 요소를 차례로 지정합니다.  <xref:System.Windows.Controls.DockPanel>은 단추의 <xref:System.Windows.Controls.ContentPresenter>를 호스팅하는 데 사용됩니다.  <xref:System.Windows.Controls.ContentPresenter>에는 단추의 내용이 표시됩니다.  이 연습에서 이 내용은 텍스트입니다\("Button 1", "Button 2", "Button 3"\).  모든 템플릿 구성 요소인 직사각형과 <xref:System.Windows.Controls.DockPanel>은 <xref:System.Windows.Controls.Grid> 내에 배치됩니다.  
  
    ```  
    <Setter.Value>  
      <ControlTemplate TargetType="Button">  
        <Grid Width="{TemplateBinding Width}"   
         Height="{TemplateBinding Height}" ClipToBounds="True">  
  
          <!-- Outer Rectangle with rounded corners. -->  
          <Rectangle x:Name="outerRectangle"   
            HorizontalAlignment="Stretch"   
            VerticalAlignment="Stretch"   
            Stroke="{TemplateBinding Background}"   
            RadiusX="20" RadiusY="20" StrokeThickness="5"   
            Fill="Transparent" />  
  
          <!-- Inner Rectangle with rounded corners. -->  
          <Rectangle x:Name="innerRectangle"   
            HorizontalAlignment="Stretch"   
            VerticalAlignment="Stretch" Stroke="Transparent"   
            StrokeThickness="20"   
            Fill="{TemplateBinding Background}"   
            RadiusX="20" RadiusY="20"   />  
  
          <!-- Present Content (text) of the button. -->  
          <DockPanel Name="myContentPresenterDockPanel">  
            <ContentPresenter x:Name="myContentPresenter" Margin="20"   
              Content="{TemplateBinding  Content}"   
              TextBlock.Foreground="Black" />  
          </DockPanel>  
        </Grid>  
      </ControlTemplate>  
    </Setter.Value>  
    ```  
  
     F5 키를 눌러 응용 프로그램을 실행합니다.  다음과 같이 표시됩니다.  
  
     ![](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-4.gif "custom\_button\_AnimatedButton\_4")  
  
3.  **템플릿에 투명 효과 추가.** 다음으로 투명 효과를 추가합니다.  우선 투명 그라데이션 효과를 만드는 리소스를 만듭니다.  이러한 그라데이션 리소스를 `Application.Resources` 블록 내에 추가합니다.  
  
    ```  
    <Application.Resources>  
      <GradientStopCollection x:Key="MyGlassGradientStopsResource">  
        <GradientStop Color="WhiteSmoke" Offset="0.2" />  
        <GradientStop Color="Transparent" Offset="0.4" />  
        <GradientStop Color="WhiteSmoke" Offset="0.5" />  
        <GradientStop Color="Transparent" Offset="0.75" />  
        <GradientStop Color="WhiteSmoke" Offset="0.9" />  
        <GradientStop Color="Transparent" Offset="1" />  
      </GradientStopCollection>  
  
      <LinearGradientBrush x:Key="MyGlassBrushResource"   
       StartPoint="0,0" EndPoint="1,1" Opacity="0.75"   
       GradientStops="{StaticResource MyGlassGradientStopsResource}" />  
    <!-- Styles and other resources below here. -->  
    ```  
  
     이러한 리소스는 단추 템플릿의 <xref:System.Windows.Controls.Grid>에 삽입하는 직사각형의 <xref:System.Windows.Shapes.Shape.Fill%2A>로 사용됩니다.  템플릿에 다음의 강조 표시된 태그를 추가합니다.  
  
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
  
          <!-- These transforms have no effect as they are declared here.   
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
    </ControlTemplate>  
    </Setter.Value>  
    ```  
  
     `x:Name` 속성이 "glassCube"인 직사각형의 <xref:System.Windows.UIElement.Opacity%2A>가 0이므로 샘플을 실행하면 맨 위에 겹쳐서 표시된 투명 직사각형이 보이지 않습니다.  이는 사용자가 단추와 상호 작용하는 데 필요한 트리거를 템플릿에 나중에 추가하기 때문입니다.  하지만 <xref:System.Windows.UIElement.Opacity%2A> 값을 1로 변경하고 응용 프로그램을 실행하면 단추 모양이 어떤지 확인할 수 있습니다.  다음 그림을 참조하십시오.  다음 단계로 진행하기 전에 <xref:System.Windows.UIElement.Opacity%2A>를 다시 0으로 변경합니다.  
  
     ![XAML을 사용하여 만든 사용자 지정 단추](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.png "custom\_button\_AnimatedButton\_5")  
  
## 단추 대화형 작업 만들기  
 이 단원에서는 마우스 포인터를 단추 위에 놓거나 클릭하는 등의 사용자 작업에 응답하여 속성 값을 변경하고 애니메이션을 실행하는 속성 트리거 및 이벤트 트리거를 만듭니다.  
  
 항목 위에 마우스 놓기, 항목 범위 밖으로 마우스 이동, 클릭 등과 같은 대화형 작업을 추가하는 쉬운 방법은 템플릿이나 스타일 내에 트리거를 정의하는 것입니다.  <xref:System.Windows.Trigger>를 만들려면 The button <xref:System.Windows.UIElement.IsMouseOver%2A> property value is equal to `true`와 같은 속성 "조건"을 정의합니다.  그런 다음 트리거 조건이 true일 경우 발생하는 setter\(작업\)를 정의합니다.  
  
#### 단추 대화형 작업을 만들려면  
  
1.  **템플릿 트리거 추가.** 강조 표시된 태그를 템플릿에 추가합니다.  
  
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
  
        <ControlTemplate.Triggers>  
          <!-- Set action triggers for the buttons and define  
               what the button does in response to those triggers. -->  
        </ControlTemplate.Triggers>  
      </ControlTemplate>  
    </Setter.Value>  
    ```  
  
2.  **속성 트리거 추가.** 강조 표시된 태그를 `ControlTemplate.Triggers` 블록에 추가합니다.  
  
    ```  
    <ControlTemplate.Triggers>  
  
      <!-- Set properties when mouse pointer is over the button. -->  
      <Trigger Property="IsMouseOver" Value="True">  
  
        <!-- Below are three property settings that occur when the   
             condition is met (user mouses over button).  -->  
        <!-- Change the color of the outer rectangle when user   
             mouses over it. -->  
        <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"  
          Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />  
  
        <!-- Sets the glass opacity to 1, therefore, the   
             glass "appears" when user mouses over it. -->  
        <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />  
  
        <!-- Makes the text slightly blurry as though you   
             were looking at it through blurry glass. -->  
        <Setter Property="ContentPresenter.BitmapEffect"   
          TargetName="myContentPresenter">  
          <Setter.Value>  
            <BlurBitmapEffect Radius="1" />  
          </Setter.Value>  
        </Setter>  
      </Trigger>  
  
    <ControlTemplate.Triggers/>  
    ```  
  
     F5 키를 눌러 응용 프로그램을 실행하고 마우스 포인터를 단추 위에 놓을 때의 효과를 확인합니다.  
  
3.  **포커스 트리거 추가.** 다음으로 단추에 포커스가 있을 때 예를 들어 사용자가 단추를 클릭한 후의 경우를 처리하는 몇 가지 유사한 setter를 추가합니다.  
  
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
      <!-- Set properties when button has focus. -->  
      <Trigger Property="IsFocused" Value="true">  
        <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />  
        <Setter Property="Rectangle.Stroke" TargetName="outerRectangle"  
          Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />  
        <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />  
      </Trigger>  
  
    </ControlTemplate.Triggers>  
    ```  
  
     F5 키를 눌러 응용 프로그램을 실행하고 단추 중 하나를 클릭합니다.  단추를 클릭한 후에도 계속 단추에 포커스가 있으므로 단추가 강조 표시된 상태로 유지됩니다.  다른 단추를 클릭하면 새 단추가 포커스를 얻고 마지막 단추는 포커스를 잃습니다.  
  
4.  <xref:System.Windows.UIElement.MouseEnter> **및** <xref:System.Windows.UIElement.MouseLeave>**에 대한 애니메이션 추가.** 다음으로 트리거에 몇 가지 애니메이션을 추가합니다.  `ControlTemplate.Triggers` 블록 내에 다음 태그를 추가합니다.  
  
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
  
     마우스 포인터를 단추 위로 이동하면 투명 직사각형이 축소되고 포인터를 다른 위치로 이동하면 단추가 원래 크기로 돌아옵니다.  
  
     포인터를 단추 위로 이동할 때 두 가지 애니메이션이 트리거됩니다\(<xref:System.Windows.UIElement.MouseEnter> 이벤트 발생\).  이러한 애니메이션에서는 투명 직사각형을 X축과 Y축을 따라 축소합니다.  <xref:System.Windows.Media.Animation.DoubleAnimation> 요소에는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>라는 속성이 있습니다.  <xref:System.Windows.Media.Animation.Timeline.Duration%2A>은 애니메이션이 0.5초 동안 발생하도록 지정하고 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>는 투명 직사각형이 10%씩 축소되도록 지정합니다.  
  
     두 번째 이벤트 트리거\(<xref:System.Windows.UIElement.MouseLeave>\)는 첫 번째 트리거를 중지하기만 합니다.  <xref:System.Windows.Media.Animation.Storyboard>를 중지하면 모든 애니메이션 속성이 기본값으로 되돌아옵니다.  따라서 사용자가 포인터를 단추 밖으로 이동하면 단추가 마우스 포인터를 단추 위에 올려 놓기 전의 모양으로 되돌아갑니다.  애니메이션에 대한 자세한 내용은 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)를 참조하십시오.  
  
5.  **단추를 클릭할 때를 위한 애니메이션 추가.** 마지막 단계에서는 사용자가 단추를 클릭할 때를 위한 트리거를 추가합니다.  `ControlTemplate.Triggers` 블록 내에 아무 위치에 다음 태그를 추가합니다.  
  
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
  
     F5 키를 눌러 응용 프로그램을 실행하고 단추 중 하나를 클릭합니다.  단추를 클릭하면 투명 직사각형이 회전합니다.  
  
## 요약  
 이 연습에서는 다음 연습을 수행했습니다.  
  
-   <xref:System.Windows.Style>의 대상을 개체 형식\(<xref:System.Windows.Controls.Button>\)으로 지정했습니다.  
  
-   <xref:System.Windows.Style>을 사용하여 전체 응용 프로그램에서 단추의 기본 속성을 제어했습니다.  
  
-   <xref:System.Windows.Style> setter의 속성 값으로 사용할 그라데이션과 같은 리소스를 만들었습니다.  
  
-   단추에 템플릿을 적용하여 전체 응용 프로그램에서 단추 모양을 사용자 지정했습니다.  
  
-   <xref:System.Windows.UIElement.MouseEnter>, <xref:System.Windows.UIElement.MouseLeave> 및 <xref:System.Windows.Controls.Primitives.ButtonBase.Click>과 같은 사용자 작업에 응답하는 애니메이션 효과가 포함된 단추의 동작을 사용자 지정했습니다.  
  
## 참고 항목  
 [Microsoft Expression Blend를 사용하여 단추 만들기](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md)   
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [단색 및 그라데이션을 사용한 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)   
 [비트맵 효과 개요](../../../../docs/framework/wpf/graphics-multimedia/bitmap-effects-overview.md)