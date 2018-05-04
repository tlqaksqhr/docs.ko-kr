### <a name="opt-in-break-to-revert-from-different-45-sql-generation-to-simpler-40-sql-generation"></a>다른 4.5 SQL 생성에서 더 간단한 4.0 SQL 생성으로 되돌리는 옵트인 문제

|   |   |
|---|---|
|설명|OrderBy를 먼저 사용하지 않고 JOIN 문을 생성하고 제한 작업에 대한 호출을 포함하는 쿼리가 이제 보다 단순한 SQL을 생성합니다. .NET Framework 4.5로 업그레이드한 후 이러한 쿼리는 이전 버전보다 더욱 복잡한 SQL을 생성했습니다.|
|제안 해결 방법|이 기능은 기본적으로 비활성화되어 있습니다. Entity Framework가 성능 저하를 일으키는 추가 JOIN 문을 생성하는 경우 다음의 항목을 응용 프로그램 구성 파일(app.config)의 <code>&lt;appSettings&gt;</code> 섹션에 추가하여 이 기능을 활성화할 수 있습니다.<pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyLimitOperations&quot; value=&quot;true&quot; /&gt;&#13;&#10;</code></pre>|
|범위|투명|
|버전|4.5.2|
|형식|런타임|

