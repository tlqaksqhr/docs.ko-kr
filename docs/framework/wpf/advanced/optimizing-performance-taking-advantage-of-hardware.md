---
title: "성능 최적화: 하드웨어 이용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [WPF], performance
- hardware rendering pipeline [WPF]
- rendering tiers [WPF]
- graphics rendering tiers [WPF]
- graphics [WPF], rendering tiers
- software rendering pipeline [WPF]
ms.assetid: bfb89bae-7aab-4cac-a26c-a956eda8fce2
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 55c9482ecb540baab3ddd57ca9350fd7265ac251
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="optimizing-performance-taking-advantage-of-hardware"></a>성능 최적화: 하드웨어 이용
내부 아키텍처 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 에 두 개의 렌더링 파이프라인, 하드웨어 및 소프트웨어. 이 항목에서는 응용 프로그램의 성능 최적화에 대 한 결정을 내릴 수 있도록 이러한 렌더링 파이프라인에 대 한 정보를 제공 합니다.  
  
## <a name="hardware-rendering-pipeline"></a>하드웨어 렌더링 파이프라인  
 결정 하는 데 가장 중요 한 요소 중 하나 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 성능 렌더링 범위 된다는 점입니다-픽셀 수가 클수록 성능 비용을 렌더링 해야 합니다. 그러나에 있는 렌더링이 더를 오프 로드할 수는 [!INCLUDE[TLA#tla_gpu](../../../../includes/tlasharptla-gpu-md.md)], 성능 이점이 더를 얻을 수 있습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램 하드웨어 렌더링 파이프라인은 완전히 활용 [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)] 기능을 지 원하는 최소 하드웨어에서 [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)] 버전 7.0입니다. 추가 최적화가 지 원하는 하드웨어에 얻을 수 [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)] 버전 7.0 및 PixelShader 2.0 + 기능입니다.  
  
## <a name="software-rendering-pipeline"></a>소프트웨어 렌더링 파이프라인  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 소프트웨어 렌더링 파이프라인은 전적으로 CPU 사용량이 합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]SSE 및 SSE2 명령 활용 최적화, 완전 한 기능의 소프트웨어 래스터를 구현 하는 CPU에 설정 합니다. 소프트웨어 대체 (fallback)은 언제 든 지 하드웨어 렌더링 파이프라인을 사용 하 여 응용 프로그램의 기능을 렌더링할 수 없으면 원활 합니다.  
  
 가장 큰 성능 문제 렌더링 소프트웨어 모드에서 렌더링 하는 픽셀 수로 정의 된 비율 채우기와 관련 된 경우 발생 합니다. 소프트웨어 렌더링 모드에서 성능에 대 한 관심이 경우 픽셀을 다시 그리면 시간 수를 최소화 하려고 합니다. 예를 들어 위에 약간 투명 한 이미지를 렌더링 합니다, 파란색 배경의 응용 프로그램이 있는 경우 응용 프로그램을 두 번의 픽셀의 모든 렌더링 됩니다. 결과적으로, 걸리는 두 번 파란색 배경만 갖는 경우 보다 이미지와 함께 응용 프로그램을 렌더링 하는 데 소요 되는입니다.  
  
### <a name="graphics-rendering-tiers"></a>그래픽 렌더링 계층  
 응용 프로그램에서 실행 하는 하드웨어 구성을 예측 하기가 매우 어려울 수 있습니다. 그러나 다음 고려 하면 응용 프로그램을 원활 하 게 기능을 전환할 다른 하드웨어에서 실행 하는 경우 각 다른 하드웨어 구성에 완전히 활용을 수행할 수 있도록 하는 디자인 하는 것이 좋습니다.  
  
 이 작업을 수행할 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 런타임에 시스템의 그래픽 기능을 확인 하는 기능을 제공 합니다. 세 개의 기능 계층을 렌더링 중 하나로 비디오 카드를 범주화 하 여 그래픽 기능이 결정 됩니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]노출 된 [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] 렌더링 기능 계층을 쿼리 하는 응용 프로그램을 허용 하 합니다. 그러면 응용 프로그램 하드웨어에서 지 원하는 렌더링 계층에 따라 실행 시 서로 다른 코드 경로 수행할 수 있습니다.  
  
 렌더링 계층 수준에 가장 큰 영향을 미치는 그래픽 하드웨어 기능은 다음과 같습니다.  
  
-   **비디오 RAM** 그래픽 하드웨어의 비디오 메모리 양에 따라 그래픽을 합성하는 데 사용할 수 있는 버퍼의 크기와 수를 결정합니다.  
  
-   **픽셀 셰이더** 픽셀 셰이더는 픽셀별 미치는 영향을 계산하는 그래픽 처리 함수입니다. 표시된 그래픽의 해상도에 따라 표시 프레임별로 수백만 픽셀을 처리해야 할 수도 있습니다.  
  
-   **꼭짓점 셰이더** 꼭짓점 셰이더는 개체의 꼭짓점 데이터에서 수학 연산을 수행하는 그래픽 처리 함수입니다.  
  
-   **여러 질감 지원** 여러 질감 지원은 3D 그래픽 개체에서 혼합 작업 중에 두 개 이상의 개별 질감을 적용할 수 있는 기능을 나타냅니다. 여러 질감 지원 정도는 그래픽 하드웨어의 여러 질감 단위 수에 따라 결정됩니다.  
  
 픽셀 셰이더, 꼭 짓 점 셰이더 및 질감 기능 하는 데 특정 정의 [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 에서 다양 한 렌더링 계층을 정의 하는 데 사용 되는 버전 수준이 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]합니다.  
  
 그래픽 하드웨어 기능에 따라 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램의 렌더링 기능이 결정됩니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 시스템에서는 다음 세 개의 렌더링 계층을 정의합니다.  
  
-   **렌더링 계층 0** 그래픽 하드웨어 가속이 없습니다. [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 버전 7.0 보다 낮은 버전 수준입니다.  
  
-   **계층 1 렌더링** 부분 그래픽 하드웨어 가속이 적용 합니다. [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 버전 수준 보다 크거나 버전 7.0, 및 **미만** 버전 9.0 보다 합니다.  
  
-   **렌더링 계층 2** 대부분의 그래픽 기능에서는 그래픽 하드웨어 가속을 사용합니다. [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 버전 수준은 버전 9.0 이상입니다.  
  
 대 한 자세한 내용은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 참조 계층을 렌더링, [그래픽 렌더링 계층](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [WPF 응용 프로그램 성능 최적화](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [응용 프로그램 성능 계획](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
 [레이아웃 및 디자인](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [2차원 그래픽 및 이미징](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [개체 동작](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [응용 프로그램 리소스](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
 [텍스트](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [데이터 바인딩](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [기타 성능 권장 사항](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)
