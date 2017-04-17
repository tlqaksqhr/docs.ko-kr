---
title: "&lt;customCookieHandler&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 6
---
# &lt;customCookieHandler&gt;
사용자 지정 쿠키 처리기 형식을 설정합니다.  만이 요소가 있을 수 있습니다 경우는 `mode` 의 특성은 `<cookieHandler>` 요소인 "Custom".  지정 된 형식에서 파생 되어야 합니다는 <xref:System.IdentityModel.Services.CookieHandler> 클래스입니다.  
  
## 구문  
  
```  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode=”Custom”>  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" >  
      </customCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|type|파생 되는 사용자 지정 형식 지정은 <xref:System.IdentityModel.Services.CookieHandler> 클래스입니다.  지정 하는 방법에 대 한 자세한 내용은 `type` 특성, 볼 [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_CustomTypeReferences).|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<cookieHandler\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|구성의 <xref:System.IdentityModel.Services.CookieHandler> 에 <xref:System.IdentityModel.Services.SessionAuthenticationModule> 읽기 및 쓰기 쿠키를 사용 하 여.|  
  
## 설명  
 지정 쿠키를 사용자 지정 처리기를 설정 하 여는 `mode` 의 특성은 `<cookieHandler>` 요소 "사용자 지정"을 포함 하 여 사용자 지정 쿠키 처리기 형식을 지정 해야는 `<customCookieHandler>` 쿠키 처리기 형식을 참조 하는 자식 요소.  이 요소가 될 수 없습니다 시기 지정는 `mode` 특성 "청크" 또는 "기본"으로 설정 되어 있습니다.  사용자 지정 쿠키 처리기에서 파생 해야는 <xref:System.IdentityModel.Services.CookieHandler> 클래스입니다.  
  
 `<customCookieHandler>` 요소가 표시 되는 <xref:System.IdentityModel.Configuration.CustomTypeElement> 클래스입니다.  
  
## 예제  
 다음 예제에서는 처리기 형식의 사용자 지정 쿠키를 사용 하 여 SAM 구성 `MyNamespace.MyCustomCookieHandler`.  
  
```  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## 참고 항목  
 <xref:System.IdentityModel.Services.CookieHandler>