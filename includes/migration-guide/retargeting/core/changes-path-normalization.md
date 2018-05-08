### <a name="changes-in-path-normalization"></a>경로 정규화의 변경

|   |   |
|---|---|
|설명|.NET Framework 4.6.2를 대상으로 하는 앱부터 런타임이 경로를 정규화하는 방식이 변경되었습니다. 경로 정규화 중에는 대상 운영 체제의 올바른 경로에 맞게 경로 또는 파일을 식별하는 문자열이 수정됩니다. 정규화에는 일반적으로 다음이 수행됩니다.<ul><li>구성 요소 및 디렉터리 구분 기호 정규화</li><li>상대 경로에 현재 디렉터리 적용</li><li>경로의 상대 디렉터리(.) 또는 부모 디렉터리(..) 평가</li><li>지정된 문자 자르기</li></ul>.NET Framework 4.6.2를 대상으로 하는 앱부터는 경로 정규화의 다음 변경이 기본적으로 사용됩니다.<ul><li>런타임은 운영 체제의 [GetFullPathName](https://msdn.microsoft.com/library/windows/desktop/aa364963(v=vs.85).aspx) 함수를 지연시켜 경로를 정규화합니다.</li><li>정규화 중에 더 이상 디렉터리 세그먼트의 끝(예: 디렉터리 이름 끝의 공백)이 잘리지 않습니다.</li><li><code>\.&lt;/code&gt; and, for file I/O APIs in mscorlib.dll, <code>\?&lt;/code&gt;.을 포함하여 완전 신뢰에서 장치 경로 구문 지원</li><li>The runtime does not validate device syntax paths.</li><li>The use of device syntax to access alternate data streams is supported.</li></ul>These changes improve performance while allowing methods to access previously inaccessible paths. Apps that target the .NET Framework 4.6.1 and earlier versions but are running under the .NET Framework 4.6.2 or later are unaffected by this change.|
|제안 해결 방법|.NET Framework 4.6.2 이상을 대상으로 하는 앱은 응용 프로그램 구성 파일의 <code>&lt;runtime&gt;</code> 섹션에 다음을 추가하여 이 변경을 옵트아웃하고 레거시 정규화를 사용할 수 있습니다.<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.UseLegacyPathHandling=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>.NET Framework 4.6.1 이하를 대상으로 하지만 .NET Framework 4.6.2 이상에서 실행되는 앱은 응용 프로그램 구성 파일의 <code>&lt;runtime&gt;</code> 섹션에 다음 줄을 추가하여 경로 정규화에 변경을 사용할 수 있습니다.<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.UseLegacyPathHandling=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|범위|부|
|버전|4.6.2|
|형식|대상 변경|

