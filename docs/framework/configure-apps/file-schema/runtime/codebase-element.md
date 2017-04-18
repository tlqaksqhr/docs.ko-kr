---
title: "&lt;codeBase&gt; 요소 | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#codeBase"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/codeBase"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<codeBase> 요소"
  - "codeBase 요소"
  - "컨테이너 태그, <codeBase> 요소"
ms.assetid: d48a3983-2297-43ff-a14d-1f29d3995822
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# &lt;codeBase&gt; 요소
공용 언어 런타임에서 어셈블리를 찾는 위치를 지정합니다.  
  
## 구문  
  
```  
  
   <codeBase    
version="Assembly version"  
href="URL of assembly"/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`href`|필수 특성입니다.<br /><br /> 지정된 어셈블리 버전을 런타임에서 찾는 URL을 지정합니다.|  
|`version`|필수 특성입니다.<br /><br /> codebase가 적용되는 어셈블리 버전을 지정합니다.  어셈블리 버전 번호의 형식은 *major.minor.build.revision*과 같습니다.|  
  
## version 특성  
  
|값|설명|  
|-------|--------|  
|버전 번호의 각 부분에 사용할 수 있는 값은 0부터 65535까지입니다.|해당 사항 없음.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`buildproviders`|사용자 지정 리소스 파일의 컴파일에 사용되는 빌드 공급자의 컬렉션을 정의합니다.  빌드 공급자의 수에는 제한이 없습니다.|  
|`compilation`|ASP.NET이 사용하는 모든 컴파일 설정을 구성합니다.|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`System.web`|ASP.NET 구성 섹션의 루트 요소를 지정합니다.|  
  
## 설명  
 런타임에서 컴퓨터 구성 파일 또는 게시자 정책 파일의 **\<codeBase\>** 설정을 사용하기 위해서는 파일은 어셈블리 버전을 리디렉션해야 합니다.  응용 프로그램 구성 파일의 경우에는 어셈블리 버전을 리디렉션하지 않아도 codebase 설정을 사용할 수 있습니다.  사용할 어셈블리 버전을 결정한 후, 런타임에서는 버전을 결정하는 파일의 codebase 설정을 적용합니다.  지정된 codebase가 없는 경우, 런타임에서는 일반적인 방법으로 어셈블리를 찾습니다.  
  
 어셈블리 이름이 강력한 이름이면 codebase 설정은 로컬 인트라넷 또는 인터넷의 아무 위치에 있어도 되지만  어셈블리가 전용 어셈블리이면 codebase 설정은 응용 프로그램 디렉터리에 상대적인 경로에 위치해야 합니다.  
  
 강력한 이름이 없는 어셈블리의 경우, 버전이 무시되고 로더는 \<dependentAssembly\> 내에서 처음 나오는 \<codebase\> 을 사용합니다.  응용 프로그램 구성 파일에 다른 어셈블리로 바인딩을 리디렉션하는 항목이 있으면 어셈블리 버전이 바인딩 요청과 일치하지 않는 경우에도 리디렉션이 우선적으로 적용됩니다.  
  
## 예제  
 다음 예제에서는 런타임에서 어셈블리를 찾는 위치를 지정하는 방법을 보여 줍니다.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <codeBase version="2.0.0.0"  
                      href="http://www.litwareinc.com/myAssembly.dll"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## 참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [어셈블리 위치 지정](../../../../../docs/framework/configure-apps/specify-assembly-location.md)   
 [런타임에서 어셈블리를 찾는 방법](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)