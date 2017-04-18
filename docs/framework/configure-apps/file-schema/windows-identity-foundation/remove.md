---
title: "&lt;remove&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
caps.latest.revision: 5
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# &lt;remove&gt;
토큰 처리기 컬렉션에서 지정 된 보안 토큰 처리기를 제거합니다.  
  
## 구문  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <remove type=xs:string >  
      </remove>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|type|제거할 토큰 처리기의 CLR 형식 이름입니다.  지정 하는 방법에 대 한 자세한 내용은 `type` 특성, 볼 [Custom Type References](http://msdn.microsoft.com/ko-kr/7286d2e3-c63d-49fd-abdc-ce2705f22c24).  필수 요소.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<securityTokenHandlers\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|끝점을 등록 하는 보안 토큰 처리기의 컬렉션을 지정 합니다.|  
  
## 예제  
 다음 XML 사용을 보여 줍니다.의 `<add>` 및 `<remove>` 요소를 사용자 지정 하는 세션 토큰 처리기가 기본 세션 토큰 처리기를 대체할 수 있습니다.  XML을 가져온 것은 `ClaimsAwareWebFarm` 샘플입니다.  
  
```  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```