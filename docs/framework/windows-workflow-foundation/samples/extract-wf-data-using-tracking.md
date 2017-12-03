---
title: "추적을 사용하여 WF 데이터 추출"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e30c68f5-8c6a-495a-bd20-667a4364c68e
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 988dbef057b5980ac3f23b88c39669706d44557e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="extract-wf-data-using-tracking"></a>추적을 사용하여 WF 데이터 추출
이 샘플에서는 워크플로 추적을 사용하여 활동에서 워크플로 변수와 인수를 추출하는 방법을 보여 줍니다. 또한 여기에서는 추적 레코드에 주석을 추가하고 사용자 지정 추적 레코드 내의 데이터 페이로드를 추출하는 방법도 보여 줍니다. 이 샘플에서 워크플로의 데이터를 추출하는 데는 ETW(Event Tracing for Windows) 추적 참가자가 사용됩니다.  
  
## <a name="sample-details"></a>샘플 세부 정보  
 [!INCLUDE[wf](../../../../includes/wf-md.md)]에서는 워크플로 인스턴스의 실행을 시각적으로 추적할 수 있는 기능을 제공합니다. 추적 런타임에서는 워크플로를 실행하는 동안 워크플로 추적 레코드를 내보냅니다. 워크플로 추적 레코드와 함께 워크플로 인스턴스 내의 데이터를 워크플로에서 추출할 수 있습니다. 다음 목록에는 추적 레코드로부터 추출할 수 있는 데이터의 형식에 대한 자세한 설명이 나와 있습니다.  
  
1.  활동을 실행하는 동안의 활동 및 추적 레코드 내의 워크플로 변수.  
  
     워크플로 변수를 추출하려면 추출할 변수를 프로필에 지정해야 합니다. 추출할 변수를 지정하는 데는 `ActivityStateQueries`만 사용할 수 있습니다. 다음 코드 예제에서는 활동으로부터 워크플로 변수를 추출하는 데 사용되는 추적 프로필을 보여 줍니다.  
  
    ```xml  
    <activityStateQuery activityName="StockPriceService">  
         <states>  
              <state name="Closed"/>  
         </states>  
         <variables>  
              <variable name="symbol"/>  
         </variables>  
    </activityStateQuery>  
    ```  
  
2.  활동 인수 및 활동 상태 추적 레코드.  
  
     인수는 데이터가 활동을 드나들며 이동하는 방식을 정의합니다. 추출할 인수를 지정하는 데는 <xref:System.Activities.Tracking.ActivityStateQuery>를 사용합니다. 다음 코드 예제에서는 `Value` 인수를 추출하는 추적 프로필을 보여 줍니다.  
  
    ```xml  
    <activityStateQuery activityName="GetStockPrice">  
         <states>  
              <state name="Closed"/>  
         </states>  
         <arguments>  
              <argument name="Value"/>  
         </arguments>  
    </activityStateQuery>  
    ```  
  
3.  주석은 내보낸 임의의 추적 레코드에 추가할 수 있는 키/값 쌍입니다.  
  
     주석은 추적 레코드에 대한 태그 설정 메커니즘 역할을 합니다. 주석은 추적 프로필을 통해 추적 레코드에 추가됩니다. 주석을 추가할 수 있는 워크플로 추적 쿼리의 유형에는 제한이 없습니다. 다음 코드 예제에는 추적 레코드에 주석을 추가하는 방법을 보여 주는 추적 프로필이 나와 있습니다.  
  
    ```xml  
    <workflowInstanceQuery>  
         <states>  
              <state name="Started"/>  
         </states>  
         <annotations>  
              <annotation name="StockPriceWorkflow" value="Begin"/>  
         </annotations>  
    </workflowInstanceQuery>  
    ```  
  
4.  사용자 지정 추적 레코드는 사용자 정의 활동으로부터 내보내집니다.  
  
     사용자 지정 추적 레코드는 이 활동 내에 정의된 페이로드 데이터를 지닐 수 있습니다. 추적 프로필에서 사용자 지정 추적 레코드를 구독하면 추적 레코드 내의 페이로드를 추출할 수 있습니다. 사용자 지정 추적 레코드는 사용자 지정 <xref:System.Activities.Tracking.TrackingQuery>를 사용하여 추출할 수 있습니다. 다음 코드 예제에서는 사용자 지정 추적 레코드를 해당 페이로드와 함께 추출하는 추적 프로필을 보여 줍니다.  
  
    ```xml  
    <customTrackingQuery name="QuoteLookupEvent" activityName="GetStockPrice"/>  
    ```  
  
 이 샘플에서는 Web.config에 지정된 프로필을 사용하여 변수, 인수 및 사용자 지정 레코드를 추출하고 주석을 추가하는 방법을 보여 줍니다. 샘플 워크플로 서비스에 대해 추적 기능을 사용하기 위해 `<etwTracking>` 동작 요소를 추가합니다. 다음 코드 예제에서는 `ExtractWorkflowVariables` 추적 프로필에 대한 추적을 활성화합니다.  
  
```xml  
<serviceBehaviors>  
     <behavior>  
               <etwTracking profileName="ExtractWorkflowVariables"/>  
     </behavior>  
</serviceBehaviors>  
```  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 WFStockPriceApplication.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  F5 키를 눌러 솔루션을 실행합니다.  
  
     브라우저 창이 열리고 응용 프로그램의 디렉터리 목록이 표시됩니다.  
  
4.  브라우저에서 StockPriceService.xamlx를 클릭합니다.  
  
5.  브라우저에 StockPriceService 페이지가 표시됩니다. 이 페이지에는 로컬 서비스 WSDL 주소가 포함되어 있습니다. 이 주소를 복사합니다.  
  
     다음은 로컬 서비스 WSDL 주소의 예입니다. `http://localhost:53797/StockPriceService.xamlx?wsdl`  
  
6.  서비스를 호출하기 전에 이벤트 뷰어를 시작하고 이벤트 로그가 워크플로 서비스에서 내보낸 추적 이벤트를 수신 대기하고 있는지 확인합니다.  
  
7.  **시작** 메뉴 선택 **관리 도구** 차례로 **이벤트 뷰어**합니다.  
  
8.  이벤트 뷰어의 트리 뷰에서 이동 **이벤트 뷰어**, **Applications and Services Logs**, 및 **Microsoft**합니다. 마우스 오른쪽 단추로 클릭 **Microsoft** 선택 **보기** 차례로 **분석 및 디버그 로그 표시**합니다.  
  
     확인 된 **분석 및 디버그 로그 표시** 옵션을 선택 합니다.  
  
9. 이벤트 뷰어의 트리 뷰에서 이동 **이벤트 뷰어**, **Applications and Services Logs**, **Microsoft**, **Windows**,  **응용 프로그램 서버-응용 프로그램**합니다. 마우스 오른쪽 단추로 클릭 **분석** 선택 **로그 사용**합니다.  
  
10. [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]를 사용하여 WCF 테스트 클라이언트를 엽니다.  
  
     WCF 테스트 클라이언트 (WcfTestClient.exe)에 \< [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 설치 폴더 > \Common7\IDE\ 폴더입니다.  
  
     기본 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 설치 폴더는 C:\Program Files\Microsoft Visual Studio 10.0입니다.  
  
11. WCF 테스트 클라이언트에서 선택 **서비스 추가** 에서 **파일** 메뉴.  
  
     앞서 복사한 로컬 서비스 WSDL 주소를 입력 상자에 붙여넣습니다.  
  
12. WCF 테스트 클라이언트에서 `GetStockPrice`를 두 번 클릭합니다.  
  
     그러면 `GetStockPrice` 메서드가 열립니다. 요청에 매개 변수 한 개가 필요합니다. 값을 사용 하 여 **Contoso**합니다.  
  
13. 클릭 **호출**합니다.  
  
14. 이벤트 뷰어로 다시 전환한 이동한 **이벤트 뷰어**, **Applications and Services Logs**, **Microsoft**, **Windows**,  **응용 프로그램 서버-응용 프로그램**합니다. 마우스 오른쪽 단추로 클릭 **분석** 선택 **새로 고침**합니다. 워크플로 이벤트의 이벤트 ID 범위는 100-199입니다.  
  
     이벤트에 주석, 변수, 인수 및 사용자 지정 추적 레코드가 포함되어 있고 이러한 내용을 이벤트 뷰어에서 볼 수 있습니다.  
  
## <a name="cleaning-up-in-the-event-viewer"></a>이벤트 뷰어 정리  
 이벤트 뷰어에서 다음과 같이 이벤트 로그의 분석 채널을 정리할 수 있습니다.  
  
#### <a name="to-clean-up-optional"></a>정리하려면(옵션)  
  
1.  이벤트 뷰어를 엽니다.  
  
2.  로 이동 **이벤트 뷰어**, **Applications and Services Logs**, **Microsoft**, **Windows**, **응용 프로그램 서버-응용 프로그램**합니다. 마우스 오른쪽 단추로 클릭 **분석** 선택 **로그 사용 안 함**합니다.  
  
3.  로 이동 **이벤트 뷰어**, **Applications and Services Logs**, **Microsoft**, **Windows**, **응용 프로그램 서버-응용 프로그램**합니다. 마우스 오른쪽 단추로 클릭 **분석** 선택 **로그 지우기**합니다.  
  
     선택 된 **지우기** 이벤트를 해결 하는 옵션입니다.  
  
## <a name="known-issue"></a>알려진 문제  
  
> [!NOTE]
>  ETW 이벤트가 디코딩되지 않을 수 있으며, 이는 이벤트 뷰어와 관련하여 알려진 문제입니다. 다음과 같은 오류 메시지가 표시될 수 있습니다.  
>   
>  `The description for Event ID <id> from source Microsoft-Windows-Application Server-Applications cannot be found. Either the component that raises this event is not installed on your local computer or the installation is corrupted. You can install or repair the component on the local computer.`  
>   
>  이 오류를 발생 하는 경우 클릭 **새로 고침** 작업 창에서. 그러면 이벤트가 올바르게 디코딩됩니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\ExtractWfData`  
  
## <a name="see-also"></a>참고 항목  
 [AppFabric 모니터링 샘플](http://go.microsoft.com/fwlink/?LinkId=193959)
