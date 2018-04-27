### <a name="wpf-layout-rounding-of-margins-has-changed"></a>여백의 WPF 레이아웃 반올림이 변경됨

|   |   |
|---|---|
|설명|여백이 반올림되는 방식과 그 안의 테두리 및 배경이 변경되었습니다. 레이아웃을 변경한 결과는 다음과 같습니다.<ul><li>요소의 너비나 높이가 최대 1픽셀씩 늘어나거나 줄어들 수 있습니다.</li><li>개체의 배치가 최대 1픽셀씩 이동할 수 있습니다.</li><li>가운데 맞춤 요소가 가로 또는 세로로 최대 1픽셀씩 가운데에서 벗어날 수 있습니다.</li></ul>기본적으로 이 새 레이아웃은 .NET Framework 4.6을 대상으로 하는 앱에 대해서만 사용할 수 있습니다.|
|제안 해결 방법|이 수정은 높은 DPI에서 WPF 컨트롤의 오른쪽 또는 아래쪽 잘림을 제거하는 경향이 있으므로 이전 버전의 .NET Framework를 대상으로 하지만 .NET Framework 4.6에서 실행되는 앱은 다음 줄을 app.config 파일의 <code>&lt;runtime&gt;</code> 섹션에 추가하여 이 새 동작을 옵트인(opt in)할 수 있습니다. <code>&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false&quot; /&gt;</code>.NET Framework 4.6을 대상으로 하지만 WPF 컨트롤이 이전 레이아웃 알고리즘을 사용하여 렌더링되도록 하려는 앱은 app.config 파일의 <code>&lt;runtime&gt;</code> 섹션에 <code>&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true&quot; /&gt;</code> 줄을 추가하여 수행할 수 있습니다.|
|범위|부|
|버전|4.6|
|형식|대상 변경|

