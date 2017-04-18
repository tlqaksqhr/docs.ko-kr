---
title: "성능 최적화: 하드웨어 이용 | Microsoft Docs"
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
  - "하드웨어 렌더링 파이프라인"
  - "렌더링 계층"
  - "소프트웨어 렌더링 파이프라인"
ms.assetid: bfb89bae-7aab-4cac-a26c-a956eda8fce2
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 성능 최적화: 하드웨어 이용
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 내부 아키텍처에는 두 개의 렌더링 파이프라인인 하드웨어와 소프트웨어가 있습니다.  이 항목에서는 응용 프로그램의 성능 최적화에 대한 결정을 내리는 데 도움이 되도록 이러한 렌더링 파이프라인에 대한 정보를 제공합니다.  
  
## 하드웨어 렌더링 파이프라인  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 성능을 결정하는 데 있어 가장 중요한 요소 중 하나는 렌더링 바인딩되어 있다는 점이며 이는 렌더링할 픽셀이 많을수록 성능 비용이 더 커집니다.  하지만 [!INCLUDE[TLA#tla_gpu](../../../../includes/tlasharptla-gpu-md.md)]에 오프로드할 수 있는 렌더링이 더 많을수록 얻을 수 있는 성능 이점이 더 커집니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램 하드웨어 렌더링 파이프라인은 최소한의 [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)] 버전 7.0을 지원하는 하드웨어에서 [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)] 기능을 최대한 활용합니다.  [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)] 버전 7.0 및 PixelShader 2.0\+ 기능을 지원하는 하드웨어에서 추가 최적화가 가능합니다.  
  
## 소프트웨어 렌더링 파이프라인  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 소프트웨어 렌더링 파이프라인은 전적으로 CPU 바인딩됩니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 CPU의 SSE 및 SSE2 명령 집합을 활용하여 최적화된, 완전한 기능의 소프트웨어 래스터라이저를 구현합니다.  하드웨어 렌더링 파이프라인을 사용하여 응용 프로그램 기능을 렌더링할 수 없을 때 소프트웨어로 대체\(fallback\)하면 원활하게 렌더링됩니다.  
  
 소프트웨어 모드에서 렌더링할 때 발생할 수 있는 가장 큰 성능 문제는 렌더링하고 있는 픽셀 수로 정의되는 비율 채우기와 관련이 있습니다.  소프트웨어 렌더링 모드에서의 성능을 고려해야 할 경우 픽셀이 다시 그려지는 횟수를 최소화하십시오.  예를 들어 파란색 배경의 응용 프로그램이 있고 해당 응용 프로그램에서 그 위에 있는 약간 투명한 이미지를 렌더링하는 경우 응용 프로그램의 모든 픽셀을 두 번 렌더링합니다.  따라서 파란색 배경만 있는 경우보다 이미지가 있는 응용 프로그램을 렌더링하는 데 두 배가 더 걸립니다.  
  
### 그래픽 렌더링 계층  
 응용 프로그램이 실행될 하드웨어 구성을 예측하기가 매우 어려울 수 있습니다.  하지만 다른 하드웨어에서 실행될 때 응용 프로그램에서 다양한 하드웨어 구성을 각각 활용할 수 있도록 원활하게 기능을 전환할 수 있게 해주는 디자인을 고려해볼 수 있습니다.  
  
 이를 위해 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 런타임에 시스템의 그래픽 기능을 확인하는 기능을 제공합니다.  그래픽 기능은 세 개의 렌더링 기능 계층 중 하나로 비디오 카드를 범주화하여 결정됩니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 응용 프로그램에서 렌더링 기능 계층을 쿼리할 수 있게 해 주는 [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)]를 노출합니다.  그러면 런타임에 응용 프로그램에서 하드웨어가 지원하는 렌더링 계층에 따라 다른 코드 경로를 사용할 수 있습니다.  
  
 렌더링 계층 수준에 가장 큰 영향을 주는 그래픽 하드웨어 기능은 다음과 같습니다.  
  
-   **비디오 RAM** \- 그래픽 하드웨어의 비디오 메모리 용량에 따라 그래픽 합성에 사용할 수 있는 버퍼의 크기와 수가 결정됩니다.  
  
-   **픽셀 셰이더** \- 픽셀 셰이더는 픽셀 단위로 효과를 계산하는 그래픽 처리 기능입니다.  표시된 그래픽의 해상도에 따라 표시 프레임별로 수백만 개의 픽셀을 처리해야 하는 경우도 있습니다.  
  
-   **꼭짓점 셰이더** \- 꼭짓점 셰이더는 개체의 꼭짓점 데이터에 대한 수학 연산을 수행하는 그래픽 처리 기능입니다.  
  
-   **다중 질감 지원** \- 다중 질감 지원은 3D 그래픽 개체에 대한 혼합 연산을 수행하는 동안 두 개 이상의 개별 질감을 적용하는 기능을 의미합니다.  여러 질감 지원의 수준은 그래픽 하드웨어의 여러 질감 단위 수에 따라 결정됩니다.  
  
 픽셀 셰이더, 꼭짓점 셰이더 및 다중 질감 기능은 특정 [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 버전 수준을 정의하는 데 사용되며, 이렇게 정의된 버전 수준은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 다양한 렌더링 계층을 정의하는 데 사용됩니다.  
  
 그래픽 하드웨어의 기능에 따라 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램의 렌더링 기능이 결정됩니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 시스템에서는 다음과 같은 세 가지 렌더링 계층을 정의합니다.  
  
-   **렌더링 계층 0** \- 그래픽 하드웨어 가속이 없습니다.  [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 버전 수준은 버전 7.0보다 낮습니다.  
  
-   **렌더링 계층 1** \- 부분 그래픽 하드웨어 가속이 있습니다.  [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 버전 수준은 버전 7.0보다 높거나 같고 버전 9.0보다 **낮습니다**.  
  
-   **렌더링 계층 2** \- 대부분의 그래픽 기능에서 그래픽 하드웨어 가속을 사용합니다.  [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 버전 수준은 버전 9.0보다 높거나 같습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 렌더링 계층에 대한 자세한 내용은 [그래픽 렌더링 계층](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md)을 참조하십시오.  
  
## 참고 항목  
 [WPF 응용 프로그램 성능 최적화](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [응용 프로그램 성능 계획](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)   
 [레이아웃 및 디자인](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)   
 [2차원 그래픽 및 이미징](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [개체 동작](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)   
 [응용 프로그램 리소스](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)   
 [텍스트](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [데이터 바인딩](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [기타 성능 권장 사항](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)