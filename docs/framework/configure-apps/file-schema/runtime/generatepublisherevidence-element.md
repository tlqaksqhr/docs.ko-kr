---
title: "&lt;generatePublisherEvidence&gt; 요소 | Microsoft Docs"
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
  - "<generatePublisherEvidence> 요소"
  - "generatePublisherEvidence 요소"
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
caps.latest.revision: 21
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 21
---
# &lt;generatePublisherEvidence&gt; 요소
런타임에서 CAS\(코드 액세스 보안\)의 <xref:System.Security.Policy.Publisher> 증거를 만들지 여부를 지정합니다.  
  
## 구문  
  
```  
<generatePublisherEvidence    
   enabled="true|false"/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`enabled`|필수 특성입니다.<br /><br /> 런타임에서 <xref:System.Security.Policy.Publisher> 증거를 만들지 여부를 지정합니다.|  
  
## enabled 특성  
  
|값|설명|  
|-------|--------|  
|`false`|<xref:System.Security.Policy.Publisher> 증거를 만들지 않습니다.|  
|`true`|<xref:System.Security.Policy.Publisher> 증거를 만듭니다.  이 값이 기본값입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|  
  
## 설명  
  
> [!NOTE]
>  [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] 이상에서 이 요소는 어셈블리 로드 시간에 아무 영향을 미치지 않습니다.  자세한 내용은 [보안 변경 내용](../../../../../docs/framework/security/security-changes.md)의 "보안 정책 단순화" 섹션을 참조하십시오.  
  
 CLR\(공용 언어 런타임\)은 어셈블리에 대한 <xref:System.Security.Policy.Publisher> 증명 정보를 만들기 위해 로드 시 Authenticode 서명을 확인합니다.  그러나 기본적으로 대부분의 응용 프로그램에는 <xref:System.Security.Policy.Publisher> 증명 정보가 필요하지 않습니다.  표준 CAS 정책은 <xref:System.Security.Policy.PublisherMembershipCondition>을 사용하지 않습니다.  사용자 응용 프로그램이 사용자 지정 CAS 정책을 사용하는 컴퓨터에서 실행되지 않거나 부분 신뢰 환경에서 <xref:System.Security.Permissions.PublisherIdentityPermission>에 대한 요청을 충족시키기 위한 것이 아닐 경우 게시자 서명 확인과 관련된 불필요한 시작 작업을 수행하지 않아야 합니다. 전체 신뢰 환경에서는 ID 권한 요청이 항상 성공합니다.  
  
> [!NOTE]
>  서비스에서 `<generatePublisherEvidence>` 요소를 사용하여 시작 성능을 향상시키는 것이 좋습니다.  이 요소를 사용하면 시간이 초과되거나 서비스 시작이 취소될 수 있는 지연을 방지할 수도 있습니다.  
  
## 구성 파일  
 이 요소는 응용 프로그램 구성 파일에서만 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 `<generatePublisherEvidence>` 요소를 사용하여 응용 프로그램에 대한 CAS 게시자 정책을 검사하지 않도록 하는 방법을 보여 줍니다.  
  
```  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## 참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)