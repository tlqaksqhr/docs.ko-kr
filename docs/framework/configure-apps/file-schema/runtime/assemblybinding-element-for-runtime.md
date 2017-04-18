---
title: "&lt;runtime&gt;에 대한 &lt;assemblyBinding&gt; 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<assemblyBinding> 요소"
  - "assemblyBinding 요소"
  - "컨테이너 태그, <assemblyBinding> 요소"
ms.assetid: 964cbb35-ab49-4498-8471-209689e5dada
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# &lt;runtime&gt;에 대한 &lt;assemblyBinding&gt; 요소
어셈블리 버전 리디렉션 및 어셈블리 위치에 대한 정보를 포함합니다.  
  
## 구문  
  
```  
  
        <assemblyBinding    
   xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
</assemblyBinding>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|**xmlns**|필수 특성입니다.<br /><br /> 어셈블리 바인딩에 필요한 XML 네임스페이스를 지정합니다.  문자열 string "urn:schemas\-microsoft\-com:asm.v1"을 값으로 사용합니다.|  
|**appliesTo**|.NET Framework 어셈블리 리디렉션이 적용되는 런타임 버전을 지정합니다.  이 선택적 특성은 .NET Framework 버전 번호를 사용하여 특성이 적용되는 버전을 지정합니다.  **appliesTo** 특성이 지정되지 않으면 **\<assemblyBinding\>** 요소는 .NET Framework의 모든 버전에 적용됩니다.  **appliesTo** 특성은 .NET Framework 버전 1.1에서 도입되었고 .NET Framework 버전 1.0에서는 무시됩니다.  즉, .NET Framework 버전 1.0을 사용할 때는 **appliesTo** 특성을 지정해도 모든 **\<assemblyBinding\>** 요소가 적용됩니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<dependentAssembly\>](../../../../../docs/framework/configure-apps/file-schema/runtime/dependentassembly-element.md)|어셈블리에 대한 바인딩 정책 및 어셈블리 위치를 캡슐화합니다.  각 어셈블리에 **\<dependentAssembly\>** 태그를 하나만 사용할 수 있습니다.|  
|[\<probing\>](../../../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md)|어셈블리를 로드할 때 공용 언어 런타임이 검색하는 하위 디렉터리를 지정합니다.|  
|[\<publisherPolicy\>](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md)|런타임이 게시자 정책을 적용할지를 지정합니다.|  
|[\<qualifyAssembly\>](../../../../../docs/framework/configure-apps/file-schema/runtime/qualifyassembly-element.md)|부분 이름이 사용될 때 동적으로 로드되어야 하는 어셈블리의 전체 이름을 지정합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 수집에 대한 정보를 포함합니다.|  
  
## 예제  
 다음 예제에서는 어셈블리 버전을 다른 버전으로 리디렉션하는 방법을 보여 주고 Codebase를 제공합니다.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <bindingRedirect oldVersion="1.0.0.0"  
                             newVersion="2.0.0.0"/>  
            <codeBase version="2.0.0.0"  
                      href="http://www.litwareinc.com/myAssembly.dll"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 다음 예제에서는 **appliesTo** 특성을 사용하여 .NET Framework 어셈블리의 바인딩을 리디렉션하는 방법을 보여 줍니다.  
  
```  
<runtime>  
   <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
      <dependentAssembly>   
         <assemblyIdentity name="mscorcfg" publicKeyToken="b03f5f7f11d50a3a" culture=""/>  
         <bindingRedirect oldVersion="0.0.0.0-65535.65535.65535.65535" newVersion="1.0.3300.0"/>  
      </dependentAssembly>  
   </assemblyBinding>  
</runtime>  
```  
  
## 참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [어셈블리 버전 리디렉션](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)