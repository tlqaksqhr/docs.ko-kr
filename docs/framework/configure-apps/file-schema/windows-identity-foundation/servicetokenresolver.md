---
title: '&lt;serviceTokenResolver&gt;'
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: c25ea1fc32c93e7eb57ef8ed06d6f786ae0a670e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755762"
---
# <a name="ltservicetokenresolvergt"></a>&lt;serviceTokenResolver&gt;
토큰 처리기 컬렉션에 대 한 처리기가 사용 되는 서비스 토큰 확인자를 등록 합니다. 서비스 토큰 확인 자가 들어오는 토큰 및 메시지 암호화 토큰을 확인 하는 데 사용 됩니다.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<securityTokenHandlers>  
\<securityTokenHandlerConfiguration >  
\<serviceTokenResolver >  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <serviceTokenResolver type=xs:string>  
        </serviceTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|type|서비스 토큰 확인 자가 유형을 지정합니다. 중 하나는 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> 형식 또는 형식에서 파생 되는 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> 클래스입니다. 지정 하는 방법에 대 한 자세한 내용은 `type` 특성 [사용자 지정 형식 참조]를 참조 하십시오. 필수.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|구성 컬렉션의 보안 토큰 처리기를 제공합니다.|  
  
## <a name="remarks"></a>설명  
 들어오는 토큰 및 메시지 암호화 토큰을 확인 하려면 서비스 토큰 확인 자가 사용할 수 있습니다. 들어오는 토큰의 암호를 해독 하는 데 사용 해야 하는 키를 검색 하는 데 사용 됩니다. 지정 해야 합니다는 `type` 특성입니다. 지정 된 형식의 수 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> 또는 사용자 지정 형식에서 파생 되는 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> 클래스입니다.  
  
 일부 토큰 처리기를 사용 하면 구성에서 서비스 토큰 확인자 설정을 지정할 수 있도록 합니다. 개별 토큰 처리기의 설정을 재정의 보안 토큰 처리기 컬렉션에서 지정 합니다.  
  
> [!NOTE]
>  지정 하는 `<serviceTokenResolver>` 의 자식 요소로 요소는 [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소, 되지 않지만 이전 버전과 호환성을 위해 계속 지원 됩니다. 설정에는 `<securityTokenHandlerConfiguration>` 요소에서 재정의 된 `<identityConfiguration>` 요소입니다.  
  
## <a name="example"></a>예제  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
