---
title: "&lt;configuration&gt;에 대한 &lt;assemblyBinding&gt; 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<assemblyBinding> 요소"
  - "assemblyBinding 요소"
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# &lt;configuration&gt;에 대한 &lt;assemblyBinding&gt; 요소
구성 수준에서 어셈블리 바인딩 정책을 지정합니다.  
  
## 구문  
  
```  
<assemblyBinding    
   xmlns="urn:schemas-microsoft-com:asm.v1">  
</assemblyBinding>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`xmlns`|필수 특성입니다.<br /><br /> 어셈블리 바인딩에 필요한 XML 네임스페이스를 지정합니다.  "urn:schemas\-microsoft\-com:asm.v1"을 값으로 사용합니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<linkedConfiguration\> 요소](../../../../docs/framework/configure-apps/file-schema/linkedconfiguration-element.md)|포함할 구성 파일을 지정합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<configuration\> 요소](../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
  
## 설명  
 [\<linkedConfiguration\> 요소](../../../../docs/framework/configure-apps/file-schema/linkedconfiguration-element.md)를 사용하면 어셈블리 구성 설정을 복제하는 대신 잘 알려진 위치의 어셈블리 구성 파일을 응용 프로그램 구성 파일에 포함할 수 있으므로 구성 요소 어셈블리를 간단하게 관리할 수 있습니다.  
  
> [!NOTE]
>  Windows side\-by\-side 매니페스트가 있는 응용 프로그램에는 `<linkedConfiguration>` 요소를 사용할 수 없습니다.  
  
## 예제  
 다음 코드 예제에서는 로컬 하드 디스크의 구성 파일을 포함하는 방법을 보여 줍니다.  
  
```  
<configuration>  
   <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
      <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>  
   </assemblyBinding>  
</configuration>  
```  
  
## 참고 항목  
 [구성 파일 스키마](../../../../docs/framework/configure-apps/file-schema/index.md)