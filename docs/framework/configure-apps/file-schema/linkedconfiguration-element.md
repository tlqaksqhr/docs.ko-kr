---
title: "&lt;linkedConfiguration&gt; 요소 | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding/linkedConfiguration"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#linkedConfiguration"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<linkedConfiguration> 요소"
  - "구성 파일[.NET Framework], 링크된 구성 파일"
  - "구성 파일 포함"
  - "링크된 구성 파일"
  - "linkedConfiguration 요소"
ms.assetid: 8eb34f3b-427e-4288-a7ff-c73f489deb45
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# &lt;linkedConfiguration&gt; 요소
포함할 구성 파일을 지정합니다.  
  
## 구문  
  
```  
<linkedConfiguration  
   href="URL of linked configuration file"/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`href`|포함할 구성 파일의 URL입니다.  `href` 특성에 대해 지원되는 형식은 "file:\/\/"뿐입니다.  즉, 로컬 파일과 UNC 파일이 지원됩니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<assemblyBinding\> 요소](../../../../docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)|구성 수준에서 어셈블리 바인딩 정책을 지정합니다.|  
  
## 설명  
 `<linkedConfiguration>` 요소는 구성 요소 어셈블리에 대한 서비스를 단순화합니다.  하나 이상의 응용 프로그램에서 잘 알려진 위치에 구성 파일이 있는 어셈블리를 사용하는 경우 해당 어셈블리를 사용하는 응용 프로그램의 구성 파일에서 `<linkedConfiguration>` 요소를 사용하여 구성 정보를 직접 포함하지 않고 어셈블리 구성 파일을 포함할 수 있습니다.  구성 요소 어셈블리가 서비스될 때 공통 구성 파일을 업데이트하면 해당 어셈블리를 사용하는 모든 응용 프로그램에 업데이트된 구성 정보가 제공됩니다.  
  
> [!NOTE]
>  Windows side\-by\-side 매니페스트가 있는 응용 프로그램에는 `<linkedConfiguration>` 요소를 사용할 수 없습니다.  
  
 다음은 연결된 구성 파일의 사용 방식을 제어하는 규칙입니다.  
  
-   포함된 구성 파일의 설정은 로더 바인딩 정책에만 영향을 주고 로더에서만 사용됩니다.  포함된 구성 파일에는 바인딩 정책 이외의 설정이 있을 수 있지만 이러한 설정은 어떤 영향도 주지 않습니다.  
  
-   `href` 특성에 대해 지원되는 형식은 "file:\/\/"뿐입니다.  즉, 로컬 파일과 UNC 파일이 지원됩니다.  
  
-   각 구성 파일에 연결되는 구성의 수에는 제한이 없습니다.  
  
-   연결된 모든 구성 파일은 C\/C\+\+의 `#include` 지시문 동작과 비슷하게 한 파일로 병합됩니다.  
  
-   `<linkedConfiguration>` 요소는 응용 프로그램 구성 파일에서만 사용할 수 있으며 Machine.config에서는 무시됩니다.  
  
-   순환 참조는 검색되어 종료됩니다.  즉, 여러 구성 파일의 `<linkedConfiguration>` 요소가 루프를 형성할 경우 해당 루프가 검색되어 중지됩니다.  
  
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
 [\<assemblyBinding\> 요소](../../../../docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)   
 [구성 파일 스키마](../../../../docs/framework/configure-apps/file-schema/index.md)