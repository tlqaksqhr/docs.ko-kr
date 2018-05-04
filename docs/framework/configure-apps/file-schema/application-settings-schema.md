---
title: 응용 프로그램 설정 스키마
ms.date: 03/30/2017
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 7af6342e9c05fc4e6c1bf4daac59db14ccdf22c7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="application-settings-schema"></a>응용 프로그램 설정 스키마

응용 프로그램 설정을 저장 하 고 응용 프로그램 범위 및 사용자 범위 설정을 검색 하는 Windows Forms 또는 ASP.NET 응용 프로그램을 사용 합니다. 이 컨텍스트에서 *설정* 는 응용 프로그램 관련 또는 현재 사용자에 게 특정 수 있는 정보의 일부-사용자에 게 데이터베이스 연결 문자열에서 모든 항목의 기본 창 크기 기본 설정 합니다.

Windows Forms 응용 프로그램에서 응용 프로그램 설정을 사용 하 여 기본적으로는 <xref:System.Configuration.LocalFileSettingsProvider> 클래스를 사용 하 여.NET 구성 시스템이 설정을 XML 구성 파일에 저장 합니다. 응용 프로그램 설정에서 사용 하는 파일에 대 한 자세한 내용은 참조 [응용 프로그램 설정 아키텍처](~/docs/framework/winforms/advanced/application-settings-architecture.md)합니다.

응용 프로그램 설정을 사용 하 여 구성 파일의 일부로 다음과 같은 요소를 정의 합니다.

| 요소                    | 설명                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| **\<applicationSettings >** | 모든 포함  **\<설정 >** 태그 응용 프로그램에 특정 합니다.                         |
| **\<g s >**        | 모든 포함  **\<설정 >** 현재 사용자에 게 특정 태그입니다.                        |
| **\<설정 >**             | 설정을 정의합니다. 자식 요소  **\<applicationSettings >** 또는  **\<g s >** 합니다. |
| **\<value>**               | 설정 값을 정의합니다. 자식  **\<설정 >** 합니다.                                   |

## <a name="applicationsettings-element"></a>\<applicationSettings > 요소

이 요소는 모든 포함  **\<설정 >** 클라이언트 컴퓨터에서 응용 프로그램의 인스턴스에 관련 된 태그입니다. 특성 없음을 정의합니다.

## <a name="usersettings-element"></a>\<g s > 요소

이 요소는 모든 포함  **\<설정 >** 응용 프로그램 현재 사용 하는 사용자에만 적용 되는 태그입니다. 특성 없음을 정의합니다.

## <a name="setting-element"></a>\<설정 > 요소

이 요소는 설정을 정의 합니다. 다음과 같은 특성이 있습니다.

| 특성        | 설명 |
| ---------------- | ----------- |
| **name**         | 필수. 설정의 고유 ID입니다. Visual Studio를 통해 만든 설정은 이름으로 저장 됩니다 `ProjectName.Properties.Settings`합니다. |
| **serializedAs** | 필수. 값을 텍스트로 직렬화 하는 작업에 사용할 형식입니다. 올바른 값은 다음과 같습니다.<br><br>- `string`. 값을 사용 하 여 문자열 직렬화는 <xref:System.ComponentModel.TypeConverter>합니다.<br>- `xml`. 값은 XML serialization을 사용 하 여 serialize 됩니다.<br>- `binary`. 값은 이진 serialization을 사용 하 여 텍스트로 인코딩된 이진 형식으로 serialize 됩니다.<br />- `custom`. 설정 공급자가이 설정의 내재 된 지식이 직렬화 및 역직렬화 serialize 합니다. |

## <a name="value-element"></a>\<값 > 요소

이 요소는 설정의 값을 포함합니다.

## <a name="example"></a>예제

다음 예제에서는 두 개의 응용 프로그램 범위 설정 및 두 개의 사용자 범위 설정을 정의 하는 응용 프로그램 설정 파일을 보여 줍니다.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <sectionGroup name="applicationSettings" type="System.Configuration.ApplicationSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
    </sectionGroup>
    <sectionGroup name="userSettings" type="System.Configuration.UserSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" allowExeDefinition="MachineToLocalUser" />
    </sectionGroup>
  </configSections>
  <applicationSettings>
    <WindowsApplication1.Properties.Settings>
      <setting name="Cursor" serializeAs="String">
        <value>Default</value>
      </setting>
      <setting name="DoubleBuffering" serializeAs="String">
        <value>False</value>
      </setting>
    </WindowsApplication1.Properties.Settings>
  </applicationSettings>
  <userSettings>
    <WindowsApplication1.Properties.Settings>
      <setting name="FormTitle" serializeAs="String">
        <value>Form1</value>
      </setting>
      <setting name="FormSize" serializeAs="String">
        <value>595, 536</value>
      </setting>
    </WindowsApplication1.Properties.Settings>
  </userSettings>
</configuration>
```

## <a name="see-also"></a>참고자료

[응용 프로그램 설정 개요](~/docs/framework/winforms/advanced/application-settings-overview.md)   
[응용 프로그램 설정 아키텍처](~/docs/framework/winforms/advanced/application-settings-architecture.md)
