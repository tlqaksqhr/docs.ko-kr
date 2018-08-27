---
title: 투명 효과 프레임을 WPF 응용 프로그램으로 확장
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applications [WPF], extending glass frames into
- graphics [WPF], extending glass frames into applications
- extending glass frames into applications [WPF]
- glass frames [WPF], extending into applications
ms.assetid: 74388a3a-4b69-4a9d-ba1f-e107636bd660
ms.openlocfilehash: 93eda6d6a13d6a510f2aeb06ab1c66d0cd40927f
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42931542"
---
# <a name="extend-glass-frame-into-a-wpf-application"></a>투명 효과 프레임을 WPF 응용 프로그램으로 확장
이 항목을 확장 하는 방법에 설명 합니다 [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] Windows Presentation Foundation (WPF) 응용 프로그램의 클라이언트 영역에 투명 효과 프레임입니다.  
  
> [!NOTE]
>  이 예제는 투명 효과가 사용되도록 설정된 DWM(바탕 화면 창 관리자)를 실행하는 [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] 컴퓨터에서만 작동합니다. [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] Home Basic Edition에서는 투명 효과를 지원하지 않습니다. 일반적으로 [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)]의 다른 버전에서 투명 효과로 렌더링되는 영역은 불투명하게 렌더링됩니다.  
  
## <a name="example"></a>예  
 다음 그림에서는 Internet Explorer 7의 주소 표시줄로 확장되는 투명 효과 프레임을 보여 줍니다.  
  
 **주소 표시줄 뒤로 투명 효과 프레임이 확장된 Internet Explorer**  
  
 ![주소 표시줄 뒤로 투명 효과 프레임이 확장된 IE7](../../../../docs/framework/wpf/graphics-multimedia/media/ie7glasstopbar.PNG "IE7glasstopbar")  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램에서 투명 효과 프레임을 확장하려면 관리되지 않는 [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)]에 액세스해야 합니다. 다음 코드 예제에서는 프레임을 클라이언트 영역으로 확장하는 데 필요한 두 개의 [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]에 대해 플랫폼 호출(pinvoke)을 수행합니다. 이러한 각 [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]는 **NonClientRegionAPI**라는 클래스에 선언됩니다.  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
public struct MARGINS  
{  
    public int cxLeftWidth;      // width of left border that retains its size  
    public int cxRightWidth;     // width of right border that retains its size  
    public int cyTopHeight;      // height of top border that retains its size  
    public int cyBottomHeight;   // height of bottom border that retains its size  
};  
  
[DllImport("DwmApi.dll")]  
public static extern int DwmExtendFrameIntoClientArea(  
    IntPtr hwnd,  
    ref MARGINS pMarInset);  
```  
  
```vb  
<StructLayout(LayoutKind.Sequential)>  
        Public Structure MARGINS  
            Public cxLeftWidth As Integer ' width of left border that retains its size  
            Public cxRightWidth As Integer ' width of right border that retains its size  
            Public cyTopHeight As Integer ' height of top border that retains its size  
            Public cyBottomHeight As Integer ' height of bottom border that retains its size  
        End Structure  
  
        <DllImport("DwmApi.dll")>  
        Public Shared Function DwmExtendFrameIntoClientArea(ByVal hwnd As IntPtr, ByRef pMarInset As MARGINS) As Integer  
        End Function  
```  
  
 [DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea)는 프레임을 클라이언트 영역으로 확장하는 DWM 함수입니다. 이 함수는 창 핸들 및 [MARGINS](/windows/desktop/api/uxtheme/ns-uxtheme-_margins) 구조체의 두 매개 변수를 사용합니다. [MARGINS](/windows/desktop/api/uxtheme/ns-uxtheme-_margins)는 프레임을 클라이언트 영역으로 얼마나 추가로 확장해야 하는지를 나타내는 데 사용됩니다.  
  
## <a name="example"></a>예  
 [DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea) 함수를 사용하려면 창 핸들을 가져와야 합니다. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서 창 핸들을 가져올 수 있습니다 합니다 <xref:System.Windows.Interop.HwndSource.Handle%2A> 의 속성을 <xref:System.Windows.Interop.HwndSource>. 다음 예제에서는 프레임은 확장을 클라이언트 영역으로에 <xref:System.Windows.FrameworkElement.Loaded> 창의 이벤트입니다.  
  
```csharp  
void OnLoaded(object sender, RoutedEventArgs e)  
{  
   try  
   {  
      // Obtain the window handle for WPF application  
      IntPtr mainWindowPtr = new WindowInteropHelper(this).Handle;  
      HwndSource mainWindowSrc = HwndSource.FromHwnd(mainWindowPtr);  
      mainWindowSrc.CompositionTarget.BackgroundColor = Color.FromArgb(0, 0, 0, 0);  
  
      // Get System Dpi  
      System.Drawing.Graphics desktop = System.Drawing.Graphics.FromHwnd(mainWindowPtr);  
      float DesktopDpiX = desktop.DpiX;  
      float DesktopDpiY = desktop.DpiY;  
  
      // Set Margins  
      NonClientRegionAPI.MARGINS margins = new NonClientRegionAPI.MARGINS();  
  
      // Extend glass frame into client area  
      // Note that the default desktop Dpi is 96dpi. The  margins are  
      // adjusted for the system Dpi.  
      margins.cxLeftWidth = Convert.ToInt32(5 * (DesktopDpiX / 96));  
      margins.cxRightWidth = Convert.ToInt32(5 * (DesktopDpiX / 96));  
      margins.cyTopHeight = Convert.ToInt32(((int)topBar.ActualHeight + 5) * (DesktopDpiX / 96));  
      margins.cyBottomHeight = Convert.ToInt32(5 * (DesktopDpiX / 96));  
  
      int hr = NonClientRegionAPI.DwmExtendFrameIntoClientArea(mainWindowSrc.Handle, ref margins);  
      //  
      if (hr < 0)  
      {  
         //DwmExtendFrameIntoClientArea Failed  
      }  
   }  
   // If not Vista, paint background white.  
   catch (DllNotFoundException)  
   {  
      Application.Current.MainWindow.Background = Brushes.White;  
   }  
}  
```  
  
## <a name="example"></a>예  
 다음 예제는 프레임이 클라이언트 영역으로 확장되는 간단한 창을 보여 줍니다. 프레임은 두 가지를 포함 하는 위쪽 테두리 뒤로 확장 됩니다 <xref:System.Windows.Controls.TextBox> 개체입니다.  
  
```xaml  
<Window x:Class="SDKSample.Window1"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    Title="Extended Glass in WPF" Height="300" Width="400"   
    Loaded="OnLoaded" Background="Transparent"  
    >  
  <Grid ShowGridLines="True">  
    <DockPanel Name="mainDock">  
      <!-- The border is used to compute the rendered height with margins.  
           topBar contents will be displayed on the extended glass frame.-->  
      <Border Name="topBar" DockPanel.Dock="Top" >  
        <Grid Name="grid">  
          <Grid.ColumnDefinitions>  
            <ColumnDefinition MinWidth="100" Width="*"/>  
            <ColumnDefinition Width="Auto"/>  
          </Grid.ColumnDefinitions>  
          <TextBox Grid.Column="0" MinWidth="100" Margin="0,0,10,5">Path</TextBox>  
          <TextBox Grid.Column="1" MinWidth="75" Margin="0,0,0,5">Search</TextBox>  
        </Grid>  
      </Border>  
      <Grid DockPanel.Dock="Top" >  
        <Grid.ColumnDefinitions>  
          <ColumnDefinition/>  
        </Grid.ColumnDefinitions>  
        <TextBox Grid.Column="0" AcceptsReturn="True"/>  
      </Grid>  
    </DockPanel>  
  </Grid>  
</Window>  
```  
  
 다음 그림에서는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램으로 확장되는 투명 효과 프레임을 보여 줍니다.  
  
 **투명 효과 프레임이 확장 된는**[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]**응용 프로그램입니다.**  
  
 ![WPF 응용 프로그램으로 확장된 투명 효과 프레임](../../../../docs/framework/wpf/graphics-multimedia/media/wpfextendedglassintoclient.PNG "WPFextendedGlassIntoClient")  
  
## <a name="see-also"></a>참고 항목  
 [바탕 화면 창 관리자 개요](/windows/desktop/dwm/dwm-overview)  
 [바탕 화면 창 관리자 흐림 효과 개요](/windows/desktop/dwm/blur-ovw)  
 [DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea)
