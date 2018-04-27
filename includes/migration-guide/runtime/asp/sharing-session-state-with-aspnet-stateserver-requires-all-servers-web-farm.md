### <a name="sharing-session-state-with-aspnet-stateserver-requires-all-servers-in-the-web-farm-to-use-the-same-net-framework-version"></a>Asp.Net StateServer와 세션 상태를 공유하려면 웹 팜의 모든 서버가 동일한 .NET Framework 버전을 사용해야 합니다.

|   |   |
|---|---|
|설명|<xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=name> 세션 상태를 활성화할 때 상태를 올바르게 공유하려면 지정된 웹 팜의 모든 서버가 동일한 .NET Framework 버전을 사용해야 합니다.|
|제안 해결 방법|동시에 상태를 공유하는 웹 서버에서 .NET Framework 버전을 업그레이드해야 합니다.|
|범위|Microsoft Edge|
|버전|4.5|
|형식|런타임|
|영향을 받는 API|<ul><li><xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=nameWithType></li></ul>|

