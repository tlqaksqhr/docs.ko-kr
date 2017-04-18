---
title: "응용 프로그램 설정 특성 | Microsoft Docs"
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
  - "응용 프로그램 설정[Windows Forms], 특성"
  - "특성[Windows Forms], 응용 프로그램 설정"
  - "래퍼 클래스, 응용 프로그램 설정"
ms.assetid: 53caa66c-a9fb-43a5-953c-ad092590098d
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 응용 프로그램 설정 특성
응용 프로그램 설정 아키텍처는 응용 프로그램 설정 래퍼 클래스 또는 해당되는 개별 속성에 적용할 수 있는 여러 특성을 제공합니다.  이러한 특성은 사용자 지정 래퍼의 정해진 요구에 맞게 기능을 조절하기 위해 응용 프로그램 설정 인프라\(특히 설정 공급자인 경우가 많음\)에서 런타임에 검사합니다.  
  
 다음 표에서는 응용 프로그램 설정 래퍼 클래스나 이 클래스의 개별 속성 또는 둘 다에 적용할 수 있는 특성을 보여 줍니다.  정의에 따라 하나의 범위 특성 즉, **UserScopedSettingAttribute** 또는 **ApplicationScopedSettingAttribute**만 각각의 설정 속성에 적용되어야 합니다.  
  
> [!NOTE]
>  <xref:System.Configuration.SettingsProvider>에서 파생된 사용자 지정 설정 공급자는 **ApplicationScopedSettingAttribute**, **UserScopedSettingAttribute** 및 **DefaultSettingValueAttribute** 속성 등 세 가지 속성을 인식할 때만 필요합니다.  
  
|특성|대상|설명|  
|--------|--------|--------|  
|<xref:System.Configuration.SettingsProviderAttribute>|Both|지속성을 위해 사용할 설정 공급자의 약식 이름을 지정합니다.<br /><br /> 이 특성을 지정하지 않으면 기본 공급자인 <xref:System.Configuration.LocalFileSettingsProvider>가 사용됩니다.|  
|<xref:System.Configuration.UserScopedSettingAttribute>|Both|속성을 사용자 범위 응용 프로그램 설정으로 정의합니다.|  
|<xref:System.Configuration.ApplicationScopedSettingAttribute>|Both|속성을 응용 프로그램 범위 응용 프로그램 설정으로 정의합니다.|  
|<xref:System.Configuration.DefaultSettingValueAttribute>|Property|공급자가 deserialize할 수 있는 문자열을 이 속성에 대해 하드 코드된 기본값으로 지정합니다.<br /><br /> <xref:System.Configuration.LocalFileSettingsProvider>에는 이 특성이 필요하지 않으며 이미 유지되고 있는 값이 있으면 이 특성에서 지정하는 값으로 재정의됩니다.|  
|<xref:System.Configuration.SettingsDescriptionAttribute>|Property|주로 런타임 및 디자인 타임 도구에서 사용되는 개별 설정에 대한 설명 텍스트를 지정합니다.|  
|<xref:System.Configuration.SettingsGroupNameAttribute>|클래스|설정 그룹의 명시적 이름을 지정합니다.  이 특성이 없으면 <xref:System.Configuration.ApplicationSettingsBase>는 래퍼 클래스 이름을 사용합니다.|  
|<xref:System.Configuration.SettingsGroupDescriptionAttribute>|클래스|주로 런타임 및 디자인 타임 도구에서 사용되는 설정 그룹에 대한 설명 텍스트를 지정합니다.|  
|<xref:System.Configuration.SettingsManageabilityAttribute>|Both|설정 그룹 또는 속성에 지정해야 하는 하나 이상의 관리 효율성 서비스를 지정하거나 지정하지 않습니다.  사용 가능한 서비스는 <xref:System.Configuration.SettingsManageability> 열거형에서 설명합니다.|  
|<xref:System.Configuration.SpecialSettingAttribute>|Property|설정이 설정 공급자에서 특수하게 처리하도록 제안하는 연결 문자열과 같은 미리 정의된 특수 범주에 속해 있음을 나타냅니다.  이 특성에 대해 미리 정의된 범주는 <xref:System.Configuration.SpecialSetting> 열거형에서 정의합니다.|  
|<xref:System.Configuration.SettingsSerializeAsAttribute>|Both|설정 그룹 또는 속성에 대해 기본 설정 serialization 메커니즘을 지정합니다.  사용 가능한 serialization 메커니즘은 <xref:System.Configuration.SettingsSerializeAs> 열거형에서 정의합니다.|  
|<xref:System.Configuration.NoSettingsVersionUpgradeAttribute>|Property|설정 공급자가 표시된 속성에 대해 모든 응용 프로그램 업그레이드 기능을 사용하지 않도록 지정합니다.|  
  
 *클래스*는 특성을 응용 프로그램 설정 래퍼 클래스에만 적용할 수 있음을 나타냅니다.  *속성*은 특성을 설정 속성에만 적용할 수 있음을 나타내며  *모두*는 특성을 어느 수준에나 적용할 수 있음을 나타냅니다.  
  
## 참고 항목  
 <xref:System.Configuration.ApplicationSettingsBase>   
 <xref:System.Configuration.SettingsProvider>   
 [응용 프로그램 설정 아키텍처](../../../../docs/framework/winforms/advanced/application-settings-architecture.md)   
 [How to: Create Application Settings](http://msdn.microsoft.com/ko-kr/53b3af80-1c02-4e35-99c6-787663148945)