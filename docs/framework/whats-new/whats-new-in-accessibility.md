---
title: ".NET Framework의 내게 필요한 옵션의 새로운 기능"
ms.custom: updateeachrelease
ms.date: 10/13/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: what's new [.NET Framework]
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4886dad94d3a67e78525241a1538c06b9fe4b0be
ms.sourcegitcommit: 6f49c973f62855ffd6c4a322903e7dd50c5c1b50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2017
---
# <a name="whats-new-in-accessibility-in-the-net-framework"></a>.NET Framework의 내게 필요한 옵션의 새로운 기능

.NET Framework 응용 프로그램 사용자에 대 한 자세한 accessibile 만드는 것을 목표로 합니다. 내게 필요한 옵션 기능 환경을 제공할 수 있도록 적절 한 사용자가 보조 기술에 대 한 응용 프로그램을 허용 합니다. .NET Framework 4.7.1 부터는.NET Framework 액세스할 수 있는 응용 프로그램을 만드는 데 사용할 수 있는 내게 필요한 옵션 기능 향상의 다 수 포함 되어 있습니다. 

새로운 내게 필요한 옵션 기능은 4.7.1.NET Framework를 대상으로 하는 응용 프로그램에 대해 기본적으로 활성화 되어 이상이 됩니다. 또한 4.7.1.NET Framework에서 실행 되 고 또는 나중에 선택할 수 있지만 이전 버전의.NET Framework 대상 하는 응용 프로그램의 레거시 내게 필요한 옵션 동작 (및 함으로써.NET Framework 4.7.1의에서 내게 필요한 옵션 기능이 향상 옵트인) 하 여 다음 스위치를 추가 [ `<AppContextSwitchOverrides>` ](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 요소에는 [ `<runtime>` ](~/docs/framework/configure-apps/file-schema/runtime/index.md) 응용 프로그램의 구성 파일의 섹션입니다. 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

4.7.1 부터는.NET Framework의 버전을 대상으로 하는 응용 프로그램에 다음 스위치를 추가 하 여 내게 필요한 옵션 기능을 비활성화할 수 마찬가지로,는 [ `<AppContextSwitchOverrides>` ](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 요소에는 [ `<runtime>` ](~/docs/framework/configure-apps/file-schema/runtime/index.md) 응용 프로그램의 구성 파일의 섹션입니다. 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-the-net-framework-471"></a>.NET Framework 4.7.1의에서 내게 필요한 옵션의 새로운 기능

.NET Framework 4.7.1에 다음과 같은 영역의 새 내게 필요한 옵션 기능이 포함 됩니다.

- [WPF(Windows Presentation Foundation)](#windows-presentation-foundation-wpf)

- [Windows Forms](#windows-forms-accessibility-improvements)

### <a name="windows-presentation-foundation-wpf"></a>WPF(Windows Presentation Foundation)

**화면 판독기 개선**

접근성 향상 된 기능을 사용할 경우.NET Framework 4.7.1 화면 판독기에 영향을 주는 다음과 같은 향상 기능이 포함 되어 있습니다.

- .NET Framework 4.7 이전 버전에서 <xref:System.Windows.Controls.Expander> 단추가 화면 판독기가 발표 된 컨트롤입니다. .NET Framework 4.7.1 부터는 올바르게 별도로 공지 되 확장/축소 가능한 그룹 이라고 합니다.

- .NET Framework 4.7 이전 버전에서 <xref:System.Windows.Controls.DataGridCell> 컨트롤은 화면 판독기가 "custom"으로 발표 된 .NET Framework 4.7.1 부터는 이제 올바르게 별도로 공지 되 데이터 표 형태 셀 (지역화 된)으로 합니다.
 
- .NET Framework 4.7.1 부터는 화면 판독기의 편집 가능한 이름을 알리기 <xref:System.Windows.Controls.ComboBox>합니다.

- .NET Framework 4.7 이전 버전에서 <xref:System.Windows.Controls.PasswordBox> 컨트롤 "보기의 항목 없음"으로 발표 된 또는 잘못 된 동작입니다. 이 문제는.NET Framework 4.7.1부터 해결 합니다.     

**UIAutomation LiveRegion 지원**

내레이터 도움말 사람과 같은 화면 판독기가 포커스가 있는 UI 콘텐츠의 텍스트 음성 변환 출력에 의해 응용 프로그램의 UI 내용을 읽고 하는 일반적으로 합니다. 그러나 UI 요소를 변경 하 여 포커스가 없는 경우 사용자 알림이 표시 되지 않을 수 있습니다 및 중요 한 정보를 놓칠 수 있습니다. 이 문제를 해결할 수 있는 라이브 영역 목표입니다. 개발자는 화면 판독기 또는 다른 UIAutomation 클라이언트 UI 요소에 중요 한 변경 사항 이루어졌을 알리기 위해 사용할 수 있습니다. 화면 판독기 방법 및 시점을 세울 수이 변경의 사용자에 게에 있습니다. 

라이브 영역을 지원 하려면 다음과 같은 Api WPF에 추가 되었습니다.

- <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> 및 <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> 식별 하는 필드는 **LiveSetting** 속성 및 **LiveRegionChanged** 이벤트입니다. XAML을 사용 하 여 설정할 수 있습니다.

- **AutomationProperties.LiveSetting** 연결 된 사용자에 대 한 UI 변경의 중요성 화면 판독기에 게 속성입니다.

- <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> 을 식별 하는 **AutomationProperties.LiveSetting** 연결 된 속성입니다.
 
- <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> 제공 하는 재정의 될 수 있는 메서드는 **LiveSetting** 값입니다.

- <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> 및 <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> 가져오고 설정 하는 메서드는 **LiveSetting** 값입니다.
 
- <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> 다음과 같은 가능한을 정의 하는 열거형 **LiveSetting** 값:

   - <xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>. 요소는 라이브 영역의 콘텐츠 변경 된 경우 알림을 보내지 않습니다.   
   - <xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>. 라이브 영역의 콘텐츠가 변경된 경우 요소는 비중단 알림을 보냅니다.   

  - <xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>. 라이브 영역의 콘텐츠가 변경된 경우 요소는 중단 알림을 보냅니다.   

LiveRegion 설정 하 여 만들 수 있습니다는 **AutomationProperties.LiveSetting** 다음 예제와 같이 관심 있는 요소의 속성에:   

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

라이브 영역에 있는 데이터를 변경 하는 경우 화면 판독기에 알려야 할 하면 명시적으로 이벤트를 발생 다음 샘플과 같이 합니다.

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```
```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

**고대비**

.NET Framework 4.7.1 부터는 고대비의 향상 된 기능에 적용 된 다양 한 WPF 컨트롤입니다. 이제 표시 되는 경우는 <xref:System.Windows.SystemParameters.HighContrast%2A> 설정 되었습니다. 여기에는 다음이 포함됩니다.

- <xref:System.Windows.Controls.Expander> 컨트롤

    에 대 한 시각적 포커스는 <xref:System.Windows.Controls.Expander> 컨트롤에 표시 됩니다. 에 대 한 키보드 표시 <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox>, 및 <xref:System.Windows.Controls.RadioButton> 컨트롤이 표시 됩니다. 예:

    이전: 
    
    ![내게 필요한 옵션 기능 향상 하기 전에 포커스가 있는 expander 컨트롤](media/expander-before.png)

    이후: 

    ![내게 필요한 옵션 기능 향상 후 포커스가 있는 expander 컨트롤](media/expander-after.png)

- <xref:System.Windows.Controls.CheckBox>및 <xref:System.Windows.Controls.RadioButton> 컨트롤
 
    텍스트는 <xref:System.Windows.Controls.CheckBox> 및 <xref:System.Windows.Controls.RadioButton> 컨트롤 보기에서 고대비 테마 선택 하면 쉽게 되었습니다. 예:

    이전: 

    ![내게 필요한 옵션 기능 향상 하기 전에 포커스가 있는 고대비 라디오 단추](media/radio-button-before.png)
    
    이후: 

    ![내게 필요한 옵션 기능 향상 후 포커스가 있는 고대비 라디오 단추](media/radio-button-after.png)

- <xref:System.Windows.Controls.ComboBox> 컨트롤
 
    .NET Framework 4.7.1, 비활성화 된 테두리부터 <xref:System.Windows.Controls.ComboBox> 컨트롤은 사용할 수 없는 텍스트 색입니다. 예:
    
    이전: 

     ![콤보 상자 테두리와 텍스트 내게 필요한 옵션 기능 향상 하기 전에 사용 하지 않도록 설정](media/combo-disabled-before.png)

    이후:   

     ![내게 필요한 옵션 기능 향상 이후에 테두리와 텍스트를 비활성화 하는 콤보 상자](media/combo-disabled-after.png)

    또한 사용 안 함 및 포커스가 있는 단추는 올바른 테마 색을 사용 합니다.

    이전:

    ![내게 필요한 옵션 기능 향상 하기 전에 단추 테마 색](media/button-themes-before.png) 
    
    이후: 

    ![내게 필요한 옵션 기능 향상 후 단추 테마 색](media/button-themes-after.png) 

    .NET Framework 4.7 및 이전 버전에서는 설정에서 마지막으로, 한 <xref:System.Windows.Controls.ComboBox> 컨트롤의 스타일을 `Toolbar.ComboBoxStyleKey` 표시 되지 않도록 하려면 드롭다운 화살표를 발생 합니다. 이 문제는.NET Framework 4.7.1부터 해결 합니다. 예:

    이전: 

    ![내게 필요한 옵션 기능 향상 하기 전에 Toolbar.ComboBoxStyleKey](media/comboboxstylekey-before.png) 
    
    이후: 

    ![내게 필요한 옵션 기능 향상 후 Toolbar.ComboBoxStyleKey](media/comboboxstylekey-after.png) 

- <xref:System.Windows.Controls.DataGrid> 컨트롤

    .NET Framework 4.7.1에 있는 정렬 표시기 화살표부터 <xref:System.Windows.Controls.DataGrid> 지금 사용 하 여 해결 테마 색을 제어 합니다. 예:

    이전: 

    ![내게 필요한 옵션 기능 향상 하기 전에 정렬 표시기 화살표](media/sort-indicator-before.png) 
    
    이후:   
 
    ![내게 필요한 옵션 기능 향상 후 정렬 표시기 화살표](media/sort-indicator-after.png) 
    
    또한.NET Framework 4.7 및 이전 버전에서는 기본 링크 스타일으로 변경 마우스에서 잘못 된 색을 통해 고대비 모드. 이.NET Framework 4.7.1부터 확인 됩니다. 마찬가지로, <xref:System.Windows.Controls.DataGrid> 확인란 열 예상 되는 색을 사용 하 여.NET Framework 4.7.1부터 키보드 포커스 피드백에 대 한 합니다.

    이전: 

    ![내게 필요한 옵션 기능 향상 하기 전에 DataGrid 기본 링크 스타일](media/default-link-style-before.png) 
 
    이후:    
  
    ![내게 필요한 옵션 기능 향상 후 DataGrid 기본 링크 스타일](media/default-link-style-after.png)  

.NET Framework 4.7.1의에서 향상 된 WPF 내게 필요한 옵션 기능에 대 한 자세한 내용은 참조 하십시오. [WPF의 향상 된 접근성](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf)합니다.

## <a name="windows-forms-accessibility-improvements"></a>Windows Forms 내게 필요한 옵션 기능 향상

4.7.1.NET Framework Windows Forms (WinForms)에 다음 분야에서 내게 필요한 옵션 변경 내용을 포함합니다.

**고대비 모드에서 향상 된 표시**

다양 한 WinForms 컨트롤.NET Framework 4.7.1 부터는 운영 체제에서 사용할 수 있는 고 대비 모드에서 향상 된 렌더링을 제공 합니다. Windows 10에 일부 고대비 시스템 색에 대 한 값을 변경 하 고 Windows 10 Win32 프레임 워크를 기반으로 하는 Windows Forms 키를 누릅니다. 최상의 환경을 위해 최신 버전의 Windows에서 실행 한 다음 표시 되도록를 app.manifest 파일에는 테스트 응용 프로그램 및 Windows 10 주석 지원 OS 줄을 추가 하 여 최신 OS 변경에 옵트인 합니다.

```xml
<!– Windows 10 –>
<supportedOS Id=”{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}” />
```
고대비 변경의 몇 가지 예는 다음과 같습니다.

- 확인 표시 <xref:System.Windows.Forms.MenuStrip> 항목을 더 쉽게 확인 됩니다.

- 옵션을 선택 하면 비활성화 <xref:System.Windows.Forms.MenuStrip> 항목을 더 쉽게 확인 됩니다.

- 선택된 된 텍스트로 <xref:System.Windows.Forms.Button> 선택 색상으로 비교를 제어 합니다.

- 비활성된 텍스트 읽기가 쉽습니다. 예:

    이전:

    ![내게 필요한 옵션 기능 향상 하기 전에 비활성된 텍스트](media/wf-disabled-before.png) 

    이후:

    ![내게 필요한 옵션 기능 향상 후 사용할 수 없는 텍스트](media/wf-disabled-after.png) 

- 스레드 예외 대화 상자에서 고대비 개선 되었습니다.

**내레이터 지원 향상된**

.NET framework 4.7.1 Windows Forms 내레이터에 대 한 다음과 같은 내게 필요한 옵션 개선 사항이 포함 되어 있습니다.

- <xref:System.Windows.Forms.MonthCalendar> 다른 UI 자동화 도구에 따라서도 내레이터, 컨트롤에 액세스할 수 있습니다.

- <xref:System.Windows.Forms.CheckedListBox> 컨트롤 목록 항목의 값을 변경 했습니다은 사용자가 알림을 있으므로 항목의 선택 상태가 변경 될 때 내레이터를에 알립니다.
 
- <xref:System.Windows.Forms.DataGridViewCell> 컨트롤 내레이터를 올바른 읽기 전용 상태를 보고 합니다.
 
- 내레이터 disabled 읽을 수 있습니다 <xref:System.Windows.Forms.ToolStripMenuItem> 텍스트, 이전에 비활성화 된 메뉴 항목 위에 건너 뛸 반면 합니다.

**UIAutomation 내게 필요한 옵션 패턴에 대 한 향상 된 지원**

내게 필요한 옵션 기술 도구 개발자는.NET Framework 4.7.1 부터는 API 내게 필요한 옵션의 일반 패턴 및 WinForms 컨트롤을 몇 개에 대 한 속성 활용할 수 있습니다. 접근성 향상 된 기능은 다음과 같습니다.

- <xref:System.Windows.Forms.ComboBox> 및 <xref:System.Windows.Forms.ToolStripSplitButton> 이제 지원는 [확장/축소 패턴](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md)합니다.
 
- <xref:System.Windows.Forms.DataGridViewCheckBoxCell> 이제 지원는 [toggle 패턴](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md)합니다.
 
- <xref:System.Windows.Forms.ToolStripItem> 지원는 <xref:System.Windows.Automation.AutomationElement.Name> 속성 및 [확장/축소 패턴](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md)합니다.

- <xref:System.Windows.Forms.NumericUpDown> 및 <xref:System.Windows.Forms.DomainUpDown> 지원을 제어는 <xref:System.Windows.Automation.automationElement.Name> 속성입니다.

**향상 된 속성 브라우저 경험**

.NET Framework 4.7.1 부터는 Windows Forms에 포함 됩니다.

- 다양 한 드롭다운 선택 창을 통해 키보드 탐색 기능을 향상 합니다.
- 불필요 한 탭 정지의 감소 합니다.
- 컨트롤 종류의 향상 된 보고 기능입니다.
- 향상 된 내레이터 동작입니다.
 
## <a name="see-also"></a>참고 항목
[.NET Framework의 새로운 기능](whats-new.md)   
 