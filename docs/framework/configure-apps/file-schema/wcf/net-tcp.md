---
title: '&lt;net.tcp&gt;'
ms.date: 03/30/2017
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
ms.openlocfilehash: 9e44ddcc3a3e983abe6e36d4b6095c5c4a67529f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="ltnettcpgt"></a>&lt;net.tcp&gt;
여러 프로세스에서 동일한 TCP 포트를 공유할 수 있도록 하는 NET.TCP Port Sharing Service에 대한 구성 설정을 지정합니다.  
  
 \<system.serviceModel.activation>  
\<net.tcp>  
  
## <a name="syntax"></a>구문  
  
```xml  
<configuration>  
   <system.serviceModel.activation>  
       <net.tcp listenBacklog="Integer"  
          maxPendingAccepts="Integer"  
          maxPendingConnections="Integer"  
          receiveTimeout="TimeSpan"  
          teredoEnabled="Boolean">  
          <allowAccounts>  
             <!-- LocalSystem account -->   
             <add securityIdentifier="S-1-5-18"/>  
             <!-- LocalService account -->   
             <add securityIdentifier="S-1-5-19"/>  
             <!-- Administrators account -->   
             <add securityIdentifier="S-1-5-20"/>  
             <!-- Network Service account -->   
             <add securityIdentifier="S-1-5-32-544" />  
             <!-- IIS_IUSRS account (Vista only)-->   
             <add securityIdentifier="S-1-5-32-568"/>  
           </allowAccounts>  
       </net.tcp>  
   </system.serviceModel.activation>  
</configuration>  
```  
  
## <a name="type"></a>형식  
 `Type`  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`listenBacklog`|공유 연결 로부터 허용 되는 Windows Communication Foundation (WCF) 서비스 아직 디스패치되는 활성 연결의 최대를 지정 하는 정수입니다. 기본값은 10입니다.|  
|`maxPendingAccepts`|공유 서비스에 대한 수신 끝점에서 동시에 수용할 수 있는 활성 스레드의 최대 수를 지정하는 정수입니다. 기본값은 2입니다.|  
|`MaxPendingConnections`|응용 프로그램에서 수락할 때까지 수신기에서 기다릴 수 있는 최대 연결 수입니다. 이 할당량 값을 초과하면 새 들어 오는 연결은 수락될 때까지 기다리지 않고 연결이 끊깁니다. 메시지 보안과 같은 연결 기능을 통해 클라이언트가 둘 이상의 연결을 열 수 있습니다. 서비스 관리자는 이 할당량 값을 설정할 때 이러한 추가 연결을 고려해야 합니다. 기본값은 10입니다.|  
|`receiveTimeout`|프레이밍 데이터를 읽고 내부 연결에서 연결 디스패치를 수행하는 데 대한 제한 시간을 지정하는 `TimeSpan`입니다. 기본값은 "00:00:10"입니다.|  
|`teredoEnabled`|포트 공유 서비스가 WCF 서비스를 대신 하 여 TCP 포트에서 수신 하도록 Microsoft Teredo 서비스를 사용 하는지 여부를 나타내는 부울 값입니다. 기본값은 `false`입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<allowAccounts>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|포함 하는 구성 요소의 컬렉션을 `securityIdentifier` 는 WCF 서비스를 호스팅하고 공유 서비스에 대 한 연결 액세스가 부여 된 프로세스에 대 한 사용자 계정을 지정 하는 특성입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|수신기 프로세스 SMSvcHost.exe에 대한 구성 설정을 포함합니다.|  
  
## <a name="remarks"></a>설명  
 포트 공유에 대 한 자세한 내용은 참조 하십시오. [Net.TCP 포트 공유](http://msdn.microsoft.com/library/f13692ee-a179-4439-ae72-50db9534eded)합니다. 포트 공유 서비스를 구성 하는 방법을 알아보려면 참조 [Net.TCP Port Sharing Service 구성](http://msdn.microsoft.com/library/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>  
 [Net.TCP 포트 공유](http://msdn.microsoft.com/library/f13692ee-a179-4439-ae72-50db9534eded)  
 [Net.TCP Port Sharing Service 구성](http://msdn.microsoft.com/library/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0)
