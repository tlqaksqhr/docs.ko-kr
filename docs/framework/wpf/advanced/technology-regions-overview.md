---
title: 기술 영역 개요
ms.date: 03/30/2017
helpviewer_keywords:
- window regions [WPF]
- Win32 code [WPF], WPF interoperation
- Win32 code [WPF], airspace
- airspace [WPF]
- interoperability [WPF], airspace
- Win32 code [WPF], window regions
ms.assetid: b7cc350f-b9e2-48b1-be14-60f3d853222e
ms.openlocfilehash: 2fef7a0f3b4e01d7ce29baeb70fbdd7ea37f2c89
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548846"
---
# <a name="technology-regions-overview"></a>기술 영역 개요
응용 프로그램에 WPF, Win32 또는 DirectX와 같은 여러 프레젠테이션 기술이 사용되는 경우 이러한 기술은 공통 최상위 창에서 렌더링 영역을 공유해야 합니다. 이 항목에서는 WPF 상호 운용 응용 프로그램에 대한 프레젠테이션과 입력에 영향을 미칠 수 있는 문제를 설명합니다.  
  
## <a name="regions"></a>영역  
 최상위 창에서 상호 운용 응용 프로그램의 기술 중 하나로 구성되는 각 HWND에 자체 영역("에어스페이스"라고도 함)이 포함되도록 개념화할 수 있습니다. 창 내의 각 픽셀은 해당 HWND의 영역을 형성하는 정확히 하나의 HWND에 속합니다. 엄격히 말하면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] HWND가 두 개 이상 있는 경우 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 영역도 두 개 이상 있지만 이 설명을 위해 하나만 있다고 가정할 수 있습니다. 영역은 응용 프로그램 수명 중에 해당 픽셀 위에 렌더링되는 모든 계층 또는 기타 창이 같은 렌더링 수준 기술에 포함되어야 함을 의미합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 픽셀을 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 위에 렌더링하려고 시도하면 원하지 않는 결과가 발생하고 이 시도는 상호 운용 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]를 통해 가능한 한 많이 허용되지 않습니다.  
  
### <a name="region-examples"></a>영역 예제  
 다음 그림에서는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 및 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 혼합하는 응용 프로그램을 보여 줍니다. 각 기술은 자체적인 별도의 겹치지 않는 픽셀 집합을 사용하고 영역 문제가 없습니다.  
  
 ![에어스페이스 문제가 없는 창](../../../../docs/framework/wpf/advanced/media/migrationinteroparchitectarticle01.png "MigrationInteropArchitectArticle01")  
  
 이 응용 프로그램이 마우스 포인터 위치를 사용하여 이러한 세 개의 영역 위에 렌더링할 애니메이션을 만든다고 가정해 봅니다. 애니메이션 자체에 응답 가능한 기술이 무엇이든 관계없이 해당 기술은 다른 두 기술의 영역을 침해합니다. 다음 그림에서는 Win32 영역 위에 WPF 원을 렌더링하는 시도를 보여 줍니다.  
  
 ![Interop 다이어그램](../../../../docs/framework/wpf/advanced/media/migrationinteroparchitectarticle02.png "MigrationInteropArchitectArticle02")  
  
 또 다른 침해는 서로 다른 기술 사이에 투명도/알파 블렌딩을 사용하려는 경우입니다.  다음 그림에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 상자는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 및 [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 영역을 침해합니다. 해당 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 상자의 픽셀은 반투명하므로 [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 및 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]가 둘 다 공동으로 이러한 픽셀을 소유해야 하지만 이는 불가능합니다.  따라서 이는 또 다른 침해이며 빌드될 수 없습니다.  
  
 ![Interop 다이어그램](../../../../docs/framework/wpf/advanced/media/migrationinteroparchitectarticle03.png "MigrationInteropArchitectArticle03")  
  
 이전 세 개의 예제에서는 사각형 영역을 사용했으나 다른 모양이 가능합니다.  예를 들어 영역에 구멍이 있을 수 있습니다. 다음 그림에서는 사각형 구멍이 있는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 영역을 보여 줍니다. 구멍의 크기는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 및 [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 영역이 결합된 크기입니다.  
  
 ![Interop 다이어그램](../../../../docs/framework/wpf/advanced/media/migrationinteroparchitectarticle04.png "MigrationInteropArchitectArticle04")  
  
 영역은 완전히 사각형이 아니거나 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] HRGN(영역)으로 설명 가능한 모양일 수도 있습니다.  
  
 ![Interop 다이어그램](../../../../docs/framework/wpf/advanced/media/migrationinteroparchitectarticle05.png "MigrationInteropArchitectArticle05")  
  
## <a name="transparency-and-top-level-windows"></a>투명도 및 최상위 창  
 Windows의 창 관리자는 실제로 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] HWND만 처리합니다. 따라서 모든 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window> HWND 됩니다. <xref:System.Windows.Window> HWND 어떤 HWND에 대 한 일반 규칙을 준수 해야 합니다. 해당 HWND 내에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 코드는 전체 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]가 지원하는 모든 작업을 수행할 수 있습니다. 하지만 데스크톱에 있는 다른 HWND에 대한 상호 작용의 경우 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 처리 및 렌더링 규칙을 따라야 합니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]를 사용하여 사각형이 아닌 창을 지원합니다(사각형이 아닌 창인 경우 HRGN 및 픽셀별 알파인 경우 겹쳐진 창).  
  
 상수 알파 및 색 키는 지원되지 않습니다.  [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창 겹침 기능은 플랫폼에 따라 달라집니다.  
  
 창 겹침의 경우 창의 모든 픽셀에 적용할 알파 값을 지정하여 전체 창을 반투명하게 만들 수 있습니다.  실제로 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]는 픽셀별 알파를 지원하지만, 이 모드에서는 대화 상자, 드롭다운을 포함된 모든 자식 HWND를 직접 그려야 하므로 이 기술은 실제 프로그램에서 사용하기 매우 어렵습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 HRGN을 지원하지만 이 기능에 대한 관리되는 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]가 없습니다. 플랫폼을 사용할 수 있습니다 호출 및 <xref:System.Windows.Interop.HwndSource> 관련 호출할 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]합니다. 자세한 내용은 [관리 코드에서 네이티브 함수 호출](/cpp/dotnet/calling-native-functions-from-managed-code)을 참조하세요.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 창 겹침에는 다양한 운영 체제에 대한 여러 가지 기능이 포함됩니다. 이는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 렌더링에 [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)]를 사용하고, 겹쳐진 창은 기본적으로 [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 렌더링이 아닌 [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] 렌더링용으로 디자인되었기 때문입니다.  
  
-   [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 [!INCLUDE[TLA#tla_longhorn](../../../../includes/tlasharptla-longhorn-md.md)] 이상에서 하드웨어 가속 창 겹침을 지원합니다. [!INCLUDE[TLA2#tla_winxp](../../../../includes/tla2sharptla-winxp-md.md)]에서 하드웨어 가속 창 겹침을 사용하려면 [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)]의 지원이 필요하므로 기능은 해당 컴퓨터의 [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)] 버전에 따라 달라집니다.  
  
-   [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 투명색 키를 지원하지 않습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 특히 렌더링이 하드웨어 가속될 경우 요청한 정확한 색을 렌더링하도록 보장할 수 없기 때문입니다.  
  
-   응용 프로그램이 [!INCLUDE[TLA2#tla_winxp](../../../../includes/tla2sharptla-winxp-md.md)]에서 실행될 경우 [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 응용 프로그램이 렌더링될 때 [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 화면 위의 겹쳐진 창이 깜박입니다.  실제 렌더링 시퀀스는 [!INCLUDE[TLA#tla_gdi](../../../../includes/tlasharptla-gdi-md.md)]가 겹쳐진 창을 숨기고 나서, [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)]가 그린 다음, [!INCLUDE[TLA#tla_gdi](../../../../includes/tlasharptla-gdi-md.md)]가 겹쳐진 창을 되돌리는 것입니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]가 아닌 겹쳐진 창에는 이 제한 사항이 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [WPF 및 Win32 상호 운용성](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)  
 [연습: Win32에서 WPF 시계 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-clock-in-win32.md)  
 [WPF에서 Win32 콘텐츠 호스트](../../../../docs/framework/wpf/advanced/hosting-win32-content-in-wpf.md)
