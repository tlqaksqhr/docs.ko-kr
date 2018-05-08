### <a name="contextmenustripsourcecontrol-property-contains-a-valid-control-in-the-case-of-nested-toolstripmenuitems"></a>중첩된 ToolStripMenuItems의 경우 ContextMenuStrip.SourceControl 속성은 유효한 컨트롤 포함함

|   |   |
|---|---|
|설명|.NET Framework 4.7.1 및 이전 버전에서 사용자가 중첩된 <xref:System.Windows.Forms.ToolStripMenuItem> 컨트롤에서 메뉴를 열 경우 <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> 속성은 null을 잘못 반환합니다. .NET framework 4.7.2 이상에서 <xref:System.Windows.Forms.ContextMenuStrip.SourceControl> 속성은 항상 실제 원본 제어로 설정됩니다.|
|제안 해결 방법|<strong>이러한 변경을 선택 또는 해제하는 방법</strong> 응용 프로그램이 이러한 변경의 이점을 활용하도록 하기 위해 .NET Framework 4.7.2 이상에서 실행해야 합니다. 응용 프로그램은 다음과 같은 방법으로 이러한 변경의 이점을 활용할 수 있습니다.<ul><li>.NET Framework 4.7.2를 대상으로 합니다. 이러한 변경 내용은 .NET Framework 4.7.2 이상을 대상으로 하는 Windows Forms 응용 프로그램에서 기본적으로 활성화됩니다.</li><li>.NET Framework 4.7.1 이전 버전을 대상으로 하며 다음 예제와 같이 app.config 파일의 <code>&lt;runtime&gt;</code> 섹션에 [AppContext 스위치](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element)를 추가하고 이를 <code>false</code>로 설정하여 레거시 접근성 동작을 옵트아웃합니다.</li></ul><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>.NET Framework 4.7.2 이상을 대상으로 하고 레거시 동작을 유지하려는 응용 프로그램은 이 AppContext 스위치를 <code>true</code>로 명확하게 설정하여 레거시 원본 제어 값 사용을 옵트인할 수 있습니다.|
|범위|Microsoft Edge|
|버전|4.7.2|
|형식|대상 변경|
|영향을 받는 API|<ul><li><xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType></li></ul>|

