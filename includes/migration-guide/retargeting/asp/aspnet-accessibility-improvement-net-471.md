### <a name="aspnet-accessibility-improvement-in-net-471"></a>.NET 4.7.1에서 향상된 ASP.NET 액세스 가능성

|   |   |
|---|---|
|설명|ASP.NET 웹 컨트롤에서 Visual Studio의 액세스 가능성 기술을 사용하여 ASP.NET 고객을 더 효율적으로 지원하도록 ASP.NET이 향상되었습니다.  여기에는 다음과 같은 변경이 포함됩니다.<ul><li>세부 정보 보기 마법사의 필드 추가 대화 상자와 같이 컨트롤에서 누락된 UI 액세스 가능성 패턴을 구현하도록 변경되었습니다.</li><li>데이터 호출기 필드 편집기와 같이 고대비 모드에서 디스플레이를 개선하도록 변경됨.</li><li>개체 컨텍스트 구성 창 또는 데이터 원본 구성 창과 같은 컨트롤에 대한 키보드 탐색 환경을 향상시키도록 변경되었습니다.</li></ul>|
|제안 해결 방법|**이러한 변경을 선택/해제하는 방법** Visual Studio 디자이너에서 이러한 변경의 이점을 얻으려면 .NET Framework 4.7.1 이상에서 실행해야 합니다. 웹 응용 프로그램은 다음과 같은 방법으로 이러한 변경의 이점을 활용할 수 있습니다.<ul><li>기본적으로 다음 AppContext 스위치를 사용하여 새로운 액세스 가능성 기능을 지원하는 Visual Studio 2017 15.3 이상을 설치합니다.</li><li>다음 예제와 같이 devenv.exe.config 파일의 `<runtime>` 섹션에 **Switch.UseLegacyAccessibility** AppContext 스위치를 추가하고 이를 `false`로 설정하여 레거시 액세스 가능성 동작을 옵트아웃합니다.</li></ul><pre><code>&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;<br />&lt;configuration&gt;<br />&lt;runtime&gt;<br />...</code></pre>|
|범위|부|
|버전|4.7.1|
|형식|대상 변경|
