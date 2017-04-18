---
title: "&lt;serviceTokenResolver&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# &lt;serviceTokenResolver&gt;
토큰 처리기 컬렉션에 대 한 처리기에서 사용 되는 서비스 토큰 확인자를 등록 합니다.  토큰 확인자 서비스는 들어오는 토큰 및 메시지 암호화 토큰을 확인 하는 데 사용 됩니다.  
  
## 구문  
  
```  
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
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|type|토큰 확인자 서비스의 형식을 지정합니다.  두는 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> 형식 또는 파생 형식에 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> 클래스.  지정 하는 방법에 대 한 자세한 내용은 `type` 특성, 볼 [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_CustomTypeReferences).  필수 요소.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|구성 컬렉션의 보안 토큰 처리기를 제공합니다.|  
  
## 설명  
 토큰 확인 자가 서비스 암호화 토큰에 들어오는 토큰 및 메시지를 해결 하려면 사용할 수 있습니다.  들어오는 토큰을 해독 하는 데 사용할 키를 검색할 수 있습니다.  지정 해야는 `type` 특성.  형식을 지정할 수 있습니다 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> 또는 사용자 지정 형식에서 파생 되는 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> 클래스입니다.  
  
 일부 토큰 처리기 서비스 토큰 확인자 설정 구성을 지정할 수 있습니다.  보안 토큰 처리기 컬렉션에서 지정 된 설정을 개별 토큰 처리기를 재정의합니다.  
  
> [!NOTE]
>  지정 하는 `<serviceTokenResolver>` 의 자식 요소로 요소는 [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소가 되지 않습니다, 있지만 이전 버전과 호환성을 위해 여전히 지원 됩니다.  설정에는 `<securityTokenHandlerConfiguration>` 요소의 대체에 `<identityConfiguration>` 요소입니다.  
  
## 예제  
  
```  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```