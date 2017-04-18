---
title: "투명 효과 프레임을 WPF 응용 프로그램으로 확장 | Microsoft Docs"
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
  - "응용 프로그램, 투명 효과 프레임 확장"
  - "투명 효과 프레임을 응용 프로그램으로 확장"
  - "투명 효과 프레임, 응용 프로그램으로 확장"
  - "그래픽, 투명 효과 프레임을 응용 프로그램으로 확장"
ms.assetid: 74388a3a-4b69-4a9d-ba1f-e107636bd660
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 투명 효과 프레임을 WPF 응용 프로그램으로 확장
이 항목에서는 [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] 투명 효과 프레임을 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 응용 프로그램의 클라이언트 영역으로 확장하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  이 예제는 투명 효과가 설정되어 있는 DWM\(데스크톱 창 관리자\)을 실행 중인 [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] 시스템에서만 작동합니다.  [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] Home Basic Edition에서는 투명 효과를 지원하지 않습니다.  [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)]의 다른 버전에서는 일반적으로 투명 효과로 렌더링될 영역이 불투명하게 렌더링됩니다.  
  
## 예제  
 다음 이미지에서는 Internet Explorer 7의 주소 표시줄로 확장되는 투명 효과 프레임을 보여 줍니다.  
  
 **주소 표시줄 뒤로 투명 효과 프레임이 확장된 Internet Explorer**  
  
 ![주소 표시줄 뒤로 투명 효과 프레임이 확장된 IE7](../../../../docs/framework/wpf/graphics-multimedia/media/ie7glasstopbar.PNG "IE7glasstopbar")  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램에서 투명 효과 프레임을 확장하려면 관리되지 않는 [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)]로 액세스해야 합니다.  다음 코드 예제에서는 프레임을 클라이언트 영역으로 확장하는 데 필요한 두 개의 [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]에 대해 플랫폼 호출\(pinvoke\)을 수행합니다.  이러한 각 [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]는 **NonClientRegionAPI**라는 클래스에 선언되어 있습니다.  
  
<!-- TODO: review snippet reference  [!CODE [AvalonClientGlass#DWMExtendFramePInvokeAPI](AvalonClientGlass#DWMExtendFramePInvokeAPI)]  -->  
  
 [DwmExtendFrameIntoClientArea](_udwm_dwmextendframeintoclientarea) [](_udwm_dwmextendframeintoclientarea)는 프레임을 클라이언트 영역으로 확장하는 DWM 함수입니다.  이 함수는 두 개의 매개 변수, 즉 창 핸들과 [MARGINS](inet_MARGINS) 구조체를 사용합니다.  [MARGINS](inet_MARGINS)는 프레임의 여백을 얼마나 클라이언트 영역으로 확장해야 하는지를 DWM에 알리는 데 사용됩니다.  
  
## 예제  
 [DwmExtendFrameIntoClientArea](_udwm_dwmextendframeintoclientarea) 함수를 사용하려면 창 핸들을 가져와야 합니다.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서 창 핸들은 <xref:System.Windows.Interop.HwndSource>의 <xref:System.Windows.Interop.HwndSource.Handle%2A> 속성에서 가져올 수 있습니다.  다음 예제에서 프레임은 창의 <xref:System.Windows.FrameworkElement.Loaded> 이벤트에 있는 클라이언트 영역으로 확장됩니다.  
  
<!-- TODO: review snippet reference  [!CODE [AvalonClientGlass#AvalonGlassOnLoadedCSharp](AvalonClientGlass#AvalonGlassOnLoadedCSharp)]  -->  
  
## 예제  
 다음 예제에서는 프레임이 클라이언트 영역으로 확장되는 간단한 창을 보여 줍니다.  프레임은 두 개의 <xref:System.Windows.Controls.TextBox> 개체가 포함된 위쪽 테두리 뒤에서 확장됩니다.  
  
<!-- TODO: review snippet reference  [!CODE [AvalonClientGlass#AvalonGlassFullWindowXAML](AvalonClientGlass#AvalonGlassFullWindowXAML)]  -->  
  
 다음 이미지에서는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램으로 확장된 투명 효과 프레임을 보여 줍니다.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]  **응용 프로그램으로 확장된 투명 효과 프레임**  
  
 ![WPF 응용 프로그램으로 확장된 투명 효과 프레임](../../../../docs/framework/wpf/graphics-multimedia/media/wpfextendedglassintoclient.png "WPFextendedGlassIntoClient")  
  
## 참고 항목  
 [Desktop Window Manager Overview](_udwm_overview)   
 [Desktop Window Manager Blur Overview](_udwm_blur_ovw)   
 [DwmExtendFrameIntoClientArea](_udwm_dwmextendframeintoclientarea)