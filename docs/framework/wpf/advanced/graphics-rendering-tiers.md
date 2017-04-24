---
title: "그래픽 렌더링 계층 | Microsoft Docs"
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
  - "그래픽 렌더링 계층"
  - "그래픽, 성능"
  - "그래픽, 렌더링 계층"
  - "그래픽 렌더링"
  - "렌더링 계층"
ms.assetid: 08dd1606-02a2-4122-9351-c0afd2ec3a70
caps.latest.revision: 44
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 43
---
# 그래픽 렌더링 계층
렌더링 계층은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램을 실행하는 장치의 그래픽 하드웨어 기능 및 성능 수준을 정의합니다.  
  
   
  
<a name="graphics_hardware"></a>   
## 그래픽 하드웨어  
 렌더링 계층 수준에 가장 큰 영향을 주는 그래픽 하드웨어 기능은 다음과 같습니다.  
  
-   **비디오 RAM** \- 그래픽 하드웨어의 비디오 메모리 용량에 따라 그래픽 합성에 사용할 수 있는 버퍼의 크기와 수가 결정됩니다.  
  
-   **픽셀 셰이더** \- 픽셀 셰이더는 픽셀 단위로 효과를 계산하는 그래픽 처리 기능입니다.  표시된 그래픽의 해상도에 따라 표시 프레임별로 수백만 개의 픽셀을 처리해야 하는 경우도 있습니다.  
  
-   **꼭짓점 셰이더** \- 꼭짓점 셰이더는 개체의 꼭짓점 데이터에 대한 수학 연산을 수행하는 그래픽 처리 기능입니다.  
  
-   **다중 질감 지원** \- 다중 질감 지원은 3D 그래픽 개체에 대한 혼합 연산을 수행하는 동안 두 개 이상의 개별 질감을 적용하는 기능을 의미합니다.  여러 질감 지원의 수준은 그래픽 하드웨어의 여러 질감 단위 수에 따라 결정됩니다.  
  
<a name="rendering_tier_definitions"></a>   
## 렌더링 계층 정의  
 그래픽 하드웨어의 기능에 따라 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램의 렌더링 기능이 결정됩니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 시스템에서는 다음과 같은 세 가지 렌더링 계층을 정의합니다.  
  
-   **렌더링 계층 0** \- 그래픽 하드웨어 가속이 없습니다.  모든 그래픽 기능은 소프트웨어 가속을 사용합니다.  [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 버전 수준은 버전 7.0보다 낮습니다.  
  
-   **렌더링 계층 1** \- 일부 그래픽 기능에서 그래픽 하드웨어 가속을 사용합니다.  [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 버전 수준은 버전 9.0보다 높거나 같습니다.  
  
-   **렌더링 계층 2** \- 대부분의 그래픽 기능에서 그래픽 하드웨어 가속을 사용합니다.  [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 버전 수준은 버전 9.0보다 높거나 같습니다.  
  
 <xref:System.Windows.Media.RenderCapability.Tier%2A?displayProperty=fullName> 속성을 사용하여 응용 프로그램 런타임에 렌더링 계층을 검색할 수 있습니다.  렌더링 계층을 사용하여 장치에서 특정 하드웨어 가속 그래픽 기능을 지원하는지 여부를 확인합니다.  그러면 런타임에 응용 프로그램에서 장치가 지원하는 렌더링 계층에 따라 다른 코드 경로를 사용할 수 있습니다.  
  
### 렌더링 계층 0  
 렌더링 계층 값이 0이라는 것은 장치에서 응용 프로그램에 사용할 수 있는 그래픽 하드웨어 가속이 없음을 의미합니다.  이 계층 수준에서는 소프트웨어가 모든 그래픽을 하드웨어 가속 없이 렌더링한다고 간주해야 합니다.  이 계층의 기능은 9.0 이하의 [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 버전에 해당합니다.  
  
### 렌더링 계층 1 및 렌더링 계층 2  
  
> [!NOTE]
>  .NET Framework 4부터 렌더링 계층 1은 [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 9.0 이상을 지원하는 그래픽 하드웨어만 포함하도록 다시 정의되었습니다.  [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 7 또는 8을 지원하는 그래픽 하드웨어는 이제 렌더링 계층 0으로 정의됩니다.  
  
 렌더링 계층 값 1 또는 2는 필요한 시스템 리소스가 사용 가능하며 모두 사용되지 않은 경우 대부분의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 그래픽 기능에서 하드웨어 가속을 사용함을 의미합니다.  이 값은 9.0 이상의 [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 버전에 해당합니다.  
  
 다음 표에서는 렌더링 계층 1과 렌더링 계층 2에 대한 그래픽 하드웨어 요구 사항의 차이점을 보여 줍니다.  
  
|기능|계층 1|계층 2|  
|--------|----------|----------|  
|[!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 버전|9.0보다 높거나 같아야 합니다.|9.0보다 높거나 같아야 합니다.|  
|비디오 RAM|60MB보다 크거나 같아야 합니다.|120MB보다 크거나 같아야 합니다.|  
|픽셀 셰이더|버전 수준이 2.0보다 높거나 같아야 합니다.|버전 수준이 2.0보다 높거나 같아야 합니다.|  
|꼭짓점 셰이더|요구 사항 없음|버전 수준이 2.0보다 높거나 같아야 합니다.|  
|다중 질감 단위|요구 사항 없음|단위 수가 4보다 크거나 같아야 합니다.|  
  
 다음 기능은 렌더링 계층 1과 렌더링 계층 2에서 하드웨어 가속됩니다.  
  
|기능|참고|  
|--------|--------|  
|2D 렌더링|대부분의 2D 렌더링이 지원됩니다.|  
|3D 래스터화|대부분의 3D 래스터화가 지원됩니다.|  
|3D 이방성 필터링|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 3D 콘텐츠를 렌더링할 때 이방성 필터링을 사용하려고 시도합니다.  이방성 필터링은 카메라를 기준으로 멀리 떨어져 있고 비스듬한 각도의 표면에서 질감의 이미지 품질을 개선하는 것을 의미합니다.|  
|3D MIP 매핑|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 3D 콘텐츠를 렌더링할 때 MIP 매핑을 사용하려고 시도합니다. MIP 매핑은 <xref:System.Windows.Controls.Viewport3D>에서 질감이 차지하는 뷰 필드의 면적이 작을 때 질감 렌더링의 품질을 향상시킵니다.|  
|방사형 그라데이션|<xref:System.Windows.Media.RadialGradientBrush>가 지원되기는 하지만 대형 개체에서는 이 기능을 사용하지 마십시오.|  
|3D 조명 계산|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 꼭짓점 조명별로 이 계산을 수행합니다. 즉, 메시에 적용한 각 재질의 각 꼭짓점에서 조명 강도를 계산해야 합니다.|  
|텍스트 렌더링|하위 픽셀 글꼴 렌더링에서는 그래픽 하드웨어에서 사용 가능한 픽셀 셰이더를 사용합니다.|  
  
 다음 기능은 렌더링 계층 2에서만 하드웨어 가속됩니다.  
  
|기능|참고|  
|--------|--------|  
|3D 앤티 앨리어싱|3D 앤티 앨리어싱은 [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] 및 [!INCLUDE[win7](../../../../includes/win7-md.md)]과 같이 WDDM\(Windows Display Driver Model\)을 지원하는 운영 체제에서만 지원됩니다.|  
  
 다음 기능은 하드웨어 가속되지 **않습니다**.  
  
|기능|참고|  
|--------|--------|  
|인쇄된 콘텐츠|모든 인쇄된 콘텐츠는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 소프트웨어 파이프라인을 사용하여 렌더링됩니다.|  
|<xref:System.Windows.Media.Imaging.RenderTargetBitmap>을 사용하고 래스터화된 콘텐츠|<xref:System.Windows.Media.Imaging.RenderTargetBitmap>의 <xref:System.Windows.Media.Imaging.RenderTargetBitmap.Render%2A> 메서드를 사용하여 렌더링된 모든 콘텐츠에 적용됩니다.|  
|<xref:System.Windows.Media.TileBrush>를 사용하고 바둑판식으로 표시된 콘텐츠|<xref:System.Windows.Media.TileBrush>의 <xref:System.Windows.Media.TileBrush.TileMode%2A> 속성이 <xref:System.Windows.Media.TileMode>로 설정되어 있고 바둑판식으로 표시된 콘텐츠에 적용됩니다.|  
|그래픽 하드웨어의 최대 질감 크기를 초과하는 화면|대부분의 그래픽 하드웨어에서 대형 화면의 크기는 2048x2048 또는 4096x4096픽셀입니다.|  
|비디오 RAM 요구 사항이 그래픽 하드웨어의 메모리를 초과하는 작업|Windows SDK의 [WPF 성능 제품군](../Topic/WPF%20Performance%20Suite.md)에 포함된 Perforator 도구를 사용하여 응용 프로그램의 비디오 RAM 사용을 모니터링할 수 있습니다.|  
|계층 창|계층 창을 사용하면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에서 콘텐츠를 사각형이 아닌 창의 화면에 렌더링할 수 있습니다.  [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] 및 [!INCLUDE[win7](../../../../includes/win7-md.md)]과 같이 WDDM\(Windows Display Driver Model\)을 지원하는 운영 체제에서는 계층 창이 하드웨어 가속됩니다.  [!INCLUDE[winxp](../../../../includes/winxp-md.md)] 등의 다른 시스템에서는 계층 창이 소프트웨어를 통해 하드웨어 가속 없이 렌더링됩니다.<br /><br /> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 다음과 같은 <xref:System.Windows.Window> 속성을 설정하여 계층 창을 사용할 수 있습니다.<br /><br /> -   <xref:System.Windows.Window.WindowStyle%2A> \= <xref:System.Windows.WindowStyle><br />-   <xref:System.Windows.Window.AllowsTransparency%2A> \= `true`<br />-   <xref:System.Windows.Controls.Control.Background%2A> \= <xref:System.Windows.Media.Brushes.Transparent%2A>|  
  
<a name="other_resources"></a>   
## 기타 리소스  
 다음 리소스를 사용하여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램의 성능 특성을 분석할 수 있습니다.  
  
### 그래픽 렌더링 레지스트리 설정  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 렌더링을 제어하기 위한 다음과 같은 네 가지 레지스트리 설정을 제공합니다.  
  
|설정|설명|  
|--------|--------|  
|**Disable Hardware Acceleration 옵션**|하드웨어 가속을 사용해야 하는지 여부를 지정합니다.|  
|**Maximum Multisample 값**|앤티 앨리어싱 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 콘텐츠에 대한 다중 샘플링 수준을 지정합니다.|  
|**Required Video Driver Date 설정**|2004년 11월 이전에 출시된 드라이버에 대해 하드웨어 가속을 사용하지 않을지 여부를 지정합니다.|  
|**Use Reference Rasterizer 옵션**|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 기준 래스터라이저를 사용해야 하는지 여부를 지정합니다.|  
  
 이러한 설정은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레지스트리 설정을 참조할 수 있는 외부 구성 유틸리티에서 액세스할 수 있습니다.  또한 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 레지스트리 편집기를 사용하여 직접 값에 액세스하여 이러한 설정을 만들거나 수정할 수도 있습니다.  자세한 내용은 [그래픽 렌더링 레지스트리 설정](../../../../docs/framework/wpf/graphics-multimedia/graphics-rendering-registry-settings.md)을 참조하십시오.  
  
### WPF 성능 프로파일링 도구  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 응용 프로그램의 런타임 동작을 분석하고 적용할 수 있는 성능 최적화 형식을 결정하는 데 사용할 수 있는 성능 프로파일링 도구 집합을 제공합니다.  다음 표에서는 [!INCLUDE[TLA2#tla_lhsdk](../../../../includes/tla2sharptla-lhsdk-md.md)] 도구 WPF Performance Suite에 포함된 성능 프로파일링 도구를 보여 줍니다.  
  
|도구|설명|  
|--------|--------|  
|Perforator|렌더링 동작을 분석하는 데 사용합니다.|  
|Visual Profiler|레이아웃 및 이벤트 처리 같은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 서비스의 사용을 시각적 트리의 요소별로 프로파일링하는 데 사용합니다.|  
  
 WPF Performance Suite에서는 성능 데이터에 대한 다양한 그래픽 뷰를 제공합니다.  WPF 성능 도구에 대한 자세한 내용은 [WPF 성능 제품군](../Topic/WPF%20Performance%20Suite.md)를 참조하십시오.  
  
### DirectX 진단 도구  
 [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 진단 도구 Dxdiag.exe는 [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 관련 문제를 해결할 수 있도록 도와주기 위해 설계되었습니다.  [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 진단 도구의 기본 설치 폴더는 다음과 같습니다.  
  
 `~\Windows\System32`  
  
 [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 진단 도구를 실행하면 주 창에 [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 관련 정보를 표시하고 진단하는 데 사용할 수 있는 몇 가지 탭이 표시됩니다.  예를 들어 **시스템** 탭에서는 컴퓨터에 대한 시스템 정보를 제공하고 컴퓨터에 설치된 [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 버전을 지정합니다.  
  
 ![스크린 샷: DirectX 진단 도구](../../../../docs/framework/wpf/advanced/media/directxdiagnostictool-01.png "DirectXDiagnosticTool\_01")  
DirectX 진단 도구 주 창  
  
## 참고 항목  
 <xref:System.Windows.Media.RenderCapability>   
 <xref:System.Windows.Media.RenderOptions>   
 [WPF 응용 프로그램 성능 최적화](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [WPF 성능 제품군](../Topic/WPF%20Performance%20Suite.md)   
 [그래픽 렌더링 레지스트리 설정](../../../../docs/framework/wpf/graphics-multimedia/graphics-rendering-registry-settings.md)   
 [애니메이션에 대한 유용한 정보](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)