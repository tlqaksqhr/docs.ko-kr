---
title: "방법: Windows Server App Fabric을 사용하여 워크플로 서비스 호스팅 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 83b62cce-5fc2-4c6d-b27c-5742ba3bac73
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# 방법: Windows Server App Fabric을 사용하여 워크플로 서비스 호스팅
App Fabric에서 워크플로 서비스를 호스팅하는 것은 IIS\/WAS에서 호스팅하는 것과 유사합니다.유일한 차이점은 App Fabric에서 워크플로 서비스의 배포, 모니터링 및 관리를 위해 제공하는 도구입니다.이 항목에서는 [장기 실행 워크플로 서비스 만들기](../../../../docs/framework/wcf/feature-details/creating-a-long-running-workflow-service.md)에서 만든 워크플로 서비스를 사용합니다.이 항목에서는 워크플로 서비스를 만드는 방법을 안내하며,App Fabric을 사용하여 워크플로 서비스를 호스팅하는 방법을 설명합니다.Windows Server App Fabric[!INCLUDE[crabout](../../../../includes/crabout-md.md)][Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=193037&clcid=0x412)을 참조하십시오.아래의 단계를 완료하기 전에 Windows Server App Fabric이 설치되어 있는지 확인합니다.이렇게 하려면 인터넷 정보 서비스\(inetmgr.exe\)를 열고 **연결** 뷰에서 서버 이름을 클릭한 다음 사이트를 클릭하고 **기본 웹 사이트**를 클릭합니다.화면의 오른쪽에 **App Fabric**이라는 섹션이 표시됩니다.이 섹션\(오른쪽 창의 맨 위에 있음\)이 없으면 App Fabric이 설치되지 않은 것입니다.Windows Server App Fabric 설치에 대한 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]는 [Windows Server AppFabric 설치](http://go.microsoft.com/fwlink/?LinkId=193136)\(영문 페이지일 수 있음\)를 참조하십시오.  
  
### 간단한 워크플로 서비스 만들기  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]을 열고 [장기 실행 워크플로 서비스 만들기](../../../../docs/framework/wcf/feature-details/creating-a-long-running-workflow-service.md) 항목에서 만든 OrderProcessing 솔루션을 로드합니다.  
  
2.  **OrderService** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택한 다음 **웹** 탭을 선택합니다.  
  
3.  속성 페이지의 **시작 작업** 섹션에서 **특정 페이지**를 선택하고 편집 상자에 Service1.xamlx를 입력합니다.  
  
4.  속성 페이지의 **서버** 섹션에서 **로컬 IIS 웹 서버 사용**을 선택하고 URL `http://localhost/OrderService`를 입력합니다.  
  
5.  **가상 디렉터리 만들기** 단추를 클릭합니다.새 가상 디렉터리가 만들어지고 프로젝트가 빌드될 때 이 가상 디렉터리에 필요한 파일을 복사하도록 프로젝트가 설정됩니다.또는 .xamlx, web.config 및 필요한 DLL을 가상 디렉터리에 수동으로 복사할 수 있습니다.  
  
### Windows Server App Fabric에서 호스팅되는 워크플로 서비스 구성  
  
1.  인터넷 정보 서비스 관리자\(inetmgr.exe\)를 엽니다.  
  
2.  **연결** 창에서 OrderService 가상 디렉터리로 이동합니다.  
  
3.  OrderService를 마우스 오른쪽 단추로 클릭하고 **WCF 및 WF 서비스 관리**, **구성…**을 차례로 선택합니다.**응용 프로그램에 대해 WCF 및 WF 구성** 대화 상자가 표시됩니다.  
  
4.  **일반** 탭을 선택하여 다음 스크린 샷과 같이 응용 프로그램에 대한 일반 정보를 표시합니다.  
  
     ![App Fabric 구성 대화 상자의 일반 탭](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-general.gif "AppFabricConfiguration\-General")  
  
5.  **모니터링** 탭을 선택합니다.다음 스크린 샷과 같이 다양한 모니터링 설정이 표시됩니다.  
  
     ![App Fabric 구성 모니터링 탭](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-monitoring.gif "AppFabricConfiguration\-Monitoring")  
  
     App Fabric에서 워크플로 서비스 모니터링을 구성하는 방법[!INCLUDE[crabout](../../../../includes/crabout-md.md)][모니터링 구성](http://go.microsoft.com/fwlink/?LinkId=193153)을 참조하십시오.  
  
6.  **워크플로 지속성** 탭을 선택합니다.여기에서는 다음 스크린 샷과 같이 App Fabric의 기본 지속성 공급자를 사용하도록 응용 프로그램을 구성할 수 있습니다.  
  
     ![App Fabric 구성 &#45; 지속성](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-persistence.gif "AppFabricConfiguration\-Persistence")  
  
     Windows Server App Fabric에서 워크플로 지속성을 구성하는 방법[!INCLUDE[crabout](../../../../includes/crabout-md.md)][워크플로 지속성 구성](http://go.microsoft.com/fwlink/?LinkId=193148)을 참조하십시오.  
  
7.  **워크플로 호스트 관리** 탭을 선택합니다.여기에서는 다음 스크린 샷과 같이 유휴 워크플로 서비스 인스턴스가 언로드되고 유지되는 때를 지정할 수 있습니다.  
  
     ![App Fabric 구성 워크플로 호스트 관리](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-management.gif "AppFabricConfiguration\-Management")  
  
     워크플로 호스트 관리 구성[!INCLUDE[crabout](../../../../includes/crabout-md.md)][워크플로 호스트 관리 구성](http://go.microsoft.com/fwlink/?LinkId=193151)을 참조하십시오.  
  
8.  **자동 시작** 탭을 선택합니다.여기에서는 다음 스크린 샷과 같이 응용 프로그램에서 워크플로 서비스에 대한 자동 시작 설정을 지정할 수 있습니다.  
  
     ![App Fabric 자동 시작 구성](../../../../docs/framework/wcf/feature-details/media/appfabricconfigurationautostart.gif "AppFabricConfigurationAutostart")  
  
     자동 시작 구성[!INCLUDE[crabout](../../../../includes/crabout-md.md)][자동 시작 구성](http://go.microsoft.com/fwlink/?LinkId=193150)을 참조하십시오.  
  
9. **제한** 탭을 선택합니다.여기에서는 다음 스크린 샷과 같이 워크플로 서비스에 대한 제한 설정을 구성할 수 있습니다.  
  
     ![App Fabric 구성 제한](../../../../docs/framework/wcf/feature-details/media/appfabricconfigurationthrottling.gif "AppFabricConfigurationThrottling")  
  
     제한 구성[!INCLUDE[crabout](../../../../includes/crabout-md.md)][App Fabric 제한 구성](http://go.microsoft.com/fwlink/?LinkId=193149)을 참조하십시오.  
  
10. **보안** 탭을 선택합니다.여기에서는 다음 스크린 샷과 같이 응용 프로그램에 대한 보안 설정을 구성할 수 있습니다.  
  
     ![App Fabric 보안 구성](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-security.gif "AppFabricConfiguration\-Security")  
  
     Windows Server App Fabric에서 보안을 구성하는 방법[!INCLUDE[crabout](../../../../includes/crabout-md.md)][보안 구성](http://go.microsoft.com/fwlink/?LinkId=193152)을 참조하십시오.  
  
### Windows Server App Fabric 사용  
  
1.  솔루션을 빌드하여 필요한 파일을 가상 디렉터리에 복사합니다.  
  
2.  OrderClient 프로젝트를 마우스 오른쪽 단추로 클릭하고 **디버그**, **새 인스턴스 시작**을 차례로 선택하여 클라이언트 응용 프로그램을 시작합니다.  
  
3.  클라이언트가 실행되고 Visual Studio에서 **연결 보안 경고** 대화 상자가 표시되면 **연결 안 함** 단추를 클릭합니다.이렇게 하면 Visual Studio에서 디버깅을 위해 IIS 프로세스에 연결하지 않습니다.  
  
4.  클라이언트 응용 프로그램은 워크플로 서비스를 즉시 호출한 다음 기다립니다.워크플로 서비스는 유휴 상태가 되고 유지됩니다.인터넷 정보 서비스\(inetmgr.exe\)를 시작하고 연결 창에서 OrderService로 이동한 다음 선택하여 이를 확인할 수 있습니다.그런 다음 오른쪽 창에서 App Fabric 대시보드 아이콘을 클릭합니다.지속된 WF 인스턴스 아래에 다음 스크린 샷과 같이 유지된 워크플로 서비스 인스턴스가 하나 있습니다.  
  
     ![App Fabric 대시보드](../../../../docs/framework/wcf/feature-details/media/appfabricdashboard.gif "AppFabricDashboard")  
  
     **WF 인스턴스 기록**에는 워크플로 서비스 활성화 수, 워크플로 서비스 인스턴스 완료 수 및 오류가 있는 워크플로 인스턴스 수와 같은 워크플로 서비스에 대한 정보가 표시됩니다.활성 또는 유휴 인스턴스 아래에 링크가 표시됩니다. 이 링크를 클릭하면 다음 스크린 샷과 같이 유휴 워크플로 인스턴스에 대한 자세한 정보가 표시됩니다.  
  
     ![지속된 워크플로 인스턴스 세부 정보](../../../../docs/framework/wcf/feature-details/media/persisteddetail.gif "PersistedDetail")  
  
     Window Server App Fabric 기능과 사용 방법에 대한 자세한 내용은 [Windows Server App Fabric 호스팅 기능](http://go.microsoft.com/fwlink/?LinkID=193143&clcid=0x412)\(영문 페이지일 수 있음\)을 참조하십시오.  
  
## 참고 항목  
 [장기 실행 워크플로 서비스 만들기](../../../../docs/framework/wcf/feature-details/creating-a-long-running-workflow-service.md)   
 [AppFabric 호스팅 기능](http://go.microsoft.com/fwlink/?LinkId=193143)   
 [Windows Server AppFabric 설치](http://go.microsoft.com/fwlink/?LinkId=193136)   
 [Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=193037&clcid=0x412)