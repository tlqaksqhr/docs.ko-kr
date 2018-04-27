### <a name="servicebase-doesnt-propagate-onstart-exceptions"></a>ServiceBase는 OnStart 예외를 전파하지 않음

|   |   |
|---|---|
|설명|.NET Framework 4.7 이전 버전에서는 서비스 시작 시 발생하는 예외가 <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType>의 호출자에게 전파되지 않습니다. .Net Framework 4.7.1을 대상으로 하는 응용 프로그램부터는 런타임이 시작 실패하는 서비스를 위해 <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType>으로 예외를 전파합니다.|
|제안 해결 방법|서비스 시작 시 예외가 있는 경우 해당 예외가 전파됩니다. 이는 서비스가 시작되지 않는 부분을 진단하는 데 도움이 됩니다. 이 동작이 바람직하지 않은 경우 응용 프로그램 구성 파일의 <runtime> 섹션에 다음 <AppContextSwitchOverrides> 요소를 추가하여 옵트아웃할 수 있습니다.<pre><code class="language-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceProcess.DontThrowExceptionsOnStart=true&quot; /&gt;&#13;&#10;</code></pre>응용 프로그램이 4.7.1 이전 버전을 대상으로 하지만 이 동작을 원할 경우 응용 프로그램 구성 파일의 <runtime> 섹션에 다음 <AppContextSwitchOverrides> 요소를 추가합니다.<pre><code class="language-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceProcess.DontThrowExceptionsOnStart=false&quot; /&gt;&#13;&#10;</code></pre>|
|범위|부|
|버전|4.7.1|
|형식|대상 변경|
|영향을 받는 API|<ul><li><xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase)?displayProperty=nameWithType></li><li><xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase[])?displayProperty=nameWithType></li></ul>|

