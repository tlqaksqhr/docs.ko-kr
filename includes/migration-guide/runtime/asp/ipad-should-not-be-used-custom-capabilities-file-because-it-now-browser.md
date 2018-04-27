### <a name="ipad-should-not-be-used-in-custom-capabilities-file-because-it-is-now-a-browser-capability"></a>이제 iPad는 브라우저 기능이므로 사용자 지정 기능 파일에서 사용해서는 안 됩니다.

|   |   |
|---|---|
|설명|.NET 4.5부터 iPad는 기본 ASP.NET 브라우저 기능 파일의 식별자이므로 사용자 지정 기능 파일에 사용해서는 안 됩니다.|
|제안 해결 방법|iPad 관련 기능이 필요한 경우, 사용자 에이전트 일치로 새로운 &quot;IPad&quot; ID를 생성하는 대신 사전 정의된 게이트웨이 refID &quot;IPad&quot;에서 기능을 설정하여 iPad 동작을 수정해야 합니다.|
|범위|Microsoft Edge|
|버전|4.5|
|형식|런타임|

