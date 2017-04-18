---
title: "&lt;dependentAssembly&gt; 요소 | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#dependentAssembly"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<dependentAssembly> 요소"
  - "컨테이너 태그, <dependentAssembly> 요소"
  - "dependentAssembly 요소"
ms.assetid: 14e95627-dd79-4b82-ac85-e682aa3a31d8
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# &lt;dependentAssembly&gt; 요소
각 어셈블리에 대한 바인딩 정책 및 어셈블리 위치를 캡슐화합니다.  각 어셈블리에 `dependentAssembly` 요소를 하나만 사용할 수 있습니다.  
  
## 구문  
  
```  
<dependentAssembly>   
</dependentAssembly>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|`assemblyIdentity`|어셈블리에 대한 ID 정보를 포함합니다.  이 요소는 각 `dependentAssembly` 요소에 포함되어야 합니다.|  
|`codeBase`|공유 어셈블리가 컴퓨터에 설치되어 있지 않은 경우에 런타임에서 공유 어셈블리를 찾는 위치를 지정합니다.|  
|`bindingRedirect`|어셈블리 버전을 다른 버전으로 리디렉션합니다.|  
|`publisherPolicy`|런타임에서 이 어셈블리에 대해 게시자 정책을 적용하는지 여부를 지정합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`assemblyBinding`|어셈블리 버전 리디렉션 및 어셈블리 위치에 대한 정보를 포함합니다.|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 수집에 대한 정보를 포함합니다.|  
  
## 예제  
 다음 예제에서는 두 어셈블리의 정보를 캡슐화하는 방법을 보여 줍니다.  
  
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
         <dependentAssembly>  
            <assemblyIdentity name="mySecondAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for mySecondAssembly.-->  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## 참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [어셈블리 버전 리디렉션](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)