### <a name="wpf-textbox-defaults-to-undo-limit-of-100"></a>WPF TextBox 기본값이 100개의 제한을 실행 취소

|   |   |
|---|---|
|설명|.NET 4.5에서는 WPF TextBox에 대한 실행 취소 제한 기본값은 100(.NET 4.0에서 무제한이던 것과 반대)|
|제안 해결 방법|100개의 실행 취소 제한이 너무 낮으면 제한을 <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit>로 명시적으로 설정할 수 있습니다.|
|범위|Microsoft Edge|
|버전|4.5|
|형식|런타임|
|영향을 받는 API|<ul><li><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|

