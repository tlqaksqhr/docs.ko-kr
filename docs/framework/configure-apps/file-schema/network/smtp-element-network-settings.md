---
title: "&lt;smtp&gt; 요소 (네트워크 설정)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp
- http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp
helpviewer_keywords:
- <smtp> element
- smtp element
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 598fe3dc2a49187e923cd689f863d0a3327e735f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltsmtpgt-element-network-settings"></a>&lt;smtp&gt; 요소 (네트워크 설정)
전자 메일 전송을 위한 배달 형식, 배달 방법 및 보낸 사람 주소를 구성합니다.  
  
 \<configuration>  
\<system.net >  
\<mailSettings >  
\<smtp >  
  
## <a name="syntax"></a>구문  
  
```xml  
      <smtp  
        deliveryFormat="format"   
        deliveryMethod="method"   
        from="from address">
          <specifiedPickupDirectory> … </ specifiedPickupDirectory >  
          <network> … </network>  
      </smtp>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`deliveryFormat`|보낼 전자 메일의 배달 형식을 지정합니다. 허용 가능한 값은 SevenBit와 International입니다.|  
|`deliveryMethod`|전자 메일에 대 한 배달 방법을 지정합니다. 허용 되는 값은 네트워크, pickupDirectoryFromIis, 및 specifiedPickupDirectory입니다.|  
|`from`|보낼 전자 메일의 보낸 사람 주소를 지정합니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|특성|설명|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|전송 프로토콜 SMTP (Simple Mail) 서버에 대 한 로컬 디렉터리를 구성합니다.|  
|`network`|외부 SMTP 서버에 대 한 네트워크 옵션을 구성 합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[\<mailSettings> 요소(네트워크 설정)](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|메일 보내기 옵션을 구성 합니다.|  
  
## <a name="example"></a>예  
 다음 예제에서는 기본 네트워크 자격 증명을 사용 하 여 전자 메일을 보낼 적절 한 SMTP 매개 변수를 지정 합니다.  
  
```xml  
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
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpDeliveryFormat>  
 <xref:System.Net.Mail.SmtpDeliveryMethod>  
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
