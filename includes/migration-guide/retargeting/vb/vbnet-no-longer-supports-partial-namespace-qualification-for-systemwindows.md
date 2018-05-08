### <a name="vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a>VB.NET가 System.Windows API에 대한 부분 네임스페이스 한정을 더 이상 지원하지 않음

|   |   |
|---|---|
|설명|.NET Framework 4.5.2부터 VB.NET 프로젝트는 부분적으로 정규화된 네임스페이스를 사용하는 System.Windows API를 지정할 수 없습니다. 예를 들어 <code>Windows.Forms.DialogResult</code>를 참조하면 실패합니다. 대신, 코드는 정규화된 이름(<xref:System.Windows.Forms.DialogResult>)을 참조하거나 특정 네임스페이스를 가져오고 간단히 <xref:System.Windows.Forms.DialogResult?displayProperty=name>를 참조해야 합니다.|
|제안 해결 방법|코드는 간단한 이름(및 관련 네임스페이스를 가져오는) 또는 정규화된 이름을 사용하는 <code>System.Windows</code> API를 참조하도록 업데이트되어야 합니다.|
|범위|부|
|버전|4.5.2|
|형식|대상 변경|

