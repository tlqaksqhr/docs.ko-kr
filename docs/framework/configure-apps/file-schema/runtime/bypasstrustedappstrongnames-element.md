---
title: "&lt;bypassTrustedAppStrongNames&gt; 요소 | Microsoft Docs"
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
  - "<bypassTrustedAppStrongNames> 요소"
  - "bypassTrustedAppStrongNames 요소"
  - "강력한 이름 건너뛰기 기능"
  - "강력한 이름의 어셈블리, 신뢰할 수 있는 응용 프로그램 도메인으로 로드"
ms.assetid: 71b2ebf6-3843-41e2-ad52-ffa5cd083a40
caps.latest.revision: 18
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 18
---
# &lt;bypassTrustedAppStrongNames&gt; 요소
완전 신뢰 <xref:System.AppDomain>에 로드된 완전 신뢰 어셈블리에 대해 강력한 이름 유효성 검사를 건너뛸지 여부를 지정합니다.  
  
## 구문  
  
```  
<bypassTrustedAppStrongNames    
   enabled="true|false"/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`enabled`|필수 특성입니다.<br /><br /> 완전 신뢰 어셈블리에 대해 강력한 이름 유효성 검사를 건너뛰는 기능을 사용할지 여부를 지정합니다.  이 기능을 사용하면 어셈블리를 로드할 때 강력한 이름의 유효성이 검사되지 않습니다.  기본값은 `true`입니다.|  
  
## enabled 특성  
  
|값|설명|  
|-------|--------|  
|`true`|완전 신뢰 <xref:System.AppDomain>에 어셈블리를 로드할 때 완전 신뢰 어셈블리에 대해 강력한 이름 서명의 유효성이 검사되지 않습니다.  이 값이 기본값입니다.|  
|`false`|완전 신뢰 <xref:System.AppDomain>에 어셈블리를 로드할 때 완전 신뢰 어셈블리에 대해 강력한 이름 서명의 유효성이 검사됩니다.  강력한 이름 서명이 정확한지 여부만 검사되고 다른 강력한 이름과 일치하는지 여부는 비교되지 않습니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 수집에 대한 정보를 포함합니다.|  
  
## 설명  
 강력한 이름 건너뛰기 기능을 사용하면 완전 신뢰 어셈블리의 강력한 이름 서명을 확인하는 데 따르는 오버헤드가 발생하지 않습니다.  
  
 건너뛰기 기능은 강력한 이름으로 서명되었으며 다음과 같은 특징이 있는 모든 어셈블리에 적용됩니다.  
  
-   <xref:System.Security.Policy.StrongName> 증명 정보 없이 완전 신뢰 가능\(예: `MyComputer` 영역 증명 정보 보유\)  
  
-   완전 신뢰 <xref:System.AppDomain>에 로드  
  
-   해당 <xref:System.AppDomain>의 <xref:System.AppDomainSetup.ApplicationBase%2A> 속성 아래에 있는 위치에서 로드  
  
-   서명이 연기되지 않음  
  
> [!NOTE]
>  레지스트리 키를 사용하여 컴퓨터의 모든 응용 프로그램에 대해 건너뛰기 기능을 해제하면 이 구성 파일 설정이 적용되지 않습니다.  자세한 내용은 [방법: 강력한 이름 건너뛰기 기능 비활성화](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md)을 참조하십시오.  
  
## 예제  
 다음 예제에서는 완전 신뢰 어셈블리에 대해 강력한 이름 서명의 유효성을 검사하는 동작을 지정하는 방법을 보여 줍니다.  
  
```  
<configuration>  
   <runtime>  
      <bypassTrustedAppStrongNames enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
## 참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [방법: 강력한 이름 건너뛰기 기능 비활성화](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md)