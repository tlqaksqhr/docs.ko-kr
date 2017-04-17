---
title: "&lt;NetFx40_PInvokeStackResilience&gt; 요소 | Microsoft Docs"
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
  - "<NetFx40_PInvokeStackResilience> 요소"
  - "NetFx40_PInvokeStackResilience 요소"
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# &lt;NetFx40_PInvokeStackResilience&gt; 요소
프로그램 관리 및 비관리 코드 사이의 느린 전환 비용으로 런타임에 잘못된 플랫폼 호출 선언을 자동으로 해결할지 여부를 지정합니다.  
  
## 구문  
  
```  
<NetFx40_PInvokeStackResilience  enabled="1|0"/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`enabled`|필수 특성입니다.<br /><br /> 런타임에 잘못된 플랫폼 호출 선언을 검색하고 32비트 플랫폼에서 런타임에 자동으로 스택을 해결할지 여부를 지정합니다.|  
  
## enabled 특성  
  
|값|설명|  
|-------|--------|  
|`0`|런타임은 잘못된 플랫폼 호출 선언을 검색하고 해결하지 못하는 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]에 도입된 빠른 interop 마샬링 아키텍처를 사용합니다.  이 값이 기본값입니다.|  
|`1`|런타임은 잘못된 플랫폼 호출 선언을 감지하고 해결하는 느린 전환을 사용합니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|  
  
## 설명  
 이 요소는 잘못된 플랫폼 호출 선언에 대해 런타임 복원력에 대한 빠른 interop 마샬링을 수행할 수 있습니다.  
  
 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 로 시작하는 합리적인 interop 마샬링 아키텍처 전환 관리 코드에서 비관리 코드에 대한 상당한 성능 향상을 제공합니다.  이전 버전의 .NET Framework에서는 마샬링 계층이 32비트 플랫폼에서 잘못된 플랫폼 호출 선언을 감지하고 스택을 자동으로 해결했습니다.  새로운 마샬링 아키텍처는 이 단계를 제거합니다.  결과적으로 전환은 매우 빠르지만 잘못된 플랫폼 호출 선언으로 인해 프로그램 오류가 발생할 수 있습니다.  
  
 개발하는 동안 잘못된 선언을 찾기 쉽도록 Visual Studio 디버깅 환경이 개선되었습니다.  [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) MDA\(관리 디버깅 도우미\)는 연결된 디버거를 사용하여 응용 프로그램을 실행할 때 사용자가 잘못된 플랫폼 호출 선언에 대해 알립니다.  
  
 응용 프로그램이 다시 컴파일할 수 없고 잘못된 플랫폼 호출 선언이 있는 구성 요소를 사용하는 시나리오를 해결하려면 `NetFx40_PInvokeStackResilience` 요소를 사용할 수 있습니다.  `enabled="1"`과 함께 응용 프로그램 구성 파일에 이 요소를 추가하면 느린 전환 비용으로 이전 버전의 .NET Framework 동작과의 호환성 모드를 사용합니다.  이전 버전의 .NET Framework에 대해 컴파일된 어셈블리는 이 호환성 모드를 자동으로 선택하며 이 요소가 필요하지 않습니다.  
  
## 구성 파일  
 이 요소는 응용 프로그램 구성 파일에서만 사용할 수 있습니다.  
  
## 예제  
 다음 예제는 관리되는 코드와 관리되지 않는 코드 사이의 느린 전환 비용으로 응용 프로그램에 대한 잘못된 플랫폼 호출 선언에 대해 증가된 복원을 선택하는 방법을 보여줍니다.  
  
```  
<configuration>  
   <runtime>  
      <NetFx40_PInvokeStackResilience enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## 참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)