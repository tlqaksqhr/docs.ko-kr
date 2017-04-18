---
title: "Windows Process Activation Service에서의 호스팅 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "서비스 호스팅 [WCF], WAS"
ms.assetid: d2b9d226-15b7-41fc-8c9a-cb651ac20ecd
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# Windows Process Activation Service에서의 호스팅
WAS\(Windows Process Activation Service\)는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스를 호스트하는 응용 프로그램이 포함된 작업자 프로세스의 활성화 및 수명을 관리합니다.  WAS 프로세스 모델은 HTTP에 대한 종속성을 제거하여 HTTP 서버의 [!INCLUDE[iis601](../../../../includes/iis601-md.md)] 프로세스 모델을 일반화합니다.  이렇게 하면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스가 메시지 기반 활성화를 지원하고 지정된 컴퓨터에서 여러 응용 프로그램을 호스트하는 기능을 제공하는 호스팅 환경에서 Net.TCP와 같은 HTTP 프로토콜 및 HTTP가 아닌 프로토콜을 모두 사용할 수 있습니다.  
  
 WAS 호스팅 환경에서 실행되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 빌드[!INCLUDE[crabout](../../../../includes/crabout-md.md)] [방법: WAS에서 WCF 서비스 호스팅](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md)을 참조하세요.  
  
 WAS 프로세스 모델에서는 보다 강력하고, 보다 집중적으로 관리할 수 있으며, 리소스를 효율적으로 사용하는 방식으로 응용 프로그램을 호스트할 수 있도록 여러 기능을 제공합니다.  
  
-   HTTP 및 HTTP가 아닌 네트워크 프로토콜을 사용하여 도착하는 들어오는 작업 항목에 대한 응답으로 응용 프로그램 및 작업자 프로세스 응용 프로그램의 메시지 기반 활성화가 동적으로 시작 및 중지  
  
-   실행 중인 응용 프로그램의 상태를 유지 관리하기 위한 강력한 응용 프로그램 및 작업자 프로세스의 재활용  
  
-   중앙 집중화된 응용 프로그램 구성 및 관리  
  
-   전체 IIS 설치를 위한 배포 공간 없이도 응용 프로그램에서 IIS 프로세스 모델 사용 가능  
  
 WAS 기능[!INCLUDE[crabout](../../../../includes/crabout-md.md)] [IIS 7.0 Beta: IIS 7.0 Web Administration](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md)를 참조하세요.  
  
 [Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=196496)은 [!INCLUDE[iisver](../../../../includes/iisver-md.md)] 및 WAS\(Windows Process Activation Service\)와 작동하여 NET4 WCF 및 WF 서비스에 대한 다양한 기능이 포함된 응용 프로그램 호스팅 환경을 제공합니다.  이러한 기능에는 프로세스 수명 주기 관리, 프로세스 재활용, 공유 호스팅, 빠른 오류 보호, 프로세스 분리, 요청 시 활성화, 상태 모니터링 등이 포함됩니다.  자세한 내용은 [AppFabric 호스팅 기능](http://go.microsoft.com/fwlink/?LinkId=196494) 및 [AppFabric 호스팅 개념](http://go.microsoft.com/fwlink/?LinkId=196495)을 참조하세요.  
  
## WAS 주소 지정 모델의 요소  
 응용 프로그램에는 서버에서 관리하는 수명 및 실행 환경의 코드 단위인 URI\(Uniform Resource Identifier\) 주소가 있습니다.  단일 WAS 서버 인스턴스는 여러 응용 프로그램에 대한 홈이 될 수 있습니다.  서버에서는 *사이트*라는 그룹으로 응용 프로그램을 구성합니다.  사이트에서 응용 프로그램은 계층적 방식으로 배열되어 외부 주소로 사용되는 URI의 구조를 반영합니다.  
  
 응용 프로그램 주소는 기본 URI 접두사와 응용 프로그램별 상대 주소\(경로\)의 두 부분으로 구성됩니다. 이 두 부분이 함께 결합될 경우 응용 프로그램의 외부 주소를 제공합니다.  기본 URI 접두사는 사이트 바인딩에서 생성되며 사이트의 모든 응용 프로그램에 사용됩니다.  응용 프로그램 주소는 “\/applicationOne”과 같은 응용 프로그램별 경로 부분을 “net.tcp:\/\/localhost”와 같은 기본 URI 접두사에 추가하여 전체 응용 프로그램 URI를 만들어 생성됩니다.  
  
 다음 표에서는 HTTP 사이트 바인딩 및 HTTP가 아닌 사이트 바인딩을 모두 사용하여 WAS 사이트에 대한 가능한 여러 주소 지정 시나리오를 보여 줍니다.  
  
|시나리오|사이트 바인딩|응용 프로그램 경로|기본 응용 프로그램 URI|  
|----------|-------------|----------------|--------------------|  
|HTTP인 경우에만|http: \*:80:\*|\/appTwo|http:\/\/localhost\/appTwo\/|  
|HTTP 및 HTTP가 아닌 경우 모두|http: \*:80:\*<br /><br /> net.tcp: 808:\*|\/appTwo|http:\/\/localhost\/appTwo\/                 <br /> net.tcp:\/\/localhost\/appTwo\/|  
|HTTP가 아닌 경우에만|net.pipe: \*|\/appThree|net.pipe:\/\/appThree\/|  
  
 응용 프로그램의 서비스 및 리소스의 주소도 지정할 수 있습니다.  응용 프로그램에서 응용 프로그램 리소스는 기본 응용 프로그램 경로에 따라 주소가 지정됩니다.  예를 들어, contoso.com이라는 컴퓨터 이름의 사이트에 HTTP 및 Net.TCP 프로토콜 모두에 대한 사이트 바인딩이 있고,  GetOrders.svc에 서비스를 노출시키는 \/Billing에 위치하는 하나의 응용 프로그램이 해당 사이트에 포함된다고 가정해 봅니다.  그러면 GetOrders.svc 서비스가 SecureEndpoint의 상대 주소와 함께 끝점을 노출시키면 서비스 끝점이 다음 두 URI에 노출됩니다.  
  
 http:\/\/contoso.com\/Billing\/GetOrders.svc\/SecureEndpoint           
 net.tcp:\/\/contoso.com\/Billing\/GetOrders.svc\/SecureEndpoint  
  
## WAS 런타임  
 응용 프로그램은 주소 지정 및 관리를 위해 사이트로 구성됩니다.  런타임에 응용 프로그램은 또한 응용 프로그램 풀로 그룹화됩니다.  응용 프로그램 풀에는 여러 다른 사이트의 여러 다른 응용 프로그램을 보유할 수 있습니다.  응용 프로그램 풀에 있는 모든 응용 프로그램은 공용 런타임 특성 집합을 공유합니다.  예를 들어, 이러한 응용 프로그램은 같은 버전의 CLR\(공용 언어 런타임\)에서 모두 실행되며 공통 프로세스 ID를 공유합니다.  각 응용 프로그램 풀은 작업자 프로세스\(w3wp.exe\)의 인스턴스에 해당합니다.  관리되는 각 응용 프로그램은 공유 응용 프로그램 풀에서 실행되며 CLR AppDomain을 사용하여 다른 응용 프로그램과 격리됩니다.  
  
## 참고 항목  
 [WAS Activation 아키텍처](../../../../docs/framework/wcf/feature-details/was-activation-architecture.md)   
 [WCF와 함께 사용하도록 WAS 구성](../../../../docs/framework/wcf/feature-details/configuring-the-wpa--service-for-use-with-wcf.md)   
 [방법: WCF Activation 구성 요소 설치 및 구성](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)   
 [방법: WAS에서 WCF 서비스 호스팅](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md)   
 [Windows Server App Fabric 호스팅 기능 \(영문\)](http://go.microsoft.com/fwlink/?LinkId=201276)