---
title: '방법: Windows Server AppFabric을 사용하여 워크플로 서비스 호스팅'
ms.date: 03/30/2017
ms.assetid: 83b62cce-5fc2-4c6d-b27c-5742ba3bac73
ms.openlocfilehash: a1e2312beed61b340e034a48c36f739e799b1bf8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33495843"
---
# <a name="how-to-host-a-workflow-service-with-windows-server-app-fabric"></a>방법: Windows Server AppFabric을 사용하여 워크플로 서비스 호스팅
AppFabric에서 워크플로 서비스를 호스팅하는 것은 IIS/WAS에서 호스팅하는 것과 유사합니다. 유일한 차이점은 AppFabric에서 워크플로 서비스의 배포, 모니터링 및 관리를 위해 제공하는 도구입니다. 이 항목에서는에서 만든 워크플로 서비스는 [장기 실행 워크플로 서비스를 만드는](../../../../docs/framework/wcf/feature-details/creating-a-long-running-workflow-service.md)합니다. 이 항목에서는 워크플로 서비스를 만드는 방법을 안내하며, AppFabric을 사용하여 워크플로 서비스를 호스팅하는 방법을 설명합니다. Windows Server App Fabric에 대 한 자세한 내용은 참조 [Windows Server App Fabric 문서](http://go.microsoft.com/fwlink/?LinkID=193037&clcid=0x409)합니다. 아래의 단계를 완료하기 전에 Windows Server AppFabric이 설치되어 있는지 확인합니다.  인터넷 정보 서비스 (inetmgr.exe)를이 열고를 수행 하려면 서버 이름을 클릭는 **연결** 사이트를 클릭 하 고 클릭 **기본 웹 사이트**합니다. 화면 오른쪽에 있는 섹션이 표시 되어야 **App Fabric**합니다. 이 섹션(오른쪽 창의 맨 위에 있음)이 없으면 AppFabric이 설치되지 않은 것입니다. Windows Server Appfabric을 설치 하는 방법에 대 한 자세한 내용은 참조 [설치 Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=193136)합니다.  
  
### <a name="creating-a-simple-workflow-service"></a>간단한 워크플로 서비스 만들기  
  
1.  열기 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 에서 만든 OrderProcessing 솔루션을 로드 하 고는 [장기 실행 워크플로 서비스를 만드는](../../../../docs/framework/wcf/feature-details/creating-a-long-running-workflow-service.md) 항목입니다.  
  
2.  마우스 오른쪽 단추로 클릭는 **OrderService** 프로젝트를 마우스 선택 **속성** 선택 하 고는 **웹** 탭 합니다.  
  
3.  에 **시작 작업** 속성 페이지의 섹션 선택 **특정 페이지** 편집 상자에 Service1.xamlx를 입력 합니다.  
  
4.  에 **서버** 속성 페이지의 섹션을 선택 **로컬 IIS 웹 서버 사용** 및 다음 url에서 형식: `http://localhost/OrderService`합니다.  
  
5.  클릭는 **가상 디렉터리 만들기** 단추입니다. 새 가상 디렉터리가 만들어지고 프로젝트가 빌드될 때 이 가상 디렉터리에 필요한 파일을 복사하도록 프로젝트가 설정됩니다.  또는 .xamlx, web.config 및 필요한 DLL을 가상 디렉터리에 수동으로 복사할 수 있습니다.  
  
### <a name="configuring-a-workflow-service-hosted-in-windows-server-app-fabric"></a>Windows Server AppFabric에서 호스팅되는 워크플로 서비스 구성  
  
1.  인터넷 정보 서비스 관리자(inetmgr.exe)를 엽니다.  
  
2.  OrderService 가상 디렉터리로 이동 된 **연결** 창.  
  
3.  OrderService를 마우스 오른쪽 단추로 클릭 하 고 선택 **WCF 및 WF 서비스 관리**, **구성 중...** . **WCF 및 WF 응용 프로그램에 대 한 구성** 대화 상자가 표시 됩니다.  
  
4.  선택 된 **일반** 다음 스크린 샷과 같이 응용 프로그램에 대 한 일반 정보를 표시 하려면 탭 합니다.  
  
     ![App Fabric 구성 대화 상자의 일반 탭](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-general.gif "AppFabricConfiguration-일반")  
  
5.  선택 된 **모니터링** 탭 합니다. 다음 스크린 샷과 같이 다양한 모니터링 설정이 표시됩니다.  
  
     ![App Fabric Configuration Monitoring 탭](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-monitoring.gif "AppFabricConfiguration 모니터링")  
  
     워크플로 서비스를 구성 하는 방법에 대 한 자세한 내용은 참조에서 App Fabric 모니터링 [App Fabric로 모니터링 구성](http://go.microsoft.com/fwlink/?LinkId=193153)합니다.  
  
6.  선택 된 **워크플로 지 속성** 탭 합니다. 여기에서는 다음 스크린 샷과 같이 AppFabric의 기본 지속성 공급자를 사용하도록 응용 프로그램을 구성할 수 있습니다.  
  
     ![App Fabric 구성 &#45; 지 속성](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-persistence.gif "AppFabricConfiguration 지 속성")  
  
     Windows Server Appfabric에서 워크플로 지 속성을 구성 하는 방법에 대 한 자세한 내용은 참조 [Appfabric에서 워크플로 지 속성 구성](http://go.microsoft.com/fwlink/?LinkId=193148)합니다.  
  
7.  선택 된 **워크플로 호스트 관리** 탭 합니다. 여기에서는 다음 스크린 샷과 같이 유휴 워크플로 서비스 인스턴스가 언로드되고 유지되는 때를 지정할 수 있습니다.  
  
     ![App Fabric 구성 워크플로 호스트 관리](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-management.gif "AppFabricConfiguration 관리")  
  
     워크플로 호스트 관리 구성에 대 한 자세한 내용은 참조 [Appfabric에서 워크플로 호스트 관리 구성](http://go.microsoft.com/fwlink/?LinkId=193151)합니다.  
  
8.  선택 된 **자동 시작** 탭 합니다. 여기에서는 다음 스크린 샷과 같이 응용 프로그램에서 워크플로 서비스에 대한 자동 시작 설정을 지정할 수 있습니다.  
  
     ![App Fabric 자동&#45;구성을 시작](../../../../docs/framework/wcf/feature-details/media/appfabricconfigurationautostart.gif "AppFabricConfigurationAutostart")  
  
     자동 시작 구성 하는 방법에 대 한 자세한 내용은 참조 [구성 자동 시작 App Fabric로](http://go.microsoft.com/fwlink/?LinkId=193150)합니다.  
  
9. 선택 된 **제한** 탭 합니다. 여기에서는 다음 스크린 샷과 같이 워크플로 서비스에 대한 제한 설정을 구성할 수 있습니다.  
  
     ![App Fabric 구성 스로틀](../../../../docs/framework/wcf/feature-details/media/appfabricconfigurationthrottling.gif "AppFabricConfigurationThrottling")  
  
     조정 구성에 대 한 자세한 내용은 참조 [App Fabric로 제한 구성](http://go.microsoft.com/fwlink/?LinkId=193149)합니다.  
  
10. 선택 된 **보안** 탭 합니다. 여기에서는 다음 스크린 샷과 같이 응용 프로그램에 대한 보안 설정을 구성할 수 있습니다.  
  
     ![App Fabric 보안 구성](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-security.gif "AppFabricConfiguration 보안")  
  
     Windows Server Appfabric을 사용 하 여 보안을 구성 하는 방법에 대 한 자세한 내용은 참조 [App Fabric로 보안 구성](http://go.microsoft.com/fwlink/?LinkId=193152)합니다.  
  
### <a name="using-windows-server-app-fabric"></a>Windows Server AppFabric 사용  
  
1.  솔루션을 빌드하여 필요한 파일을 가상 디렉터리에 복사합니다.  
  
2.  OrderClient 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **디버그**, **새 인스턴스 시작** 클라이언트 응용 프로그램을 시작 합니다.  
  
3.  클라이언트가 실행 되 고 이름이 표시 됩니다는 **연결 보안 경고** 대화 상자를 클릭는 **연결 안 함** 단추입니다. 이렇게 하면 Visual Studio에서 디버깅을 위해 IIS 프로세스에 연결하지 않습니다.  
  
4.  클라이언트 응용 프로그램은 워크플로 서비스를 즉시 호출한 다음 기다립니다. 워크플로 서비스는 유휴 상태가 되고 유지됩니다. 인터넷 정보 서비스(inetmgr.exe)를 시작하고 연결 창에서 OrderService로 이동한 다음 선택하여 이를 확인할 수 있습니다. 그런 다음 오른쪽 창에서 AppFabric 대시보드 아이콘을 클릭합니다. 지속된 WF 인스턴스 아래에 다음 스크린 샷과 같이 유지된 워크플로 서비스 인스턴스가 하나 있습니다.  
  
     ![App Fabric 대시보드](../../../../docs/framework/wcf/feature-details/media/appfabricdashboard.gif "AppFabricDashboard")  
  
     **WF 인스턴스 기록** 워크플로 서비스 정품 인증 수, 워크플로 서비스 인스턴스 완료 수 및 오류가 있는 워크플로 인스턴스 수와 같은 워크플로 서비스에 대 한 정보를 나열 합니다. 활성 또는 유휴 인스턴스 아래에 링크가 표시됩니다. 이 링크를 클릭하면 다음 스크린 샷과 같이 유휴 워크플로 인스턴스에 대한 자세한 정보가 표시됩니다.  
  
     ![지속형 워크플로 인스턴스 정보](../../../../docs/framework/wcf/feature-details/media/persisteddetail.gif "PersistedDetail")  
  
     Windows Server App Fabric에 대 한 자세한 내용은 기능 및 사용 하는 방법 참조 [Windows Server App Fabric 호스팅 기능](http://go.microsoft.com/fwlink/?LinkID=193143&clcid=0x409)  
  
## <a name="see-also"></a>참고 항목  
 [장기 실행 워크플로 서비스 만들기](../../../../docs/framework/wcf/feature-details/creating-a-long-running-workflow-service.md)  
 [Windows Server App Fabric 호스팅 기능](http://go.microsoft.com/fwlink/?LinkId=193143)  
 [Windows Server Appfabric 설치](http://go.microsoft.com/fwlink/?LinkId=193136)  
 [Windows Server App Fabric 문서](http://go.microsoft.com/fwlink/?LinkID=193037&clcid=0x409)
