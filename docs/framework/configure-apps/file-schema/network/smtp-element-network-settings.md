---
title: '&lt;smtp&gt; 요소 (네트워크 설정)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp
- http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp
helpviewer_keywords:
- <smtp> element
- smtp element
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 56912e09d24fc83e93a91cc42b1d96dcc68210f2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32741895"
---
# <a name="ltsmtpgt-element-network-settings"></a>&lt;smtp&gt; 요소 (네트워크 설정)
배달 형식, 배달 방법 구성 들어오고 보내는 전자 메일에 대 한 주소입니다.  
  
 \<configuration>  
\<system.net>  
\<mailSettings>  
\<smtp>  
  
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
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`deliveryFormat`|보내는 전자 메일 배달 형식을 지정합니다. 허용 가능한 값은 SevenBit와 International입니다.|  
|`deliveryMethod`|메일에 대 한 배달 방법을 지정합니다. 허용 되는 값은 네트워크, pickupDirectoryFromIis, 및 specifiedPickupDirectory입니다.|  
|`from`|지정 된 보낸 사람 주소를 나가는 전자 메일이 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|특성|설명|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|전송 프로토콜 SMTP (Simple Mail) 서버에 대 한 로컬 디렉터리를 구성합니다.|  
|`network`|외부 SMTP 서버에 대 한 네트워크 옵션을 구성 합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[\<mailSettings> 요소(네트워크 설정)](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|메일 보내기 옵션을 구성 합니다.|  
  
## <a name="example"></a>예제  
 다음 예제에서는 기본 네트워크 자격 증명을 사용 하 여 전자 메일을 보내는 적절 한 SMTP 매개 변수를 지정 합니다.  
  
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
