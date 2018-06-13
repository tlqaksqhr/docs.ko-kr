---
title: 인터넷 정보 서비스에서의 호스팅
ms.date: 03/30/2017
helpviewer_keywords:
- hosting services [WCF], IIS
ms.assetid: ddae14e8-143c-442d-b660-2046809b2d43
ms.openlocfilehash: 588e069280afc369256fdbee0132f732348ffc37
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33494116"
---
# <a name="hosting-in-internet-information-services"></a>인터넷 정보 서비스에서의 호스팅
Windows Communication Foundation (WCF) 서비스를 호스팅하기 위한 한 가지 옵션은 인터넷 정보 서비스 (IIS) 응용 프로그램 내부 하는 것입니다. 이 호스팅 모델은 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 및 ASP.NET 웹 서비스(ASMX) 웹 서비스에서 사용되는 모델과 비슷합니다.  
  
## <a name="versions-of-iis"></a>IIS 버전  
 WCF 다음 운영 체제에 다음 버전의 IIS에서 호스트 될 수 있습니다.  
  
-   [!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)]의 IIS 5.1. 이 환경은 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]과 같은 서버 운영 체제에서 나중에 배포되는 IIS에서 호스트되는 응용 프로그램의 설계 및 개발에 유용합니다.  
  
-   [!INCLUDE[iis601](../../../../includes/iis601-md.md)]의 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]. [!INCLUDE[iis601](../../../../includes/iis601-md.md)]은 향상된 확장성, 신뢰성 및 응용 프로그램 격리 기능을 지원하는 고급 프로세스 모델을 제공합니다. 이 환경은 HTTP 통신을 독점적으로 사용 하는 WCF 서비스의 프로덕션 배포에 적합 합니다.  
  
-   [!INCLUDE[wv](../../../../includes/wv-md.md)] 및 [!INCLUDE[lserver](../../../../includes/lserver-md.md)]의 IIS 7.0. IIS 7.0은 [!INCLUDE[iis601](../../../../includes/iis601-md.md)]과 동일한 고급 프로세스 모델을 제공하지만 WAS(Windows Process Activation Service)를 사용하여 HTTP 이외의 프로토콜을 통해 활성화 및 네트워크 통신을 수행할 수 있습니다. 이 환경은 (HTTP, net.tcp, net.pipe 및 net.msmq 포함)는 WCF에서 지 원하는 모든 네트워크 프로토콜을 통해 통신 하는 WCF 서비스의 개발에 적합 합니다. WAS에 대 한 자세한 내용은 참조 [Windows Process Activation Service에서의 호스팅](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md)합니다.  
  
-   [Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=196496) 연동 [!INCLUDE[iisver](../../../../includes/iisver-md.md)] 및 WAS Windows Process Activation Service ()는 응용 프로그램 호스팅 NET4 WCF 및 WF 서비스에 대 한 환경을 제공 하기. 이러한 기능에는 프로세스 수명 주기 관리, 프로세스 재활용, 공유 호스팅, 빠른 오류 보호, 프로세스 분리, 요청 시 활성화, 상태 모니터링 등이 포함됩니다. 자세한 내용은 참조 [AppFabric 호스팅 기능](http://go.microsoft.com/fwlink/?LinkId=196494) 및 [AppFabric 호스팅 개념](http://go.microsoft.com/fwlink/?LinkId=196495)합니다.  
  
## <a name="benefits-of-iis-hosting"></a>IIS 호스팅의 장점  
 IIS에서 WCF 서비스 호스팅 몇 가지 이점이 있습니다.  
  
-   IIS에서 호스팅되는 WCF 서비스 배포 되 고 다른 유형의 IIS 응용 프로그램을 같이 관리 되는 포함 하 여 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램 및 ASMX 합니다.  
  
-   IIS는 프로세스 활성화, 상태 관리 및 재활용 기능을 제공하여 호스트된 응용 프로그램의 신뢰성이 향상됩니다.  
  
-   마찬가지로 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], WCF 서비스에서 호스트 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 활용할 수 있습니다는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 여러 응용 프로그램이 공통 작업자 프로세스 향상 된 서버 밀도 및 확장성을 위해 상주 하는 위치는 공유 호스팅 모델입니다.  
  
-   IIS에서 호스팅되는 WCF 서비스 사용과 동일한 동적 컴파일 모델 [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)], 개발 간소화 및 호스팅된 서비스의 배포 합니다.  
  
 기억할 중요 한은 IIS에서 WCF 서비스 호스트를 결정할 때는 해당 IIS 5.1 및 [!INCLUDE[iis601](../../../../includes/iis601-md.md)] HTTP 통신 으로만 제한 됩니다. 호스팅 환경 선택 하는 방법에 대 한 자세한 내용은 참조 [호스팅 서비스](../../../../docs/framework/wcf/hosting-services.md)합니다.  
  
## <a name="deploying-an-iis-hosted-wcf-service"></a>IIS에서 호스트되는 WCF 서비스 배포  
 개발 하 고 IIS에서 호스팅되는 WCF 서비스 배포는 다음과 같은 작업으로 구성 됩니다.  
  
-   IIS, ASP.NET, WCF 및 WCF HTTP 활성화 구성 요소가 올바르게 설치 되어 등록을 확인 합니다.  
  
-   새 IIS 응용 프로그램을 만들거나 기존 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램을 다시 사용합니다.  
  
-   WCF 서비스에 대 한.svc 파일을 만듭니다.  
  
-   IIS 응용 프로그램에 서비스 구현을 배포합니다.  
  
-   WCF 서비스를 구성 합니다.  
  
 이러한 각 작업의 논의 알려면 [인터넷 WCF 서비스 배포](../../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md)합니다.  
  
## <a name="wcf-services-and-aspnet"></a>WCF 서비스 및 ASP.NET  
 WCF 서비스 수 어느--와 함께 호스트 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 또는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 호환 모드는 서비스에서 제공 하는 기능을 걸릴 수 있습니다는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 웹 응용 프로그램 플랫폼입니다. 이러한 기능의 논의 알려면 [WCF 서비스 및 ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ServiceHostFactory를 사용하여 호스팅 확장](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md)  
 [인터넷 정보 서비스에서 호스트하는 WCF 서비스 배포](../../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md)  
 [WCF 서비스 및 ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)  
 [인터넷 정보 서비스 호스팅을 위한 최선의 방법](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)  
 [Windows Communication Foundation에 대해 Internet Information Services 7.0 구성](../../../../docs/framework/wcf/feature-details/configuring-iis-for-wcf.md)  
 [Windows Server App Fabric 호스팅 기능](http://go.microsoft.com/fwlink/?LinkId=201276)
