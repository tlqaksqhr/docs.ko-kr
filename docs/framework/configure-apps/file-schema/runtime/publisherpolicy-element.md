---
title: "&lt;publisherPolicy&gt; 요소 | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/publisherPolicy"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/publisherPolicy"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#publisherPolicy"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<publisherPolicy> 요소"
  - "컨테이너 태그, <publisherPolicy> 요소"
  - "publisherPolicy 요소"
ms.assetid: 4613407e-d0a8-4ef2-9f81-a6acb9fdc7d4
caps.latest.revision: 18
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 17
---
# &lt;publisherPolicy&gt; 요소
런타임에서 게시자 정책을 적용하는지 여부를 지정합니다.  
  
## 구문  
  
```  
  
<publisherPolicy apply="yes|no"/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`apply`|게시자 정책을 적용할지 여부를 지정합니다.|  
  
## 특성 적용  
  
|값|설명|  
|-------|--------|  
|`yes`|게시자 정책을 적용합니다.  이것이 기본값입니다.|  
|`no`|게시자 정책을 적용하지 않습니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 수집에 대한 정보를 포함합니다.|  
  
## 설명  
 구성 요소 공급업체는 특정 어셈블리의 새 버전을 릴리스할 때, 어셈블리의 이전 버전을 사용하는 응용 프로그램에서 새 버전을 사용할 수 있도록 새 어셈블리에 게시자 정책을 포함시킬 수 있습니다.  특정 어셈블리에 대해 게시자 정책을 적용할지 여부를 지정하려면 **\<publisherPolicy\>** 요소를 **\<dependentAssembly\>** 요소 안에 사용합니다.  
  
 **apply** 특성의 기본값은 **yes**입니다.  **apply** 특성을 **no**로 설정하면 이전의 모든 **yes** 설정이 재정의됩니다.  
  
 권한은 응용 프로그램 구성 파일의 [\<publisherPolicy apply\="no"\>](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) 요소를 사용하여 게시자 정책을 명시적으로 무시하기 위해 응용 프로그램에 필요합니다.  이 권한은 [BindingRedirects](frlrfSystemSecurityPermissionsSecurityPermissionFlagClassTopic) 플래그를 설정함으로서 부여됩니다. 이 플래그는 [SecurityPermission Class](frlrfSystemSecurityPermissionsSecurityPermissionClassTopic)에 있습니다.  자세한 내용은 [어셈블리 바인딩 리디렉션 보안 권한](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md)을 참조하십시오.  
  
## 예제  
 다음 예제에서는 `myAssembly` 어셈블리에 대해 게시자 정책 적용 기능을 해제합니다.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                                    publicKeyToken="32ab4ba45e0a69a1"  
                                    culture="neutral" />  
            <publisherPolicy apply="no"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## 참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [런타임에서 어셈블리를 찾는 방법](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)   
 [어셈블리 버전 리디렉션](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)