---
title: "&lt;issuerTokenResolver&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
caps.latest.revision: 9
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# &lt;issuerTokenResolver&gt;
사용 하 여 컬렉션에 있는 토큰 처리기 처리기 발급자 토큰 확인자를 등록 합니다.  토큰 확인 자가 발급자는 들어오는 토큰 및 메시지 서명 토큰을 확인 하는 데 사용 됩니다.  
  
## 구문  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerTokenResolver type=xs:string>  
        </issuerTokenResolver>  
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
|type|확인자 토큰 발급자의 종류를 지정합니다.  여야는 <xref:System.IdentityModel.Tokens.IssuerTokenResolver> 클래스나 형식에서 파생 되는 <xref:System.IdentityModel.Tokens.IssuerTokenResolver> 클래스입니다.  지정 하는 방법에 대 한 자세한 내용은 `type` 특성, 볼 [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_CustomTypeReferences).  필수 요소.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|구성 컬렉션의 보안 토큰 처리기를 제공합니다.|  
  
## 설명  
 토큰 확인 자가 발급자는 들어오는 토큰 및 메시지 서명 토큰을 확인 하는 데 사용 됩니다.  서명을 확인 하는 데 사용 되는 암호화 자료를 검색할 수 있습니다.  지정 해야는 `type` 특성.  형식을 지정할 수 있습니다 <xref:System.IdentityModel.Tokens.IssuerTokenResolver> 또는 사용자 지정 형식에서 파생 되는 <xref:System.IdentityModel.Tokens.IssuerTokenResolver> 클래스입니다.  
  
 일부 토큰 처리기 발급자 토큰 확인자 설정 구성을 지정할 수 있습니다.  보안 토큰 처리기 컬렉션에서 지정 된 설정을 개별 토큰 처리기를 재정의합니다.  
  
> [!NOTE]
>  지정 하는 `<issuerTokenResolver>` 의 자식 요소로 요소는 [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소가 되지 않습니다, 있지만 이전 버전과 호환성을 위해 여전히 지원 됩니다.  설정에는 `<securityTokenHandlerConfiguration>` 요소의 대체에 `<identityConfiguration>` 요소입니다.  
  
## 예제  
 다음 XML에서 파생 되는 사용자 지정 클래스를 기반으로 하는 발급자 토큰 확인자 구성을 보여 줍니다. <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.  확인자 토큰에서 사용자 지정 구성 요소를 초기화 하는 청중 키 쌍의 사전을 유지 \(`<AddAudienceKeyPair>`\)에 대 한 클래스를 정의 합니다.  클래스 재정의 <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> 이 요소를 처리 하는 메서드.  재정의 다음 예제에 표시 됩니다. 그러나 호출 하는 메서드는 간단히 표시 되지 않습니다.  전체 예제를 보려면를 참조는 `CustomToken` 샘플입니다.  
  
```  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## 예제  
  
```  
public override void LoadCustomConfiguration(System.Xml.XmlNodeList nodelist)  
{  
    foreach (XmlNode node in nodelist)  
    {  
        XmlDictionaryReader rdr = XmlDictionaryReader.CreateDictionaryReader(new XmlTextReader(new StringReader(node.OuterXml)));  
        rdr.MoveToContent();  
  
        string symmetricKey = rdr.GetAttribute("symmetricKey");  
        string audience = rdr.GetAttribute("audience");  
  
        this.AddAudienceKeyPair(audience, symmetricKey);  
    }  
}  
```  
  
## 참고 항목  
 <xref:System.IdentityModel.Tokens.IssuerTokenResolver>