### <a name="xml-schema-validation-is-stricter"></a>XML 스키마 유효성 검사가 더 엄격합니다.

|   |   |
|---|---|
|설명|.NET Framework 4.5에서는 XML 스키마 유효성 검사가 더 엄격합니다. mailto 프로토콜과 같이 URI의 유효성을 검사하기 위해 xsd:anyURI을 사용하는 경우 URI에 공백이 있으면 유효성 검사에 실패합니다. 이전 버전의 .NET Framework에서는 유효성 검사에 성공했습니다. 해당 변경 내용은 .NET Framework 4.5를 대상으로 하는 응용 프로그램에만 영향을 줍니다.|
|제안 해결 방법|완화된 .NET Framework 4.0 유효성 검사가 필요한 경우 유효성 검사 응용 프로그램은 .NET Framework 4.0 버전을 대상으로 할 수 있습니다. 하지만 .NET Framework 4.5로 대상을 변경할 때는 anyURI 데이터 형식을 사용하는 잘못된 URI(공백 포함)가 특성 값으로 요구되지 않도록 코드 검토를 수행해야 합니다.|
|범위|부|
|버전|4.5|
|형식|대상 변경|

