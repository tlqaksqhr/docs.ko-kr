### <a name="eventlistener-truncates-strings-with-embedded-nulls"></a>EventListener는 포함된 null이 있는 문자열을 자릅니다.

|   |   |
|---|---|
|설명|<xref:System.Diagnostics.Tracing.EventListener?displayProperty=name>는 포함된 null이 있는 문자열을 자릅니다. Null 문자는 <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> 클래스에서 지원되지 않습니다. 이 변경 내용은 <xref:System.Diagnostics.Tracing.EventListener?displayProperty=name>를 사용하여 프로세스의 <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> 데이터를 읽고 null 문자를 구분 기호로 사용하는 앱에만 영향을 줍니다.|
|제안 해결 방법|가능하면 포함된 null 문자를 사용하지 않도록 <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> 데이터를 업데이트해야 합니다.|
|범위|Microsoft Edge|
|버전|4.5.1|
|형식|런타임|
|영향을 받는 API|<ul><li><xref:System.Diagnostics.Tracing.EventListener.%23ctor?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords,System.Collections.Generic.IDictionary{System.String,System.String})?displayProperty=nameWithType></li></ul>|

