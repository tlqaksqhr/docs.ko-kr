### <a name="x509certificate2tostringbool-does-not-throw-now-when-net-cannot-handle-the-certificate"></a>X509Certificate2.ToString(bool)은 .NET이 인증서를 처리할 수 없을 때 throw하지 않습니다

|   |   |
|---|---|
|설명|이전에는 verbose 매개 변수에 <code>true</code>가 전달되고 .Net Framework에서 지원하지 않는 인증서가 설치된 경우 이 메서드가 throw되었습니다. 이제 이 메서드는 성공하고 인증서의 액세스할 수 없는 부분을 생략하는 유효한 문자열을 반환합니다.|
|제안 해결 방법|<xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)>에 종속된 모든 코드는 API가 이전에 throw된 일부 경우에서 반환된 문자열이 일부 인증서 데이터(예: 공개 키, 개인 키 및 확장명)를 제외하도록 업데이트되어야 합니다.|
|범위|Microsoft Edge|
|버전|4.6|
|형식|런타임|
|영향을 받는 API|<ul><li><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType></li></ul>|

