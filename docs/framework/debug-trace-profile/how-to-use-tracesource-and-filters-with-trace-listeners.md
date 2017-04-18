---
title: "How to: Use TraceSource and Filters with Trace Listeners | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "initializing trace listeners"
  - "configuration files [.NET Framework], trace listeners"
  - "app.config files, trace listeners"
  - "levels of writing trace messages"
  - "trace listeners, TraceSource class"
  - "application configuration files, trace listeners"
  - "filters, trace listeners"
  - "TraceSource class, trace listeners"
  - "trace listeners, creating"
  - "trace listeners, filters"
  - "trace listeners, initializing"
ms.assetid: 21dc2169-947d-453a-b0e2-3dac3ba0cc9f
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# How to: Use TraceSource and Filters with Trace Listeners
향상된 추적 시스템은 .NET Framework 버전 2.0의 새로운 기능 중 하나입니다.  기본 전제는 변경되지 않습니다. 추적 메시지는 스위치를 통해 수신기로 전송되며, 이 수신기는 데이터를 연관된 출력 매체에 보고합니다.  버전 2.0의 기본적인 차이는 <xref:System.Diagnostics.TraceSource> 클래스의 인스턴스를 통해 추적을 시작할 수 있다는 것입니다.  <xref:System.Diagnostics.TraceSource>는 향상된 추적 시스템으로 작동하는 데 사용되며 이전 <xref:System.Diagnostics.Trace> 및 <xref:System.Diagnostics.Debug> 추적 클래스의 정적 메서드 대신 사용될 수 있습니다.  익숙한 <xref:System.Diagnostics.Trace> 및 <xref:System.Diagnostics.Debug> 클래스는 계속 존재하지만 <xref:System.Diagnostics.TraceSource> 클래스를 사용하여 추적하는 것이 좋습니다.  
  
 이 항목에서는 응용 프로그램 구성 파일과 함께 <xref:System.Diagnostics.TraceSource>를 사용하는 방법에 대해 설명합니다.  권장되지는 않지만 구성 파일을 사용하지 않고 <xref:System.Diagnostics.TraceSource>를 사용하여 추적할 수 있습니다.  구성 파일을 사용하지 않고 추적하는 방법에 대한 자세한 내용은 [방법: 추적 소스 생성 및 초기화](../../../docs/framework/debug-trace-profile/how-to-create-and-initialize-trace-sources.md)를 참조하십시오.  
  
### 추적 소스를 만들고 초기화하려면  
  
1.  추적을 사용하여 응용 프로그램을 계측하는 첫 단계에서는 추적 소스를 만듭니다.  다양한 구성 요소가 있는 대규모 프로젝트에서는 구성 요소마다 별도의 추적 소스를 만들 수 있습니다.  권장되는 방법은 응용 프로그램의 이름을 추적 소스 이름으로 사용하는 것입니다.  이렇게 하면 서로 다른 추적을 개별적으로 더 쉽게 유지할 수 있습니다.  다음 코드에서는 새 추적 소스\(`mySource)`\)를 만들고 이벤트를 추적하는 메서드\(`Activity1`\)를 호출합니다.  기본 추적 수신기는 추적 메시지를 씁니다.  
  
    ```  
    using System;  
    using System.Diagnostics;  
    using System.Threading;  
  
    namespace TraceSourceApp  
    {  
        class Program  
        {  
            private static TraceSource mySource =   
                new TraceSource("TraceSourceApp");  
            static void Main(string[] args)  
            {  
                Activity1();  
                mySource.Close();  
                return;  
            }  
            static void Activity1()  
            {  
                mySource.TraceEvent(TraceEventType.Error, 1,   
                    "Error message.");  
                mySource.TraceEvent(TraceEventType.Warning, 2,   
                    "Warning message.");  
            }  
        }  
    }  
    ```  
  
### 추적 수신기 및 필터를 만들고 초기화하려면  
  
1.  첫 번째 절차의 코드에서는 추적 수신기나 필터를 프로그래밍 방식으로 식별하지 않습니다.  코드만으로는 추적 메시지가 기본 추적 수신기에 기록됩니다.  특정 추적 수신기와 관련 필터를 구성하려면 응용 프로그램의 이름에 해당하는 구성 파일을 편집합니다.  이 파일에서 수신기를 추가 또는 제거하거나 수신기의 속성과 필터를 설정할 수 있으며, 여러 수신기를 제거할 수도 있습니다.  다음 구성 파일 예제에서는 이전 절차에서 만든 추적 소스에 대해 텍스트 작성기 추적 수신기와 콘솔 추적 수신기를 초기화하는 방법을 보여 줍니다.  구성 파일에서는 추적 수신기를 구성하고 두 수신기에 대한 필터를 만들고 추적 소스에 대한 소스 스위치를 만듭니다.  추적 수신기를 추가하는 데는 두 가지 방법이 사용됩니다. 즉 수신기를 추적 소스에 직접 추가하는 방법과 수신기를 공유 컬렉션에 추가한 다음 이를 이름별로 추적 소스에 추가하는 방법이 있습니다.  두 수신기에 대해 식별된 필터는 서로 다른 소스 수준으로 초기화됩니다.  이로 인해 일부 메시지가 두 수신기 중 하나에 의해서만 기록됩니다.  
  
    ```  
    <configuration>  
      <system.diagnostics>  
        <sources>  
          <source name="TraceSourceApp"   
            switchName="sourceSwitch"   
            switchType="System.Diagnostics.SourceSwitch">  
            <listeners>  
              <add name="console"   
                type="System.Diagnostics.ConsoleTraceListener">  
                <filter type="System.Diagnostics.EventTypeFilter"   
                  initializeData="Warning"/>  
              </add>  
              <add name="myListener"/>  
              <remove name="Default"/>  
            </listeners>  
          </source>  
        </sources>  
        <switches>  
          <add name="sourceSwitch" value="Warning"/>  
        </switches>  
        <sharedListeners>  
          <add name="myListener"   
            type="System.Diagnostics.TextWriterTraceListener"   
            initializeData="myListener.log">  
            <filter type="System.Diagnostics.EventTypeFilter"   
              initializeData="Error"/>  
          </add>  
        </sharedListeners>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
### 수신기가 추적 메시지를 쓰는 수준을 변경하려면  
  
1.  구성 파일은 응용 프로그램이 초기화될 때 추적 소스에 대한 설정을 초기화합니다.  해당 설정을 변경하려면 구성 파일을 변경하고 응용 프로그램을 다시 시작하거나 <xref:System.Diagnostics.Trace.Refresh%2A?displayProperty=fullName> 메서드를 사용하여 응용 프로그램을 프로그래밍 방식으로 새로 고쳐야 합니다.  응용 프로그램은 구성 파일에서 설정되는 속성을 동적으로 변경하여 사용자가 지정한 설정을 재정의할 수 있습니다.  예를 들어, 현재 구성 설정과 관계없이 항상 중요한 메시지를 텍스트 파일로 보낼 수 있습니다.  
  
    ```  
    using System;  
    using System.Diagnostics;  
    using System.Threading;  
  
    namespace TraceSourceApp  
    {  
        class Program  
        {  
            private static TraceSource mySource =   
                new TraceSource("TraceSourceApp");  
            static void Main(string[] args)  
            {  
                Activity1();  
  
                // Change the event type for which tracing occurs.  
                // The console trace listener must be specified   
                // in the configuration file. First, save the original  
                // settings from the configuration file.  
                EventTypeFilter configFilter =   
                    (EventTypeFilter)mySource.Listeners["console"].Filter;  
  
                // Then create a new event type filter that ensures   
                // critical messages will be written.  
                mySource.Listeners["console"].Filter =  
                    new EventTypeFilter(SourceLevels.Critical);  
                Activity2();  
  
                // Allow the trace source to send messages to listeners   
                // for all event types. This statement will override   
                // any settings in the configuration file.  
                mySource.Switch.Level = SourceLevels.All;  
  
                // Restore the original filter settings.  
                mySource.Listeners["console"].Filter = configFilter;  
                Activity3();  
                mySource.Close();  
                return;  
            }  
            static void Activity1()  
            {  
                mySource.TraceEvent(TraceEventType.Error, 1,   
                    "Error message.");  
                mySource.TraceEvent(TraceEventType.Warning, 2,   
                    "Warning message.");  
            }  
            static void Activity2()  
            {  
                mySource.TraceEvent(TraceEventType.Critical, 3,   
                    "Critical message.");  
                mySource.TraceInformation("Informational message.");  
            }  
            static void Activity3()  
            {  
                mySource.TraceEvent(TraceEventType.Error, 4,   
                    "Error message.");  
                mySource.TraceInformation("Informational message.");  
            }  
        }  
    }  
    ```  
  
## 참고 항목  
 <xref:System.Diagnostics.TraceSource>   
 <xref:System.Diagnostics.TextWriterTraceListener>   
 <xref:System.Diagnostics.ConsoleTraceListener>   
 <xref:System.Diagnostics.EventTypeFilter>   
 [방법: 추적 소스 생성 및 초기화](../../../docs/framework/debug-trace-profile/how-to-create-and-initialize-trace-sources.md)   
 [Trace Listeners](../../../docs/framework/debug-trace-profile/trace-listeners.md)