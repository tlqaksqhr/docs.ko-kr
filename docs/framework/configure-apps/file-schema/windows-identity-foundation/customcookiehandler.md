---
title: '&lt;customCookieHandler&gt;'
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: b974767aa86801bff234e200e1fce021bfc422c5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755606"
---
# <a name="ltcustomcookiehandlergt"></a>&lt;customCookieHandler&gt;
사용자 지정 쿠키 처리기 유형을 설정합니다. 이 요소를 사용할 수만 있습니다 하는 경우는 `mode` 특성에는 `<cookieHandler>` 요소는 "Custom"입니다. 사용자 지정 형식에서 파생 되어야 합니다는 <xref:System.IdentityModel.Services.CookieHandler> 클래스입니다.  
  
 \<system.identityModel.services >  
\<federationConfiguration >  
\<cookieHandler >  
\<customCookieHandler >  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Custom">  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" >  
      </customCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|type|파생 되는 사용자 지정 형식을 지정 된 <xref:System.IdentityModel.Services.CookieHandler> 클래스입니다. 지정 하는 방법에 대 한 자세한 내용은 `type` 특성을 참조 하십시오. [사용자 정의 형식 참조](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<cookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|구성에서 <xref:System.IdentityModel.Services.CookieHandler> 하는 <xref:System.IdentityModel.Services.SessionAuthenticationModule> 읽기 및 쓰기 쿠키를 사용 하 여 합니다.|  
  
## <a name="remarks"></a>설명  
 사용자 지정 쿠키 처리기를 설정 하 여 지정 되는 경우는 `mode` 특성의는 `<cookieHandler>` 요소를 포함 하 여 사용자 지정 쿠키 처리기의 형식을 지정 해야 하는 "Custom"으로 `<customCookieHandler>` 쿠키 처리기 형식을 참조 하는 자식 요소입니다. 이 요소 수 없습니다 될 때 지정 되는 `mode` 특성은 "이 Chunked" 또는 "Default"로 설정 합니다. 사용자 지정 쿠키 처리기에서 파생 되어야 합니다는 <xref:System.IdentityModel.Services.CookieHandler> 클래스입니다.  
  
 `<customCookieHandler>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Configuration.CustomTypeElement> 클래스입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 구성 유형의 사용자 지정 쿠키 처리기 사용 하 여 SAM `MyNamespace.MyCustomCookieHandler`합니다.  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IdentityModel.Services.CookieHandler>
