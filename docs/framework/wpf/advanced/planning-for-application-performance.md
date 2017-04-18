---
title: "응용 프로그램 성능 계획 | Microsoft Docs"
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
  - "응용 프로그램, 최적화"
  - "WPF 응용 프로그램, 최적화"
ms.assetid: c91bd0c5-a193-46ff-9da1-eb7a3a76a3b3
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 응용 프로그램 성능 계획
성능 목표의 성공적인 달성은 성능 전략을 얼마나 잘 개발하는지에 달려 있습니다.  모든 제품 개발에서 첫 번째 단계는 계획입니다.  이 항목에서는 훌륭한 성능 전략을 개발하기 위한 몇 가지 아주 간단한 규칙에 대해 설명합니다.  
  
## 시나리오 측면에서 고려  
 시나리오는 응용 프로그램의 중요한 구성 요소에 집중하는 데 도움이 될 수 있습니다.  시나리오는 일반적으로 경쟁 제품뿐 아니라 고객에게서 얻습니다.  항상 고객을 연구하고 고객이 자사의 제품이나 경쟁사의 제품에 열광하는 진짜 이유를 찾아봅니다.  고객의 의견은 응용 프로그램의 기본 시나리오를 결정하는 데 도움을 줄 수 있습니다.  예를 들어 시작 시 사용할 구성 요소를 디자인하는 경우 이 구성 요소는 응용 프로그램이 시작할 때 한 번만 호출될 것입니다.  이때에는 시작 시간이 주요 시나리오가 됩니다.  다른 예로 애니메이션 시퀀스의 원하는 프레임 속도, 응용 프로그램에 허용되는 최대 작업 집합 등도 주요 시나리오가 될 수 있습니다.  
  
## 목표 정의  
 목표는 응용 프로그램을 빠르게 수행할지, 아니면 느리게 수행할지를 결정하는 데 도움이 됩니다.  모든 시나리오에 대해 목표를 정의해야 합니다.  정의하는 모든 성능 목표는 고객의 기대를 기반으로 해야 합니다.  아직 해결되지 않은 많은 문제가 있는 응용 프로그램 개발 주기의 초기에는 성능 목표를 설정하는 것이 어려울 수 있습니다.  그러나 초기 목표를 설정하고 나중에 수정하는 것이 성능 목표가 전혀 없는 것보다 낫습니다.  
  
## 플랫폼 이해  
 응용 프로그램 개발 주기 동안 측정, 조사, 구체화\/수정의 주기를 항상 유지합니다.  개발 주기의 시작부터 끝까지 신뢰할 수 있는 안정된 환경에서 응용 프로그램의 성능을 측정해야 합니다.  외부 요인에 따른 가변성을 방지해야 합니다.  예를 들어 성능을 테스트할 때는 성능 테스트 결과에 영향을 주지 않도록 바이러스 백신 또는 SMS와 같은 자동 업데이트를 사용하지 않도록 설정해야 합니다.  응용 프로그램 성능을 측정한 후에는 성능을 가장 크게 개선할 변경 사항을 식별해야 합니다.  응용 프로그램을 수정하고 나서 주기를 다시 시작합니다.  
  
## 반복적인 성능 조정  
 사용할 각 기능의 상대적 비용을 알고 있어야 합니다.  예를 들어 [!INCLUDE[TLA#tla_avalonwinfx](../../../../includes/tlasharptla-avalonwinfx-md.md)]에서 리플렉션을 사용하면 일반적으로 컴퓨팅 리소스의 측면에서 성능에 상당한 영향을 미치므로 현명하게 사용해야 합니다.  이는 리플렉션을 사용하지 말라는 의미는 아니고 단지 응용 프로그램의 성능 요구 사항과 사용하는 기능의 성능 요구 사항 사이의 균형을 유지할 수 있도록 주의를 기울여야 한다는 의미입니다.  
  
## 그래픽 다양성 개발  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램 성능을 성취하기 위한 확장 가능한 접근 방법을 구축하기 위한 핵심 기술은 그래픽 다양성과 복잡성을 개발하는 것입니다.  항상 처음에는 성능에 가장 적은 영향을 주는 리소스를 사용하여 시나리오 목표를 달성합니다.  이러한 목표를 달성했으면 항상 시나리오 목표를 염두에 두고 성능에 더 많은 영향을 주는 기능을 사용하여 그래픽 다양성을 개발합니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 매우 다양한 그래픽 기능을 제공하는 강력한 플랫폼입니다.  성능에 큰 영향을 주는 기능을 생각 없이 사용하면 전체 응용 프로그램 성능에 나쁜 영향을 줄 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤은 해당 컨트롤 동작은 변경하지 않고도 모양의 광범위한 사용자 지정을 통해 기본적으로 확장할 수 있습니다.  스타일, 데이터 템플릿 및 컨트롤 템플릿을 활용하여 성능 요구 사항에 맞는 사용자 지정 가능한 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]를 만들고 점차적으로 개선할 수 있습니다.  
  
## 참고 항목  
 [WPF 응용 프로그램 성능 최적화](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [하드웨어 이용](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)   
 [레이아웃 및 디자인](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)   
 [2차원 그래픽 및 이미징](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [개체 동작](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)   
 [응용 프로그램 리소스](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)   
 [텍스트](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [데이터 바인딩](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [기타 성능 권장 사항](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)