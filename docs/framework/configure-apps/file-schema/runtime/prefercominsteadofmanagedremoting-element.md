---
title: "&lt;PreferComInsteadOfManagedRemoting&gt; 요소 | Microsoft Docs"
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
  - "<PreferComInsteadOfManagedRemoting> 요소"
  - "PreferComInsteadOfManagedRemoting 요소"
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
caps.latest.revision: 17
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 17
---
# &lt;PreferComInsteadOfManagedRemoting&gt; 요소
런타임에서 응용 프로그램 도메인 경계를 넘는 모든 호출에 원격 서비스 대신 COM interop를 사용하는지 여부를 지정합니다.  
  
## 구문  
  
```  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`enabled`|필수 특성입니다.<br /><br /> 런타임이 응용 프로그램 도메인 경계에서 원격 서비스 대신 COM interop를 사용하는지 여부를 나타냅니다.|  
  
## enabled 특성  
  
|값|설명|  
|-------|--------|  
|`false`|런타임이 응용 프로그램 도메인 경계에서 원격 서비스를 사용합니다.  이 값이 기본값입니다.|  
|`true`|런타임이 응용 프로그램 도메인 경계에서 COM interop를 사용합니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 수집에 대한 정보를 포함합니다.|  
  
## 설명  
 `enabled` 특성을 `true`로 설정하면 런타임이 다음과 같이 동작합니다.  
  
-   런타임은 [IUnknown::QueryInterface](http://go.microsoft.com/fwlink/?LinkID=144867) 를 [IManagedObject](../../../../../ocs/framework/unmanaged-api/hosting/imanagedobject-interface.md) 인터페이스를 위해  [IUnknown](http://go.microsoft.com/fwlink/?LinkId=148003) 인터페이스가 COM 인터페이스를 통해 도메인을 입력시킬 때 호출 하지 않습니다.  개체 주위에 RCW\([RCW](../../../../../docs/framework/interop/runtime-callable-wrapper.md)\)를 만듭니다.  
  
-   런타임이 이 도메인에서 만든 CCW\([CCW](../../../../../docs/framework/interop/com-callable-wrapper.md)\)의 [IManagedObject](../../../../../ocs/framework/unmanaged-api/hosting/imanagedobject-interface.md) 인터페이스에 대한 `QueryInterface` 호출을 받으면 E\_NOINTERFACE를 반환합니다.  
  
 이러한 두 동작은 응용 프로그램 도메인 경계에서 관리되는 개체 간의 COM 인터페이스에 대한 모든 호출에 원격 서비스 대신 COM과 COM interop가 사용되도록 합니다.  
  
## 예제  
 다음 예제에서는 런타임이 격리 경계에서 COM interop를 사용하도록 지정하는 방법을 보여 줍니다.  
  
```  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## 참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)