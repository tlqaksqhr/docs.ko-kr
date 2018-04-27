### <a name="sqlvariant-data-uses-sqlvariant-collation-rather-than-database-collation"></a>Sql_variant 데이터는 데이터베이스 데이터 정렬 대신 sql_variant 데이터 정렬을 사용합니다.

|   |   |
|---|---|
|설명|<code>sql_variant</code> 데이터는 데이터베이스 데이터 정렬 대신 <code>sql_variant</code> 데이터 정렬을 사용합니다.|
|제안 해결 방법|이러한 변경을 통해 데이터베이스 데이터 정렬이 <code>sql_variant</code> 데이터 정렬과 다른 경우 데이터 손상 가능성을 해결합니다. 손상된 데이터를 사용하는 응용 프로그램은 오류가 발생할 수 있습니다.|
|범위|투명|
|버전|4.5|
|형식|런타임|

