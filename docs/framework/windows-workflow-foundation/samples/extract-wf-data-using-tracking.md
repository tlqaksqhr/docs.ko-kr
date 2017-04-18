---
title: "추적을 사용하여 WF 데이터 추출 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e30c68f5-8c6a-495a-bd20-667a4364c68e
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# 추적을 사용하여 WF 데이터 추출
이 샘플에서는 워크플로 추적을 사용하여 활동에서 워크플로 변수와 인수를 추출하는 방법을 보여 줍니다.또한 여기에서는 추적 레코드에 주석을 추가하고 사용자 지정 추적 레코드 내의 데이터 페이로드를 추출하는 방법도 보여 줍니다.이 샘플에서 워크플로의 데이터를 추출하는 데는 ETW\(Event Tracing for Windows\) 추적 참가자가 사용됩니다.  
  
## 샘플 세부 정보  
 [!INCLUDE[wf](../../../../includes/wf-md.md)]에서는 워크플로 인스턴스의 실행을 시각적으로 추적할 수 있는 기능을 제공합니다.추적 런타임에서는 워크플로를 실행하는 동안 워크플로 추적 레코드를 내보냅니다.워크플로 추적 레코드와 함께 워크플로 인스턴스 내의 데이터를 워크플로에서 추출할 수 있습니다.다음 목록에는 추적 레코드로부터 추출할 수 있는 데이터의 형식에 대한 자세한 설명이 나와 있습니다.  
  
1.  활동을 실행하는 동안의 활동 및 추적 레코드 내의 워크플로 변수.  
  
     워크플로 변수를 추출하려면 추출할 변수를 프로필에 지정해야 합니다.추출할 변수를 지정하는 데는 `ActivityStateQueries`만 사용할 수 있습니다.다음 코드 예제에서는 활동으로부터 워크플로 변수를 추출하는 데 사용되는 추적 프로필을 보여 줍니다.  
  
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
  
     인수는 데이터가 활동을 드나들며 이동하는 방식을 정의합니다.추출할 인수를 지정하는 데는 <xref:System.Activities.Tracking.ActivityStateQuery>를 사용합니다. 다음 코드 예제에서는 `Value` 인수를 추출하는 추적 프로필을 보여 줍니다.  
  
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
  
3.  주석은 내보낸 임의의 추적 레코드에 추가할 수 있는 키\/값 쌍입니다.  
  
     주석은 추적 레코드에 대한 태그 설정 메커니즘 역할을 합니다.주석은 추적 프로필을 통해 추적 레코드에 추가됩니다.주석을 추가할 수 있는 워크플로 추적 쿼리의 유형에는 제한이 없습니다.다음 코드 예제에는 추적 레코드에 주석을 추가하는 방법을 보여 주는 추적 프로필이 나와 있습니다.  
  
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
  
     사용자 지정 추적 레코드는 이 활동 내에 정의된 페이로드 데이터를 지닐 수 있습니다.추적 프로필에서 사용자 지정 추적 레코드를 구독하면 추적 레코드 내의 페이로드를 추출할 수 있습니다.사용자 지정 추적 레코드는 사용자 지정 <xref:System.Activities.Tracking.TrackingQuery>를 사용하여 추출할 수 있습니다.다음 코드 예제에서는 사용자 지정 추적 레코드를 해당 페이로드와 함께 추출하는 추적 프로필을 보여 줍니다.  
  
    ```  
    <customTrackingQuery name="QuoteLookupEvent" activityName="GetStockPrice"/>  
    ```  
  
 이 샘플에서는 Web.config에 지정된 프로필을 사용하여 변수, 인수 및 사용자 지정 레코드를 추출하고 주석을 추가하는 방법을 보여 줍니다.샘플 워크플로 서비스에 대해 추적 기능을 사용하기 위해 `<etwTracking>` 동작 요소를 추가합니다.다음 코드 예제에서는 `ExtractWorkflowVariables` 추적 프로필에 대한 추적을 활성화합니다.  
  
```  
<serviceBehaviors>  
     <behavior>  
               <etwTracking profileName="ExtractWorkflowVariables"/>  
     </behavior>  
</serviceBehaviors>  
```  
  
#### 이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 WFStockPriceApplication.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl\+Shift\+B를 눌러 솔루션을 빌드합니다.  
  
3.  F5 키를 눌러 솔루션을 실행합니다.  
  
     브라우저 창이 열리고 응용 프로그램의 디렉터리 목록이 표시됩니다.  
  
4.  브라우저에서 StockPriceService.xamlx를 클릭합니다.  
  
5.  브라우저에 StockPriceService 페이지가 표시됩니다. 이 페이지에는 로컬 서비스 WSDL 주소가 포함되어 있습니다.이 주소를 복사합니다.  
  
     다음은 로컬 서비스 WSDL 주소의 예입니다.`http://localhost:53797/StockPriceService.xamlx?wsdl`  
  
6.  서비스를 호출하기 전에 이벤트 뷰어를 시작하고 이벤트 로그가 워크플로 서비스에서 내보낸 추적 이벤트를 수신 대기하고 있는지 확인합니다.  
  
7.  **시작** 메뉴에서 **관리 도구**를 선택한 다음 **이벤트 뷰어**를 선택합니다.  
  
8.  이벤트 뷰어의 트리 뷰에서 **이벤트 뷰어**, **응용 프로그램 및 서비스 로그** 및 **Microsoft**로 이동합니다.**Microsoft**를 마우스 오른쪽 단추로 클릭하고 **보기**를 선택한 다음 **분석 및 디버그 로그 표시**를 선택합니다.  
  
     **분석 및 디버그 로그 표시** 옵션이 선택되어 있는지 확인합니다.  
  
9. 이벤트 뷰어의 트리 뷰에서 **이벤트 뷰어**, **응용 프로그램 및 서비스 로그**, **Microsoft**, **Windows**, **응용 프로그램 서버\-응용 프로그램**으로 이동합니다.**분석**을 마우스 오른쪽 단추로 클릭하고 **로그 사용**을 선택합니다.  
  
10. [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]를 사용하여 WCF 테스트 클라이언트를 엽니다.  
  
     WCF 테스트 클라이언트\(WcfTestClient.exe\)는 \<[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 설치 폴더\>\\Common7\\IDE\\ 폴더에 있습니다.  
  
     기본 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 설치 폴더는 C:\\Program Files\\Microsoft Visual Studio 10.0입니다.  
  
11. WCF 테스트 클라이언트의 **파일** 메뉴에서 **서비스 추가**를 선택합니다.  
  
     앞서 복사한 로컬 서비스 WSDL 주소를 입력 상자에 붙여넣습니다.  
  
12. WCF 테스트 클라이언트에서 `GetStockPrice`를 두 번 클릭합니다.  
  
     그러면 `GetStockPrice` 메서드가 열립니다.요청에 매개 변수 한 개가 필요합니다.**Contoso**라는 값을 사용합니다.  
  
13. **호출**을 클릭합니다.  
  
14. 이벤트 뷰어로 다시 전환한 다음, **이벤트 뷰어**, **응용 프로그램 및 서비스 로그**, **Microsoft**, **Windows**, **응용 프로그램 서버\-응용 프로그램**으로 이동합니다.**분석**을 마우스 오른쪽 단추로 클릭하고 **새로 고침**을 선택합니다.워크플로 이벤트의 이벤트 ID 범위는 100\-199입니다.  
  
     이벤트에 주석, 변수, 인수 및 사용자 지정 추적 레코드가 포함되어 있고 이러한 내용을 이벤트 뷰어에서 볼 수 있습니다.  
  
## 이벤트 뷰어 정리  
 이벤트 뷰어에서 다음과 같이 이벤트 로그의 분석 채널을 정리할 수 있습니다.  
  
#### 정리하려면\(옵션\)  
  
1.  이벤트 뷰어를 엽니다.  
  
2.  **이벤트 뷰어**, **응용 프로그램 및 서비스 로그**, **Microsoft**, **Windows**, **응용 프로그램 서버\-응용 프로그램**으로 이동합니다.**분석**을 마우스 오른쪽 단추로 클릭하고 **로그 사용 안 함**을 선택합니다.  
  
3.  **이벤트 뷰어**, **응용 프로그램 및 서비스 로그**, **Microsoft**, **Windows**, **응용 프로그램 서버\-응용 프로그램**으로 이동합니다.**분석**을 마우스 오른쪽 단추로 클릭하고 **로그 지우기**를 선택합니다.  
  
     **지우기** 옵션을 선택하여 이벤트를 지웁니다.  
  
## 알려진 문제  
  
> [!NOTE]
>  ETW 이벤트가 디코딩되지 않을 수 있으며, 이는 이벤트 뷰어와 관련하여 알려진 문제입니다.다음과 같은 오류 메시지가 표시될 수 있습니다.  
>   
>  `Microsoft-Windows-Application Server-Applications 원본에서 이벤트 ID <id>에 대한 설명을 찾을 수 없습니다이 이벤트를 발생시킨 구성 요소가 로컬 컴퓨터에 설치되어 있지 않거나 설치가 손상되었습니다.로컬 컴퓨터에서 구성 요소를 설치 또는 복구할 수 있습니다.`  
>   
>  이 오류가 발생하면 동작 창에서 **새로 고침**을 클릭합니다.그러면 이벤트가 올바르게 디코딩됩니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\ExtractWfData`  
  
## 참고 항목  
 [AppFabric 모니터링 샘플](http://go.microsoft.com/fwlink/?LinkId=193959)