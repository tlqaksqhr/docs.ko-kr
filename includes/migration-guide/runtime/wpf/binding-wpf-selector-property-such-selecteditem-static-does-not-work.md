### <a name="binding-a-wpf-selector-property-such-as-selecteditem-to-a-static-property-does-not-work"></a>WPF 선택기 속성(예: 'SelectedItem')을 정적 속성에 바인딩하면 작동하지 않습니다.

|   |   |
|---|---|
|설명|.NET Framework 4.5에서는 데이터가 정적 속성에 바인딩된 WPF 선택기 속성(예: <xref:System.Windows.Controls.ListBox?displayProperty=name> 또는 <xref:System.Windows.Controls.DataGrid?displayProperty=name>의 &#39;SelectedItem&#39;)이 업데이트될 때 이 바인딩 속성이 제대로 업데이트되지 않습니다.|
|제안 해결 방법|이 동작은 .NET Framework 4.5에 대한 서비스 업데이트에서 되돌려졌습니다. 이 문제를 해결하려면 .NET Framework 4.5를 업데이트하거나 .NET Framework 4.5.1 이상으로 업그레이드하십시오.|
|범위|부|
|버전|4.5|
|형식|런타임|

