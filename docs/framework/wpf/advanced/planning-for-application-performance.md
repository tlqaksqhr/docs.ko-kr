---
title: "응용 프로그램 성능 계획"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications [WPF], optimizing
- WPF application [WPF], optimizing
ms.assetid: c91bd0c5-a193-46ff-9da1-eb7a3a76a3b3
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6bdb140d90de02fa817c55a05f40e57fcd0d636c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="planning-for-application-performance"></a>응용 프로그램 성능 계획
성공적인 성능 목표를 달성 성능 전략 개발 정도에 따라 다릅니다. 계획은 모든 제품 개발의 첫 번째 단계입니다. 이 항목에서는 성능이 현저히 전략을 개발 하기 위한 매우 간단한 몇 가지 규칙을 설명 합니다.  
  
## <a name="think-in-terms-of-scenarios"></a>시나리오의 측면에서 고민해  
 시나리오의 활용 응용 프로그램의 중요 한 구성 요소에 집중 합니다. 시나리오는 경쟁 제품 뿐 아니라 고객 프로그램에서 일반적으로 파생 됩니다. 항상 고객 연구 하 고 확인 하는 진짜 이유 제품을 경쟁 업체의 제품에 대 한 기쁘게 생각 합니다. 고객의 의견 응용 프로그램의 기본 시나리오를 결정 하는 데 도움이 됩니다. 예를 들어, 시작 시 사용 될 구성 요소를 디자인 하는 경우 응용 프로그램이 시작 될 때 구성 요소를 한 번만 호출할으로 가능성이 됩니다. 시작 시간은 주요 시나리오가 됩니다. 주요 시나리오의 다른 예에 애니메이션 시퀀스에 대 한 원하는 프레임 속도 수 또는 최대 응용 프로그램에 대 한 허용 집합을 작업 수 없습니다.  
  
## <a name="define-goals"></a>목표 정의  
 목표는 응용 프로그램으로 더 빠르거나 더 느리게 수행 되는지 여부를 확인 하는 데 도움이 됩니다. 모든 시나리오에 대 한 목표를 정의 해야 합니다. 모든 성능 목표는 정의 하는 고객의 기대를 기반으로 해야 합니다. 주기를 여전히 많은 해결 되지 않은 문제가 있는 경우 응용 프로그램 개발에서 초기에 목표 집합 성능 하기 어려울 수 있습니다. 그러나 초기 목표를 설정 하 고 나중에 없는 목표를 전혀 보다 수정 하는 것이 좋습니다.  
  
## <a name="understand-your-platform"></a>플랫폼 이해  
 측정, 조사, 응용 프로그램 개발 주기 동안 구체화/수정의 주기를 항상 유지 합니다. 개발 주기의 끝부터 안정적이 고 안정 된 환경에서 응용 프로그램의 성능을 측정 해야 합니다. 외부 요인에 따른 가변성을 피해 야 합니다. 예를 들어 성능을 테스트할 때 바이러스 백신 또는 SMS 같은 자동 업데이트를 사용 하지 않도록 설정, 성능에 영향을 하지 하려면 테스트 결과 해야 있습니다. 응용 프로그램의 성능의 측정 한 후에 가장 큰 향상에서 초래할 변화를 확인 해야 합니다. 응용 프로그램을 수정 하면 주기를 다시 시작 합니다.  
  
## <a name="make-performance-tuning-an-iterative-process"></a>성능 튜닝 방법으로 반복적인 프로세스를 확인 합니다.  
 사용 하 여 각 기능의 상대적 비용을 알고 있어야 합니다. 리플렉션 사용 예를 들어 [!INCLUDE[TLA#tla_avalonwinfx](../../../../includes/tlasharptla-avalonwinfx-md.md)] 않습니다 일반적으로 성능 집중적인 되므로 주의 해 서 사용 하 여 원하는 컴퓨팅 리소스를 기준으로 합니다. 그렇다고 리플렉션 사용을 방지 하기 위해 사용 하는 기능의 성능 요구 응용 프로그램의 성능 요구 사항을 균형을 조정 하는 주의 해야 하에 합니다.  
  
## <a name="build-towards-graphical-richness"></a>그래픽 다양성 개발  
 확장 가능한 접근 방법을 하기 위한 핵심 기술은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램의 성능을 그래픽 다양성 및 복잡성을 형성 하는 것입니다. 항상 최소 성능 집약적인 리소스를 사용 하 여 시나리오 목표를 달성 하기 시작 합니다. 이러한 목표를 달성 되 면 더 많은 성능 집약적인 기능을 항상 염두 시나리오 목표를 사용 하 여 그래픽 다양성 빌드하십시오. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 강력한 플랫폼 하며 매우 다양 한 그래픽 기능을 제공 합니다. 고려 하지 않고 성능 집약적인 기능을 사용 하 여 전체 응용 프로그램 성능이 저하 될 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]컨트롤은 광범위 한 사용자 지정 컨트롤 동작을 변경 하지 않고도 모양의 허용 하 여 기본적으로 확장할 수 있습니다. 스타일, 데이터 템플릿 및 컨트롤 템플릿을 활용 하 여 만들 수 있으며 점차적으로 사용자 지정 가능한를 개선할 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 하는 성능 요구 사항에 맞게 변경 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [WPF 응용 프로그램 성능 최적화](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [하드웨어 이용](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
 [레이아웃 및 디자인](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [2차원 그래픽 및 이미징](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [개체 동작](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [응용 프로그램 리소스](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
 [텍스트](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [데이터 바인딩](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [기타 성능 권장 사항](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)
