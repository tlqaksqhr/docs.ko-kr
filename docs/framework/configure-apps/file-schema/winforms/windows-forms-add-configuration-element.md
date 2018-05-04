---
title: Windows Forms 구성 요소를 추가합니다.
ms.date: 04/07/2017
helpviewer_keywords:
- Windows Forms Add configuration element
- configuring Windows Forms applications
ms.assetid: 3e3e04de-99d1-4658-b716-44cb669d9589
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 529dbccd5ddb4dd1f1456fb9a6043f3c5f7b378d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="windows-forms-add-configuration-element"></a>Windows Forms 구성 요소를 추가합니다.

`<add>` 요소는 Windows Form 응용 프로그램에서.NET Framework 4.7 이상 Windows Forms 앱에 추가 된 기능을 지원 하는지 여부를 지정 하는 미리 정의 된 키를 추가 합니다.

## <a name="syntax"></a>구문

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="key-name" value="key-value" />
</System.Windows.Forms.ApplicationConfigurationSection>
```

## <a name="attributes-and-elements"></a>특성 및 요소

다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.

### <a name="attributes"></a>특성

| 특성 | 설명 |
| --------- | ----------- |
| `key`     | 필수 특성입니다. 특정 Windows Forms 사용자 지정 가능한 기능에 해당 하는 미리 정의 된 키 이름입니다. |
| `value`   | 필수 특성입니다. 에 할당할 값 `key`합니다. |

### <a name="key-attribute-names-and-associated-values"></a>`key` 특성 이름 및 관련된 값

| `key` 이름 | 값 | 설명 |
| ---------- | ------ | ----------- |
| "AnchorLayout.DisableSinglePassControlScaling" | "true"&#124;"false" | 단일 패스에서 고정 된 컨트롤의 배율 조정 여부를 나타냅니다. 크기 조정; 단일을 사용 하지 않도록 설정 하려면 "true" 전달 그렇지 않으면 false입니다. "단일 배율 pass" 섹션을 참조는 [주의](#Remarks) 자세한 정보에 대 한 합니다. |
| "DpiAwareness" | "PerMonitorV2"&#124;"false" | 응용 프로그램을 DPI를 인식 하는지 여부를 나타냅니다. 키를 "PerMonitorV2" Dpi 인식;를 지원 하도록 설정 그렇지 않으면 "false"로 설정 합니다. DPI 인식은 옵트인 기능입니다. Windows Forms의 높은 DPI 지원을 이용 하려면 해당 값을 "PerMonitorV2"로 설정 해야 합니다. 참조는 [주의](#remarks) 한 자세 합니다. |
| "CheckedListBox.DisableHighDpiImprovements" | "true"&#124;"false" | 나타냅니다 여부는 <xref:System.Windows.Forms.CheckedListBox> 컨트롤에서는.NET Framework 4.7에 도입 된 크기 조정 및 레이아웃 개선 사항 활용 합니다. caling 및 레이아웃 개선;의 선택을 취소 하는 "true" 그렇지 않으면 "false"입니다. |
| "DataGridView.DisableHighDpiImprovements" | "true"&#124;"false" | 나타냅니다 여부는 <xref:System.Windows.Forms.DataGridView> .NET Framework 4.7에 도입 된 크기 조정 및 레이아웃 향상 된 기능을 제어 합니다. DPI 인식;의 선택을 취소 하는 "true" "false" 그렇지 않은 경우. |
| "DisableDpiChangedMessageHandling" | "true"&#124;"false" | DPI 변경; 배율을 관련 된 메시지를 받는 옵트아웃 하는 "true" "false" 그렇지 않은 경우. 참조는 [주의](#remarks) 한 자세 합니다. |
| "EnableWindowsFormsHighDpiAutoResizing" | "true"&#124;"false" | DPI 배율 변경으로 인해 Windows Forms 응용 프로그램은 자동으로 조정 되는지 여부를 나타냅니다. 자동 크기 조정; 사용 하도록 설정 하려면 "true" 그렇지 않으면 false입니다. |
| "Form.DisableSinglePassControlScaling" | "true"&#124;"false" | 나타냅니다 여부는 <xref:System.Windows.Forms.Form> 단일 패스에서 크기가 조정 됩니다. 크기 조정; 사용 하지 않도록 설정 하려면 "true" 한 번 통과 그렇지 않으면 false입니다. "단일 배율 pass" 섹션을 참조는 [주의](#Remarks) 자세한 정보에 대 한 합니다. |
| "MonthCalendar.DisableSinglePassControlScaling" | "true"&#124;"false" | 나타냅니다 여부는 <xref:System.Windows.Forms.MonthCalendar> 단일 패스에서 컨트롤의 크기가 조정 됩니다. 크기 조정; 사용 하지 않도록 설정 하려면 "true" 한 번 통과 그렇지 않으면 false입니다. "단일 배율 pass" 섹션을 참조는 [주의](#Remarks) 자세한 정보에 대 한 합니다. |
| "Toolstrip.DisableHighDpiImprovements" | "true"&#124;"false" | 나타냅니다 여부는 <xref:System.Windows.Forms.ToolStrip> 컨트롤에서는.NET Framework 4.7에 도입 된 크기 조정 및 레이아웃 개선 사항 활용 합니다. DPI 인식;의 선택을 취소 하는 "true" "false" 그렇지 않은 경우. |

### <a name="child-elements"></a>자식 요소

없음

### <a name="parent-elements"></a>부모 요소

| 요소 | 설명 |
| ------- | ----------- |
| [`<System.Windows.Forms.ApplicationConfigurationSection>`](../../../../../docs/framework/configure-apps/file-schema/winforms/index.md) | 새 Windows Forms 응용 프로그램 기능에 대 한 지원을 구성합니다. |

## <a name="a-nameremarks--remarks"></a><a name="remarks" /> 설명

.NET Framework 4.7부터는 `<System.Windows.Forms.ApplicationConfigurationSection>` 요소를 사용하여 Windows Forms 응용 프로그램을 구성해 최신 .NET Framework 릴리스에 추가된 기능을 활용할 수 있습니다. 

`<System.Windows.Forms.ApplicationConfigurationSection>` 요소를 사용 하면 하나 이상의 하위 항목 추가 `<add>` 특정 구성 설정을 정의 하는 요소입니다.  

Windows Forms 높은 DPI 지원의 개요를 참조 하십시오. [Windows Forms의 높은 DPI 지원](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)합니다.

### <a name="dpiawareness"></a>DpiAwareness

.NET Framework에 도입 된 높은 DPI 개선 사항 활용 하기 위해.NET Framework 4.7부터 Windows 10 작성자 Edition 및.NET Framework의 버전을 대상으로 시작 하는 Windows 버전에서 실행 되는 Windows Forms 앱을 구성할 수 있습니다. 4.7 합니다. 여기에는 다음이 포함됩니다.

- 사용자가 변경한 DPI 또는 배율 인수는 Windows Forms 응용 프로그램 시작 된 후 동적 DPI 시나리오를 지원 합니다.

- 와 같은 확장 및 레이아웃의 다양 한 Windows Forms의 향상 된 컨트롤의 <xref:System.Windows.Forms.MonthCalendar> 제어 및 <xref:System.Windows.Forms.CheckedListBox> 제어 합니다. 

높은 DPI 인식은 옵트인 기능입니다. 기본적으로 값 `DpiAwareness` 은 `false`합니다. 이 키의 값을 설정 하 여 DPI 인식에 대 한 Windows Forms 지원으로 선택할 수 `PerMonitorV2` 응용 프로그램 구성 파일에 있습니다. DPI 인식을 사용 하는 경우 모든 개별 DPI 기능도 사용할 수 있습니다. 여기에는 다음이 포함됩니다.

- DPI 변경에 의해 제어 되는 메시지는 `DisableDpiChangedMessageHandling` 키입니다.

- 동적 DPI 지원에 의해 제어 되는 `EnableWindowsFormsHighDpiAutoResizing` 키입니다.

- 한 번 통과 컨트롤 크기 조정 의해 제어 되는 `Form.DisableSinglePassControlScaling` 개인에 대 한 <xref:System.Windows.Forms.Form> 으로 제어는 `AnchorLayout.DisableSinglePassControlScaling` 및 고정 된 컨트롤에 대 한 키는 `MonthCalendar.DisableSinglePassControlScaling` 에 대 한 키는 <xref:System.Windows.Forms.MonthCalendar> 컨트롤 

- 높은 DPI 배율 및 레이아웃 개선으로 제어 되는 `CheckListBox.DisableHighDpiImprovements` 에 대 한 키는 <xref:System.Windows.Forms.CheckedListBox> 으로 제어는 `DataGridView.DisableHighDpiImprovements` 에 대 한 키는 <xref:System.Windows.Forms.DataGridView> 컨트롤 및는 `Toolstrip.DisableHighDpiImprovements` 에 대 한 키는 <xref:System.Windows.Forms.ToolStrip> 컨트롤입니다.  

제공 하는 단일 기본 옵트인 설정을 설정 하 여 `DpiAwareness` 를 `PerMonitorV2` 일반적으로 새 Windows Forms 응용 프로그램에 적합 합니다. 그러나 선택할 수 있습니다 다음 개별 높은 DPI 개선 사항에서 응용 프로그램 구성 파일에 해당 하는 키를 추가 하 여 합니다. 예를 들어 동적 DPI 지원을 제외한 모든 새 DPI featuers를 이용 하려면 다음에 추가한 응용 프로그램 구성 파일:

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
   <add key="DpiAwareness" value="PerMonitorV2" />
   <--! Disable dynamic DPI support -->
   <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" />
</System.Windows.Forms.ApplicationConfigurationSection>
```
일반적으로 옵트인 있습니다 특정 기능을 옵트아웃 있으므로 프로그래밍 방식으로 처리 하도록 선택 했습니다.

Windows Forms 응용 프로그램의 높은 DPI 지원을 사용해에 자세한 내용은 참조 [Windows Forms의 높은 DPI 지원](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)합니다.
 
### <a name="disabledpichangedmessagehandling"></a>DisableDpiChangedMessageHandling

.NET Framework 4.7 이상에서는 Windows Forms 컨트롤 다양을 한 DPI 조정으로 변경과 관련 된 이벤트를 발생 시킵니다. 여기에 <xref:System.Windows.Forms.Control.DpiChangedAfterParent>, <xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, 및 <xref:System.Windows.Forms.Form.DpiChanged> 이벤트입니다. 값은 `DisableDpiChangedMessageHandling` 키 이러한 이벤트는 Windows Forms 응용 프로그램에서 발생 하는지 여부를 결정 합니다. 

### <a name="single-pass-scaling"></a>한 번 통과 크기 조정

단일 또는 다중 pass 배율 영향을 줍니다 사용자 인터페이스의 인지 되는 응답성, 사용자 인터페이스 요소의 모양으로 크기가 조정 됩니다. .NET Framework 4.7 이상에서는 Windows Forms 단일 패스 크기 조정을 사용 합니다. .NET Framework의 이전 버전에서는 크기 조정 필요 이상 인해 일부 컨트롤 크기를 조정할 수 있는 여러 과정을 통해 수행할 되었습니다. 한 번 통과 배율는 사용할 수 이전 동작에 종속 되는 앱입니다.  

## <a name="see-also"></a>참고자료
 
[Windows Forms 구성 섹션입니다.](../../../../../docs/framework/configure-apps/file-schema/winforms/index.md)   
[Windows Forms의 높은 DPI 지원](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)
