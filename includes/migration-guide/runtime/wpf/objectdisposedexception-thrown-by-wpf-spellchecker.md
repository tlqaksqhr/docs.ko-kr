### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a>WPF 맞춤법 검사기에 의해 throw된 ObjectDisposedException

|   |   |
|---|---|
|설명|WPF 응용 프로그램은 응용 프로그램 종료 중에 맞춤법 검사기에서 throw된 <xref:System.ObjectDisposedException?displayProperty=name>으로 인해 때때로 크래시됩니다. 이는 .NET Framework 4.7 WPF에서 예외를 제대로 처리하여 응용 프로그램이 더 이상 부정적인 영향을 받지 않도록 함으로써 해결되었습니다. 디버거에서 실행 중인 응용 프로그램에서는 경우에 따라 첫째 예외만 계속 확인될 수 있습니다.|
|제안 해결 방법|NET Framework 4.7로 업그레이드|
|범위|Microsoft Edge|
|버전|4.6.1|
|형식|런타임|

