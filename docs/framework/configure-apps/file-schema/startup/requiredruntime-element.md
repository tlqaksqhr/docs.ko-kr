---
title: "&lt;requiredRuntime&gt; 요소 | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<requiredRuntime> 요소"
  - "컨테이너 태그, <requiredRuntime> 요소"
  - "requiredRuntime 요소"
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# &lt;requiredRuntime&gt; 요소
응용 프로그램이 공용 언어 런타임 버전 1.0만 지원하도록 지정합니다.  
  
## 구문  
  
```  
  
   <requiredRuntime    
version="runtime version"  
safemode="true|false"/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`version`|선택적 특성입니다.<br /><br /> 이 응용 프로그램이 지원하는 .NET Framework 버전을 지정하는 문자열 값입니다.  이 문자열 값은 .NET Framework 설치 루트 아래에 있는 디렉터리 이름과 일치해야 합니다.  문자열 값의 내용은 구문 분석되지 않습니다.|  
|`safemode`|선택적 특성입니다.<br /><br /> 런타임 버전을 확인하기 위해 런타임 시작 코드로 레지스트리를 검색하는지 여부를 지정합니다.|  
  
## safemode 특성  
  
|값|설명|  
|-------|--------|  
|`false`|런타임 시작 코드가 레지스트리를 검색합니다.  기본값입니다.|  
|`true`|런타임 시작 코드가 레지스트리를 검색하지 않습니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`startup`|`<requiredRuntime>` 요소를 포함합니다.|  
  
## 설명  
 런타임 버전 1.0만 지원하도록 작성된 응용 프로그램은 `<requiredRuntime>` 요소를 사용해야 합니다.  버전 1.1 이상 런타임을 사용하여 빌드된 응용 프로그램은 `<supportedRuntime>` 요소를 사용해야 합니다.  
  
> [!NOTE]
>  [CorBindToRuntimeByCfg](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) 함수를 사용하여 구성 파일을 지정하는 경우 모든 버전의 런타임에 대해 `<requiredRuntime>` 요소를 사용해야 합니다.  [CorBindToRuntimeByCfg](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)를 사용할 때 `<supportedRuntime>` 요소는 무시됩니다.  
  
 `version` 특성 문자열은 지정된 .NET Framework 버전의 설치 폴더 이름과 일치해야 합니다.  이 문자열은 해석되지 않습니다.  일치하는 폴더를 런타임 시작 코드가 찾지 못하면 런타임은 로드되지 않고 시작 코드는 오류 메시지를 표시한 후 종료됩니다.  
  
> [!NOTE]
>  Microsoft Internet Explorer에 호스팅되는 응용 프로그램의 시작 코드는 `<requiredRuntime>` 요소를 무시합니다.  
  
## 예제  
 다음 예제에서는 구성 파일에 런타임 버전을 지정하는 방법을 보여 줍니다.  
  
```  
<configuration>  
   <startup>  
      <requiredRuntime version="v1.0.3705" safemode="true"/>  
   </startup>  
</configuration>  
```  
  
## 참고 항목  
 [시작 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<PaveOver\> Specifying Which Runtime Version to Use](http://msdn.microsoft.com/ko-kr/c376208d-980d-42b4-865b-fbe0d9cc97c2)