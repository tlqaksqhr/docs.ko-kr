### <a name="etw-event-names-cannot-differ-only-by-a-start-or-stop-suffix"></a>ETW 이벤트 이름은 "Start" 또는 "Stop" 접미사만 다를 수 없음

|   |   |
|---|---|
|설명|.NET Framework 4.6 및 4.6.1의 경우 두 개의 ETW(Windows용 이벤트 추적) 이벤트 이름이 &quot;Start&quot; 또는 &quot;Stop&quot; 접미사만 다를 때(예: 한 이벤트는 <code>LogUser</code>, 다른 이벤트는 <code>LogUserStart</code>라고 이름을 지정하는 경우) 런타임에서 <xref:System.ArgumentException>을 throw합니다. 이 경우 런타임에서 로깅을 발생할 수 없는 이벤트 소스를 구성할 수 없습니다.<ul><li>[X] Quirked // 일반적으로 런타임 대상 지정, AppContext 또는 구성 파일을 사용하여 기능을 설정/해제하는 몇 가지 메커니즘을 사용합니다. 일부 상황에서는 자동으로 설정되어야 합니다.</li><li>[] 빌드 시간 중단 // 다시 컴파일하려고 하면 중단됩니다</li></ul>|
|제안 해결 방법|예외를 방지하려면 두 이벤트 이름이 &quot;시작&quot; 또는 &quot;중지&quot; 접미사만 다르지 않도록 하세요. 이 요구 사항은 .NET Framework 4.6.2부터 제거됩니다. 런타임은 &quot;시작&quot; 및 &quot;중지&quot; 접미사만 다른 이벤트 이름을 명확하게 할 수 있습니다.|
|범위|Microsoft Edge|
|버전|4.6|
|형식|런타임|

