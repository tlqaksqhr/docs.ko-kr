### <a name="deadlock-may-result-when-using-reentrant-services"></a>재진입 서비스를 사용할 때 교착 상태가 발생할 수 있습니다.

|   |   |
|---|---|
|설명|교착 상태가 발생하면 재진입 서비스의 인스턴스가 한번에 하나의 실행 스레드로 제한됩니다. 이 문제가 발생하기 쉬운 서비스는 코드에 다음과 같은 <xref:System.ServiceModel.ServiceBehaviorAttribute>가 있습니다.<pre><code class="language-csharp">[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]&#13;&#10;</code></pre>|
|제안 해결 방법|이 문제를 해결하려면 다음을 수행합니다.<ul><li>서비스의 동시성 모드를 <xref:System.ServiceModel.ConcurrencyMode.Single?displayProperty=nameWithType> 또는 &lt;System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType&gt;로 설정합니다. 예:</li></ul><pre><code class="language-csharp">[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single)]&#13;&#10;</code></pre><ul><li>.NET Framework 4.6.2의 최신 업데이트를 설치하거나 이후 버전의 .NET Framework로 업그레이드합니다. 이렇게 하면 <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>에서 <xref:System.Threading.ExecutionContext>의 흐름이 비활성화됩니다. 이 동작은 구성할 수 있습니다. 구성 파일에 다음 앱 설정을 추가하는 것과 같습니다.</li></ul><pre><code class="language-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.ServiceModel.DisableOperationContextAsyncFlow&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&#13;&#10;The value of &#39;Switch.System.ServiceModel.DisableOperationContextAsyncFlow&#39; should never be set to &#39;false&#39; for Rentrant services.&#13;&#10;</code></pre>|
|범위|부|
|버전|4.6.2|
|형식|대상 변경|
|영향을 받는 API|<ul><li><xref:System.ServiceModel.ServiceBehaviorAttribute?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ConcurrencyMode.Reentrant?displayProperty=nameWithType></li></ul>|

