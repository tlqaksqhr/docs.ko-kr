---
title: "그래픽 렌더링 레지스트리 설정 | Microsoft Docs"
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
  - "그래픽[WPF], 렌더링"
  - "그래픽 렌더링"
  - "그래픽 렌더링, 레지스트리 설정"
  - "그래픽 렌더링, 문제 해결"
  - "그래픽 렌더링 문제 해결"
ms.assetid: f4b41b42-327d-407c-b398-3ed5f505df8b
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# 그래픽 렌더링 레지스트리 설정
이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에 영향을 주는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 그래픽 렌더링 레지스트리 설정의 개요를 제공합니다.  
  
   
  
<a name="overview"></a>   
## 그래픽 렌더링 레지스트리 설정을 사용하는 경우  
 이러한 레지스트리 설정은 문제 해결, 디버깅 및 제품 지원 목적을 위해 제공됩니다.  레지스트리를 변경하면 모든 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에 영향을 주기 때문에 응용 프로그램에서 이러한 레지스트리 키를 자동으로 또는 설치 도중에 변경해서는 안 됩니다.  
  
<a name="xpdmandwddm"></a>   
## XPDM 및 WDDM  
 일부 그래픽 렌더링 레지스트리 설정은 비디오 카드에서 XPDM 드라이버를 사용하는지 아니면 WDDM 드라이버를 사용하는지 여부에 따라 다른 기본값을 가집니다.  XPDM은 [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] 디스플레이 드라이버 모델이고 WDDM은 Windows 디스플레이 드라이버 모델입니다.  WDDM은 [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] 및 [!INCLUDE[win7](../../../../includes/win7-md.md)]을 실행 중인 컴퓨터에서 사용할 수 있습니다.  XPDM은 [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)], [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] 및 [!INCLUDE[TLA#tla_winnetsvrfam](../../../../includes/tlasharptla-winnetsvrfam-md.md)]을 실행 중인 컴퓨터에서 사용할 수 있습니다.  WDDM에 대한 자세한 내용은 [Windows Vista Display Driver Model Design Guide](http://go.microsoft.com/fwlink/?LinkId=178394)를 참조하십시오.  
  
<a name="registry_settings"></a>   
## 레지스트리 설정  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 렌더링을 제어하기 위한 다음과 같은 네 가지 레지스트리 설정을 제공합니다.  
  
|설정|설명|  
|--------|--------|  
|**Disable Hardware Acceleration 옵션**|하드웨어 가속을 사용해야 하는지 여부를 지정합니다.|  
|**Maximum Multisample 값**|앤티 앨리어싱 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 콘텐츠에 대한 다중 샘플링 수준을 지정합니다.|  
|**Required Video Driver Date 설정**|2004년 11월 이전에 출시된 드라이버에 대해 하드웨어 가속을 사용하지 않을지 여부를 지정합니다.|  
|**Use Reference Rasterizer 옵션**|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 기준 래스터라이저를 사용해야 하는지 여부를 지정합니다.|  
  
 이러한 설정은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레지스트리 설정을 참조할 수 있는 외부 구성 유틸리티에서 액세스할 수 있습니다.  또한 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 레지스트리 편집기를 사용하여 직접 값에 액세스하여 이러한 설정을 만들거나 수정할 수도 있습니다.  
  
<a name="disablehardwareacceleration"></a>   
## Disable Hardware Acceleration 옵션  
  
|레지스트리 키|값 형식|  
|-------------|----------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\DisableHWAcceleration`|DWORD|  
  
 **Disable Hardware Acceleration 옵션**을 사용하면 디버깅 및 테스트 목적을 위해 하드웨어 가속을 해제할 수 있습니다.  응용 프로그램에서 렌더링 아티팩트가 표시될 경우 하드웨어 가속을 해제해 보십시오.  아티팩트가 사라질 경우 비디오 드라이버에 문제가 있는 것일 수 있습니다.  
  
 **Disable Hardware Acceleration 옵션**은 0 또는 1인 DWORD 값입니다.  값이 1이면 하드웨어 가속이 사용되지 않습니다.  값이 0이면 시스템에서 하드웨어 가속 요구 사항을 충족할 경우 하드웨어 가속이 사용됩니다. 자세한 내용은 [그래픽 렌더링 계층](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md)을 참조하십시오.  
  
<a name="maxmultisample"></a>   
## Maximum Multisample 값  
  
|레지스트리 키|값 형식|  
|-------------|----------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\MaxMultisampleType`|DWORD|  
  
 **Maximum Multisample 값**을 사용하면 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 콘텐츠의 최대 앤티 앨리어싱 양을 조정할 수 있습니다.  이 수준을 사용하여 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 앤티 앨리어싱을 [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)]에서 사용하지 않도록 설정하거나 [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)]에서 사용하도록 설정합니다.  
  
 **maximum multisample 값**은 범위가 0부터 16까지인 DWORD 값입니다.  값 0은 3차원 콘텐츠의 다중 샘플 앤티 앨리어싱을 사용하지 않도록 설정하고 값 16은 비디오 카드에서 지원할 경우 최대 16배의 다중 샘플 앤티 앨리어싱 사용을 시도합니다.  XPDM 드라이버를 사용하는 컴퓨터에서 이 레지스트리 키 값을 설정하면 응용 프로그램에서 많은 양의 추가 비디오 메모리를 사용하고 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 렌더링 성능이 저하되며 렌더링 오류 및 안정성 문제가 발생할 수 있습니다.  
  
 이 레지스트리 키가 설정되지 않은 경우 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 기본값은 XPDM 드라이버의 경우 0이고 WDDM 드라이버의 경우 4입니다.  
  
<a name="requiredvideodriverdatesetting"></a>   
## Required Video Driver Date 설정  
  
|레지스트리 키|값 형식|  
|-------------|----------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\RequiredVideoDriverDate`|String|  
  
 2004년 11월에 [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)]는 새 버전의 드라이버 테스트 지침을 출시했습니다. 이 날짜 이후로 작성된 드라이버는 향상된 안정성을 제공합니다.  기본적으로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 이러한 드라이버에 대해 하드웨어 가속 파이프라인을 사용하며 이 날짜 이전에 게시된 XPDM 드라이버의 경우 소프트웨어 렌더링으로 대체\(fallback\)됩니다.  
  
 **Required Video Driver Date 설정**을 사용하면 XPDM 드라이버의 대체 최소 날짜를 지정할 수 있습니다.  사용하는 비디오 드라이버가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 지원하기에 충분히 안정적이라는 것이 확실한 경우에만 2004년 11월 이전의 날짜를 지정해야 합니다.  
  
 필수 비디오 드라이버 설정은 다음 형식의 문자열을 가집니다.  
  
||  
|-|  
|*YYYY* `/` *MM* `/` *DD*|  
  
 여기서 *YYYY*는 네 자리 연도이고 *MM*은 두 자리 월이며 *DD*는 두 자리 일입니다.  이 값이 설정되지 않은 경우 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 2004년 11월을 필수 비디오 드라이버 날짜로 사용합니다.  
  
<a name="usereferencerasterizeroption"></a>   
## Use Reference Rasterizer 옵션  
  
|레지스트리 키|값 형식|  
|-------------|----------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\UseReferenceRasterizer`|DWORD|  
  
 **Use Reference Rasterizer 옵션**을 사용하면 디버깅을 위해 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]가 시뮬레이션된 하드웨어 렌더링 모두가 되도록 강제 적용할 수 있습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 하드웨어 모드가 되지만 실제 하드웨어 장치 대신에 [!INCLUDE[TLA#tla_d3d](../../../../includes/tlasharptla-d3d-md.md)] 기준 소프트웨어 래스터라이저인 d3dref9.dll을 사용합니다.  
  
 기준 래스터라이저는 매우 느리지만 드라이버 문제에 의한 렌더링 문제를 방지하기 위해 비디오 드라이버를 무시합니다.  이러한 이유 때문에 기준 래스터라이저를 사용하여 렌더링 문제가 비디오 드라이버에 의한 것인지 확인할 수 있습니다.  d3dref9.dll 파일은 시스템 경로의 위치 또는 응용 프로그램의 로컬 디렉터리와 같이 응용 프로그램이 액세스할 수 있는 위치에 있어야 합니다.  
  
 **Use Reference Rasterizer 옵션**은 DWORD 값을 가집니다.  값 0은 기준 래스터라이저가 사용되지 않는다는 것을 나타냅니다.  0이 아닌 다른 값은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 기준 래스터라이저를 사용하도록 강제 적용합니다.  
  
## 참고 항목  
 [그래픽 렌더링 계층](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md)   
 [WPF 그래픽 렌더링 개요](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)