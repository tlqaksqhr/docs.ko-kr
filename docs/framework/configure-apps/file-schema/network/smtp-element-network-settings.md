---
title: "&lt;smtp&gt; 요소(네트워크 설정) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<smtp> 요소"
  - "smtp 요소"
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# &lt;smtp&gt; 요소(네트워크 설정)
전자 메일 전송을 위한 배달 방법과 보낸 사람 주소를 구성합니다.  
  
## 구문  
  
```  
  
      <smtp  
  deliveryFormat="format"   
  deliveryMethod="method"   
  from="from address"   
  <specifiedPickupDirectory> … </ specifiedPickupDirectory >  
  <network> … </network>  
/smtp>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`deliveryFormat`|보낼 전자 메일의 배달 형식을 지정합니다.  허용 가능한 값은 SevenBit 과 International 입니다.|  
|`deliveryMethod`|전자 메일의 배달 방법을 지정합니다.  가능한 값은 network, pickupDirectoryFromIis 및 specifiedPickupDirectory입니다.|  
|`from`|전자 메일의 보낸 사람 주소를 지정합니다.|  
  
### 자식 요소  
  
|특성|설명|  
|--------|--------|  
|`specifiedPickupDirectory`|SMTP\(Simple Mail Transport Protocol\) 서버의 로컬 디렉터리를 구성합니다.|  
|`network`|외부 SMTP 서버에 대한 네트워크 옵션을 구성합니다.|  
  
### 부모 요소  
  
|**요소**|**설명**|  
|------------|------------|  
|[\<mailSettings\> 요소\(네트워크 설정\)](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|메일 보내기 옵션을 구성합니다.|  
  
## 예제  
 다음 코드 예제에서는 기본 네트워크 자격 증명을 사용하여 전자 메일을 보내도록 적절한 SMTP 매개 변수를 지정합니다.  
  
```  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="network" deliveryFormat="SevenBit"  from="ben@contoso.com">  
        <network  
          host="localhost"  
          port="25"  
          defaultCredentials="true"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## 참고 항목  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=fullName>   
 <xref:System.Net.Mail.SmtpClient?displayProperty=fullName>   
 <xref:System.Net.Mail.SmtpDeliveryFormat>   
 <xref:System.Net.Mail.SmtpDeliveryMethod>   
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)