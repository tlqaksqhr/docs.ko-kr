---
title: "&lt;mailSettings&gt; 요소(네트워크 설정) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<mailSettings> 요소"
  - "mailSettings 요소"
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
caps.latest.revision: 20
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 20
---
# &lt;mailSettings&gt; 요소(네트워크 설정)
메일 보내기 옵션을 구성합니다.  
  
## 구문  
  
```  
  
      <mailSettings  
  <smtp> … </smtp>  
/mailsettings>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|특성|설명|  
|--------|--------|  
|[\<smtp\> 요소\(네트워크 설정\)](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|SMTP\(Simple Mail Transport Protocol\) 옵션을 구성합니다.|  
  
### 부모 요소  
  
|**요소**|**설명**|  
|------------|------------|  
|[\<system.Net\> 요소\(네트워크 설정\)](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|.NET Framework의 네트워크 연결 방법을 지정하는 설정을 포함합니다.|  
  
## 예제  
 다음 코드 예제에서는 기본 네트워크 자격 증명을 사용하여 전자 메일을 보내도록 적절한 SMTP 매개 변수를 지정합니다.  
  
```  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="network">  
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
 <xref:System.Net.Mail.SmtpClient>   
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)