---
title: '&lt;tokenReplayDetection&gt;'
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 7f0cef2590bb301e6897aa4922454942ecdd0957
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755229"
---
# <a name="lttokenreplaydetectiongt"></a>&lt;tokenReplayDetection&gt;
토큰 재생 검색을 사용 하도록 설정 하 고 토큰에 대 한 만료 시간을 지정 합니다.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<tokenReplayDetection >  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a>형식  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|사용|토큰 재생 검색; 사용할지 여부를 지정 하는 값 토큰을 사용 하도록 설정 하려면 "true" 재생 검색 합니다.|  
|expirationPeriod|A <xref:System.TimeSpan> 항목 만료 된 것으로 간주 되어 캐시에서 제거 하기 전의 시간을 최대 크기를 지정 하는 합니다.  지정 하는 방법에 대 한 자세한 내용은 <xref:System.TimeSpan> 값, 참조 [Timespan 값](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|서비스 수준 id 설정을 지정합니다.|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|구성 컬렉션의 보안 토큰 처리기를 제공합니다.|  
  
## <a name="remarks"></a>설명  
 A `<tokenReplayDetection>` 에서 서비스 수준에서 요소를 지정할 수 있습니다는 `<identityConfiguration>` 요소 또는 보안 토큰 처리기 컬렉션 수준 아래에 `<securityTokenHandlerConfiguration>` 요소입니다. 서비스에 지정 된 토큰 처리기 컬렉션에 대 한 설정을 재정의 합니다.  
  
 변수로 지정 된 토큰 재생 캐시 형식은 [ \<tokenReplayCache >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) 요소입니다.
