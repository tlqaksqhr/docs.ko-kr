### <a name="winrt-stream-adapters-no-long-call-flushasync-automatically-on-close"></a>종료 시 WinRT 스트림 어댑터가 더 이상 FlushAsync를 자동으로 호출하지 않음

|   |   |
|---|---|
|설명|Windows Store 앱에서 Windows 런타임 스트림 어댑터는 더 이상 Dispose 메서드에서 FlushAsync 메서드를 호출하지 않습니다.|
|제안 해결 방법|이 변경 내용은 영향을 주지 않습니다. 개발자는 다음과 같은 코드를 작성하여 이전 동작을 복원할 수 있습니다.<pre><code class="language-csharp">using (var stream = GetWindowsRuntimeStream() as Stream)&#13;&#10;{&#13;&#10;// do something&#13;&#10;await stream.FlushAsync();&#13;&#10;}&#13;&#10;</code></pre>|
|범위|투명|
|버전|4.5.1|
|형식|런타임|

