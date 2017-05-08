---
title: "&lt;claimTypeRequired&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
caps.latest.revision: 5
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# &lt;claimTypeRequired&gt;
들어오는 보안 토큰에 대 한 필요한 클레임 집합을 지정합니다.  
  
## 구문  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<claimType\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtype.md)|들어오는 보안 토큰에 대 한 하나의 선택적 또는 필수 클레임을 지정합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|서비스 수준 id 설정을 지정합니다.|