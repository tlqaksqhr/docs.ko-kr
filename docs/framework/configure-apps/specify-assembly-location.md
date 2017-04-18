---
title: "어셈블리 위치 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
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
  - "응용 프로그램 구성[.NET Framework]"
  - "어셈블리[.NET Framework], 위치 지정"
  - "구성[.NET Framework], 응용 프로그램"
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# 어셈블리 위치 지정
어셈블리 위치를 지정하는 방법에는 다음과 같은 두 가지가 있습니다.  
  
-   [\<codeBase\>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) 요소 사용  
  
-   [\<probing\>](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) 요소 사용  
  
 또한 [.NET Framework 구성 도구\(Mscorcfg.msc\)](http://msdn.microsoft.com/ko-kr/a7106c52-68da-490e-b129-971b2c743764) 요소를 사용하여 어셈블리 위치를 지정하거나 공용 언어 런타임의 위치를 지정하여 어셈블리를 검색할 수 있습니다.  
  
## \<codeBase\> 요소 사용  
 **\<codeBase\>** 요소를 어셈블리 버전을 리디렉션하는 컴퓨터 구성 파일 또는 게시자 정책 파일에서만 사용될 수 있습니다.  런타임에서는 사용할 어셈블리 버전을 결정할 때 파일의 코드 베이스 설정을 적용합니다. 이 코드 베이스 설정에 의해 버전이 결정됩니다.  코드 베이스가 지정되지 않은 경우 런타임에서는 정상적인 방법으로 어셈블리를 검색합니다.  자세한 내용은 [런타임에서 어셈블리를 찾는 방법](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)을 참조하십시오.  
  
 다음 예제는 어셈블리 위치 지정 방법을 나타냅니다.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
       <dependentAssembly>  
         <assemblyIdentity name="myAssembly"  
                           publicKeyToken="32ab4ba45e0a69a1"  
                           culture="en-us" />  
         <codeBase version="2.0.0.0"  
                   href="http://www.litwareinc.com/myAssembly.dll"/>  
       </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 강력한 이름의 모든 어셈블리에는 **version** 특성이 필요하지만 강력한 이름이 아닌 어셈블리에는 이 특성을 사용하면 안 됩니다.  **\<codeBase\>** 요소는 **href** 특성이 필요합니다.  **\<codeBase\>** 요소에서 버전 범위를 지정할 수 없습니다.  
  
> [!NOTE]
>  강력한 이름이 아닌 어셈블리에 코드 베이스 힌트를 제공하는 경우, 이 힌트는 응용 프로그램 기본 디렉터리 또는 응용 프로그램 기본 디렉터리의 하위 디렉터리를 가리켜야 합니다.  
  
## \<probing\> 요소 사용  
 런타임에서는 검색을 사용하여 코드 베이스가 없는 어셈블리를 찾습니다.  검색에 대한 자세한 내용은 [런타임에서 어셈블리를 찾는 방법](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)을 참조하십시오.  
  
 응용 구성 파일에서 [\<probing\>](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) 요소를 어셈블리를 찾을 때 런타임에서 검색해야 하는 하위 디렉터리를 지정할 수 있습니다.  다음 예제는 런타임에서 검색할 디렉터리를 지정하는 방법을 나타냅니다.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 **privatePath** 특성에는 런타임에서 어셈블리를 검색할 디렉터리가 들어 있습니다.  응용 프로그램이 C:\\Program Files\\MyApp에 존재하는 경우, 런타임에서는 코드 베이스를 지정하지 않는 어셈블리를 C:\\Program Files\\MyApp\\Bin, C:\\Program Files\\MyApp\\Bin2\\Subbin 및 C:\\Program Files\\MyApp\\Bin3에서 검색할 것입니다.  **privatePath**에 지정된 디렉터리는 응용 프로그램 기본 디렉터리의 하위 디렉터리가 되어야 합니다.  
  
## 참고 항목  
 [공용 언어 런타임의 어셈블리](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)   
 [어셈블리를 사용한 프로그래밍](../../../docs/framework/app-domains/programming-with-assemblies.md)   
 [런타임에서 어셈블리를 찾는 방법](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)   
 [Configuring .NET Framework Apps](http://msdn.microsoft.com/ko-kr/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)