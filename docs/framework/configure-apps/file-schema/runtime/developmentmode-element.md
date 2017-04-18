---
title: "&lt;developmentMode&gt; 요소 | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/developmentMode"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#developmentMode"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<developmentMode> 요소"
  - "컨테이너 태그, <developmentMode> 요소"
  - "developmentMode 요소"
ms.assetid: 60e79a8c-415a-497d-be29-b9d0fd9bdee3
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# &lt;developmentMode&gt; 요소
런타임에서, DEVPATH 환경 변수에 지정된 디렉터리에서 어셈블리를 찾는지 여부를 지정합니다.  
  
## 구문  
  
```  
<developmentMode developerInstallation="true | false"/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|**developerInstallation**|런타임에서, DEVPATH 환경 변수에 지정된 디렉터리에서 어셈블리를 찾는지 여부를 지정합니다.|  
  
## developerInstallation 특성  
  
|값|설명|  
|-------|--------|  
|**true**|DEVPATH 환경 변수에 지정된 경로에서 어셈블리를 검색합니다.|  
|**false**|DEVPATH 환경 변수에 지정된 경로에서 어셈블리를 검색하지 않습니다.  이것은 기본값입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 수집에 대한 정보를 포함합니다.|  
  
## 설명  
 이 설정은 개발 과정에서만 사용해야 합니다.  런타임에는 DEVPATH에 있는 강력한 이름의 어셈블리의 버전은 확인하지 않고  처음 발견한 어셈블리를 사용합니다.  
  
## 예제  
 다음 예제에서는 DEVPATH 환경 변수에 지정된 디렉터리에서 어셈블리를 찾도록 런타임을 지정하는 방법을 보여 줍니다.  
  
```  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## 참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [방법: DEVPATH를 사용하여 어셈블리 찾기](../../../../../docs/framework/configure-apps/how-to-locate-assemblies-by-using-devpath.md)