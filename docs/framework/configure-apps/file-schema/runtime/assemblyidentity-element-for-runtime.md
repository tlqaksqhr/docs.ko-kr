---
title: "&lt;runtime&gt;에 대한 &lt;assemblyIdentity&gt; 요소 | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/assemblyIdentity"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#assemblyIdentity"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<assemblyIdentity> 요소"
  - "assemblyIdentity 요소"
  - "컨테이너 태그, <assemblyIdentity> 요소"
ms.assetid: cea4d187-6398-4da4-af09-c1abc6a349c1
caps.latest.revision: 17
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 17
---
# &lt;runtime&gt;에 대한 &lt;assemblyIdentity&gt; 요소
어셈블리에 대한 ID 정보를 포함합니다.  
  
## 구문  
  
```  
  
   <assemblyIdentity    
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`name`|필수 특성입니다.<br /><br /> 어셈블리의 이름입니다.|  
|`culture`|선택적 특성입니다.<br /><br /> 어셈블리의 언어 및 국가\/지역을 지정하는 문자열입니다.|  
|`publicKeyToken`|선택적 특성입니다.<br /><br /> 어셈블리의 강력한 이름을 지정하는 16진수 값입니다.|  
|`processorArchitecture`|선택적 특성입니다.<br /><br /> 프로세서별 코드가 들어 있는 어셈블리의 프로세서 아키텍처를 지정하는 "x86", "amd64", "msil" 또는 "ia64" 값 중 하나입니다.  값은 대\/소문자를 구분하지 않습니다.  특성에 다른 값이 지정되면 `<assemblyIdentity>` 요소 전체가 무시됩니다.  <xref:System.Reflection.ProcessorArchitecture>를 참조하십시오.|  
  
## processorArchitecture 특성  
  
|값|설명|  
|-------|--------|  
|`amd64`|64비트 AMD 프로세서 전용입니다.|  
|`ia64`|64비트 Intel 프로세서 전용입니다.|  
|`msil`|프로세서 및 워드 당 비트 수에 대해 중립적입니다.|  
|`x86`|네이티브 32비트 Intel 프로세서 또는 64비트 플랫폼의 WOW\(Windows On Windows\) 환경에서 실행되는 32비트 Intel 프로세서입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`assemblyBinding`|어셈블리 버전 리디렉션 및 어셈블리 위치에 대한 정보를 포함합니다.|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`dependentAssembly`|각 어셈블리에 대한 바인딩 정책 및 어셈블리 위치를 캡슐화합니다.  각 어셈블리에 `<dependentAssembly>` 요소를 하나만 사용할 수 있습니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 수집에 대한 정보를 포함합니다.|  
  
## 설명  
 모든 **\<dependentAssembly\>** 요소에는 **\<assemblyIdentity\>** 자식 요소가 하나 있어야 합니다.  
  
 `processorArchitecture` 특성이 있으면 `<assemblyIdentity>` 요소는 해당 프로세서 아키텍처가 있는 어셈블리에만 적용됩니다.  `processorArchitecture` 특성이 없으면 `<assemblyIdentity>` 요소는 임의의 프로세서 아키텍처가 있는 어셈블리에 적용될 수 있습니다.  
  
 다음 예제에서는 각기 다른 두 프로세서 아키텍처를 대상으로 하며 각 버전이 동기화 상태를 유지하지 않는 같은 이름의 두 어셈블리에 대한 구성 파일을 보여 줍니다.  x86 플랫폼에서 응용 프로그램이 실행되면 첫 번째 `<assemblyIdentity>` 요소만 적용되고 다른 요소는 무시됩니다.  x86 또는 ia64 이외의 플랫폼에서 응용 프로그램이 실행될 경우에는 두 요소가 모두 무시됩니다.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"  
                  processorArchitecture="x86" />  
            <bindingRedirect oldVersion= "1.0.0.0"   
                  newVersion="1.1.0.0" />  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"   
                  processorArchitecture="ia64" />  
            <bindingRedirect oldVersion="1.0.0.0"   
                  newVersion="2.0.0.0" />  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 구성 파일에 `processorArchitecture` 특성이 없는 `<assemblyIdentity>` 요소가 들어 있고 일치하는 플랫폼을 지정하는 요소가 들어 있지 않으면 `processorArchitecture` 특성이 없는 요소가 사용됩니다.  
  
## 예제  
 다음 예제에서는 어셈블리에 대한 정보를 제공하는 방법을 보여 줍니다.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for myAssembly.-->  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## 참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [어셈블리 버전 리디렉션](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)