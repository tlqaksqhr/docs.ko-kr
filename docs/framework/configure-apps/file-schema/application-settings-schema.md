---
title: "응용 프로그램 설정 스키마 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "응용 프로그램 설정, 스키마[Windows Forms]"
  - "구성 스키마[.NET Framework], 응용 프로그램 설정"
  - "스키마 응용 프로그램 설정"
  - "Windows Forms, 응용 프로그램 설정 스키마"
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
caps.latest.revision: 3
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 3
---
# 응용 프로그램 설정 스키마
응용 프로그램 설정을 사용하여 Windows Forms 또는 ASP.NET 응용 프로그램에서 응용 프로그램 범위 및 사용자 범위 설정을 저장하고 검색할 수 있습니다.  여기서 "설정"은 데이터베이스 연결 문자열에서부터 사용자가 원하는 기본 창 크기에 이르기까지 응용 프로그램 또는 현재 사용자에게 고유한 모든 정보를 의미합니다.  
  
 기본적으로 Windows Forms 응용 프로그램의 응용 프로그램 설정은 .NET 구성 시스템을 사용하여 설정을 XML 구성 파일에 저장하는 <xref:System.Configuration.LocalFileSettingsProvider>를 사용합니다.  응용 프로그램 설정에서 사용되는 파일에 대한 자세한 내용은 [응용 프로그램 설정 아키텍처](../../../../docs/framework/winforms/advanced/application-settings-architecture.md)를 참조하십시오.  
  
 응용 프로그램 설정은 사용하는 구성 파일의 일부로 다음 요소를 정의합니다.  
  
|요소|설명|  
|--------|--------|  
|`<applicationSettings>` 요소|응용 프로그램의 모든 고유한 `<setting>` 태그가 들어 있습니다.|  
|`<userSettings>` 요소|현재 사용자의 모든 고유한 `<setting>` 태그가 들어 있습니다.|  
|`<setting>` 요소|설정을 정의합니다.  `<applicationSettings>` 또는 `<userSettings>`의 자식 요소입니다.|  
|`<value>` 요소|설정 값을 정의합니다.  `<setting>`의 자식 요소입니다.|  
  
## \<applicationSettings\> 요소  
 이 요소에는 클라이언트 컴퓨터에 있는 응용 프로그램 인스턴스에 고유한 모든 \<setting\> 태그가 들어 있습니다.  이 요소는 특성을 정의하지 않습니다.  
  
## \<userSettings\> 요소  
 이 요소에는 현재 응용 프로그램을 사용하고 있는 사용자에게 고유한 모든 \<setting\>  태그가 들어 있습니다.  이 요소는 특성을 정의하지 않습니다.  
  
## \<setting\> 요소  
 이 요소는 설정을 정의합니다.  이 요소에는 다음과 같은 특성이 있습니다.  
  
|요소|설명|  
|--------|--------|  
|`name`|필수적 요소로서,  설정의 고유 ID입니다.  Visual Studio를 사용하여 만든 설정은 `ProjectName``.Properties.Settings`라는 이름으로 저장됩니다.|  
|`serializedAs`|필수적 요소로서,  값을 텍스트로 serialize하는 데 사용할 형식입니다.  올바른 값은 다음과 같습니다.<br /><br /> -   `string`.  <xref:System.ComponentModel.TypeConverter>를 사용하여 값을 문자열로 serialize합니다.<br />-   `xml`.  XML serialization을 사용하여 값을 serialize합니다.<br />-   `binary`.  이진 serialization을 사용하여 값을 텍스트로 인코딩된 이진 값으로 serialize합니다.<br />-   `custom`.  설정 공급자가 이 설정에 대한 고유 정보를 보유하며 설정을 serialize 및 de\-serialize합니다.<br />-   이진 또는 사용자 지정 serialization을 사용하려면 사용자 지정 설정 클래스를 정의하고 <xref:System.Configuration.SettingsSerializeAsAttribute>를 사용하여 이진 또는 사용자 지정 serialization을 지정해야 합니다.|  
  
## \<value\> 요소  
 이 요소에는 설정 값이 들어 있습니다.  
  
## 예제  
 다음 코드 예제에서는 두 개의 응용 프로그램 범위 설정과 두 개의 사용자 범위 설정을 정의하는 응용 프로그램 설정 파일을 보여 줍니다.  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
    <configSections>  
        <sectionGroup name="applicationSettings" type="System.Configuration.ApplicationSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" >  
            <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
        </sectionGroup>  
        <sectionGroup name="userSettings" type="System.Configuration.UserSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" >  
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
  
## 참고 항목  
 [응용 프로그램 설정 개요](../../../../docs/framework/winforms/advanced/application-settings-overview.md)   
 [응용 프로그램 설정 아키텍처](../../../../docs/framework/winforms/advanced/application-settings-architecture.md)