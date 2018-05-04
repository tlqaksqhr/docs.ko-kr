### <a name="icommandcanexecutechanged-event-behaviour-changed-in-net-45"></a>NET 4.5에서 ICommand.CanExecuteChanged 이벤트 동작이 변경되었습니다.

|   |   |
|---|---|
|설명|.NET Framework 4.5에서는 이벤트를 보낸 사람이 이벤트를 발생시킨 개체와 동일한 개체가 아닌 한 <xref:System.Windows.Input.ICommand.CanExecuteChanged?displayProperty=name>이 무시되었습니다. 이 버그는 .NET Framework 4.5 서비스 업데이트에서 수정되었습니다.|
|제안 해결 방법|이 버그는 .NET Framework 4.5 서비스 릴리즈에서 수정되었으므로 .NET Framework가 최신 버전인지 확인하거나 .NET Framework 4.5.1로 업데이트하여 방지할 수 있습니다. 또는 <xref:System.Windows.Input.ICommand.CanExecuteChanged?displayProperty=name> 명령을 실행할 때 보낸 사람이 이벤트를 발생시키는 개체와 동일한지 확인하도록 <xref:System.Windows.Input.ICommand?displayProperty=name>를 사용하는 응용 프로그램 코드를 수정할 수 있습니다.|
|범위|부|
|버전|4.5|
|형식|런타임|
|영향을 받는 API|<ul><li><xref:System.Windows.Input.ICommand.CanExecuteChanged?displayProperty=nameWithType></li></ul>|
|분석기|<ul><li>CD0084</li></ul>|

