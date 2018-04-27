### <a name="calling-itemsrefresh-on-a-wpf-listbox-listview-or-datagrid-with-items-selected-can-cause-duplicate-items-to-appear-in-the-element"></a>항목이 선택된 WPF ListBox, ListView, 또는 DataGrid에서 Items.Refresh를 호출하면 요소에 중복 항목이 표시될 수 있습니다.

|   |   |
|---|---|
|설명|.NET Framework 4.5에서 항목이 <xref:System.Windows.Controls.ListBox?displayProperty=name>에 선택되어 있을 때 ListBox.Items.Refresh 코드를 호출하면 선택된 항목이 목록에 중복될 수 있습니다. 유사한 문제가 <xref:System.Windows.Controls.ListView?displayProperty=name> 및 <xref:System.Windows.Controls.DataGrid?displayProperty=name>에서 발생합니다. 이것은 .NET Framework 4.6에서 수정되었습니다.|
|제안 해결 방법|이 문제는 <xref:System.Windows.Data.CollectionView.Refresh?displayProperty=name>를 호출하기 전에 프로그래밍 방식으로 항목 선택을 취소하고 호출이 완료된 후에 다시 선택하여 해결할 수 있습니다. 또는 .NET Framework 4.6에서 이 문제가 수정되어 해당 버전의 .NET Framework로 업그레이드하여 해결할 수 있습니다.|
|범위|부|
|버전|4.5|
|형식|런타임|
|영향을 받는 API|<ul><li><xref:System.Windows.Data.CollectionView.Refresh?displayProperty=nameWithType></li></ul>|

