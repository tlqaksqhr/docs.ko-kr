### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a>ASP.Net MVC4 앱을 프로파일링하면 심각한 실행 엔진 오류가 발생할 수 있습니다.

|   |   |
|---|---|
|설명|NGEN /Profile 어셈블리를 사용하는 프로파일러는 프로파일링된 ASP.NET MVC4 응용 프로그램을 시작할 때 '심각한 실행 엔진 예외'로 크래시가 발생할 수 있습니다.|
|제안 해결 방법|이 문제는 .NET Framework 4.5.2에서 해결되었습니다. 또는 프로파일러는 이벤트 마스크에 <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code>를 지정하여 이 문제를 방지할 수 있습니다.|
|범위|Microsoft Edge|
|버전|4.5|
|형식|런타임|

