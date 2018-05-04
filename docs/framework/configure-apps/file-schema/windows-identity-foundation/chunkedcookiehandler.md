---
title: '&lt;chunkedCookieHandler&gt;'
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 193b783e44fe4386d3575e180dc5baa6a7f9a8be
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltchunkedcookiehandlergt"></a>&lt;chunkedCookieHandler&gt;
구성에서 <xref:System.IdentityModel.Services.ChunkedCookieHandler>합니다. 이 요소를 사용할 수만 있습니다 하는 경우는 `mode` 특성에는 `<cookieHandler>` 요소는 "Default" 또는 "청크 방식"입니다.  
  
 \<system.identityModel.services >  
\<federationConfiguration >  
\<cookieHandler >  
\<chunkedCookieHandler >  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Chunked||Default" >  
      <chunkedCookieHandler size=xs:int >  
      </chunkedCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|chunkSize|HTTP 쿠키에 대 한 HTTP 쿠키 데이터를 문자, 최대 크기입니다. 청크 크기를 조정할 때 주의 해야 합니다. 웹 브라우저 쿠키 및 도메인 별로 허용 되는 수의 크기에 다른 제한 되어 있습니다. 예를 들어 원래 Netscape 사양 조건 이러한 제한으로 규정: 300 쿠키 총 (쿠키 값 뿐 아니라 메타 데이터 포함), 쿠키 헤더 별로 4096 바이트 및 도메인당 쿠키를 20입니다. 기본값은 2000입니다. 필수.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<cookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|구성에서 <xref:System.IdentityModel.Services.CookieHandler> 하는 <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) 읽기 / 쓰기 쿠키를 사용 하 여 합니다.|  
  
## <a name="remarks"></a>설명  
 지정 하는 경우는 <xref:System.IdentityModel.Services.ChunkedCookieHandler> 설정 하 여는 `mode` 특성에는 `<cookieHandler>` "Default" 또는 "Chunked" 요소를 포함 하 여 쿠키를 쓰고 읽기 쿠키 처리기를 사용 하는 청크 크기를 지정할 수 있습니다는 `<chunkedCookieHandler>` 자식 요소 및 설정의 `chunkSize` 특성입니다. 경우는 `<chunkedCookieHandler>` 요소가 존재 하지 않습니다, 2000 바이트의 기본 청크 크기가 사용 됩니다. 이 요소 수 없습니다 될 때 지정 되는 `mode` 특성은 "Custom"로 설정 합니다.  
  
 `<chunkedCookieHandler>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> 클래스입니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 3000 바이트 청크에서 쿠키를 기록 하는 청크 분할된 쿠키가 처리기를 구성 합니다.  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IdentityModel.Services.ChunkedCookieHandler>
