### <a name="httprequestcontentencoding-property-prohibits-utf7"></a>HttpRequest.ContentEncoding 속성에 UTF7이 금지됨

|   |   |
|---|---|
|설명|.NET Framework 4.5부터 <xref:System.Web.HttpRequest?displayProperty=name>의 본문에 UTF-7 인코딩이 금지됩니다. 경우에 따라 UTF-7 수신 데이터에 종속되는 응용 프로그램 데이터가 제대로 디코딩되지 않습니다.|
|제안 해결 방법|이상적으로는 <xref:System.Web.HttpRequest?displayProperty=name>에서 인코딩 UTF-7을 사용하지 않도록 응용 프로그램을 업데이트해야 합니다. 대신에 [appSettings](https://msdn.microsoft.com/library/hh975440(v=vs.110).aspx) 요소의 <code>aspnet:AllowUtf7RequestContentEncoding</code> 특성을 사용하여 레거시 동작을 복원할 수 있습니다.|
|범위|Microsoft Edge|
|버전|4.5|
|형식|런타임|
|영향을 받는 API|<ul><li><xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType></li></ul>|

