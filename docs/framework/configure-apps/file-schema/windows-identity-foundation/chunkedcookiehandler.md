---
title: "&lt;chunkedCookieHandler&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
caps.latest.revision: 5
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# &lt;chunkedCookieHandler&gt;
구성의 <xref:System.IdentityModel.Services.ChunkedCookieHandler>.  만이 요소가 있을 수 있습니다 경우는 `mode` 의 특성은 `<cookieHandler>` 요소인 "Default" 또는 "청크 분할".  
  
## 구문  
  
```  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Chunked||Default" >  
      <chunkedCookieHandler size=xs:int >  
      </chunkedCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|chunkSize|문자는 HTTP 쿠키를 HTTP 쿠키 데이터의 최대 크기입니다.  청크 크기를 조정할 때는 주의 해야 합니다.  웹 브라우저가 다른 쿠키 및 도메인 당 허용 되는 숫자의 크기에 제한이 있습니다.  예를 들어, 원래 Netscape 사양 이러한 제한을 소통은 조건으로 규정: 총 300 쿠키를 4096 바이트 당 쿠키 헤더 \(쿠키 값 뿐 아니라 메타 데이터 포함\) 및 도메인 당 20 쿠키.  기본값은 2000입니다.  필수 요소.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<cookieHandler\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|구성의 <xref:System.IdentityModel.Services.CookieHandler> 에 <xref:System.IdentityModel.Services.SessionAuthenticationModule> \(SAM\)를 사용 하 여 읽기 및 쓰기 쿠키.|  
  
## 설명  
 지정할 때는 <xref:System.IdentityModel.Services.ChunkedCookieHandler> 설정 하 여는 `mode` 특성의는 `<cookieHandler>` "Default" 또는 "청크 분할" 요소의 쿠키 처리기를 사용 하 여 읽기 및 쿠키를 포함 하 여 작성 하는 청크 크기 지정할 수는 `<chunkedCookieHandler>` 자식 요소와 설정을 해당 `chunkSize` 특성.  경우는 `<chunkedCookieHandler>` 요소는 표시 되지 않습니다, 2000 바이트의 기본 청크 크기를 사용 합니다.  이 요소가 될 수 없을 때 지정한는 `mode` 특성 설정 "사용자 정의".  
  
 `<chunkedCookieHandler>` 요소가 표시 되는 <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> 클래스입니다.  
  
## 예제  
 다음 예제에서는 3000 바이트의 청크에서 쿠키를 작성 하는 청크 분할된 쿠키 처리기를 구성 합니다.  
  
```  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## 참고 항목  
 <xref:System.IdentityModel.Services.ChunkedCookieHandler>