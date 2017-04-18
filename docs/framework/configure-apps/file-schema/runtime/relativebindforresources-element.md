---
title: "&lt;relativeBindForResources&gt; 요소 | Microsoft Docs"
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
  - "<relativeBindForResources> 요소"
  - "RelativeBindForResources 요소"
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# &lt;relativeBindForResources&gt; 요소
위성 어셈블리의 프로브를 최적화합니다.  
  
## 구문  
  
```vb  
<relativeBindForResources    
   enabled="true|false" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`enabled`|필수 특성입니다.<br /><br /> 공용 언어 런타임이 위성 어셈블리에 대한 프로브를 최적화하는지 여부를 지정 합니다.|  
  
## enabled 특성  
  
|값|설명|  
|-------|--------|  
|`false`|런타임은 위성 어셈블리의 프로브를 최적화 하지 않습니다.  기본값입니다.|  
|`true`|런타임이 위성 어셈블리에 대한 프로브를 최적화합니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|  
  
## 설명  
 일반적으로, [리소스 패키징 및 배포](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md) 항목에 명시된 것처럼, 리소스 관리자는 리소스를 찾습니다.  즉 리소스 관리자가 특정 리소스의 지역화 된 버전에 대해 조사할 때, 전역 어셈블리 캐시에서, 응용 프로그램의 코드 기반에서 문화권 별 폴더에서, 위성 어셈블리의 쿼리 Windows Installer에서 볼수 있고, <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName> 이벤트를 발생시킵니다.  `<relativeBindForResources>` 요소는 리소스 관리자가 위성 어셈블리를 찾는 방법을 최적화 합니다.  다음과 같은 경우 리소스에 대해 검색 하는 경우에 성능을 향상 시킬 수 있습니다.  
  
-   위성 어셈블리는 코드 어셈블리와 같은 위치에 배포 됩니다.  즉, 코드 어셈블리가 전역 어셈블리 캐시에 설치 되어 있으면, 위성 어셈블리도 그곳에 설치 되어 있어야 합니다.  코드 어셈블리가 응용 프로그램의 코드 베이스에 설치 된 경우에, 위성 어셈블리는 코드 베이스의 문화권별 폴더에 설치 되어야 합니다.  
  
-   Windows Installer가 사용 되지 않거나 필요한 위성 어셈블리 설치에서 드물게 쓰일 때  
  
-   응용 프로그램 코드가 <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName> 이벤트를 처리 하지 않을 때  
  
 `enabled` 특성 \(`<relativeBindForResources>` 요소에 있습니다.\)를 `true` 로 설정하는 것은 다음과 같이 위성 어셈블리의 리소스 관리자 검색을 최적화 합니다:  
  
-   부모 코드 어셈블리의 위치를 사용하여 위성 어셈블리에 대한 조사를 합니다.  
  
-   위성 어셈블리에 대해 Windows Installer를 쿼리하지 않습니다.  
  
-   이로 인해 <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName> 이벤트가 발생하지는 않습니다.  
  
## 참고 항목  
 [리소스 패키징 및 배포](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)   
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)