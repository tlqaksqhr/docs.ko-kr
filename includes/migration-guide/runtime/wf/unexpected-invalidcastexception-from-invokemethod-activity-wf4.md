### <a name="unexpected-invalidcastexception-from-invokemethod-activity-in-wf4"></a>WF4의 InvokeMethod 작업에서 예기치 않은 InvalidCastException이 발생합니다.

|   |   |
|---|---|
|설명|null 허용(nullable) 매개 변수가 있는 메서드를 대상으로 하는 <xref:System.Activities.Statements.InvokeMethod>를 사용하면 <xref:System.InvalidCastException?displayProperty=name>을 throw합니다.|
|제안 해결 방법|이 동작은 .NET Framework 4.5 서비스 릴리스에서 되돌려졌습니다. 이 문제를 해결하려면 .NET Framework 4.5를 업데이트하거나 .NET Framework 4.5.1 이상으로 업그레이드하세요.|
|범위|부|
|버전|4.5|
|형식|런타임|
|영향을 받는 API|<ul><li><xref:System.Activities.Statements.InvokeMethod.Parameters?displayProperty=nameWithType></li></ul>|
|분석기|<ul><li>CD0088</li></ul>|

