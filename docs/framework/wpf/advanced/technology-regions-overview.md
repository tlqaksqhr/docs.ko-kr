---
title: "기술 영역 개요 | Microsoft Docs"
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
  - "에어스페이스"
  - "상호 운용성[WPF], 에어스페이스"
  - "Win32 코드, 에어스페이스"
  - "Win32 코드, 창 영역"
  - "Win32 코드, WPF 상호 운용"
  - "창 영역"
ms.assetid: b7cc350f-b9e2-48b1-be14-60f3d853222e
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 기술 영역 개요
WPF, Win32 또는 DirectX와 같이 응용 프로그램에서 여러 프레젠테이션 기술이 사용되는 경우 각 프레젠테이션 기술은 공통의 최상위 창에서 렌더링 영역을 공유해야 합니다.  이 항목에서는 프레젠테이션과 WPF 상호 운용 응용 프로그램의 입력에 영향을 줄 수 있는 사항에 대해 설명합니다.  
  
## 영역  
 최상위 창에서 상호 운용 응용 프로그램의 기술 중 하나를 구성하는 각 HWND에는 "에어스페이스"라는 고유한 영역이 있는 것으로 개념화할 수 있습니다.  창 내의 각 픽셀은 정확히 한 개의 HWND에만 포함되어 해당 HWND의 영역을 구성합니다.  엄밀히 말하자면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] HWND가 두 개 이상 있으면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 영역도 두 개 이상 존재하지만 설명을 쉽게 하기 위해 HWND가 한 개만 있다고 가정할 수 있습니다.  영역이 있다는 것은 응용 프로그램의 수명 동안 특정 픽셀 위에 렌더링을 시도하는 모든 계층 또는 다른 창이 반드시 동일한 렌더링 수준 기술의 일부여야 함을 의미합니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 픽셀을 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]에서 렌더링하려고 하면 예기치 않은 결과가 나타나며 이와 같은 작업은 상호 운용 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]에서 가능한 한 제한됩니다.  
  
### 영역 예제  
 다음 그림에서는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 및 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 함께 사용하는 응용 프로그램을 보여 줍니다.  이 경우 각 기술은 서로 겹치지 않는 고유한 픽셀 집합을 사용하기 때문에 영역 문제가 없습니다.  
  
 ![에어스페이스 문제가 없는 창](../../../../docs/framework/wpf/advanced/media/migrationinteroparchitectarticle01.png "MigrationInteropArchitectArticle01")  
  
 이 응용 프로그램에서 마우스 포인터 위치를 사용하여 이러한 세 영역 중 임의의 영역에 렌더링을 시도하는 애니메이션을 만든다면  애니메이션 자체를 구현하는 데 사용된 기술이 무엇이든 관계없이 해당 기술은 다른 두 기술의 영역을 침범하게 됩니다.  다음 그림에서는 Win32 영역에 WPF 원을 렌더링하려고 하는 예를 보여 줍니다.  
  
 ![Interop 다이어그램](../../../../docs/framework/wpf/advanced/media/migrationinteroparchitectarticle02.png "MigrationInteropArchitectArticle02")  
  
 서로 다른 기술 간에 투명 효과\/알파 혼합을 사용하려는 경우에도 영역을 침범할 수 있습니다.  다음 그림에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 상자가 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 및 [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 영역을 침범하는 예를 보여 줍니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 상자의 픽셀은 반투명이기 때문에 [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)]와 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]가 공동으로 소유해야 하지만 이는 불가능합니다.  따라서 이 예의 경우도 영역이 침범되므로 구현할 수 없습니다.  
  
 ![Interop 다이어그램](../../../../docs/framework/wpf/advanced/media/migrationinteroparchitectarticle03.png "MigrationInteropArchitectArticle03")  
  
 앞의 세 가지 예에서는 사각형 영역을 예로 들었지만 다른 모양이 사용될 수도 있습니다.  예를 들어 영역에는 빈 영역이 있을 수 있습니다.  다음 그림에서는 사각형의 빈 영역이 있는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 영역을 보여 줍니다. 이 빈 영역의 크기는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 및 [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 영역을 결합한 크기에 해당합니다.  
  
 ![Interop 다이어그램](../../../../docs/framework/wpf/advanced/media/migrationinteroparchitectarticle04.png "MigrationInteropArchitectArticle04")  
  
 또한 영역은 완전히 사각형이 아닐 수도 있으며 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] HRGN\(영역\)으로 나타낼 수 있는 모든 모양이 될 수 있습니다.  
  
 ![Interop 다이어그램](../../../../docs/framework/wpf/advanced/media/migrationinteroparchitectarticle05.png "MigrationInteropArchitectArticle05")  
  
## 투명도 및 최상위 창  
 Windows의 창 관리자는 실제로는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] HWND만 처리합니다.  따라서 모든 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window>는 HWND입니다.  이에 따라 <xref:System.Windows.Window> HWND는 모든 HWND에 대한 일반적인 규칙을 준수해야 합니다.  HWND 내에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 코드로 전체 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]에서 지원하는 모든 작업을 수행할 수 있지만  데스크톱의 다른 HWND와 상호 작용하는 데 있어서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 처리 및 렌더링 규칙을 준수해야 합니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]를 사용하여 사각형이 아닌 창을 지원합니다. 즉, 사각형이 아닌 창에 대해서는 HRGN을 사용하고, 픽셀별 알파를 위해서는 계층 창을 사용합니다.  
  
 상수 알파 및 색상 키는 지원되지 않으며  [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 계층 창 기능은 플랫폼에 따라 다르게 지원됩니다.  
  
 계층 창을 사용하면 창의 모든 픽셀에 적용할 알파 값을 지정하여 창 전체를 반투명하게 만들 수 있습니다.  [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]에서 픽셀별 알파를 지원하기는 하지만 이 모드에서는 대화 상자와 드롭다운을 포함하여 모든 자식 HWND를 직접 그려야 하기 때문에 실제 프로그램에서는 사용하기 매우 어렵습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 HRGN을 지원하지만 이 기능에 대한 관리되는 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]가 없습니다.  이 경우 P\/Invoke 호출과 <xref:System.Windows.Interop.HwndSource>를 사용하여 적절한 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]를 호출할 수 있습니다.  자세한 내용은 [관리 코드에서 네이티브 함수 호출](../Topic/Calling%20Native%20Functions%20from%20Managed%20Code.md)을 참조하십시오.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 계층 창의 기능은 운영 체제에 따라 다릅니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 렌더링에 [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)]를 사용하는 반면 계층 창은 [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 렌더링이 아니라 주로 [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] 렌더링용으로 디자인되었기 때문입니다.  
  
-   [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 [!INCLUDE[TLA#tla_longhorn](../../../../includes/tlasharptla-longhorn-md.md)] 이상에서 하드웨어 가속 계층 창을 지원합니다.  [!INCLUDE[TLA2#tla_winxp](../../../../includes/tla2sharptla-winxp-md.md)]의 경우에는 하드웨어 가속 계층 창에 [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)]가 필요하기 때문에 각 컴퓨터의 [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)] 버전에 따라 사용할 수 있는 기능이 달라집니다.  
  
-   [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 투명 색상 키를 지원하지 않습니다. 그 이유는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 특히 하드웨어 가속 렌더링을 사용하는 경우 요청된 색을 정확하게 렌더링하지 못할 수 있기 때문입니다.  
  
-   응용 프로그램이 [!INCLUDE[TLA2#tla_winxp](../../../../includes/tla2sharptla-winxp-md.md)]에서 실행되는 경우, [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 화면의 맨 위에 있는 계층 창은 [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 응용 프로그램이 렌더링되는 동안 깜빡입니다.  실제로 렌더링은 [!INCLUDE[TLA#tla_gdi](../../../../includes/tlasharptla-gdi-md.md)]에서 계층 창을 숨기고 [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)]에서 그린 다음 [!INCLUDE[TLA#tla_gdi](../../../../includes/tlasharptla-gdi-md.md)]에서 계층 창을 다시 표시하는 순서로 이루어집니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]가 아닌 계층 창의 경우에도 이러한 제한이 적용됩니다.  
  
## 참고 항목  
 [WPF 및 Win32 상호 운용성](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)   
 [연습: Win32에서 WPF 시계 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-clock-in-win32.md)   
 [WPF에서 Win32 콘텐츠 호스팅](../../../../docs/framework/wpf/advanced/hosting-win32-content-in-wpf.md)