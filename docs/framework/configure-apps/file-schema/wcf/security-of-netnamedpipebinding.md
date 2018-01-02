---
title: "&lt;netNamedPipeBinding&gt;의 &lt;security&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
caps.latest.revision: "11"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: fb5d1d3a767a9f4034473baad271c40677cedca5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltsecuritygt-of-ltnetnamedpipebindinggt"></a>&lt;netNamedPipeBinding&gt;의 &lt;security&gt;
바인딩에 대한 보안 설정을 정의합니다.  
  
 \<시스템입니다. ServiceModel >  
\<바인딩 >  
\<netNamedPipeBinding >  
\<바인딩 >  
\<보안 >  
  
## <a name="syntax"></a>구문  
  
```xml  
<netNamedPipeBinding>  
      <binding>  
            <security mode="None/Transport">  
                        <transport protectionLevel="None/Sign/EncryptAndSign" />  
            </security>  
      </binding>  
</netNamedPipeBinding>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|모드|이 바인딩에 적용되는 보안 형식을 지정합니다. 유효한 값은 다음과 같습니다.<br /><br /> -None: 보안이 해제 합니다.<br />-전송: 보안이 기본 전송 기반 보안을 사용 하 여 제공 됩니다. 이 모드에서는 보호 수준을 제어할 수 있습니다.<br />-기본값은 Transport입니다. 이 특성은 <xref:System.ServiceModel.NetNamedPipeSecurityMode> 형식입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|transport|전송의 보안 설정을 정의합니다. 이 요소는 <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement> 형식입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|바인딩|바인딩 요소는 [ \<netNamedPipeBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md)합니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.NetNamedPipeSecurity>  
 <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>  
 [서비스 및 클라이언트에 보안 설정](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [자격 증명 형식 선택](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [바인딩](../../../../../docs/framework/wcf/bindings.md)  
 [시스템 제공 바인딩 구성](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<바인딩 >](../../../../../docs/framework/misc/binding.md)
