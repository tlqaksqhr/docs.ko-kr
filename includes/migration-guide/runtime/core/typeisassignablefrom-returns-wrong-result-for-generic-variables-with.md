### <a name="typeisassignablefrom-returns-wrong-result-for-generic-variables-with-constraints"></a>Type.IsAssignableFrom에서 제약 조건이 있는 제네릭 변수에 대해 잘못된 결과를 반환합니다

|   |   |
|---|---|
|설명|.NET Framework 4.5에서 <xref:System.Type.IsAssignableFrom(System.Type)>은 제약 조건이 있는 일부 제네릭 형식에 대한 모든 경우에 <code>false</code>를 잘못 반환합니다.|
|제안 해결 방법|이 문제는 서비스 업데이트에서 수정되었습니다. 이 문제를 해결하려면 .NET Framework 4.5를 업데이트하거나 .NET Framework 4.5.1 이상으로 업그레이드하십시오. 또는 제네릭 매개 변수에 대해 제약 조건이 있는 제네릭 형식으로 IsAssignableFrom을 사용하지 마십시오. 리플렉션 API는 해결 방법으로 사용될 수 있습니다.|
|범위|부|
|버전|4.5|
|형식|런타임|
|영향을 받는 API|<ul><li><xref:System.Type.IsAssignableFrom(System.Type)?displayProperty=nameWithType></li></ul>|
|분석기|<ul><li>CD0089</li></ul>|

