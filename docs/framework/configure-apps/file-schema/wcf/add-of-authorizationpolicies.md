---
title: "&lt;authorizationPolicies&gt;의 &lt;add&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 613a03d8-4384-4556-bce2-8c23286c0bb0
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# &lt;authorizationPolicies&gt;의 &lt;add&gt;
클레임 변환에 대한 권한 부여 정책을 지정합니다.  
  
## 구문  
  
```  
  
<authorizationPolicies>  
   <add policyType="String" />  
</authorizationPolicies>  
```  
  
## 형식  
 `Type`  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`policyType`|필수 String 특성입니다.<br /><br /> [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 액세스 제어 모델은 권한 부여 정책 집합을 형식으로 제공할 수 있습니다.  이 특성은 한 입력 클레임 집합을 다른 클레임 집합으로 변환할 수 있도록 하는 권한 부여 정책을 지정합니다.  그에 따라 액세스 제어가 부여되거나 거부됩니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<authorizationPolicies\>](../../../../../docs/framework/configure-apps/file-schema/wcf/authorizationpolicies.md)|권한 부여 정책 형식 컬렉션을 지정합니다.|  
  
## 설명  
 각 인증 정책에는 문자열에 해당하는 단일 필수 `policyType` 특성이 포함되어 있습니다.  이 특성은 한 입력 클레임 집합을 다른 클레임 집합으로 변환할 수 있도록 하는 인증 정책을 지정합니다.  그에 따라 액세스 제어가 부여되거나 거부됩니다.  권한 부여 정책이 작동하는 방법에 대한 자세한 내용은 <xref:System.IdentityModel.Policy.IAuthorizationPolicy> 및 [권한 부여 정책](../../../../../docs/framework/wcf/samples/authorization-policy.md)을 참조하세요.  
  
## 참고 항목  
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>   
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>   
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>   
 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>   
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>   
 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>   
 <xref:System.IdentityModel.Policy.IAuthorizationPolicy>   
 [Authorizing Access to Service Operations](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)   
 [방법: 서비스에 대한 사용자 지정 권한 부여 관리자 만들기](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)   
 [\<add\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-authorizationpolicies.md)   
 [권한 부여 정책](../../../../../docs/framework/wcf/samples/authorization-policy.md)