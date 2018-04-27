### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a>HttpUtility.JavaScriptStringEncode가 앰퍼샌드를 이스케이프합니다.

|   |   |
|---|---|
|설명|.NET Framework 4.5부터 <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=name>이 앰퍼샌드(&amp;) 문자를 이스케이프합니다.|
|제안 해결 방법|응용 프로그램이 이 메서드의 이전 동작에 종속되는 경우 aspnet:JavaScriptDoNotEncodeAmpersand 설정을 구성 파일에 있는 [ASP.NET appSettings 요소](https://msdn.microsoft.com/library/hh975440.aspx)에 추가할 수 있습니다.|
|범위|부|
|버전|4.5|
|형식|런타임|
|영향을 받는 API|<ul><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType></li></ul>|

