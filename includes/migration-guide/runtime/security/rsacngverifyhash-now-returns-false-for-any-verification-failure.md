### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a>RSACng.VerifyHash가 이제 확인 실패에 대해 False를 반환합니다.

|   |   |
|---|---|
|설명|.NET Framework 4.6.2부터 서명 자체의 형식이 잘못된 경우 이 메서드는 <strong>False</strong>를 반환합니다. 이제 모든 확인 실패에 대해 false를 반환합니다. .NET Framework 4.6 및 4.6.1에서는 서명 자체의 형식이 잘못된 경우 메서드에서 <xref:System.Security.Cryptography.CryptographicException?displayProperty=name>을 throw합니다.|
|제안 해결 방법|유효성 검사가 실패하고 이 메서드가 <strong>False</strong>를 반환하는 경우에는 <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> 처리에 따라 실행되는 코드를 대신 실행해야 합니다.|
|범위|부|
|버전|4.6.2|
|형식|런타임|
|영향을 받는 API|<ul><li><xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|

