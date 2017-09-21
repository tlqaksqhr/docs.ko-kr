---
title: "Windows Forms 구성 섹션"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6eb142d5-fc98-40e2-9d90-84733f2a27ba
caps.latest.revision: 6
author: rpetrusha
ms.author: ronpet
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b83f00f82de727812c5737915a6dc35ec98e4734
ms.contentlocale: ko-kr
ms.lasthandoff: 09/05/2017

---
# <a name="windows-forms-configuration-section"></a>Windows Forms 구성 섹션
Windows Forms 구성 설정을 통해 Windows Forms 앱에서 다중 모니터 지원, 높은 DPI 지원 및 기타 사용자 정의된 구성 설정 등의 사용자 지정된 응용 프로그램 설정에 대한 정보를 저장하고 검색할 수 있습니다.

Windows Forms 응용 프로그램 구성 설정은 응용 프로그램 구성 파일의 `System.Windows.Forms.ApplicationConfigurationSection` 요소에 저장됩니다.

## <a name="syntax"></a>구문

```xml
<configuration>
  <System.Windows.Forms.ApplicationConfigurationSection>
  ...
  </System.Windows.Forms.ApplicationConfigurationSection>
</configuration>
```

## <a name="attributes-and-elements"></a>특성 및 요소

다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.

### <a name="attributes"></a>특성

없음

### <a name="child-elements"></a>자식 요소

요소  |설명 |
---------|---------|
[`<add>`](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md) | 지정된 된 값과 함께 구성 설정 키를 추가합니다. |

### <a name="parent-elements"></a>부모 요소

요소  |설명 |
---------|---------|
[\<구성>](../configuration-element.md) | 공용 언어 런타임 및 Windows Forms 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다. |

## <a name="remarks"></a>주의

.NET Framework 4.7부터는 `<System.Windows.Forms.ApplicationConfigurationSection>` 요소를 사용하여 Windows Forms 응용 프로그램을 구성해 최신 .NET Framework 릴리스에 추가된 기능을 활용할 수 있습니다. 

`<System.Windows.Forms.ApplicationConfigurationSection>` 요소는 각각 특정 구성 설정을 정의하는 하나 이상의 [`<add>`](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md) 요소를 포함할 수 있습니다.

## <a name="see-also"></a>참고 항목

[구성 파일 스키마](../index.md)   
[Windows Forms의 높은 DPI 지원](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)

