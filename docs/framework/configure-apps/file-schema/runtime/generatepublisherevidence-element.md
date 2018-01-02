---
title: "&lt;generatePublisherEvidence&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c7f7debed03526dbd7a5b2e24ff8a370921fe020
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltgeneratepublisherevidencegt-element"></a>&lt;generatePublisherEvidence&gt; 요소
런타임에서 만들지 여부를 지정 <xref:System.Security.Policy.Publisher> 코드 액세스 보안 (CA)에 대 한 증거입니다.  
  
 \<configuration>  
\<런타임 >  
\<generatePublisherEvidence >  
  
## <a name="syntax"></a>구문  
  
```xml  
<generatePublisherEvidence    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 런타임에서 만들지 여부를 지정 <xref:System.Security.Policy.Publisher> 증명 정보입니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`false`|만들지 않고 <xref:System.Security.Policy.Publisher> 증명 정보입니다.|  
|`true`|만듭니다 <xref:System.Security.Policy.Publisher> 증명 정보입니다. 이 값이 기본값입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
>  에 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] 및 이상 버전에서는이 요소는 어셈블리 로드 시간에 영향을 주지 않습니다. 자세한 내용은의 "보안 정책 단순화" 섹션을 참조 하십시오. [보안 변경 내용](../../../../../docs/framework/security/security-changes.md)합니다.  
  
 공용 언어 런타임 (CLR) 만들기를 로드할 때 Authenticode 서명을 확인 하려고 <xref:System.Security.Policy.Publisher> 어셈블리에 대 한 증거입니다. 그러나 기본적으로 대부분의 응용 프로그램 불필요 <xref:System.Security.Policy.Publisher> 증명 정보입니다. 표준 CAS 정책에 의존 하지 않습니다는 <xref:System.Security.Policy.PublisherMembershipCondition>합니다. 연결 된 응용 프로그램 사용자 지정 CAS 정책 사용 하는 컴퓨터에서 실행 하거나에 대 한 요구를 충족 하기 위해 의도 하지 않는 한 게시자 서명을 확인 하는 필요 하지 않은 시작 비용을 피하기 위해 해야 <xref:System.Security.Permissions.PublisherIdentityPermission> 부분 신뢰 환경에서 합니다. (Id 권한 요청이 항상 완전 신뢰 환경에서 성공합니다.)  
  
> [!NOTE]
>  서비스에서 사용 하는 것이 좋습니다는 `<generatePublisherEvidence>` 시작 성능을 향상 시킬 요소입니다.  이 요소를 사용 하는 시간 제한 및 서비스를 시작한 취소 될 수 있는 지연을 방지할 수 있습니다.  
  
## <a name="configuration-file"></a>구성 파일  
 이 요소는 응용 프로그램 구성 파일에만 사용할 수 있습니다.  
  
## <a name="example"></a>예  
 사용 하는 방법을 보여 주는 다음 예제는 `<generatePublisherEvidence>` 요소를 확인 하는 응용 프로그램에 대 한 CAS 게시자 정책을 사용 하지 않도록 설정 합니다.  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
