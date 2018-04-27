### <a name="webutilityhtmlencode-and-webutilityhtmldecode-round-trip-bmp-correctly"></a>WebUtility.HtmlEncode 및 WebUtility.HtmlDecode가 BMP를 올바르게 라운드트립

|   |   |
|---|---|
|설명|.NET Framework 4.5를 대상으로 하는 응용 프로그램의 경우 BMP(기본적인 다국어 문자표) 외의 문자는 <xref:System.Net.WebUtility.HtmlDecode(System.String)> 메서드에 전달될 때 올바르게 라운드트립합니다.|
|제안 해결 방법|이 변경은 현재 응용 프로그램에 영향을 주지 않지만, 원래의 동작을 복원하려면 <code>&lt;httpRuntime&gt;</code> 요소의 <code>targetFramework</code> 속성을 &quot;4.5&quot; 이외의 문자열로 설정합니다. <code>unicodeEncodingConformance</code> 구성 요소의 <code>unicodeDecodingConformance</code> 및 <code>&lt;webUtility&gt;</code> 특성을 설정하여 대상 버전의 .NET Framework에 관계없이 이 동작을 제어할 수도 있습니다.|
|범위|Microsoft Edge|
|버전|4.5|
|형식|대상 변경|
|영향을 받는 API|<ul><li><xref:System.Net.WebUtility.HtmlEncode(System.String)?displayProperty=nameWithType></li><li><xref:System.Net.WebUtility.HtmlEncode(System.String,System.IO.TextWriter)?displayProperty=nameWithType></li></ul>|

