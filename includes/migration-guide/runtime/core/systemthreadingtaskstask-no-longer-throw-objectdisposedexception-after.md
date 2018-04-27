### <a name="systemthreadingtaskstask-no-longer-throw-objectdisposedexception-after-object-is-disposed"></a>개체를 삭제한 후 System.Threading.Tasks.Task는 더 이상 ObjectDisposedException을 throw하지 않습니다

|   |   |
|---|---|
|설명|<xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle>을 제외하고, <xref:System.Threading.Tasks.Task?displayProperty=name> 메서드는 개체가 삭제된 후에 <xref:System.ObjectDisposedException?displayProperty=name> 예외를 더 이상 throw하지 않습니다. 이 변경은 캐시된 작업의 사용을 지원합니다. 예를 들어, 메서드는 새로운 작업을 할당하는 대신에 이미 완료된 작업을 나타내기 위해 캐시된 작업을 반환할 수 있습니다. 작업의 모든 소비자는 다시 사용할 수 없게 렌더링된 작업을 삭제할 수 있었기 때문에 이전 .NET Framework 버전에서는 이것이 불가능했습니다.|
|제안 해결 방법|작업 메서드는 개체가 삭제되는 경우에 <xref:System.ObjectDisposedException?displayProperty=name>을 더 이상 throw하지 않는다는 것을 기억하세요. 앱이 작업이 삭제되었는지 알도록 이 예외에 종속된 경우 <xref:System.Threading.Tasks.Task.Status>를 사용하여 작업의 상태를 명시적으로 확인하도록 업데이트해야 합니다.|
|범위|부|
|버전|4.5|
|형식|런타임|

