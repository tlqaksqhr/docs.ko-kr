---
title: "&lt;qualifyAssembly&gt; 요소 | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#qualifyAssembly"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/qualifyAssembly"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<qualifyAssembly> 요소"
  - "컨테이너 태그, <qualifyAssembly> 요소"
  - "qualifyAssembly 요소"
ms.assetid: ad6442f6-1a9d-43b6-b733-04ac1b7f9b82
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# &lt;qualifyAssembly&gt; 요소
부분 이름이 사용될 때 동적으로 로드되어야 하는 어셈블리의 전체 이름을 지정합니다.  
  
## 구문  
  
```  
  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`partialName`|필수 특성입니다.<br /><br /> 코드에 나타나는 어셈블리의 부분 이름을 지정합니다.|  
|`fullName`|필수 특성입니다.<br /><br /> 전역 어셈블리 캐시에 나타나는 어셈블리의 전체 이름을 지정합니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`assemblyBinding`|어셈블리 버전 리디렉션 및 어셈블리 위치에 대한 정보를 포함합니다.|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 수집에 대한 정보를 포함합니다.|  
  
## 설명  
 부분 어셈블리 이름을 사용하여 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> 메서드를 호출하면 공용 언어 런타임은 응용 프로그램 기본 디렉터리에서만 어셈블리를 찾습니다.  응용 프로그램 구성 파일에서 **\<qualifyAssembly\>** 요소를 사용하여 전체 어셈블리 정보\(이름, 버전, 공개 키 토큰 및 문화권\)를 제공하며 공용 언어 런타임이 전역 어셈블리 캐시에서 어셈블리를 찾도록 합니다.  
  
 **fullName** 특성에는 어셈블리 ID의 네 가지 필드\(이름, 버전, 공개 키 토큰 및 문화권\)가 포함되어야 합니다.  **partialName** 특성은 어셈블리를 부분적으로 참조해야 합니다.  최소한 어셈블리의 텍스트 이름은 지정해야 하며\(가장 일반적인 경우\), 버전, 공개 키 토큰 또는 문화권도 포함시킬 수 있습니다. 이 네 필드의 가능한 조합도 지정할 수 있지만 네 필드 모두를 지정해서는 안 됩니다.  **partialName**은 호출에서 지정한 이름과 일치해야 합니다.  예를 들어, 구성 파일에서 `"math"`를 **partialName** 특성으로 지정하고 코드에서 `Assembly.Load("math, Version=3.3.3.3")`을 호출할 수는 없습니다.  
  
## 예제  
 다음 예제에서는 `Assembly.Load("math")`  호출을 `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`로 논리적으로 변환합니다.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <qualifyAssembly partialName="math"   
                         fullName=  
"math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## 참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [런타임에서 어셈블리를 찾는 방법](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)   
 [NIB: Partial Assembly References](http://msdn.microsoft.com/ko-kr/ec90f07a-398c-4306-9401-0fc5ff9cb59f)