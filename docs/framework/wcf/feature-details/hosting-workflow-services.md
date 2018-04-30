---
title: 워크플로 서비스 호스팅
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d55217e-8697-4113-94ce-10b60863342e
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e9f8d38b97a422d2d59e2dea05d53cf6f9684d99
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="hosting-workflow-services"></a>워크플로 서비스 호스팅
워크플로 서비스가 들어오는 메시지에 응답하기 위해서는 해당 워크플로 서비스를 호스팅해야 합니다. 워크플로 서비스는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 메시징 인프라를 사용하기 때문에 비슷한 방식으로 호스팅됩니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스와 마찬가지로 워크플로 서비스는 모든 관리되는 응용 프로그램, IIS(인터넷 정보 서비스) 또는 WAS(Windows Process Activation Services)에서 호스팅할 수 있습니다. 또한 워크플로 서비스는 Windows Server AppFabric에서 호스팅할 수 있습니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] Windows Server App Fabric 참조 [Windows Server App Fabric 설명서](http://go.microsoft.com/fwlink/?LinkId=193037), [AppFabric 호스팅 기능](http://go.microsoft.com/fwlink/?LinkId=196494), 및 [AppFabric 호스팅 개념](http://go.microsoft.com/fwlink/?LinkId=196495)합니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] 호스트 하는 여러 가지 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 참조 [호스팅 서비스](../../../../docs/framework/wcf/hosting-services.md)합니다.  
  
## <a name="hosting-in-a-managed-application"></a>관리되는 응용 프로그램에서 호스팅  
 관리되는 응용 프로그램에서 워크플로 서비스를 호스팅하려면 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 클래스를 사용합니다. <xref:System.ServiceModel.Activities.WorkflowServiceHost> 생성자를 사용하면 singleton 워크플로 서비스 인스턴스, 워크플로 서비스 정의 또는 워크플로 메시징 작업을 사용하는 작업을 지정할 수 있습니다. 호출 <<!--zz xref:System.ServiceModel.Activities.WorkflowServiceHost.Open%2A--> `System.ServiceModel.Activities.WorkflowServiceHost.Open`> 하면 서비스가 들어오는 메시지를 수신 대기를 시작 합니다.  
  
## <a name="hosting-under-iis-or-was"></a>IIS 또는 WAS에서 호스팅  
 IIS 또는 WAS에서 워크플로 서비스를 호스팅하는 작업에는 가상 디렉터리를 만들고 이 가상 디렉터리에 서비스와 해당 동작을 정의하는 파일을 저장하는 작업이 포함됩니다. IIS 또는 WAS에서는 다음과 같은 여러 가지 방법으로 워크플로 서비스를 호스팅할 수 있습니다.  
  
-   워크플로 서비스를 정의하는 .xamlx 파일을 서비스 동작, 끝점 및 기타 구성 요소를 지정하는 Web.config 파일과 함께 IIS/WAS 가상 디렉터리에 저장합니다.  
  
-   워크플로 서비스를 정의하는 .xamlx 파일을 IIS/WAS 가상 디렉터리에 저장합니다. .xamlx 파일을 사용하면 노출할 끝점을 지정할 수 있습니다. 끝점은 다음 예제와 같이 `WorkflowService.Endpoints` 요소에 지정됩니다.  
  
    ```xml  
    <WorkflowService xmlns="http://schemas.microsoft.com/netfx/2009/xaml/servicemodel"  xmlns:p1="http://schemas.microsoft.com/netfx/2009/xaml/activities" xmlns:sad="clr-namespace:System.Activities.Debugger;assembly=System.Activities" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
      <WorkflowService.Endpoints>  
        <Endpoint ServiceContractName="IWorkFlowEchoService" AddressUri="">  
          <Endpoint.Binding>  
            <BasicHttpBinding />  
          </Endpoint.Binding>  
        </Endpoint>  
      </WorkflowService.Endpoints>  
    <!-- ... -->  
    </WorkflowService>  
    ```  
  
    > [!NOTE]
    >  .xamlx 파일에는 동작을 지정할 수 없으므로 동작 설정을 지정해야 하는 경우에는 Web.config를 사용해야 합니다.  
  
-   워크플로 서비스를 정의하는 .xamlx 파일을 IIS/WAS 가상 디렉터리에 저장합니다. 또한 .svc 파일도 IIS/WAS 가상 디렉터리에 저장합니다. .svc 파일을 사용하면 사용자 지정 웹 서비스 호스트 팩터리를 지정하거나, 사용자 지정 동작을 적용하거나, 사용자 지정 위치에서 구성을 로드할 수 있습니다.  
  
-   IIS/WAS 가상 디렉터리에 WCF 메시징 작업을 사용하는 작업이 포함된 어셈블리를 저장합니다.  
  
 워크플로 서비스를 정의 하는.xamlx 파일을 포함 해야 합니다는 <`Service`>에서 파생 된 형식을 포함 하는 루트 요소 또는 루트 요소 <xref:System.Workflow.ComponentModel.Activity>합니다. .xamlx 파일은 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 작업 템플릿을 사용하거나 WCF 워크플로 서비스 템플릿을 사용할 때 만들어집니다.  
  
## <a name="hosting-workflow-services-under-windows-server-app-fabric"></a>Windows Server AppFabric에서 워크플로 서비스 호스팅  
 Windows Server AppFabric에서 워크플로 서비스를 호스팅하는 것은 IIS/WAS에서 호스팅하는 것과 동일합니다. 유일한 차이점은 Windows Server AppFabric이 설치된다는 것입니다. Windows Server AppFabric은 PowerShell cmdlet뿐만 아니라 인터넷 정보 서비스 관리자에 추가되는 도구도 제공합니다. 이러한 도구를 사용하면 워크플로 서비스와 WCF 서비스의 배포, 관리 및 추적을 간단하게 수행할 수 있습니다. 이어야 합니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] Windows Server App Fabric 참조 [Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=193037)  
  
## <a name="referencing-custom-activities"></a>사용자 지정 작업 참조  
 사용자 지정 활동에 대 한 참조를 추가 해야는 <`Assemblies`> 아래의 <`System.Web.Compilation`> 응용 프로그램 도메인에 로드 된 XAML 역직렬 변환기가 형식을 찾을 수 있도록 합니다. 이러한 설정은 응용 프로그램 수준에서 만들거나 컴퓨터의 모든 응용 프로그램에 설정을 적용해야 하는 경우 루트 Web.config에서 만들 수 있습니다.  
  
## <a name="deployment"></a>배포  
 웹 배포 도구는 배포 작업을 보다 쉽게 수행할 수 있도록 하기 위해 만들어졌습니다. 이 도구를 사용하면 IIS 6.0과 IIS 7.0 사이에서 응용 프로그램을 마이그레이션하고, 서버 팜을 동기화하고, 웹 응용 프로그램을 패키징, 보관 및 배포할 수 있습니다. 자세한 내용은 참조 [MS 배포 도구](http://go.microsoft.com/fwlink/?LinkId=178690)  
  
## <a name="see-also"></a>참고 항목  
 [워크플로 서비스 호스트 내부 기능](../../../../docs/framework/wcf/feature-details/workflow-service-host-internals.md)  
 [WorkflowServiceHost 구성](../../../../docs/framework/wcf/feature-details/configuring-workflowservicehost.md)
