---
title: "ClearType 레지스트리 설정 | Microsoft Docs"
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
  - "ClearType, 레지스트리 설정"
  - "입력 체계, ClearType 레지스트리 설정"
ms.assetid: 56f314bb-b30b-4f67-8492-8b8a9fa432ae
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# ClearType 레지스트리 설정
이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에 사용되는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)] 레지스트리 설정의 개요를 제공합니다.  
  
   
  
<a name="overview"></a>   
## 기술 개요  
 텍스트를 디스플레이 장치로 렌더링하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에서는 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] 기능을 사용하여 향상된 읽기 환경을 제공합니다.  [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]은 랩톱 화면, 포켓 PC 화면, 평면 모니터 등 기존의 LCD\(액정 디스플레이\)에서 보다 쉽게 텍스트를 읽을 수 있도록 지원하기 위해 [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)]에서 개발한 소프트웨어 기술입니다.  [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]은 LCD 화면의 모든 픽셀에 있는 각각의 세로 줄로 된 색 요소에 액세스하는 방식으로 작동합니다.  [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]에 대한 자세한 내용은 [ClearType 개요](../../../../docs/framework/wpf/advanced/cleartype-overview.md)를 참조하십시오.  
  
 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]으로 렌더링되는 텍스트는 다양한 디스플레이 장치에서 볼 경우 상당히 다르게 나타날 수 있습니다.  예를 들어 일부 모니터에서는 세로 줄로 된 색 요소가 일반적인 빨강, 녹색, 파랑\([!INCLUDE[TLA#tla_rgb](../../../../includes/tlasharptla-rgb-md.md)]\)의 순서가 아니라 파랑, 녹색, 빨강의 순서로 구현됩니다.  
  
 또한 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]으로 렌더링되는 텍스트는 각 개인이 지닌 색에 대한 민감도에 따라 상당히 다르게 보일 수 있습니다.  일부 사용자는 다른 사람보다 미묘한 색 차이를 더 잘 감지할 수 있습니다.  
  
 이러한 경우에는 모든 사람에게 최선의 읽기 환경을 제공하기 위해 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] 기능을 수정해야 합니다.  
  
<a name="registry_settings"></a>   
## 레지스트리 설정  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] 기능을 제어하기 위해 다음과 같은 네 가지 레지스트리 설정을 지정합니다.  
  
|설정|설명|  
|--------|--------|  
|[!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] 수준|[!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] 색 명확성의 수준을 설명합니다.|  
|감마 수준|디스플레이 장치의 픽셀 색 구성 요소 수준을 설명합니다.|  
|픽셀 구조체|디스플레이 장치의 픽셀 배치를 설명합니다.|  
|텍스트 대비 수준|표시된 텍스트의 대비 수준을 설명합니다.|  
  
 이러한 설정은 식별된 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] 레지스트리 설정을 참조할 수 있는 외부 구성 유틸리티에서 액세스할 수 있습니다.  또한 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 레지스트리 편집기를 사용하여 직접 값에 액세스하여 이러한 설정을 만들거나 수정할 수도 있습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] 레지스트리 설정이 지정되어 있지 않으면\(기본 상태\) [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램이 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 시스템 매개 변수 정보에서 글꼴 다듬기 설정을 쿼리합니다.  
  
> [!NOTE]
>  디스플레이 장치 이름을 열거하는 방법에 대한 자세한 내용은 `SystemParametersInfo` [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 함수를 참조하십시오.  
  
<a name="ClearType_level"></a>   
## ClearType 수준  
 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] 수준을 사용하면 개인의 색 민감도와 인식 정도를 기준으로 텍스트 렌더링을 조정할 수 있습니다. 사용자에 따라 최고 수준의 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]을 사용하는 텍스트 렌더링이 최상의 읽기 환경을 제공하지 못하는 경우도 있을 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] 수준은 0부터 100 사이의 정수 값이고  기본값은 100입니다. 다시 말해 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]에서는 디스플레이 장치에서 제공하는 최고 수준의 색 선 요소를 사용합니다.  반대로 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] 수준 0은 텍스트를 회색조로 렌더링합니다.  [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] 수준을 0에서 100 사이의 값으로 설정하면 개인의 색 민감도에 따라 적절한 중간 수준을 만들 수 있습니다.  
  
### 레지스트리 설정  
 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] 수준에 대한 레지스트리 설정 위치는 특정 디스플레이 장치 이름에 해당하는 개별 사용자 설정입니다.  
  
 `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 사용자의 각 디스플레이 장치 이름에 대해 `ClearTypeLevel` DWORD 값이 정의됩니다.  다음 스크린 샷에서는 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] 수준에 대한 레지스트리 편집기 설정을 보여 줍니다.  
  
 ![레지스트리 편집기의 ClearType 설정](../../../../docs/framework/wpf/advanced/media/cleartyperegistry01.png "ClearTypeRegistry01")  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에서는 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]이 있는 상태와 없는 상태 두 가지 모드로 텍스트를 렌더링합니다.  [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] 없이 텍스트를 렌더링하는 경우를 회색조 렌더링이라고 합니다.  
  
<a name="gamma_level"></a>   
## 감마 수준  
 감마 수준은 픽셀 값과 광도 간의 비선형 관계를 나타냅니다.  감마 수준 설정은 디스플레이 장치의 물리적 특성과 일치해야 합니다. 그렇지 않으면 렌더링된 출력에서 왜곡이 발생할 수 있습니다.  예를 들어 테스트가 지나치게 넓거나 좁게 나타난다거나 문자 모양의 세로 획 가장자리에 색 주름이 나타날 수 있습니다.  
  
 감마 수준은 1000에서 2200 사이의 정수 값이며  기본 수준은 1900입니다.  
  
### 레지스트리 설정  
 감마 수준에 대한 레지스트리 설정 위치는 특정 디스플레이 장치 이름에 해당하는 로컬 컴퓨터 설정입니다.  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 사용자의 각 디스플레이 장치 이름에 대해 `GammaLevel` DWORD 값이 정의됩니다.  다음 스크린 샷에서는 감마 수준에 대한 레지스트리 편집기 설정을 보여 줍니다.  
  
 ![레지스트리 편집기의 ClearType 설정](../../../../docs/framework/wpf/advanced/media/cleartyperegistry02.png "ClearTypeRegistry02")  
  
<a name="pixel_structure"></a>   
## 픽셀 구조체  
 픽셀 구조체는 디스플레이 장치를 구성하는 픽셀 형식을 설명합니다.  픽셀 구조체는 다음 세 가지 형식 중 하나로 정의됩니다.  
  
|형식|값|설명|  
|--------|-------|--------|  
|단순|0|디스플레이 장치에 픽셀 구조체가 없습니다.  즉, 각 색의 광원이 픽셀 영역에서 고르게 분산된다는 의미로, 이것을 회색조 렌더링이라고 합니다.  이것이 표준 디스플레이 장치가 작동하는 방식입니다.  [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]은 렌더링된 텍스트에 적용되지 않습니다.|  
|RGB|1|디스플레이 장치에 빨강, 녹색, 파랑의 순서로 세 개의 선을 구성하는 픽셀이 있습니다.  렌더링된 텍스트에 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]이 적용됩니다.|  
|BGR|2|디스플레이 장치에 파랑, 녹색, 빨강의 순서로 세 개의 선을 구성하는 픽셀이 있습니다.  렌더링된 텍스트에 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]이 적용됩니다.  색의 순서가 RGB 형식과는 반대입니다.|  
  
 픽셀 구조체는 0부터 2 사이의 정수 값에 해당하며  기본 수준은 평면 픽셀 구조체를 나타내는 0입니다.  
  
> [!NOTE]
>  디스플레이 장치 이름을 열거하는 방법에 대한 자세한 내용은 `EnumDisplayDevices` [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 함수를 참조하십시오.  
  
### 레지스트리 설정  
 픽셀 구조체에 대한 레지스트리 설정 위치는 특정 디스플레이 장치 이름에 해당하는 로컬 컴퓨터 설정입니다.  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 사용자의 각 디스플레이 장치 이름에 대해 `PixelStructure` DWORD 값이 정의됩니다.  다음 스크린 샷에서는 픽셀 구조체에 대한 레지스트리 편집기 설정을 보여 줍니다.  
  
 ![레지스트리 편집기의 ClearType 설정](../../../../docs/framework/wpf/advanced/media/cleartyperegistry02.png "ClearTypeRegistry02")  
  
<a name="text_contrast_level"></a>   
## 텍스트 대비 수준  
 텍스트 대비 수준을 사용하면 문자 모양의 획 너비를 기준으로 텍스트 렌더링을 조정할 수 있습니다.  텍스트 대비 수준은 0에서 6 사이의 정수 값이며 값이 클수록 획이 넓어집니다.  기본 수준은 1입니다.  
  
### 레지스트리 설정  
 텍스트 대비 수준에 대한 레지스트리 설정 위치는 특정 디스플레이 장치 이름에 해당하는 개별 사용자 설정입니다.  
  
 `HKEY_CURRENT_USER\Software\Microsoft\Avalon.Graphics\<displayName>`  
  
 사용자의 각 디스플레이 장치 이름에 대해 `TextContrastLevel` DWORD 값이 정의됩니다.  다음 스크린 샷에서는 텍스트 대비 수준에 대한 레지스트리 편집기 설정을 보여 줍니다.  
  
 ![레지스트리 편집기의 ClearType 설정](../../../../docs/framework/wpf/advanced/media/cleartyperegistry01.png "ClearTypeRegistry01")  
  
## 참고 항목  
 [ClearType 개요](../../../../docs/framework/wpf/advanced/cleartype-overview.md)   
 [ClearType Antialiasing](_win32_ClearType_Antialiasing)