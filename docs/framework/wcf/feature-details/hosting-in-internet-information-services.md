---
title: "인터넷 정보 서비스에서의 호스팅"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: hosting services [WCF], IIS
ms.assetid: ddae14e8-143c-442d-b660-2046809b2d43
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: dc0a2692e105588d482156dfa870d8e587008b8d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="hosting-in-internet-information-services"></a>인터넷 정보 서비스에서의 호스팅
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스 호스팅에 대한 한 가지 옵션은 IIS(인터넷 정보 서비스) 응용 프로그램 내부에 있습니다. 이 호스팅 모델은 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 및 ASP.NET 웹 서비스(ASMX) 웹 서비스에서 사용되는 모델과 비슷합니다.  
  
## <a name="versions-of-iis"></a>IIS 버전  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 다음 운영 체제의 다음과 같은 IIS 버전에서 호스트될 수 있습니다.  
  
-   [!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)]의 IIS 5.1. 이 환경은 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]과 같은 서버 운영 체제에서 나중에 배포되는 IIS에서 호스트되는 응용 프로그램의 설계 및 개발에 유용합니다.  
  
-   [!INCLUDE[iis601](../../../../includes/iis601-md.md)]의 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]. [!INCLUDE[iis601](../../../../includes/iis601-md.md)]은 향상된 확장성, 신뢰성 및 응용 프로그램 격리 기능을 지원하는 고급 프로세스 모델을 제공합니다. 이 환경은 HTTP 통신을 단독으로 사용하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스의 프로덕션 배포에 적합합니다.  
  
-   [!INCLUDE[wv](../../../../includes/wv-md.md)] 및 [!INCLUDE[lserver](../../../../includes/lserver-md.md)]의 IIS 7.0. IIS 7.0은 [!INCLUDE[iis601](../../../../includes/iis601-md.md)]과 동일한 고급 프로세스 모델을 제공하지만 WAS(Windows Process Activation Service)를 사용하여 HTTP 이외의 프로토콜을 통해 활성화 및 네트워크 통신을 수행할 수 있습니다. 이 환경은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 지원하는 네트워크 프로토콜(HTTP, net.tcp, net.pipe 및 net.msmq 포함)을 통해 통신하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 개발에 적합합니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]참조를 [Windows Process Activation Service에서의 호스팅](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md)합니다.  
  
-   [Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=196496) 연동 [!INCLUDE[iisver](../../../../includes/iisver-md.md)] 및 WAS Windows Process Activation Service ()는 응용 프로그램 호스팅 NET4 WCF 및 WF 서비스에 대 한 환경을 제공 하기. 이러한 기능에는 프로세스 수명 주기 관리, 프로세스 재활용, 공유 호스팅, 빠른 오류 보호, 프로세스 분리, 요청 시 활성화, 상태 모니터링 등이 포함됩니다. 자세한 내용은 참조 [AppFabric 호스팅 기능](http://go.microsoft.com/fwlink/?LinkId=196494) 및 [AppFabric 호스팅 개념](http://go.microsoft.com/fwlink/?LinkId=196495)합니다.  
  
## <a name="benefits-of-iis-hosting"></a>IIS 호스팅의 장점  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 IIS에서 호스트하면 다음과 같은 여러 장점이 있습니다.  
  
-   IIS에서 호스트되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램 및 ASMX를 비롯한 다른 유형의 IIS 응용 프로그램과 같이 배포되고 관리됩니다.  
  
-   IIS는 프로세스 활성화, 상태 관리 및 재활용 기능을 제공하여 호스트된 응용 프로그램의 신뢰성이 향상됩니다.  
  
-   [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]처럼 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 호스트된 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 서비스는 향상된 서버 밀도 및 확장성을 위해 여러 응용 프로그램이 공통 작업자 프로세스에 있는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 공유 호스팅 모델을 활용할 수 있습니다.  
  
-   IIS에서 호스트되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스는 [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)]과 동일한 동적 컴파일 모델을 사용하여 호스트된 서비스의 개발 및 배포를 단순화합니다.  
  
 IIS에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 호스트하는 경우 IIS 5.1 및 [!INCLUDE[iis601](../../../../includes/iis601-md.md)]은 HTTP 통신으로만 제한됩니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]호스팅 환경 선택, 참조 [호스팅 서비스](../../../../docs/framework/wcf/hosting-services.md)합니다.  
  
## <a name="deploying-an-iis-hosted-wcf-service"></a>IIS에서 호스트되는 WCF 서비스 배포  
 IIS에서 호스트되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스의 개발 및 배포는 다음과 같은 작업으로 구성됩니다.  
  
-   IIS, ASP.NET, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 및 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] HTTP 활성화 구성 요소가 제대로 설치되고 등록되었는지 확인합니다.  
  
-   새 IIS 응용 프로그램을 만들거나 기존 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램을 다시 사용합니다.  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에 대한 .svc 파일을 만듭니다.  
  
-   IIS 응용 프로그램에 서비스 구현을 배포합니다.  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 구성합니다.  
  
 이러한 각 작업의 논의 알려면 [인터넷 WCF 서비스 배포](../../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md)합니다.  
  
## <a name="wcf-services-and-aspnet"></a>WCF 서비스 및 ASP.NET  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 또는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 웹 응용 프로그램 플랫폼에서 제공하는 기능을 최대한 활용할 수 있는 서비스의 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 호환 모드에서 단계적으로 호스트될 수 있습니다. 이러한 기능의 논의 알려면 [WCF 서비스 및 ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ServiceHostFactory를 사용 하 여 호스팅](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md)  
 [인터넷 정보 서비스에서 호스팅되는 WCF 서비스 배포](../../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md)  
 [WCF 서비스 및 ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)  
 [인터넷 정보 서비스 호스팅을 위한 최선의 방법](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)  
 [Windows Communication Foundation에 대 한 인터넷 정보 서비스 7.0 구성](../../../../docs/framework/wcf/feature-details/configuring-iis-for-wcf.md)  
 [Windows Server App Fabric 호스팅 기능](http://go.microsoft.com/fwlink/?LinkId=201276)
