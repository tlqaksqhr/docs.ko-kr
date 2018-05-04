### <a name="non-pooled-sql-connections-will-leak-memory-if-not-explicitly-disposed"></a>풀링되지 않은 SQL 연결이 명시적으로 삭제되지 않으면 메모리가 누수됩니다.

|   |   |
|---|---|
|설명|.NET Framework 4.5에서는 풀링되지 않은 SQL 연결이 Dispose, Close 또는 using을 통해 명시적으로 노출되지 않으면 메모리가 누수됩니다.|
|제안 해결 방법|이 문제는 .NET Framework 4.5 서비스 업데이트에서 수정되었습니다. 이 문제를 해결하려면 .NET Framework 4.5를 업데이트하거나 .NET Framework 4.5.1 이상으로 업그레이드하십시오. 또는 &#39;using&#39; 패턴(모범 사례)에서 <xref:System.Data.SqlClient.SqlConnection?displayProperty=name>을 사용하거나 연결이 더 이상 필요하지 않을 때 Dispose 또는 Close를 명시적으로 호출하여 이 문제를 방지할 수도 있습니다.|
|범위|Microsoft Edge|
|버전|4.5|
|형식|런타임|
|영향을 받는 API|<ul><li><xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String)?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String%2CSystem.Data.SqlClient.SqlCredential)?displayProperty=nameWithType></li></ul>|

