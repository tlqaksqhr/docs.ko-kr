### <a name="incorrect-implementation-of-memberdescriptorequals"></a>MemberDescriptor.Equals의 잘못된 구현

|   |   |
|---|---|
|설명|&quot;Equals&quot; 메서드의 원래 구현은 비교 대상인 개체의 두 가지 문자열 특성을 비교했습니다. 즉, 범주 이름을 설명 문자열과 비교했습니다. 해결 방법은 첫 번째 개체의 &quot;범주&quot;를 두 번째 개체의 &quot;범주&quot;와 비교하고, &quot;설명&quot;과 &quot;설명&quot;을 비교하는 것입니다. 4.6.2를 대상으로 하는 경우 MemberDescriptorEqualsReturnsFalseIfEquivalent 구성 값을 true로 설정하여 새 동작을 옵트아웃할 수 있으며, 대상 프레임워크 버전이 4.6.2 미만인 경우 이 수정을 사용하려면 false로 설정합니다.|
|제안 해결 방법|응용 프로그램이 MemberDescriptor.Equals에 종속되어 있고 설명자가 동일할 때 false를 반환하는 경우 및 .NET Framework 4.6.2 버전을 대상으로 하는 경우에 몇 가지 옵션이 있습니다.<ol><li>Equals 메서드 실행 외에도 &quot;범주&quot; 및 &quot;설명&quot; 필드를 수동으로 비교하기 위해 코드를 변경합니다.</li><li>App.config 파일에 다음 값을 추가하여 이러한 변경 내용을 옵트아웃합니다.</li></ol><pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>응용 프로그램이 4.6.1 이하 버전의 .NET Framework를 대상으로 하는 경우 이 변경 내용을 활성화하려면 app.config 파일에 다음 값을 추가하여 호환성 스위치를 false로 설정하면 됩니다.<pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|범위|Microsoft Edge|
|버전|4.6.2|
|형식|대상 변경|
|영향을 받는 API|<ul><li><xref:System.ComponentModel.MemberDescriptor.Equals(System.Object)?displayProperty=nameWithType></li></ul>|

