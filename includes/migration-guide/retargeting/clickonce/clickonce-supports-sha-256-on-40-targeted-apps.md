### <a name="clickonce-supports-sha-256-on-40-targeted-apps"></a>ClickOnce가 4.0 대상 앱에서 SHA-256 지원

|   |   |
|---|---|
|설명|이전에 SHA-256으로 서명된 인증서가 있는 ClickOnce 앱은 앱이 4.0을 대상으로 하더라도 .NET 4.5 이상이 필요했습니다. 이제는 SHA-256으로 서명되었더라도 4.0 대상 ClickOnce 앱은 4.0에서 실행할 수 있습니다.|
|제안 해결 방법|이 변경 내용은 해당 종속성을 제거하고 .NET Framework 4 이전 버전을 대상으로 하는 ClickOnce 앱을 SHA-256 인증서로 서명할 수 있게 합니다.|
|범위|부|
|버전|4.6|
|형식|대상 변경|

