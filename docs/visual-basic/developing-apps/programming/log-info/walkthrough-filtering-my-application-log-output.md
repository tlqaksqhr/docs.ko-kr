---
title: "연습: My.Application.Log 출력 필터링(Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Log 개체를 출력 필터링"
  - "My.Application.Log 개체를 출력 필터링"
  - "응용 프로그램 이벤트 로그 출력 필터링"
ms.assetid: 2c0a457a-38a4-49e1-934d-a51320b7b4ca
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# 연습: My.Application.Log 출력 필터링(Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 연습에서는 기본 로그에 대 한 필터링을 변경 하는 방법을 보여 줍니다.는 `My.Application.Log` 개체에서 전달 되는 정보를 제어 하는 `Log` 수신기 하 고 수신기를 통해 어떤 정보를 기록 하는 개체입니다. 구성 정보는 응용 프로그램의 구성 파일에 저장 되기 때문에 응용 프로그램을 빌드한 후에 로깅 동작을 변경할 수 있습니다.  
  
## <a name="getting-started"></a>시작  
 각 메시지에 `My.Application.Log` 쓰기에 로그 출력을 제어 하는 필터링 메커니즘을 사용 하는 연결 된 심각도 수준입니다. 이 샘플 응용 프로그램에서 사용 하 여 `My.Application.Log` 메서드를 여러 다른 심각도 수준을 사용 하 여 메시지를 기록 합니다.  
  
#### <a name="to-build-the-sample-application"></a>샘플 응용 프로그램을 빌드하려면  
  
1.  새 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] Windows 응용 프로그램 프로젝트입니다.  
  
2.  Form1 Button1 라는 단추를 추가 합니다.  
  
3.  에 <xref:System.Windows.Forms.Control.Click> Button1에 대 한 이벤트 처리기에 다음 코드를 추가 합니다.  
  
     [!code-vb[VbVbcnMyApplicationLogFiltering#1](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/walkthrough-filtering-my-application-log-output_1.vb)]  
  
4.  디버거에서 응용 프로그램을 실행 합니다.  
  
5.  키를 눌러 **Button1**합니다.  
  
     응용 프로그램 응용 프로그램의 디버그 출력 및 로그 파일에 다음 정보를 씁니다.  
  
     `DefaultSource Information: 0 : In Button1_Click`  
  
     `DefaultSource Error: 2 : Error in the application.`  
  
6.  응용 프로그램을 닫습니다.  
  
     응용 프로그램의 디버그 출력 창을 확인 하는 방법에 대 한 자세한 내용은 참조 [출력 창](/visual-studio/ide/reference/output-window)합니다. 응용 프로그램의 로그 파일의 위치에 대 한 자세한 내용은 참조 [연습: 결정 여기서 My.Application.Log 기록 정보](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)합니다.  
  
    > [!NOTE]
    >  기본적으로 응용 프로그램을 닫으면 응용 프로그램 로그 파일 출력을 플러시합니다.  
  
     두 번째 호출 위의 예에서 <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A> 메서드와에 대 한 호출의 <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A> 첫 번째 및 마지막 호출을 하는 동안 로그 출력을 생성 하는 메서드는 `WriteEntry` 메서드 하지 않습니다. 때문에 이것이의 심각도 수준을 `WriteEntry` 및 `WriteException` 은 "정보" 및 "오류"에 허용 되는 둘 다는 `My.Application.Log` 개체의 기본 로그 필터링 합니다. 그러나 "Start" 및 "Stop" 심각도 수준 사용 하 여 이벤트에서 로그 출력을 생성할 수 없습니다.  
  
## <a name="filtering-for-all-myapplicationlog-listeners"></a>모든 My.Application.Log 수신기에 대 한 필터링  
  `My.Application.Log` 개체에서 사용 하는 <xref:System.Diagnostics.SourceSwitch> 라는 `DefaultSwitch` 전달할 메시지를 제어 하는 `WriteEntry` 및 `WriteException` 로그 수신기에 대 한 메서드. 구성할 수 있습니다 `DefaultSwitch` 중 하나에 해당 값을 설정 하 여 응용 프로그램의 구성 파일에는 <xref:System.Diagnostics.SourceLevels> 열거형 값입니다. 기본적으로 해당 값은 "정보"를 사용 합니다.  
  
 이 표에서 특정 수신기에 메시지를 쓰는 데 필요한 심각도 수준을 `DefaultSwitch` 설정 합니다.  
  
|||  
|-|-|  
|DefaultSwitch 값|출력에 필요한 메시지 심각도|  
|`Critical`|`Critical`|  
|`Error`|`Critical` 또는 `Error`|  
|`Warning`|`Critical`, `Error` 또는 `Warning`|  
|`Information`|`Critical`, `Error`, `Warning` 또는 `Information`|  
|`Verbose`|`Critical`, `Error`, `Warning`, `Information` 또는 `Verbose`|  
|`ActivityTracing`|`Start`, `Stop`, `Suspend`, `Resume` 또는 `Transfer`|  
|`All`|모든 메시지를 허용 합니다.|  
|`Off`|모든 메시지는 차단 됩니다.|  
  
> [!NOTE]
>   `WriteEntry` 및 `WriteException` 메서드는 각각 한 심각도 수준을 지정 하지 않는 오버 로드 합니다. 에 대 한 암시적 심각도 `WriteEntry` 오버 로드는 "정보"에 대 한 암시적 심각도 `WriteException` 오버 로드는 "오류".  
  
 다음이 표는 이전 예제에 표시 된 로그 출력이 설명: 기본 `DefaultSwitch` 에 두 번째 호출 "정보"의 설정는 `WriteEntry` 메서드 및 호출을는 `WriteException` 메서드 생성 로그 출력.  
  
#### <a name="to-log-only-activity-tracing-events"></a>작업 추적 이벤트만 기록 하려면  
  
1.  app.config를 마우스 오른쪽 단추로 클릭는 **솔루션 탐색기** 선택한 **열려**합니다.  
  
     또는  
  
     app.config 파일이 없는 경우  
  
    1.  **프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다.  
  
    2.  **새 항목 추가** 대화 상자에서 **응용 프로그램 구성 파일**을 선택합니다.  
  
    3.  **추가**를 클릭합니다.  
  
2.  찾은 `<switches>` 섹션에 있는 `<system.diagnostics>` 섹션의 최상위에 있는 `<configuration>` 섹션입니다.  
  
3.  추가 하는 요소를 찾은 다음 `DefaultSwitch` 스위치의 컬렉션에 있습니다. 이 요소에 비슷해야 합니다.  
  
     `<add name="DefaultSwitch" value="Information" />`  
  
4.  값을 변경 하는 `value` "ActivityTracing" 하는 특성입니다.  
  
5.  app.config 파일의 내용은 다음 XML과 비슷합니다.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.diagnostics>  
        <sources>  
          <!-- This section configures My.Application.Log -->  
          <source name="DefaultSource" switchName="DefaultSwitch">  
            <listeners>  
              <add name="FileLog"/>  
            </listeners>  
          </source>  
        </sources>  
        <switches>  
          <add name="DefaultSwitch" value="ActivityTracing" />  
        </switches>  
        <sharedListeners>  
          <add name="FileLog"  
               type="Microsoft.VisualBasic.Logging.FileLogTraceListener,   
                     Microsoft.VisualBasic, Version=8.0.0.0,   
                     Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a,   
                     processorArchitecture=MSIL"   
               initializeData="FileLogWriter"/>  
        </sharedListeners>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
6.  디버거에서 응용 프로그램을 실행 합니다.  
  
7.  키를 눌러 **Button1**합니다.  
  
     응용 프로그램 응용 프로그램의 디버그 출력 및 로그 파일에서 다음 정보를 씁니다.  
  
     `DefaultSource Start: 4 : Entering Button1_Click`  
  
     `DefaultSource Stop: 5 : Leaving Button1_Click`  
  
8.  응용 프로그램을 닫습니다.  
  
9. 값을 변경 하는 `value` "정보" 특성입니다.  
  
    > [!NOTE]
    >   `DefaultSwitch` 설정은 컨트롤만 전환 `My.Application.Log`합니다. 변경 되지 않습니다 방법을 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)] <xref:System.Diagnostics.Trace?displayProperty=fullName> 및 <xref:System.Diagnostics.Debug?displayProperty=fullName> 클래스의 동작입니다.  
  
## <a name="individual-filtering-for-myapplicationlog-listeners"></a>개별 My.Application.Log 수신기에 대 한 필터링  
 앞의 예제에는 모든 필터링을 변경 하는 방법을 보여 줍니다 `My.Application.Log` 출력 합니다. 이 예제에서는 개별 로그 수신기를 필터링 하는 방법을 보여 줍니다. 기본적으로 응용 프로그램 응용 프로그램의 디버그 출력 및 로그 파일에 쓰는 두 수신기를에 있습니다.  
  
 구성 파일 각각에 대 한 스위치와 비슷한 필터를 허용 하 여 로그 수신기의 동작을 제어 `My.Application.Log`합니다. 두 로그에서 메시지의 심각도 허용 하는 경우에 로그 수신기에서 메시지를 출력 `DefaultSwitch` 와 로그 수신기의 필터입니다.  
  
 에 추가 하 여 새 디버그 수신기에 대 한 필터링을 구성 하는 방법을 보여 주는이 예제는 `Log` 개체입니다. 제거 해야 하는 기본 디버그 수신기는 `Log` 개체를 새 디버그 수신기에서 디버그 메시지 가져왔는지 분명 합니다.  
  
#### <a name="to-log-only-activity-tracing-events"></a>동작 추적 이벤트만 기록 하려면  
  
1.  app.config를 마우스 오른쪽 단추로 클릭는 **솔루션 탐색기** 선택한 **열려**합니다.  
  
     또는  
  
     app.config 파일이 없는 경우  
  
    1.  **프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다.  
  
    2.  **새 항목 추가** 대화 상자에서 **응용 프로그램 구성 파일**을 선택합니다.  
  
    3.  **추가**를 클릭합니다.  
  
2.  app.config를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기**합니다. 선택 **열려**합니다.  
  
3.  찾습니다는 `<listeners>` 섹션에 `<source>` 섹션는 `name` "DefaultSource" 아래 있는 특성의 `<sources>` 섹션.  `<sources>` 섹션은는 `<system.diagnostics>` 섹션의 최상위에 `<configuration>` 섹션입니다.  
  
4.  이 요소를 추가 `<listeners>` 섹션:  
  
    ```xml  
    <!-- Remove the default debug listener. -->  
    <remove name="Default"/>  
    <!-- Add a filterable debug listener. -->  
    <add name="NewDefault"/>  
    ```  
  
5.  최상위 `<sharedListeners>` 섹션의 `<system.diagnostics>` 섹션에서 `<configuration>` 섹션을 찾습니다.  
  
6.  다음 요소를 `<sharedListeners>` 섹션에 추가합니다.  
  
    ```xml  
    <add name="NewDefault"   
         type="System.Diagnostics.DefaultTraceListener,   
               System, Version=2.0.0.0, Culture=neutral,   
               PublicKeyToken=b77a5c561934e089,   
               processorArchitecture=MSIL">  
        <filter type="System.Diagnostics.EventTypeFilter"   
                initializeData="Error" />  
    </add>  
    ```  
  
      <xref:System.Diagnostics.EventTypeFilter> 필터 중 하나를 사용 합니다.는 <xref:System.Diagnostics.SourceLevels> 열거형 값으로 해당 `initializeData` 특성입니다.  
  
7.  app.config 파일의 내용은 다음 XML과 비슷합니다.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.diagnostics>  
        <sources>  
          <!-- This section configures My.Application.Log -->  
          <source name="DefaultSource" switchName="DefaultSwitch">  
            <listeners>  
              <add name="FileLog"/>  
              <!-- Remove the default debug listener. -->  
              <remove name="Default"/>  
              <!-- Add a filterable debug listener. -->  
              <add name="NewDefault"/>  
            </listeners>  
          </source>  
        </sources>  
        <switches>  
          <add name="DefaultSwitch" value="Information" />  
        </switches>  
        <sharedListeners>  
          <add name="FileLog"  
               type="Microsoft.VisualBasic.Logging.FileLogTraceListener,   
                     Microsoft.VisualBasic, Version=8.0.0.0,   
                     Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a,   
                     processorArchitecture=MSIL"   
               initializeData="FileLogWriter"/>  
          <add name="NewDefault"   
               type="System.Diagnostics.DefaultTraceListener,   
                     System, Version=2.0.0.0, Culture=neutral,   
                     PublicKeyToken=b77a5c561934e089,   
                     processorArchitecture=MSIL">  
            <filter type="System.Diagnostics.EventTypeFilter"   
                    initializeData="Error" />  
          </add>  
        </sharedListeners>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
8.  디버거에서 응용 프로그램을 실행 합니다.  
  
9. 키를 눌러 **Button1**합니다.  
  
     응용 프로그램의 로그 파일에 다음 정보를 기록 하는 응용 프로그램:  
  
     `Default Information: 0 : In Button1_Click`  
  
     `Default Error: 2 : Error in the application.`  
  
     응용 프로그램 보다 제한적인 필터링 덕분에 응용 프로그램의 디버그 출력에 보다 적은 정보를 씁니다.  
  
     `Default Error   2   Error`  
  
10. 응용 프로그램을 닫습니다.  
  
 배포 후 로그 설정을 변경 하는 방법에 대 한 자세한 내용은 참조 [응용 프로그램 로그 작업](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [연습: my.application.log가 정보를 기록 하는 위치 확인](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)   
 [연습: my.application.log가 정보를 기록 하는 위치 변경](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)   
 [연습: 사용자 지정 로그 수신기 만들기](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-creating-custom-log-listeners.md)   
 [방법: 로그 메시지 쓰기](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)   
 [추적 스위치](../Topic/Trace%20Switches.md)   
 [응용 프로그램에서 로깅 정보](../../../../visual-basic/developing-apps/programming/log-info/logging-information-from-the-application.md)