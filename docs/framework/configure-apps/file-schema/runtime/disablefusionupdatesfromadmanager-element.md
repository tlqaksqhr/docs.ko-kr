---
title: "&lt;disableFusionUpdatesFromADManager&gt; 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
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
  - "<disableFusionUpdatesFromADManager> 요소"
  - "disableFusionUpdatesFromADManager 요소"
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# &lt;disableFusionUpdatesFromADManager&gt; 요소
런타임 호스트에서 응용 프로그램 도메인에 대한 구성 설정을 재정의할 수 있도록 허용하는 기본 동작을 해제할지 여부를 지정합니다.  
  
## 구문  
  
```  
<disableFusionUpdatesFromADManager enabled="0|1"/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|enabled|필수 특성입니다.<br /><br /> 퓨전 설정을 재정의하는 기본 기능을 사용하지 않도록 설정할지 여부를 지정합니다.|  
  
## enabled 특성  
  
|값|설명|  
|-------|--------|  
|0|퓨전 설정을 재정의하는 기능을 사용하지 않도록 설정하지 않습니다.  이는 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]부터 기본 동작입니다.|  
|1|퓨전 설정을 재정의하는 기능을 사용하지 않도록 설정합니다.  이렇게 하면 이전 .NET Framework 버전의 동작으로 돌아갑니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 수집에 대한 정보를 포함합니다.|  
  
## 설명  
 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]부터는 기본적으로 <xref:System.AppDomainManager> 개체가 <xref:System.AppDomainManager>의 서브클래스에서 <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=fullName> 메서드의 구현에 전달되는 <xref:System.AppDomainSetup> 개체의 <xref:System.AppDomainSetup.SetConfigurationBytes%2A> 메서드나 <xref:System.AppDomainSetup.ConfigurationFile%2A> 속성을 사용하여 구성 설정을 재정의할 수 있습니다.  기본 응용 프로그램 도메인에서는 사용자가 변경하는 설정이 응용 프로그램 구성 파일에 지정된 설정을 재정의합니다.  다른 응용 프로그램 도메인에서는 이러한 설정이 <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=fullName> 또는 <xref:System.AppDomain.CreateDomain%2A?displayProperty=fullName> 메서드에 전달된 구성 설정을 재정의합니다.  
  
 새 구성 정보를 전달하거나 null\(Visual Basic의 경우 `Nothing`\)을 전달하여 이전에 전달된 구성 정보를 제거할 수 있습니다.  
  
 <xref:System.AppDomainSetup.ConfigurationFile%2A> 속성과 <xref:System.AppDomainSetup.SetConfigurationBytes%2A> 메서드 모두에 구성 정보를 전달하지 않습니다.  이러한 속성과 메서드 둘 다에 구성 정보를 전달하면 <xref:System.AppDomainSetup.SetConfigurationBytes%2A> 메서드가 응용 프로그램 구성 파일의 구성 정보를 재정의하므로 <xref:System.AppDomainSetup.ConfigurationFile%2A> 속성에 전달되는 속성이 무시됩니다.  <xref:System.AppDomainSetup.ConfigurationFile%2A> 속성을 사용하는 경우 <xref:System.AppDomainSetup.SetConfigurationBytes%2A> 메서드에 null\(Visual Basic의 경우 `Nothing`\)을 전달하여 <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=fullName> 또는 <xref:System.AppDomain.CreateDomain%2A?displayProperty=fullName> 메서드에 대한 호출에 지정된 구성 바이트를 제거할 수 있습니다.  
  
 구성 정보 외에도 <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=fullName> 메서드의 구현에 전달되는 <xref:System.AppDomainSetup> 개체에 대한 설정을 변경할 수도 있습니다. 이러한 설정에는 <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A>, <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>, <xref:System.AppDomainSetup.PrivateBinPath%2A>, <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>, <xref:System.AppDomainSetup.ShadowCopyDirectories%2A> 및 <xref:System.AppDomainSetup.ShadowCopyFiles%2A>가 있습니다.  
  
 `<disableFusionUpdatesFromADManager>` 요소를 사용하는 대신 레지스트리 설정을 만들거나 환경 변수를 설정하여 기본 동작을 해제할 수 있습니다.  레지스트리에서 `HKCU\Software\Microsoft\.NETFramework` 또는 `HKLM\Software\Microsoft\.NETFramework` 아래 `COMPLUS_disableFusionUpdatesFromADManager`라는 DWORD 값을 만들고 이 값을 1로 설정합니다.  명령줄에서 환경 변수 `COMPLUS_disableFusionUpdatesFromADManager`를 1로 설정합니다.  
  
## 예제  
 다음 코드 예제에서는 `<disableFusionUpdatesFromADManager>` 요소를 사용하여 퓨전 설정을 재정의하는 기능을 사용하지 않도록 설정하는 방법을 보여 줍니다.  
  
```  
<configuration>  
   <runtime>  
      <disableFusionUpdatesFromADManager enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## 참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [런타임에서 어셈블리를 찾는 방법](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)