---
title: "서비스 호스팅"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- hosting services [WCF]
ms.assetid: 192be927-6be2-4fda-98f0-e513c4881acc
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b23dac1db5252d3ce2bd60e4f8525dd89d9127b0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="hosting-services"></a>서비스 호스팅
활성화할 서비스는 서비스를 만들고 컨텍스트와 수명을 제어하는 런타임 환경에 호스팅해야 합니다. [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 서비스는 관리 코드를 지원하는 모든 Windows 프로세스에서 실행할 수 있게 디자인되었습니다.  
  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 는 서비스 기반 응용 프로그램을 만드는 데 사용되는 통합 프로그래밍 모델을 제공합니다. 이 프로그래밍 모델은 일관적이며 서비스가 배포되는 런타임 환경에 독립적입니다. 즉, 서비스 코드는 사실상 서비스 호스팅 옵션에 관계없이 거의 동일합니다.  
  
 서비스 호스팅 옵션은 콘솔 응용 프로그램 내에서 실행하는 경우부터 서버 환경에 이르기까지 다양합니다. 서버 환경의 예를 들면 IIS(인터넷 정보 서비스) 또는 WAS(Windows Process Activation Service)에서 관리하는 작업자 프로세스 내에서 실행되는 Windows 서비스가 있습니다. 개발자는 서비스의 배포 요구 사항을 만족하는 호스팅 환경을 선택합니다. 이러한 요구 사항은 응용 프로그램이 배포되는 플랫폼, 메시지를 보내고 받는 데 필요한 전송, 충분한 가용성을 보장하는 데 필요한 프로세스 재활용 유형 및 기타 프로세스 관리 유형, 기타 관리 또는 안정성 요구 사항에 따라 달라집니다. 다음 단원에서는 호스팅 옵션에 대한 정보 및 지침을 제공합니다.  
  
## <a name="hosting-options"></a>호스팅 옵션  
  
#### <a name="self-hosting-in-a-managed-application"></a>관리되는 응용 프로그램에서의 자체 호스팅  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스는 관리되는 응용 프로그램에서 호스팅할 수 있습니다. 이 경우 배포하는 데 있어 최소한의 인프라를 필요하므로 가장 유연한 옵션입니다. 관리되는 응용 프로그램 코드 내에 서비스 코드를 포함시킨 다음 서비스를 사용할 수 있도록 <xref:System.ServiceModel.ServiceHost> 의 인스턴스를 만들고 엽니다. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][하는 방법: 관리 되는 응용 프로그램에서 WCF 서비스 호스팅](../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)합니다.  
  
 이 옵션을 사용하면 두 가지 일반적인 호스팅 시나리오가 가능합니다. 하나는 콘솔 응용 프로그램 내에서, 다른 하나는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 또는 WinForms(Windows Forms)를 기반으로 하는 응용 프로그램과 같은 리치 클라이언트 응용 프로그램 내에서 실행되는 [!INCLUDE[avalon1](../../../includes/avalon1-md.md)] 서비스입니다. 일반적으로 콘솔 응용 프로그램 내에서 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스를 호스팅하면 응용 프로그램의 개발 단계에서 유용합니다. 이 경우 쉽게 디버깅을 수행할 수 있으며, 응용 프로그램 내에서 발생하는 상황을 확인하기 위한 추적 정보를 손쉽게 얻을 수 있으며, 새 위치에 서비스를 복사하여 이동하기 용이합니다. 이 호스팅 옵션을 사용하면 리치 클라이언트 응용 프로그램(예: [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] 및 WinForms 응용 프로그램)에서 외부와 쉽게 통신할 수 있습니다. 예를 들면 사용자 인터페이스에 대해 [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] 를 사용하고 또한 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스를 호스팅하여 다른 클라이언트에서 해당 서비스에 연결하여 정보를 공유할 수 있도록 하는 피어 투 피어 공동 작업 클라이언트가 있습니다.  
  
#### <a name="managed-windows-services"></a>관리되는 Windows 서비스  
 이 호스팅 옵션은 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스를 호스팅하는 응용 프로그램 도메인(AppDomain)을 관리되는 Windows 서비스(이전의 NT 서비스)로 등록하여 프로세스 수명이 Windows 서비스의 SCM(서비스 제어 관리자)에 의해 제어되도록 하는 옵션입니다. 자체 호스팅 옵션과 같이 이러한 유형의 호스팅 환경에서는 일부 호스팅 코드를 응용 프로그램의 일부로 작성해야 합니다. 서비스를 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 계약 인터페이스에서뿐 아니라 <xref:System.ServiceProcess.ServiceBase> 클래스에서 상속시켜 서비스가 Windows 서비스와 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스로 구현됩니다. 그러면 <xref:System.ServiceModel.ServiceHost> 가 만들어지고, 재정의된 <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> 메서드 내에서 열리고 재정의된 <xref:System.ServiceProcess.ServiceBase.OnStop> 메서드 내에서 닫힙니다. Installutil.exe 도구를 사용하여 프로그램을 Windows 서비스로 설치하려면 <xref:System.Configuration.Install.Installer> 에서 상속되는 설치 관리자 클래스를 구현해야 합니다. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][하는 방법: 관리 되는 Windows 서비스에서 WCF 서비스 호스팅](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-a-managed-windows-service.md)합니다. 관리되는 Windows 서비스 호스팅 옵션을 통해 사용할 수 있는 시나리오는 메시지가 활성화되지 않은 보안 환경의 IIS 외부에서 호스팅되는 장기 실행 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스입니다. 서비스 수명은 대신 운영 체제에 의해 제어됩니다. 모든 버전의 Windows에서 이 호스팅 옵션을 사용할 수 있습니다.  
  
#### <a name="internet-information-services-iis"></a>IIS(인터넷 정보 서비스)  
 IIS 호스팅 옵션은 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 과 통합되어 있으며, 이러한 기술이 제공하는 프로세스 재활용, 유휴 상태이면 종료, 프로세스 상태 모니터링 및 메시지 기반 활성화 같은 기능을 사용합니다. [!INCLUDE[wxp](../../../includes/wxp-md.md)] 및 [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] 운영 체제에서 이 옵션은 높은 가용성 및 확장성을 필요로 하는 웹 서비스 응용 프로그램을 호스팅하는 기본 솔루션입니다. IIS는 또한 고객이 엔터프라이즈 수준의 서버 제품에서 기대하는 통합된 관리 효율성을 제공합니다. 이 호스팅 옵션을 사용하려면 IIS를 적절히 구성해야 하지만 호스팅 코드를 응용 프로그램의 일부로 작성하지 않아도 됩니다. [!INCLUDE[crabout](../../../includes/crabout-md.md)] 서비스에 대해 IIS 호스팅을 구성하는 방법에 대한 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 는 [How to: Host a WCF Service in IIS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).  
  
 IIS에서 호스팅되는 서비스는 HTTP 전송만 사용할 수 있습니다. IIS 5.1에서의 서비스 구현 시 [!INCLUDE[wxp](../../../includes/wxp-md.md)]의 경우 몇 가지 제한이 있습니다. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 의 IIS 5.1에서 호스팅되는 [!INCLUDE[wxp](../../../includes/wxp-md.md)] 서비스에 제공되는 메시지 기반 활성화 기능은 동일한 컴퓨터에서 자체 호스팅되는 다른 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스가 통신할 때 포트 80을 사용하지 못하도록 차단합니다. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스가 [!INCLUDE[iis601](../../../includes/iis601-md.md)] 의 [!INCLUDE[ws2003](../../../includes/ws2003-md.md)]에서 호스팅되는 경우에는 다른 응용 프로그램과 동일한 AppDomain/응용 프로그램 풀/작업자 프로세스에서 실행될 수 있습니다. 그러나 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 와 [!INCLUDE[iis601](../../../includes/iis601-md.md)] 모두 커널 모드 HTTP 스택(HTTP.sys)을 사용하므로 IIS 5.1과 달리 [!INCLUDE[iis601](../../../includes/iis601-md.md)] 에서는 포트 80을 동일한 시스템에서 실행되는 자체 호스팅되는 다른 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스와 공유할 수 있습니다.  
  
#### <a name="windows-process-activation-service-was"></a>WAS(Windows Process Activation Service)  
 WAS(Windows Process Activation Service)는 [!INCLUDE[lserver](../../../includes/lserver-md.md)] 에서도 사용할 수 있는 [!INCLUDE[wv](../../../includes/wv-md.md)]을 위한 새 프로세스 활성화 메커니즘입니다. 이 옵션의 경우 익숙한 [!INCLUDE[iis601](../../../includes/iis601-md.md)] 프로세스 모델(응용 프로그램 풀 및 메시지 기반 프로세스 활성화)과 호스팅 기능(오류로부터 신속한 보호, 상태 모니터링 및 재활용 등)은 유지되지만, 활성화 아키텍처에서 HTTP에 대한 종속성을 제거했습니다. [!INCLUDE[iisver](../../../includes/iisver-md.md)] 은 WAS를 사용하여 HTTP를 통한 메시지 기반 활성화를 수행합니다. 추가 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 구성 요소는 또한 WAS에 연결되어 TCP, MSMQ 및 명명된 파이프와 같은 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 에서 지원하는 다른 프로토콜을 통한 메시지 기반 활성화를 제공합니다. 이렇게 하면 통신 프로토콜을 사용하는 응용 프로그램에서 프로세스 재활용, 오류로부터 신속한 보호 및 일반적인 구성 시스템과 같은 HTTP 기반 응용 프로그램에서만 사용할 수 있었던 IIS 기능을 사용할 수 있습니다.  
  
 이 호스팅 옵션을 사용하려면 IIS를 적절히 구성해야 하지만 호스팅 코드를 응용 프로그램의 일부로 작성하지 않아도 됩니다. [!INCLUDE[crabout](../../../includes/crabout-md.md)] 는 [How to: Host a WCF Service in WAS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md).  
  
## <a name="choosing-a-hosting-environment"></a>호스팅 환경 선택  
 다음 표에서는 각 호스팅 옵션과 관련된 몇 가지 주요 이점 및 시나리오를 요약하여 설명합니다.  
  
|호스팅 환경|일반적인 시나리오|주요 이점 및 제한|  
|-------------------------|----------------------|----------------------------------|  
|관리되는 응용 프로그램("자체 호스팅")|콘솔 응용 프로그램 개발 중에 사용 합니다.<br />-리치 WinForm 및 [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] 클라이언트 응용 프로그램 서비스에 액세스 합니다.|-유연 합니다.<br />-쉽게 배포할 수 있습니다.<br />--서비스에 대 한 엔터프라이즈 솔루션입니다.|  
|Windows 서비스(이전의 NT 서비스)|-는 장기 실행 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] IIS 외부에서 호스팅된 서비스.|-서비스 프로세스 수명 메시지가 활성화 되지 운영 체제에 의해 제어 됩니다.<br />-모든 버전의 Windows에서 지원 합니다.<br />-보안 환경입니다.|  
|IIS 5.1, [!INCLUDE[iis601](../../../includes/iis601-md.md)]|-실행 중인 한 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 나란히 있는 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] HTTP 프로토콜을 사용 하 여 인터넷에서 콘텐츠입니다.|-프로세스 재활용 합니다.<br />-유휴 상태 이면 종료 합니다.<br />-프로세스 상태 모니터링.<br />-메시지 기반 활성화 합니다.<br />-HTTP 전용입니다.|  
|WAS(Windows Process Activation Service)|-실행 중인 한 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 여러 전송 프로토콜을 사용 하 여 인터넷에서 IIS를 설치 하지 않고 서비스입니다.|-IIS 필요 하지 않습니다.<br />-프로세스 재활용 합니다.<br />-유휴 상태 이면 종료 합니다.<br />-프로세스 상태 모니터링.<br />-메시지 기반 활성화 합니다.<br />-HTTP, TCP, 명명 된 파이프 및 MSMQ와 작동 합니다.|  
|IIS 7.0|-실행 중인 한 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스를 통해 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 콘텐츠입니다.<br />-실행 중인 한 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 여러 전송 프로토콜을 사용 하 여 인터넷에서 서비스입니다.|-혜택 했습니다.<br />-환경과 통합 되어 있으며 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 및 IIS 콘텐츠와 합니다.|  
  
 응용 프로그램이 배포되는 Windows 버전, 메시지를 보내는 데 필요한 전송, 응용 프로그램에서 필요로 하는 프로세스와 응용 프로그램 도메인 재활용 유형에 따라 선택하는 호스팅 환경이 달라집니다. 다음 표에서는 이러한 요구 사항과 관련된 데이터를 요약하여 설명합니다.  
  
|호스팅 환경|사용 가능한 플랫폼|지원되는 전송|프로세스 및 AppDomain 재활용|  
|-------------------------|---------------------------|--------------------------|-------------------------------------|  
|관리되는 응용 프로그램("자체 호스팅")|[!INCLUDE[wxp](../../../includes/wxp-md.md)], [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], [!INCLUDE[wv](../../../includes/wv-md.md)],<br /><br /> [!INCLUDE[lserver](../../../includes/lserver-md.md)]|HTTP,<br /><br /> net.tcp,<br /><br /> net.pipe,<br /><br /> net.msmq|아니요|  
|Windows 서비스(이전의 NT 서비스)|[!INCLUDE[wxp](../../../includes/wxp-md.md)], [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], [!INCLUDE[wv](../../../includes/wv-md.md)],<br /><br /> [!INCLUDE[lserver](../../../includes/lserver-md.md)]|HTTP,<br /><br /> net.tcp,<br /><br /> net.pipe,<br /><br /> net.msmq|아니요|  
|IIS 5.1|[!INCLUDE[wxp](../../../includes/wxp-md.md)]|HTTP|예|  
|[!INCLUDE[iis601](../../../includes/iis601-md.md)]|[!INCLUDE[ws2003](../../../includes/ws2003-md.md)]|HTTP|예|  
|WAS(Windows Process Activation Service)|[!INCLUDE[wv](../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../includes/lserver-md.md)]|HTTP,<br /><br /> net.tcp,<br /><br /> net.pipe,<br /><br /> net.msmq|예|  
  
 신뢰할 수 없는 호스트에서 서비스나 확장을 실행하면 보안이 손상된다는 점에 주의해야 합니다. 또한 가장하여 <xref:System.ServiceModel.ServiceHost> 를 열 때 응용 프로그램에서 사용자의 <xref:System.Security.Principal.WindowsIdentity> 를 캐싱하여 사용자가 로그오프되었는지 확인해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [시스템 요구 사항](../../../docs/framework/wcf/wcf-system-requirements.md)  
 [기본 프로그래밍 수명 주기](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
 [서비스 계약 구현](../../../docs/framework/wcf/implementing-service-contracts.md)  
 [방법: IIS에서 WCF 서비스 호스트](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)  
 [방법: WAS에서 WCF 서비스 호스트](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md)  
 [방법: 관리되는 Windows 서비스에서 WCF 서비스 호스팅](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-a-managed-windows-service.md)  
 [방법: 관리되는 응용 프로그램에서 WCF 서비스 호스트](../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)
