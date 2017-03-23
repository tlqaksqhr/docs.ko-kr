---
title: "연습: My.Application.Log가 정보를 기록하는 위치 변경(Visual Basic) | Microsoft Docs"
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
  - "My.Application.Log 개체, 연습"
  - "이벤트 로그, 출력 위치 변경"
ms.assetid: ecc74f95-743c-450d-93f6-09a30db0fe4a
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# 연습: My.Application.Log가 정보를 기록하는 위치 변경(Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`My.Application.Log` 및 `My.Log` 개체를 사용하여 응용 프로그램에서 발생하는 이벤트에 대한 정보를 기록할 수 있습니다. 이 연습에서는 기본 설정을 재정의하고 `Log` 개체가 다른 로그 수신기에 쓰도록 만드는 방법을 보여 줍니다.  
  
## 사전 요구 사항  
 `Log` 개체는 여러 로그 수신기에 정보를 쓸 수 있습니다. 구성을 변경하기 전에 로그 수신기의 현재 구성을 확인해야 합니다. 자세한 내용은 [연습: My.Application.Log가 정보를 기록하는 위치 확인](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)을 참조하세요.  
  
 [How to: Write Event Information to a Text File](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-event-information-to-a-text-file.md) 또는 [방법: 응용 프로그램 이벤트 로그에 쓰기](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-to-an-application-event-log.md)를 참조할 수도 있습니다.  
  
### 수신기를 추가하려면  
  
1.  **솔루션 탐색기**에서 app.config를 마우스 오른쪽 단추로 클릭하고 **열기**를 선택합니다.  
  
     또는  
  
     app.config 파일이 없는 경우  
  
    1.  **프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다.  
  
    2.  **새 항목 추가** 대화 상자에서 **응용 프로그램 구성 파일**을 선택합니다.  
  
    3.  **추가**를 클릭합니다.  
  
2.  `<sources>` 섹션에서 `name` 특성이 "DefaultSource"인 `<source>` 섹션 아래에 있는 `<listeners>` 섹션을 찾습니다.`<sources>` 섹션은 최상위 `<configuration>` 섹션의 `<system.diagnostics>` 섹션에 있습니다.  
  
3.  다음 요소를 `<listeners>` 섹션에 추가합니다.  
  
    ```  
    <!-- Uncomment to connect the application file log. -->  
    <!-- <add name="FileLog" /> -->  
    <!-- Uncomment to connect the event log. -->  
    <!-- <add name="EventLog" /> -->  
    <!-- Uncomment to connect the event log. -->  
    <!-- <add name="Delimited" /> -->  
    <!-- Uncomment to connect the XML log. -->  
    <!-- <add name="XmlWriter" /> -->  
    <!-- Uncomment to connect the console log. -->  
    <!-- <add name="Console" /> -->  
    ```  
  
4.  `Log` 메시지를 받을 로그 수신기의 주석을 해제합니다.  
  
5.  최상위 `<configuration>` 섹션의 `<system.diagnostics>` 섹션에서 `<sharedListeners>` 섹션을 찾습니다.  
  
6.  다음 요소를 `<sharedListeners>` 섹션에 추가합니다.  
  
    ```  
    <add name="FileLog"  
         type="Microsoft.VisualBasic.Logging.FileLogTraceListener,   
               Microsoft.VisualBasic, Version=8.0.0.0,   
               Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"  
         initializeData="FileLogWriter" />  
    <add name="EventLog"  
         type="System.Diagnostics.EventLogTraceListener,   
               System, Version=2.0.0.0,   
               Culture=neutral, PublicKeyToken=b77a5c561934e089"  
         initializeData="sample application"/>  
    <add name="Delimited"   
         type="System.Diagnostics.DelimitedListTraceListener,   
               System, Version=2.0.0.0,   
               Culture=neutral, PublicKeyToken=b77a5c561934e089"  
         initializeData="c:\temp\sampleDelimitedFile.txt"  
         traceOutputOptions="DateTime" />  
    <add name="XmlWriter"  
         type="System.Diagnostics.XmlWriterTraceListener,   
               System, Version=2.0.0.0,   
               Culture=neutral, PublicKeyToken=b77a5c561934e089"  
         initializeData="c:\temp\sampleLogFile.xml" />  
    <add name="Console"  
         type="System.Diagnostics.ConsoleTraceListener,   
               System, Version=2.0.0.0,   
               Culture=neutral, PublicKeyToken=b77a5c561934e089"  
         initializeData="true" />  
    ```  
  
7.  app.config 파일의 내용은 다음 XML과 비슷합니다.  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.diagnostics>  
        <sources>  
          <!-- This section configures My.Application.Log -->  
          <source name="DefaultSource" switchName="DefaultSwitch">  
            <listeners>  
              <add name="FileLog"/>  
              <!-- Uncomment to connect the application file log. -->  
              <!-- <add name="FileLog" /> -->  
              <!-- Uncomment to connect the event log. -->  
              <!-- <add name="EventLog" /> -->  
              <!-- Uncomment to connect the event log. -->  
              <!-- <add name="Delimited" /> -->  
              <!-- Uncomment to connect the XML log. -->  
              <!-- <add name="XmlWriter" /> -->  
              <!-- Uncomment to connect the console log. -->  
              <!-- <add name="Console" /> -->  
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
                     Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"  
               initializeData="FileLogWriter" />  
          <add name="EventLog"  
               type="System.Diagnostics.EventLogTraceListener,   
                     System, Version=2.0.0.0,   
                     Culture=neutral, PublicKeyToken=b77a5c561934e089"  
               initializeData="sample application"/>  
          <add name="Delimited"   
               type="System.Diagnostics.DelimitedListTraceListener,   
                     System, Version=2.0.0.0,   
                     Culture=neutral, PublicKeyToken=b77a5c561934e089"  
               initializeData="c:\temp\sampleDelimitedFile.txt"  
               traceOutputOptions="DateTime" />  
          <add name="XmlWriter"  
               type="System.Diagnostics.XmlWriterTraceListener,   
                     System, Version=2.0.0.0,   
                     Culture=neutral, PublicKeyToken=b77a5c561934e089"  
               initializeData="c:\temp\sampleLogFile.xml" />  
          <add name="Console"  
               type="System.Diagnostics.ConsoleTraceListener,   
                     System, Version=2.0.0.0,   
                     Culture=neutral, PublicKeyToken=b77a5c561934e089"  
               initializeData="true" />  
        </sharedListeners>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
### 수신기를 다시 구성하려면  
  
1.  `<sharedListeners>` 섹션에서 수신기의 `<add>` 요소를 찾습니다.  
  
2.  `type` 특성이 수신기 형식의 이름을 제공합니다. 이 형식은 <xref:System.Diagnostics.TraceListener> 클래스에서 상속해야 합니다. 올바른 형식이 사용되도록 강력한 이름의 형식 이름을 사용하세요. 자세한 내용은 아래의 "강력한 이름의 형식을 참조하려면"을 참조하세요.  
  
     다음 형식을 사용할 수 있습니다.  
  
    -   파일 로그에 쓰는 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=fullName> 수신기  
  
    -   `initializeData` 매개 변수로 지정된 컴퓨터 이벤트 로그에 정보를 쓰는 <xref:System.Diagnostics.EventLogTraceListener?displayProperty=fullName> 수신기  
  
    -   `initializeData` 매개 변수에 지정된 파일에 쓰는 <xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=fullName> 및 <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=fullName> 수신기  
  
    -   명령줄 콘솔에 쓰는 <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=fullName> 수신기  
  
     다른 형식의 로그 수신기가 정보를 쓰는 위치에 대한 자세한 내용은 해당 형식의 설명서를 참조하세요.  
  
3.  응용 프로그램에서는 로그 수신기 개체를 만들 때 `initializeData` 특성을 생성자 매개 변수로 전달합니다.`initializeData` 특성의 의미는 추적 수신기에 따라 달라집니다.  
  
4.  로그 수신기를 만든 후 응용 프로그램에서는 수신기의 속성을 설정합니다. 이들 속성은 `<add>` 요소의 다른 특성에 의해 정의됩니다. 특정 수신기의 속성에 대한 자세한 내용은 해당 수신기 형식의 설명서를 참조하세요.  
  
### 강력한 이름의 형식을 참조하려면  
  
1.  로그 수신기에 올바른 형식이 사용되도록 하려면 정규화된 형식 이름과 강력한 이름의 어셈블리 이름을 사용하세요. 강력한 이름의 형식은 다음과 같은 구문을 갖습니다.  
  
     \<*type name*\>, \<*assembly name*\>, \<*version number*\>, \<*culture*\>, \<*strong name*\>  
  
2.  이 코드 예제에서는 정규화된 형식\(이 경우 "System.Diagnostics.FileLogTraceListener"\)에 대한 강력한 이름이 지정된 형식 이름을 확인하는 방법을 보여 줍니다.  
  
     [!code-vb[VbVbalrMyApplicationLog#15](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/walkthrough-changing-where-my-application-log-writes-information_1.vb)]  
  
     출력은 다음과 같으며, 위의 "수신기를 추가하려면" 절차에서처럼 이 출력을 사용하여 강력한 이름의 형식을 고유하게 참조할 수 있습니다.  
  
     `Microsoft.VisualBasic.Logging.FileLogTraceListener, Microsoft.VisualBasic, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a`  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName>   
 <xref:System.Diagnostics.TraceListener>   
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=fullName>   
 <xref:System.Diagnostics.EventLogTraceListener?displayProperty=fullName>   
 [How to: Write Event Information to a Text File](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-event-information-to-a-text-file.md)   
 [방법: 응용 프로그램 이벤트 로그에 쓰기](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-to-an-application-event-log.md)