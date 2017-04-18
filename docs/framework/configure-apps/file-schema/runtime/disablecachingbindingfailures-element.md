---
title: "&lt;disableCachingBindingFailures&gt; 요소 | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCachingBindingFailures"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCachingBindingFailures"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<disableCachingBindingFailures> 요소"
  - "어셈블리[.NET Framework], 바인딩 실패 캐싱"
  - "어셈블리 바인딩 실패 캐싱"
  - "disableCachingBindingFailures 요소"
ms.assetid: bf598873-83b7-48de-8955-00b0504fbad0
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# &lt;disableCachingBindingFailures&gt; 요소
어셈블리는 검색을 통해 찾을 수 없기 때문에 발생하는 실패 바인딩의 캐싱을 사용하지 않도록 할지 여부를 지정합니다.  
  
## 구문  
  
```  
<disableCachingBindingFailures enabled="0|1"/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|enabled|필수 특성입니다.<br /><br /> 어셈블리는 검색을 통해 찾을 수 없기 때문에 발생하는 실패 바인딩의 캐싱을 사용하지 않도록 할지 여부를 지정합니다.|  
  
## enabled 특성  
  
|값|설명|  
|-------|--------|  
|0|어셈블리는 검색을 통해 찾을 수 없기 때문에 발생하는 실패 바인딩의 캐싱을 사용하지 않도록 설정하지 않습니다.  이는 .NET Framework 버전 2.0부터 기본 바인딩 동작입니다.|  
|1|어셈블리는 검색을 통해 찾을 수 없기 때문에 발생하는 실패 바인딩의 캐싱을 사용하지 않도록 설정합니다.  이 설정을 사용하면 .NET Framework 버전 1.1의 바인딩 동작으로 돌아갑니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 수집에 대한 정보를 포함합니다.|  
  
## 설명  
 .NET Framework 버전 2.0부터는 어셈블리 로딩의 기본 동작은 모든 바인딩과 로딩 실패를 캐시하는 것입니다.  즉, 어셈블리를 로드하는 데 실패한 경우 나중에 동일한 어셈블리를 로드하도록 다시 요청하면 어셈블리를 찾지 않고 즉시 작업이 실패하게 됩니다.  이 요소는 검색 경로에서 어셈블리를 찾을 수 없기 때문에 발생하는 바인딩 실패에 대한 기본 동작을 사용하지 않도록 합니다.  이러한 오류는 <xref:System.IO.FileNotFoundException>을 throw합니다.  
  
 일부 바인딩 및 로드 실패가 이 요소에 의해 영향을 받지 않으며 항상 캐시됩니다.  이러한 실패는 어셈블리가 발견되었지만 로드할 수 없기 때문에 발생합니다.  <xref:System.BadImageFormatException> 또는 <xref:System.IO.FileLoadException>을 throw합니다.  다음 목록에는 이러한 오류 몇 가지 포함되어 있습니다.  
  
-   유효한 어셈블리가 아닌 파일을 로드하려고 시도하는 경우 어셈블리를 로드하려는 후속 시도는 잘못된 파일이 올바른 어셈블리로 대체되더라도 실패합니다.  
  
-   파일 시스템에 의해 잠겨 있는 어셈블리를 로드하려고 시도하는 경우 어셈블리를 로드하려는 후속 시도는 시스템이 어셈블리를 해제한 후에도 실패합니다.  
  
-   로드하려는 어셈블리의 하나 이상의 버전이 검색 경로이지만 요청하고 있는 특정 버전이 그 안에 없는 경우 해당 버전을 로드하려는 후속 시도는 올바른 버전이 검색 경로로 이동하더라도 실패합니다.  
  
## 예제  
 다음 코드 예제에서는 어셈블리가 검색을 통해 찾을 수 없기 때문에 발생하는 어셈블리 바인딩 실패의 캐싱을 사용하지 않도록 하는 방법을 보여줍니다.  
  
```  
<configuration>  
   <runtime>  
      <disableCachingBindingFailures enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## 참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [런타임에서 어셈블리를 찾는 방법](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)