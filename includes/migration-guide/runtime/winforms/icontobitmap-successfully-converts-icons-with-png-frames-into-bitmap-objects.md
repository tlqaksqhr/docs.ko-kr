### <a name="icontobitmap-successfully-converts-icons-with-png-frames-into-bitmap-objects"></a>Icon.ToBitmap은 PNG 프레임이 있는 아이콘을 Bitmap 개체로 성공적으로 변환합니다.

|   |   |
|---|---|
|설명|<xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> 메서드는 .NET Framework 4.6을 대상으로 하는 앱부터 PNG 프레임이 있는 아이콘을 Bitmap 개체로 성공적으로 변환합니다. .NET Framework 4.5.2 및 이전 버전을 대상으로 하는 앱에서 아이콘 개체에 PNG 프레임이 있으면 <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> 메서드가 <xref:System.ArgumentOutOfRangeException> 예외를 throw합니다. 이 변경 사항은 .NET Framework 4.6을 대상으로 다시 컴파일되고, 아이콘 개체에 PNG 프레임이 있는 경우 throw되는 <xref:System.ArgumentOutOfRangeException>에 대한 특수 처리를 구현하는 앱에 영향을 미칩니다. .NET Framework 4.6에서 실행되는 경우 변환이 성공하고 <xref:System.ArgumentOutOfRangeException> 이 더 이상 throw되지 않습니다. 따라서 예외 처리기가 더 이상 호출되지 않습니다.<ul><li>[X] Quirked // 일반적으로 런타임 대상 지정, AppContext 또는 구성 파일을 사용하여 기능을 설정/해제하는 몇 가지 메커니즘을 사용합니다. 일부 상황에서는 자동으로 설정되어야 합니다.</li><li>[] 빌드 시간 중단 // 다시 컴파일하려고 하면 중단됩니다</li></ul>|
|제안 해결 방법|이 동작이 필요 없는 경우 app.config 파일의 <code>&lt;runtime&gt;</code> 섹션에 다음 요소를 추가하여 이전 동작을 유지할 수 있습니다.<pre><code>&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Drawing.DontSupportPngFramesInIcons=true&quot; /&gt;&#13;&#10;</code></pre>App.config 파일에 이미 <code>AppContextSwitchOverrides</code> 요소가 포함되어 있는 경우 새 값은 다음과 같이 값 특성과 병합되어야 합니다.<pre><code>&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Drawing.DontSupportPngFramesInIcons=true;&lt;previous key&gt;=&lt;previous value&gt;&quot; /&gt;&#13;&#10;</code></pre>|
|범위|부|
|버전|4.6|
|형식|런타임|
|영향을 받는 API|<ul><li><xref:System.Drawing.Icon.ToBitmap?displayProperty=nameWithType></li></ul>|

