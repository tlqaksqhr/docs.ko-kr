### <a name="sqlconnection-can-no-longer-connect-to-sql-server-1997-or-databases-using-the-via-adapter"></a>SqlConnection은 더 이상 VIA 어댑터를 사용하여 SQL Server 1997 또는 데이터베이스에 연결할 수 없습니다.

|   |   |
|---|---|
|설명|[VIA(Virtual Interface Adapter) 프로토콜](https://technet.microsoft.com/library/ms191229%28v=sql.105%29.aspx)을 사용하는 SQL Server 데이터베이스에 대한 연결은 더 이상 지원되지 않습니다. SQL Server 데이터베이스에 연결하는 데 사용되는 프로토콜은 연결 문자열에 표시됩니다. VIA 연결은 &lt;servername&gt;을 통해 포함됩니다. 이 앱이 VIA(예: tcp: 또는 np:) 이외의 프로토콜을 통해 연결하는 경우 주요 변경 내용이 발생하지 않습니다. 또한 SQL Server 7(1997)에 대한 연결은 더 이상 지원되지 않습니다.|
|제안 해결 방법|VIA 프로토콜은 사용되지 않으므로 대체 프로토콜을 사용하여 SQL 데이터베이스에 연결해야 합니다. 가장 일반적으로 사용되는 프로토콜은 TCP/IP입니다. TCP/IP 프로토콜을 사용하기 위한 지침은 [여기](https://msdn.microsoft.com/library/bb909712.aspx)에 있습니다. 데이터베이스가 인트라넷 내에서만 액세스되는 경우에 네트워크가 느린 경우 공유 파이프 프로토콜이 더 나은 성능을 제공할 수 있습니다.|
|범위|Microsoft Edge|
|버전|4.5|
|형식|런타임|
|영향을 받는 API|<ul><li><xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String)?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String,System.Data.SqlClient.SqlCredential)?displayProperty=nameWithType></li></ul>|

