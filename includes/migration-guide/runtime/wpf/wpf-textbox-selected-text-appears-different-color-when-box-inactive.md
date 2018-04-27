### <a name="wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a>텍스트 상자가 비활성일 때 WPF TextBox가 선택한 텍스트가 다른 색으로 표시됩니다.

|   |   |
|---|---|
|설명|.NET 4.5에서 WPF 텍스트 상자 컨트롤이 비활성일 때(포커스 없음) 상자 안의 선택된 텍스트가 컨트롤이 활성화될 때와 다른 색으로 표시됩니다.|
|제안 해결 방법|<xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> 속성을 <code>false</code>로 설정하여 이전(.NET 4.0) 동작을 복원할 수 있습니다.|
|범위|Microsoft Edge|
|버전|4.5|
|형식|런타임|
|영향을 받는 API|<ul><li><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|

