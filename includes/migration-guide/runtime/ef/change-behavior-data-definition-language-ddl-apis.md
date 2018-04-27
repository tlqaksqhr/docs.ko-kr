### <a name="change-in-behavior-in-data-definition-language-ddl-apis"></a>DDL(데이터 정의 언어) API에서 동작 변경

|   |   |
|---|---|
|설명|AttachDBFilename이 지정되면 DDL API의 동작은 다음과 같이 변경됩니다.<ul><li>연결 문자열에 초기 카탈로그 값을 지정할 필요는 없습니다. 이전에는 AttachDBFilename 및 초기 카탈로그가 모두 필요했습니다.</li><li>AttachDBFilename 및 초기 카탈로그가 모두 지정되고 제공된 MDF 파일이 있는 경우 ObjectContext.DatabaseExists 메서드는 true를 반환합니다. 이전에는 false를 반환했습니다.</li><li>AttachDBFilename 및 초기 카탈로그가 모두 지정되고 제공된 MDF 파일이 있는 경우 ObjectContext.DeleteDatabase 메서드 호출은 파일을 삭제합니다.</li><li>연결 문자열이 존재하지 않는 MDF와 존재하지 않는 카탈로그를 사용하여 AttachDBFilename 값을 지정할 때 ObjectContext.DeleteDatabase가 호출되면 메서드가 InvalidOperationException 예외를 throw합니다. 이전에는 SqlException 예외를 throw했습니다.</li></ul>|
|제안 해결 방법|이러한 변경으로 인해 DDL API를 사용하는 도구와 응용 프로그램을 보다 쉽게 빌드할 수 있습니다. 이러한 변경 사항은 다음 시나리오에서 응용 프로그램 호환성에 영향을 줄 수 있습니다.<ul><li>사용자는 ObjectContext.DatabaseExists가 true를 반환하는 경우 ObjectContext.DeleteDatabase를 호출하는 대신 직접 DROP DATABASE 명령을 실행하는 코드를 씁니다. 이는 데이터베이스가 연결되지 않았지만 MDF 파일이 있는 경우 기존 코드를 중단시킵니다.</li><li>사용자는 초기 카탈로그 및 MDF 파일이 없을 때 InvalidOperationException 예외보다는 SqlException 예외를 throw하기 위해 ObjectContext.DeleteDatabase 메서드를 기대하는 코드를 씁니다.</li></ul>|
|범위|부|
|버전|4.5|
|형식|런타임|

