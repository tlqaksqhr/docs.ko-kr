---
title: "응용 프로그램 설정 아키텍처 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "응용 프로그램 설정[Windows Forms], 아키텍처"
ms.assetid: c8eb2ad0-fac6-4ea2-9140-675a4a44d562
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 25
---
# 응용 프로그램 설정 아키텍처
이 항목에서는 응용 프로그램 설정 아키텍처가 작동하는 방식과 그룹 설정 및 설정 키와 같은 고급 아키텍처 기능에 대해 설명합니다.  
  
 응용 프로그램 설정 아키텍처는 응용 프로그램 또는 사용자 범위를 사용하여 강력한 형식의 설정을 정의하고 응용 프로그램 세션 간에 설정을 유지할 수 있도록 지원합니다.  또한 이 아키텍처는 로컬 파일 시스템에 설정을 저장하거나 해당 시스템의 설정을 로드하기 위한 기본 지속성 엔진을 제공하며,  사용자 지정 지속성 엔진을 제공하는 인터페이스도 정의합니다.  
  
 응용 프로그램에서 사용자 지정 구성 요소를 호스팅할 때 컨트롤의 자체 설정을 유지할 수 있도록 인터페이스가 제공됩니다.  설정 키를 사용하면 구성 요소에서 구성 요소의 여러 인스턴스에 대한 설정을 별도로 유지할 수 있습니다.  
  
## 설정 정의  
 응용 프로그램 설정 아키텍처는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]와 Windows Forms 모두에 사용되며 두 환경에서 공유되는 여러 기본 클래스를 포함합니다.  그 중에서 가장 중요한 클래스는 컬렉션을 통해 설정에 액세스할 수 있게 하고 설정을 로드 및 저장하는 하위 수준 메서드를 제공하는 <xref:System.Configuration.SettingsBase>입니다.  각 환경에서는 <xref:System.Configuration.SettingsBase>에서 파생되는 고유 클래스를 구현하여 해당 환경에 대한 추가 설정 기능을 제공합니다.  Windows Forms 기반 응용 프로그램에서는 모든 응용 프로그램 설정을 <xref:System.Configuration.ApplicationSettingsBase> 클래스에서 파생되는 클래스에서 정의해야 하며, 이 클래스는 기본 클래스에 다음과 같은 기능을 추가합니다.  
  
-   상위 수준 로드 및 저장 작업  
  
-   사용자 범위 설정 지원  
  
-   사용자 설정을 미리 정의된 기본값으로 되돌림  
  
-   이전 응용 프로그램 버전에서 설정 업그레이드  
  
-   설정을 변경하거나 저장하기 전에 설정에 대한 유효성 검사  
  
 설정은 <xref:System.Configuration> 네임스페이스에 정의된 여러 특성을 사용하여 설명할 수 있으며 [응용 프로그램 설정 특성](../../../../docs/framework/winforms/advanced/application-settings-attributes.md)에 설명되어 있습니다.  설정을 정의하면 <xref:System.Configuration.ApplicationScopedSettingAttribute> 또는 <xref:System.Configuration.UserScopedSettingAttribute>에 적용해야 합니다. 이러한 특성은 설정이 전체 응용 프로그램에 적용되는지 아니면 현재 사용자에게만 적용되는지 나타냅니다.  
  
 다음 코드 예제에서는 단일 설정 `BackgroundColor`를 사용하여 사용자 지정 설정 클래스를 정의합니다.  
  
 [!code-csharp[ApplicationSettings.Create#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/MyAppSettings.cs#1)]
 [!code-vb[ApplicationSettings.Create#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/MyAppSettings.vb#1)]  
  
## 설정 지속성  
 <xref:System.Configuration.ApplicationSettingsBase> 클래스는 설정을 직접 유지하거나 로드하지 않습니다. <xref:System.Configuration.SettingsProvider>에서 파생되는 클래스인 설정 공급자가 이러한 유지와 로드를 담당합니다.  <xref:System.Configuration.ApplicationSettingsBase>의 파생 클래스가 <xref:System.Configuration.SettingsProviderAttribute>를 통해 설정 공급자를 지정하지 않으면 기본 공급자인 <xref:System.Configuration.LocalFileSettingsProvider>가 사용됩니다.  
  
 처음에 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]에서 소개된 구성 시스템에서는 로컬 컴퓨터의 machine.config 파일 또는 응용 프로그램과 함께 배포되는 `app.`exe.config 파일을 통해 정적 응용 프로그램 구성 데이터를 제공할 수 있습니다.  <xref:System.Configuration.LocalFileSettingsProvider> 클래스는 이러한 기본적인 지원 기능을 다음과 같이 확장합니다.  
  
-   응용 프로그램 범위 설정을 machine.config 또는 `app.`exe.config 파일에 저장할 수 있습니다.  `app`.exe.config는 대부분의 응용 프로그램에서 보안상 읽기 전용으로 제한되는 반면 Machine.config는 항상 읽기 전용입니다.  
  
-   사용자 범위 설정을 `app`.exe.config 파일에 저장할 수 있으며 이 경우 정적 기본값으로 처리됩니다.  
  
-   기본값이 아닌 사용자 범위 설정은 새 파일인 *user*.config에 저장됩니다. 여기서 *user*는 응용 프로그램을 현재 실행 중인 사람의 사용자 이름입니다.  <xref:System.Configuration.DefaultSettingValueAttribute>를 사용하여 사용자 범위 설정의 기본값을 지정할 수 있습니다.  응용 프로그램을 실행하는 동안 사용자 범위 설정이 변경되는 경우가 많기 때문에 `user`.config는 항상 읽기\/쓰기가 가능합니다.  
  
 세 가지 구성 파일 모두 설정이 XML 형식으로 저장됩니다.  응용 프로그램 범위 설정에 대한 최상위 XML 요소는 `<appSettings>`이며, `<userSettings>`는 사용자 범위 설정에 사용됩니다.  응용 프로그램 범위 설정과 사용자 범위 설정의 기본값이 모두 들어 있는 `app`.exe.config 파일은 다음과 같습니다.  
  
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
  
 구성 파일의 응용 프로그램 설정 섹션에 있는 요소의 정의를 보려면 [응용 프로그램 설정 스키마](../../../../docs/framework/configure-apps/file-schema/application-settings-schema.md)를 참조하십시오.  
  
### 설정 바인딩  
 응용 프로그램 설정은 Windows Forms 데이터 바인딩 아키텍처를 사용하여 설정 개체와 구성 요소 간의 설정 업데이트에 대해 양방향 통신을 제공합니다.  Visual Studio에서 응용 프로그램 설정을 만들어 구성 요소 속성에 할당하면 이 바인딩이 자동으로 생성됩니다.  
  
 응용 프로그램 설정은 <xref:System.Windows.Forms.IBindableComponent> 인터페이스를 지원하는 구성 요소에만 바인딩할 수 있습니다.  또한 구성 요소는 바인딩된 특정 속성에 대해 변경 이벤트를 구현하거나 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스를 통해 속성이 변경되었음을 응용 프로그램 설정에 알려야 합니다.  <xref:System.Windows.Forms.IBindableComponent>를 구현하지 않는 구성 요소에 Visual Studio를 통해 바인딩하려고 하면 바인딩된 속성이 처음에 설정되지만 업데이트되지는 않습니다.  구성 요소가 <xref:System.Windows.Forms.IBindableComponent>를 구현하지만 속성 변경 알림을 지원하지 않는 경우에는 속성이 변경되어도 설정 파일의 바인딩이 업데이트되지 않습니다.  
  
 <xref:System.Windows.Forms.ToolStripItem>과 같은 일부 Windows Forms 구성 요소에서는 설정 바인딩을 지원하지 않습니다.  
  
### 설정 serialization  
 <xref:System.Configuration.LocalFileSettingsProvider>가 설정을 디스크에 저장해야 하는 경우 다음 작업을 수행합니다.  
  
1.  리플렉션을 통해 <xref:System.Configuration.ApplicationSettingsBase> 파생 클래스에 정의된 모든 속성을 검사하여 <xref:System.Configuration.ApplicationScopedSettingAttribute> 또는 <xref:System.Configuration.UserScopedSettingAttribute>와 함께 적용되는 속성을 찾습니다.  
  
2.  속성을 디스크에 serialize합니다.  형식의 관련된 <xref:System.ComponentModel.TypeConverter>에서 <xref:System.ComponentModel.TypeConverter.ConvertToString%2A> 또는 <xref:System.ComponentModel.TypeConverter.ConvertFromString%2A>를 먼저 호출합니다.  제대로 호출되지 않으면 XML serialization을 대신 사용합니다.  
  
3.  설정의 특성에 따라 어떤 파일에 어떤 설정을 사용할지 결정합니다.  
  
 고유 설정 클래스를 구현하면 <xref:System.Configuration.SettingsSerializeAsAttribute>를 통해 <xref:System.Configuration.SettingsSerializeAs> 열거형을 사용하여 이진 또는 사용자 지정 serialization에 대한 설정을 표시할 수 있습니다.  코드로 고유 설정 클래스를 만드는 방법에 대한 자세한 내용은 [방법: 응용 프로그램 설정 만들기](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md)를 참조하십시오.  
  
### 설정 파일 위치  
 `app`.exe.config 및 *user*.config 파일의 위치는 응용 프로그램을 설치하는 방법에 따라 다릅니다.  Windows Forms 기반 응용 프로그램을 로컬 컴퓨터에 복사한 경우 `app`.exe.config는 응용 프로그램의 주 실행 파일의 기본 디렉터리와 동일한 디렉터리에 있고, *user*.config는 <xref:System.Windows.Forms.Application.LocalUserAppDataPath%2A?displayProperty=fullName> 속성에서 지정한 위치에 있습니다.  [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)]를 사용하여 응용 프로그램을 설치한 경우에는 이 두 파일 모두 %InstallRoot%\\Documents and Settings\\*username*\\Local Settings 아래의 [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] 데이터 디렉터리에 있습니다.  
  
 사용자가 로밍 프로필을 활성화하여 한 도메인 내에서 다른 컴퓨터를 사용할 때 다른 Windows 및 응용 프로그램 설정을 정의할 수 있게 한 경우에는 이 파일의 저장 위치가 약간 다릅니다.  [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] 응용 프로그램과 [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] 응용 프로그램이 아닌 경우 모두 `app`.exe.config 및 *user*.config 파일이 %InstallRoot%\\Documents and Settings\\*username*\\Application Data에 저장됩니다.  
  
 새로운 배포 기술을 사용하여 응용 프로그램 설정 기능이 작동하는 방식에 대한 자세한 내용은 [ClickOnce 및 응용 프로그램 설정](../Topic/ClickOnce%20and%20Application%20Settings.md)을 참조하십시오.  [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] 데이터 디렉터리에 대한 자세한 내용은 [ClickOnce 응용 프로그램의 로컬 및 원격 데이터 액세스](../Topic/Accessing%20Local%20and%20Remote%20Data%20in%20ClickOnce%20Applications.md)를 참조하십시오.  
  
## 응용 프로그램 설정 및 보안  
 응용 프로그램 설정은 인터넷 또는 인트라넷에서 호스팅되는 Windows Forms 응용 프로그램의 기본 환경인 제한된 부분 신뢰 환경에서 작동하도록 디자인되었습니다.  기본 설정 공급자와 함께 응용 프로그램 설정을 사용하는 데는 부분 신뢰 이상의 특별한 권한이 필요하지 않습니다.  
  
 [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] 응용 프로그램에서 응용 프로그램 설정을 사용하면 `user`.config 파일이 [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] 데이터 디렉터리에 저장됩니다.  응용 프로그램의 `user`.config 파일 크기는 [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)]에서 설정된 데이터 디렉터리 할당량을 초과할 수 없습니다.  자세한 내용은 [ClickOnce 및 응용 프로그램 설정](../Topic/ClickOnce%20and%20Application%20Settings.md)을 참조하십시오.  
  
## 사용자 지정 설정 공급자  
 응용 프로그램 설정 아키텍처에는 <xref:System.Configuration.ApplicationSettingsBase>에서 파생되는 응용 프로그램 설정 래퍼 클래스와 <xref:System.Configuration.SettingsProvider>에서 파생되는 연결된 설정 공급자가 느슨하게 결합되어 있습니다.  이러한 연결은 래퍼 클래스나 해당 개별 속성에 적용되는 <xref:System.Configuration.SettingsProviderAttribute>를 통해서만 정의됩니다.  설정 공급자가 명시적으로 지정되어 있지 않으면 기본 공급자인 <xref:System.Configuration.LocalFileSettingsProvider>가 사용됩니다.  따라서 이 아키텍처는 사용자 지정 설정 공급자를 만들고 사용할 수 있도록 지원합니다.  
  
 예를 들어, Microsoft SQL Server 데이터베이스에 모든 설정 데이터를 저장하는 공급자인 `SqlSettingsProvider`를 개발하여 사용하려는 경우,  <xref:System.Configuration.SettingsProvider> 파생 클래스는 이 정보를 `Initialize` 메서드에서 <xref:System.Collections.Specialized.NameValueCollection?displayProperty=fullName> 형식의 매개 변수로 받습니다.  그러면 <xref:System.Configuration.SettingsProvider.GetPropertyValues%2A> 메서드를 구현하여 데이터 저장소에서 설정을 검색하고 <xref:System.Configuration.SettingsProvider.SetPropertyValues%2A>를 구현하여 설정을 저장합니다.  공급자는 <xref:System.Configuration.SettingsProvider.GetPropertyValues%2A>에 제공된 <xref:System.Configuration.SettingsPropertyCollection>을 사용하여 속성 이름, 형식 및 범위와 함께 해당 속성에 정의된 다른 모든 설정 특성을 확인할 수 있습니다.  
  
 공급자는 구현이 분명하지 않은 속성 하나와 메서드 하나를 구현해야 합니다.  <xref:System.Configuration.SettingsProvider.ApplicationName%2A> 속성은 <xref:System.Configuration.SettingsProvider>의 추상 속성이며 다음 내용을 반환하도록 프로그래밍해야 합니다.  
  
 [!code-csharp[ApplicationSettings.Architecture#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Architecture/CS/DummyClass.cs#2)]
 [!code-vb[ApplicationSettings.Architecture#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Architecture/VB/DummyProviderClass.vb#2)]  
  
 또한 파생 클래스는 인수를 사용하지 않고 값을 반환하지 않는 `Initialize` 메서드를 구현해야 합니다.  <xref:System.Configuration.SettingsProvider>에서는 이 메서드가 정의되지 않습니다.  
  
 마지막으로 설정을 새로 고치고 설정을 기본값으로 되돌리고 응용 프로그램 버전 간에 설정을 업그레이드할 수 있도록 공급자에 대해 <xref:System.Configuration.IApplicationSettingsProvider>를 구현합니다.  
  
 공급자를 구현하고 컴파일했으면 설정 클래스에서 기본값 대신 이 공급자를 사용하도록 지시해야 합니다.  <xref:System.Configuration.SettingsProviderAttribute>를 통해 이 작업을 수행할 수 있습니다.  공급자를 전체 설정 클래스에 적용했으면 해당 클래스가 정의하는 각 설정에 공급자가 사용되고, 개별 설정에 적용했으면 응용 프로그램 설정 아키텍처에서 해당 설정에만 이 공급자가 사용되고 나머지 설정에는 <xref:System.Configuration.LocalFileSettingsProvider>가 사용됩니다.  다음 코드 예제에서는 설정 클래스에서 사용자 지정 공급자를 사용하도록 지시하는 방법을 보여 줍니다.  
  
 [!code-csharp[ApplicationSettings.Architecture#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Architecture/CS/DummyClass.cs#1)]
 [!code-vb[ApplicationSettings.Architecture#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Architecture/VB/DummyProviderClass.vb#1)]  
  
 여러 스레드에서 동시에 한 공급자를 호출할 수 있지만 공급자는 항상 동일한 저장소 위치에 쓰므로, 응용 프로그램 아키텍처는 공급자 클래스에 대해 하나의 인스턴스만 만듭니다.  
  
> [!IMPORTANT]
>  공급자가 스레드로부터 안전한지와 한 번에 한 스레드만 구성 파일에 쓸 수 있는지 확인해야 합니다.  
  
 공급자는 최소 지원 <xref:System.Configuration.ApplicationScopedSettingAttribute> 및 <xref:System.Configuration.UserScopedSettingAttribute>에서 <xref:System.Configuration.DefaultSettingValueAttribute>도 지원해야 하는 경우에도 <xref:System.Configuration?displayProperty=fullName> 네임스페이스에 정의된 설정 특성을 모두 지원하지는 않아도 됩니다.  지원하지 않는 특성에 대해서는 알림을 보내지 않고 공급자가 오류 처리되어야 하며 예외를 throw해서는 안 됩니다.  그러나 설정 클래스에서 <xref:System.Configuration.ApplicationScopedSettingAttribute> 및 <xref:System.Configuration.UserScopedSettingAttribute>를 동일한 설정에 적용하는 것과 같이 잘못된 특성 조합을 사용하면 공급자는 예외를 throw하고 작업을 중단해야 합니다.  
  
## 참고 항목  
 <xref:System.Configuration.ApplicationSettingsBase>   
 <xref:System.Configuration.SettingsProvider>   
 <xref:System.Configuration.LocalFileSettingsProvider>   
 [응용 프로그램 설정 개요](../../../../docs/framework/winforms/advanced/application-settings-overview.md)   
 [사용자 지정 컨트롤에 대한 응용 프로그램 설정](../../../../docs/framework/winforms/advanced/application-settings-for-custom-controls.md)   
 [ClickOnce 및 응용 프로그램 설정](../Topic/ClickOnce%20and%20Application%20Settings.md)   
 [응용 프로그램 설정 스키마](../../../../docs/framework/configure-apps/file-schema/application-settings-schema.md)