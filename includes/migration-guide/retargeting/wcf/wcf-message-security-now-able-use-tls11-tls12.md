### <a name="wcf-message-security-now-is-able-to-use-tls11-and-tls12"></a>WCF 메시지 보안이 이제 TLS1.1 및 TLS1.2를 사용할 수 있음

|   |   |
|---|---|
|설명|.NET Framework 4.7부터 고객은 응용 프로그램 구성 설정을 통해 SSL3.0 및 TLS1.0 외에도 WCF 메시지 보안에 TLS1.1 또는 TLS1.2를 구성할 수 있습니다.|
|제안 해결 방법|.NET Framework 4.7에서는 WCF 메시지 보안의 TLS1.1 및 TLS1.2에 대한 지원은 기본적으로 사용할 수 없습니다. app.config 또는 web.config 파일의 <code>&lt;runtime&gt;</code> 섹션에 다음 행을 추가하여 사용할 수 있습니다.<pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|범위|Microsoft Edge|
|버전|4.7|
|형식|대상 변경|

