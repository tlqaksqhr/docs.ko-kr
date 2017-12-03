---
title: "Windows에서 이벤트 추적으로 이벤트 추적"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f812659b-0943-45ff-9430-4defa733182b
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 12dd8ee58b577df1ef7d54e8f820ff183cef6084
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="tracking-events-into-event-tracing-in-windows"></a>Windows에서 이벤트 추적으로 이벤트 추적
이 샘플에서는 워크플로 서비스에 대해 [!INCLUDE[wf](../../../../includes/wf-md.md)] 추적을 사용하고 ETW(Windows용 이벤트 추적)에 추적 이벤트를 내보내는 방법을 보여 줍니다. 이 샘플에서는 ETW 추적 참가자(<xref:System.Activities.Tracking.EtwTrackingParticipant>)를 사용하여 워크플로 추적 레코드를 ETW로 내보냅니다.  
  
 샘플에서 워크플로는 요청을 받고, 입력 데이터의 상호 데이터를 입력 변수에 할당한 다음, 클라이언트에 상호 데이터를 다시 반환합니다. 입력 데이터가 0인 경우 처리되지 않는 0으로 나누기 예외가 발생하여 워크플로가 중단됩니다. 추적 기능을 사용하도록 설정되어 있으면 오류 추적 레코드가 ETW로 내보내지므로 나중에 오류 문제를 해결하는 데 도움이 됩니다. ETW 추적 참가자는 추적 레코드를 구독하도록 추적 프로필을 사용하여 구성됩니다. 추적 프로필은 Web.config 파일에 정의되고 ETW 추적 참가자에 구성 매개 변수로 제공됩니다. ETW 추적 참가자는 워크플로 서비스의 Web.config 파일에 구성되며 서비스에 서비스 동작으로 적용됩니다. 이 샘플에서는 이벤트 뷰어를 사용하여 이벤트 로그의 추적 이벤트를 확인합니다.  
  
## <a name="workflow-tracking-details"></a>워크플로 추적 세부 정보  
 [!INCLUDE[wf2](../../../../includes/wf2-md.md)]은 워크플로 인스턴스 실행을 추적하기 위한 추적 인프라를 제공합니다. 추적 런타임은 워크플로 인스턴스를 만들어 워크플로 수명 주기와 관련된 이벤트, 워크플로 활동의 이벤트 및 사용자 지정 이벤트를 내보냅니다. 다음 표에서는 추적 인프라의 기본 구성 요소에 대해 자세히 설명합니다  
  
|구성 요소|설명|  
|---------------|-----------------|  
|추적 런타임|추적 레코드를 내보낼 인프라를 제공합니다.|  
|추적 참가자|추적 레코드에 액세스합니다. [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)]에는 추적 레코드를 ETW(Windows용 이벤트 추적) 이벤트로 기록하는 추적 참가자가 제공됩니다.|  
|추적 프로필|추적 참가자가 워크플로 인스턴스에서 내보낸 추적 레코드의 하위 집합을 구독할 수 있도록 하는 필터링 메커니즘입니다.|  
  
 다음 표에서는 워크플로 런타임에서 내보내는 추적 레코드에 대해 자세히 설명합니다.  
  
|추적 레코드|설명|  
|---------------------|-----------------|  
|워크플로 인스턴스 추적 레코드|워크플로 인스턴스의 수명 주기에 대해 설명합니다. 예를 들어 워크플로가 시작되거나 완료되면 인스턴스 레코드를 내보냅니다.|  
|활동 상태 추적 레코드|활동 실행에 대해 자세히 설명합니다. 이러한 레코드는 활동이 예약된 시점, 활동이 완료된 시점, 오류가 throw된 시점 등과 같은 워크플로 활동 상태를 나타냅니다.|  
|책갈피 다시 시작 레코드|워크플로 인스턴스 내의 책갈피를 다시 시작할 때마다 내보냅니다.|  
|사용자 지정 추적 레코드|워크플로 작성자가 사용자 지정 추적 레코드를 만들어 사용자 지정 활동 중에 내보낼 수 있습니다.|  
|<xref:System.Activities.Tracking.ActivityScheduledRecord>|이 레코드는 활동이 다른 활동을 예약할 때 내보내집니다.|  
|<xref:System.Activities.Tracking.FaultPropagationRecord>|이 레코드는 활동에서 오류가 전파될 때 내보내집니다.|  
|<xref:System.Activities.Tracking.CancelRequestedRecord>|이 레코드는 활동이 다른 활동에 의해 취소될 때 내보내집니다.|  
  
 추적 참가자는 추적 프로필을 사용하여 내보낸 추적 레코드의 하위 집합을 구독합니다. 추적 프로필에는 특정 추적 레코드 형식을 구독할 수 있도록 허용하는 추적 쿼리가 포함됩니다. 추적 프로필은 코드나 구성에 지정할 수 있습니다.  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 EtwTrackingParticipantSample.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  F5 키를 눌러 솔루션을 실행합니다.  
  
     기본적으로 서비스는 포트 53797(http://localhost:53797/SampleWorkflowService.xamlx)에서 수신 대기하고 있습니다.  
  
4.  [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]를 사용하여 WCF 테스트 클라이언트를 엽니다.  
  
     WCF 테스트 클라이언트 (WcfTestClient.exe)에 \< [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 설치 폴더 > \Common7\IDE\ 폴더입니다.  
  
     기본 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 설치 폴더는 C:\Program Files\Microsoft Visual Studio 10.0입니다.  
  
5.  WCF 테스트 클라이언트에서 선택 **서비스 추가** 에서 **파일** 메뉴.  
  
     입력 상자에 끝점 주소를 추가합니다. 기본값은 http://localhost:53797/SampleWorkflowService.xamlx입니다.  
  
6.  이벤트 뷰어 응용 프로그램을 엽니다.  
  
     이벤트 뷰어를 시작 서비스를 호출 하기 전에 **시작** 메뉴 선택 **실행** 에 입력 하 고 `eventvwr.exe`합니다. 이벤트 로그가 워크플로 서비스에서 내보낸 추적 이벤트를 수신 대기하고 있는지 확인합니다.  
  
7.  이벤트 뷰어의 트리 뷰에서 이동 **이벤트 뷰어**, **Applications and Services Logs**, 및 **Microsoft**합니다. 마우스 오른쪽 단추로 클릭 **Microsoft** 선택 **보기** 차례로 **분석 및 디버그 로그 표시** 사용 분석 및 디버그 로그에  
  
     확인 된 **분석 및 디버그 로그 표시** 옵션을 선택 합니다.  
  
8.  이벤트 뷰어의 트리 뷰에서 이동 **이벤트 뷰어**, **Applications and Services Logs**, **Microsoft**, **Windows**,  **응용 프로그램 서버-응용 프로그램**합니다. 마우스 오른쪽 단추로 클릭 **분석** 선택 **로그 사용** 사용할 수 있도록는 **분석** 로그 합니다.  
  
9. `GetData`를 두 번 클릭하여 WCF 테스트 클라이언트로 서비스를 테스트합니다.  
  
     그러면 `GetData` 메서드가 열립니다. 요청은 하나의 매개 변수를 받아들이고 값이 기본값인 0인지 확인합니다.  
  
     클릭 **호출**합니다.  
  
10. 워크플로에서 내보낸 이벤트를 확인합니다.  
  
     이벤트 뷰어로 다시 전환한 이동한 **이벤트 뷰어**, **Applications and Services Logs**, **Microsoft**, **Windows**,  **응용 프로그램 서버-응용 프로그램**합니다. 마우스 오른쪽 단추로 클릭 **분석** 선택 **새로 고침**합니다.  
  
     이벤트 뷰어에 워크플로 이벤트가 표시됩니다. 워크플로 실행 이벤트가 표시되며, 이 중 하나는 워크플로의 오류에 해당하는 처리되지 않은 예외입니다. 또한 워크플로 활동에서 경고 이벤트를 내보내며 이는 활동이 오류를 throw할 것임을 나타냅니다.  
  
11. 오류가 throw되지 않도록 0 이외의 입력 데이터를 사용하여 9단계와 10단계를 반복합니다.  
  
 추적 프로필을 사용하면 워크플로 인스턴스 상태가 변경될 때 런타임에서 내보내는 이벤트를 구독할 수 있습니다. 모니터링 요구 사항에 따라 워크플로에서 상위 수준의 상태 변경 내용 중 작은 부분만 구독하는 매우 개괄적인 프로필을 만들 수 있습니다. 그러나 나중에 실행을 다시 생성할 수 있을 정도로 출력이 풍부한 매우 정확한 프로필을 만들 수 있습니다. 이 샘플에서는 작은 이벤트 집합을 내보내는 `HealthMonitoring Tracking Profile`을 사용하여 워크플로 런타임에서 ETW로 내보내는 이벤트를 보여 줍니다. 추가 워크플로 추적 이벤트를 내보내는 다른 프로필도 `Troubleshooting Tracking Profile`이라는 Web.config에 제공됩니다. [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)]가 설치되어 있으면 Machine.config 파일에 이름이 비어 있는 기본 프로필이 구성됩니다. 프로필 이름을 지정하지 않았거나 빈 프로필 이름을 지정한 경우에는 ETW 추적 동작 구성에서 이 프로필을 사용합니다.  
  
 상태 모니터링 추적 프로필은 워크플로 인스턴스 레코드와 활동 오류 전파 레코드를 내보냅니다. 이 프로필은 Web.config 구성 파일에 다음 추적 프로필을 추가하여 만듭니다.  
  
```xml  
<<tracking>  
      <profiles>  
        <trackingProfile name="HealthMonitoring Tracking Profile">  
          <workflow activityDefinitionId="*">  
            <workflowInstanceQueries>  
              <workflowInstanceQuery>  
                <states>  
                  <state name="Started"/>  
                  <state name="Completed"/>  
                  <state name="Aborted"/>  
                  <state name="UnhandledException"/>  
                </states>  
            </workflowInstanceQuery>  
           </workflowInstanceQueries>  
            <faultPropagationQueries>  
              <faultPropagationQuery faultSourceActivityName ="*" faultHandlerActivityName="*"/>  
            </faultPropagationQueries>  
          </workflow>  
        </trackingProfile>  
       </profiles>  
</tracking>  
```  
  
 `EtwTrackingParticipant` 구성을 다음 내용으로 변경하여 프로필을 변경할 수 있습니다.  
  
```xml  
<behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <etwTracking profileName="HealthMonitoring Tracking Profile"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
#### <a name="to-clean-up-optional"></a>정리하려면(옵션)  
  
1.  이벤트 뷰어를 엽니다.  
  
2.  로 이동 **이벤트 뷰어**, **Applications and Services Logs**, **Microsoft**, **Windows**, **응용 프로그램 서버-응용 프로그램**합니다. 마우스 오른쪽 단추로 클릭 **분석** 선택 **로그 사용 안 함**합니다.  
  
3.  로 이동 **이벤트 뷰어**, **Applications and Services Logs**, **Microsoft**, **Windows**, **응용 프로그램 서버-응용 프로그램**합니다. 마우스 오른쪽 단추로 클릭 **분석** 선택 **로그 지우기**합니다.  
  
4.  선택 된 **지우기** 이벤트를 해결 하는 옵션입니다.  
  
## <a name="known-issue"></a>알려진 문제  
  
> [!NOTE]
>  ETW 이벤트가 디코딩되지 않을 수 있으며, 이는 이벤트 뷰어와 관련하여 알려진 문제입니다. 다음과 같은 오류 메시지가 표시될 수 있습니다.  
>   
>  이벤트 ID에 대 한 설명 \<id > Microsoft-Windows-응용 프로그램 서버-응용 프로그램을 찾을 수 없는 소스에서 합니다. 이 이벤트를 발생시킨 구성 요소가 로컬 컴퓨터에 설치되어 있지 않거나 설치가 손상되었습니다. 로컬 컴퓨터에서 구성 요소를 설치 또는 복구할 수 있습니다.  
>   
>  이 오류가 발생하면 동작 창에서 새로 고침을 클릭합니다. 그러면 이벤트가 올바르게 디코딩됩니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\EtwTracking`  
  
## <a name="see-also"></a>참고 항목  
 [AppFabric 모니터링 샘플](http://go.microsoft.com/fwlink/?LinkId=193959)
