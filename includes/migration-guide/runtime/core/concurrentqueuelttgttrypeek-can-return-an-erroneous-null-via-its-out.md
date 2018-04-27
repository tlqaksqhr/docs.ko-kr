### <a name="concurrentqueuelttgttrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a>ConcurrentQueue&lt;T&gt;.TryPeek는 out 매개 변수를 통해 잘못된 null을 반환할 수 있습니다.

|   |   |
|---|---|
|설명|일부 다중 스레드 시나리오에서 <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=name> true를 반환할 수 있지만 (올바르고 미리 본 값 대신) null 값으로 out 매개 변수를 채웁니다.|
|제안 해결 방법|이 문제는 .NET Framework 4.5.1에서 수정되었습니다. 해당 프레임워크로 업그레이드하면 문제가 해결됩니다.|
|범위|주요함|
|버전|4.5|
|형식|런타임|
|영향을 받는 API|<ul><li><xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=nameWithType></li></ul>|

