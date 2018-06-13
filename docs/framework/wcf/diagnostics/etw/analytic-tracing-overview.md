---
title: 분석 추적 개요
ms.date: 03/30/2017
helpviewer_keywords:
- analytic tracing [WCF], overview
ms.assetid: ae55e9cc-0809-442f-921f-d644290ebf15
ms.openlocfilehash: 1d68e3132224a7b60720fe7c293b9eee14e3fbd5
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33803348"
---
# <a name="analytic-tracing-overview"></a>분석 추적 개요
[!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] 의 분석 추적은 ETW(Event Tracing for Windows)를 기반으로 하는 고성능의 간단한 추적 기능 집합입니다. ETW는 커널 수준에서 실행되기 때문에 추적 작업의 오버헤드를 크게 줄이며, 사용자 및 커널 모드 이벤트를 효율적으로 버퍼링하고 서비스를 다시 시작하지 않고도 동적으로 로깅을 사용하도록 설정할 수 있습니다. 추적 데이터는 내보내기와 받기 과정을 거친 후 이벤트 로그에 제공됩니다.  
  
 ETW에 대 한 자세한 내용은 참조 [디버깅 개선 및 ETW를 사용한 성능 조정](http://go.microsoft.com/fwlink/?LinkId=164781)합니다.  
  
 [!INCLUDE[wv](../../../../../includes/wv-md.md)] 및 [!INCLUDE[lserver](../../../../../includes/lserver-md.md)] 에서는 Windows 시스템, 보안 및 응용 프로그램 이벤트 로그를 사용하여 응용 프로그램을 분석할 뿐 아니라 응용 프로그램 및 서비스 로그 최상위 노드 아래에 추가 로그를 제공합니다. 이러한 새 로그의 목적은 보안 이벤트 로그에 기록될 수 있는 이벤트 형식처럼 시스템 전체에 영향을 주는 전역 이벤트가 아니라 특정 응용 프로그램이나 구성 요소에 대한 이벤트를 저장하기 위한 것입니다. [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)] 통합 하 고 WCF 추적 이벤트, WCF 메시지 로그의 로깅을 상관 관계를 지정 하 고 [!INCLUDE[wf1](../../../../../includes/wf1-md.md)] 응용 프로그램 및 서비스 로그에 추적 레코드.  
  
## <a name="concepts-and-capabilities"></a>개념 및 기능  
 다음과 같은 개념 및 기능에는 WCF 분석 추적에 적용 됩니다.  
  
### <a name="enabling-wcf-diagnostics-settings"></a>WCF 진단 설정 사용  
 WCF 진단 유틸리티를 사용할 수는 \<system.serviceModel >\<진단 > 구성 섹션입니다.  
  
```xml  
<system.serviceModel>  
  <diagnostics>  
```  
  
 웹 호스팅 IIS 가상 응용 프로그램에 대한 WCF 진단 설정은 응용 프로그램의 Web.config 파일 내에서 사용 가능하게 설정할 수 있습니다. 또는 응용 프로그램 내의 하위 디렉터리에 Web.config를 만들어  하위 디렉터리 내의 모든 서비스에 진단 설정을 적용할 수도 있습니다.  진단 설정이 응용 프로그램 내의 모든 서비스에 대해 일관되게 초기화되도록 하려면 설정이 응용 프로그램 내의 개별 하위 디렉터리 중 하나가 아니라 응용 프로그램 디렉터리에 있는 Web.config 내에 있어야 합니다.  
  
### <a name="channels"></a>채널  
 ETW를 사용하면 소프트웨어 구성 요소에서 채널을 통해 추적 이벤트를 특정 대상에 보낼 수 있습니다. 예를 들어 한 채널에는 시스템 관리자에 대한 이벤트를 보내고 다른 한 채널에는 응용 프로그램 개발자가 관심을 가지고 있는 이벤트를 보낼 수 있습니다. 채널은 이름이 지정되어 Windows에 등록되기 때문에 사용자가 이벤트 뷰어를 사용하여 채널의 이벤트를 볼 수 있습니다.  
  
 WCF에는 분석 추적 기능은 [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)] Microsoft-Windows-응용 프로그램-서버-응용 프로그램 채널에 기록 합니다. 이 채널은 프로덕션 환경에서 WCF 서비스의 상태를 모니터링 하려는 사용자에 대해 특별히 설계 않았습니다. 이 채널에는 다양한 상태 모니터링 및 문제 해결 시나리오에서 사용할 수 있는 작은 이벤트 집합이 정의됩니다.  
  
 메시지가 이벤트 로그에서 적절하게 디코딩되게 하기 위해 Windows용 이벤트 추적 매니페스트를 사용하도록 설정하려면 다음과 같이 명령줄에서 ServiceModelReg 도구를 사용합니다.  
  
 `ServiceModelReg.exe -i -c:etw`  
  
### <a name="dynamic-configuration"></a>동적 구성  
 ETW 인프라를 사용하면 표준 Windows 도구를 사용하여 동적으로 추적을 사용하도록 설정하고 구성할 수 있습니다. 자세한 내용은 참조 [동적으로 사용 하면 분석 추적](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)합니다.  
  
### <a name="message-flow-tracing"></a>메시지 흐름 추적  
 메시지 흐름 추적을 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 참조 [메시지 흐름 추적 구성](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)합니다.  
  
### <a name="keywords"></a>키워드  
 키워드는 추적 메시지를 필터링하고 이벤트를 내보낸 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] 구성 요소를 정의하는 데 사용됩니다. 자세한 내용은 참조 [동적으로 사용 하면 분석 추적](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)합니다.
