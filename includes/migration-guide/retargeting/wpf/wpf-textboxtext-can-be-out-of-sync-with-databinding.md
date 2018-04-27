### <a name="wpf-textboxtext-can-be-out-of-sync-with-databinding"></a>WPF TextBox.Text가 데이터 바인딩과 비동기화될 수 있음

|   |   |
|---|---|
|설명|경우에 따라 <xref:System.Windows.Controls.TextBox.Text> 속성은 데이터 바인딩 쓰기 작업 중 속성이 수정되면 데이터 바인딩된 속성 값의 이전 값을 반영합니다.|
|제안 해결 방법|이는 부정적인 영향을 주어서는 안 됩니다. 그러나 <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty> 속성을 <code>false</code>로 설정하여 이전 동작을 복원할 수 있습니다.|
|범위|Microsoft Edge|
|버전|4.5|
|형식|대상 변경|
|영향을 받는 API|<ul><li><xref:System.Windows.Controls.TextBox.Text?displayProperty=nameWithType></li></ul>|

