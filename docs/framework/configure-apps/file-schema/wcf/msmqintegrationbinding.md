---
title: "&lt;msmqIntegrationBinding&gt;&lt;/msmqIntegrationBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "msmqIntegrationBinding 요소"
ms.assetid: edf277f3-e3bf-4ed8-9f55-83b5788430a7
caps.latest.revision: 34
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 34
---
# &lt;msmqIntegrationBinding&gt;&lt;/msmqIntegrationBinding&gt;
MSMQ를 통해 메시지를 라우팅하여 큐 지원을 제공하는 바인딩을 정의합니다.  
  
 \<system.ServiceModel>  
<>\>  
msmqIntegrationBinding  
  
## <a name="syntax"></a>구문  
  
```  
  
<msmqIntegrationBinding>  
   <binding   
       closeTimeout="TimeSpan"   
       customDeadLetterQueue="Uri"  
       deadLetterQueue="Uri"  
       durable="Boolean"  
       exactlyOnce="Boolean"   
       maxReceivedMessageSize"Integer"  
       maxRetryCycles="Integer"   
       name="string"   
       openTimeout="TimeSpan"        receiveContextEnabled=”Boolean”  
       receiveErrorHandling="Drop/Fault/Move/Reject"  
       receiveTimeout="TimeSpan"   
       receiveRetryCount="Integer"  
       retryCycleDelay="TimeSpan"    
       sendTimeout="TimeSpan"   
       serializationFormat="XML/Binary/ActiveX/ByteArray/Stream">  
       timeToLive="TimeSpan"    
       useMsmqTracing="Boolean  
       useSourceJournal="Boolean"  
   </binding>  
</msmqIntegrationBinding>   
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|closeTimeout|A <xref:System.TimeSpan> 닫기 작업을 완료에 대 한 제공 되는 시간 간격을 지정 하는 값입니다. 이 값 보다 크거나 같은 해야 <xref:System.TimeSpan.Zero>합니다. 기본값은 00:01:00입니다.|  
|customDeadLetterQueue|응용 프로그램별 배달 못 한 편지 큐의 위치를 포함하는 URI입니다. 이 큐에는 만료되었거나 전송 또는 배달하지 못한 메시지가 보관됩니다.<br /><br /> 배달 못 한 편지 큐는 송신 응용 프로그램의 큐 관리자에서 관리하는 큐로, 배달하지 못한 만료된 메시지가 보관됩니다.<br /><br /> 지정 된 URI <xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A> net.msmq 체계를 사용 해야 합니다.|  
|deadLetterQueue|A <xref:System.ServiceModel.MsmqBindingBase.DeadLetterQueue%2A>있는 경우 사용할 배달 못 한 편지 큐의 형식을 지정 하는 값입니다<br /><br /> 배달 못 한 편지 큐는 응용 프로그램에 배달하지 못한 메시지가 전송되는 위치입니다.<br /><br /> exactlyOnce 보증이 필요한 즉, `exactlyOnce` 특성이 `true`로 설정된 메시지의 경우 이 특성의 기본값은 MSMQ에서 시스템 차원의 배달 못 한 트랜잭션 큐로 설정됩니다.<br /><br /> 보증이 필요하지 않은 메시지의 경우 이 특성은 기본적으로 `null`로 설정됩니다.|  
|durable|큐의 메시지가 지속적인지 또는 일시적인지를 나타내는 부울 값입니다. 지속적 메시지는 큐 관리자가 중단되더라도 남아 있지만, 일시적 메시지는 손실됩니다. 응용 프로그램에서 더 낮은 대기 시간을 요구하며 어느 정도의 메시지 손실을 허용할 수 있다면 일시적 메시지가 유용합니다. `exactlyOnce` 특성을 `true`로 설정하면 메시지는 지속적이어야 합니다. 기본값은 `true`입니다.|  
|exactlyOnce|각 메시지가 한 번만 배달되는지 여부를 나타내는 부울 값입니다. 배달이 실패하면 발신자는 알림을 받습니다. `durable`이 `false`이면 이 특성은 무시되고 배달 보증 없이 메시지가 전송됩니다. 기본값은 `true`입니다. 자세한 내용은 참조 <xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A>합니다.|  
|maxReceivedMessageSize|이 바인딩에 의해 처리되는 최대 메시지 크기(헤더 포함)(바이트)를 정의하는 양의 정수입니다. 이 한도를 초과하는 메시지를 보낸 사람은 SOAP 오류를 받습니다. 수신자는 메시지를 삭제하고 추적 로그에 이벤트 항목을 만듭니다. 기본값은 65536입니다. 이 메시지 크기 제한은 DoS(서비스 거부) 공격에 대한 노출을 막기 위한 것입니다.|  
|maxRetryCycles|포이즌 메시지 검색 기능에 사용되는 재시도 주기 수를 나타내는 정수입니다. 모든 주기의 모든 배달 시도가 실패할 경우 메시지는 포이즌 메시지가 됩니다. 기본값은 2입니다. 자세한 내용은 참조 <xref:System.ServiceModel.MsmqBindingBase.MaxRetryCycles%2A>합니다.|  
|name|바인딩의 구성 이름을 포함하는 문자열입니다. 이 값은 바인딩의 ID로 사용되므로 고유해야 합니다. [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다. 기본 구성 및 이름 없는 바인딩 및 동작에 대 한 자세한 내용은 참조 [단순화 된 구성](../../../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스를 위한 단순화 된 구성](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.|  
|openTimeout|A <xref:System.TimeSpan> 열기 작업을 완료에 대해 제공 되는 시간 간격을 지정 하는 값입니다. 이 값 보다 크거나 같은 해야 <xref:System.TimeSpan.Zero>합니다. 기본값은 00:01:00입니다.|  
|receiveErrorHandling|A <xref:System.ServiceModel.ReceiveErrorHandling> 포이즌 메시지 및 디스패치할 수 메시지의 처리 방법을 지정 하는 값입니다.|  
|receiveRetryCount|응용 프로그램 큐에서 응용 프로그램으로의 메시지 전송이 실패할 경우 큐 관리자가 수행해야 하는 최대 즉시 재시도 횟수를 지정하는 정수입니다.<br /><br /> 최대 배달 시도 횟수에 도달했으나 응용 프로그램에서 메시지에 액세스하지 못한 경우 해당 메시지는 나중에 다시 배달하기 위해 재시도 큐로 보내집니다. 메시지가 전송 큐로 다시 돌아갈 때까지 걸리는 시간은 `retryCycleDelay`를 사용하여 제어합니다. 재시도 주기가 `maxRetryCycles` 값에 도달하면 해당 메시지가 포이즌 메시지 큐로 보내지거나 발신자에게 부정 승인이 다시 보내집니다.|  
|receiveTimeout|A <xref:System.TimeSpan> 수신 작업 완료 하기 위해 제공 되는 시간 간격을 지정 하는 값입니다. 이 값 보다 크거나 같은 해야 <xref:System.TimeSpan.Zero>합니다. 기본값은 00:10:00입니다.|  
|receiveContextEnabled|큐에서 메시지 처리를 위한 수신 컨텍스트를 사용하는지 여부를 지정하는 부울입니다. 이 값이 `true`로 설정되면 서비스가 큐에서 메시지를 "피킹"하여 처리를 시작할 수 있으며 오류가 발생하여 예외가 throw되면 큐에 메시지가 유지됩니다. 서비스에서 나중에 다시 처리하기 위해 메시지를 "잠글" 수도 있습니다. ReceiveContext를 "완료" 메시지가 처리 된 큐에서 제거할 수 있는 메커니즘을 제공 합니다. 메시지는 더 이상 읽고 큐에 다시 쓰지 네트워크를 통해 않으며 개별 메시지 처리 중 다른 서비스 인스턴스 간에 반송 되지 않습니다.|  
|retryCycleDelay|전달하지 못한 메시지를 즉시 다시 전달하려고 시도할 때 재시도 주기 사이의 지연 시간을 지정하는 TimeSpan 값입니다. 실제 대기 시간이 더 길 수 있으므로 이 값은 최소 대기 시간만 정의합니다. 기본값은 00:30:00입니다. 자세한 내용은 참조 <xref:System.ServiceModel.MsmqBindingBase.RetryCycleDelay%2A>합니다.|  
|sendTimeout|A <xref:System.TimeSpan> 보내기 작업을 완료에 대 한 제공 되는 시간 간격을 지정 하는 값입니다. 이 값 보다 크거나 같은 해야 <xref:System.TimeSpan.Zero>합니다. 기본값은 00:01:00입니다.|  
|serializationFormat|메시지 본문의 serialization에 사용되는 형식을 정의합니다. 이 특성은 형식의 <xref:System.ServiceModel.MsmqIntegration.MsmqMessageSerializationFormat>합니다.|  
|timeToLive|메시지가 만료되어 배달 못 한 큐에 추가되기 전에 메시지가 유효한 기간을 지정하는 TimeSpan 값입니다. 기본값은 1.00:00:00입니다.<br /><br /> 이 특성은 시간을 다투는 메시지가 수신 응용 프로그램에서 처리되기 전에 무효화되지 않도록 하기 위해 설정됩니다. 지정된 시간 간격 내에 수신 응용 프로그램에서 사용하지 않은 큐의 메시지는 만료된 것으로 간주됩니다. 만료된 메시지는 배달 못한 편지 큐라는 특수 큐로 보내집니다. 배달 못 한 편지 큐의 위치는 보증에 따라 `DeadLetterQueue` 특성으로 설정되거나 해당 기본값으로 설정됩니다.|  
|useMsmqTracing|이 바인딩이 처리하는 메시지를 추적할지 여부를 지정하는 부울 값입니다. 기본값은 `false`입니다. 추적 기능을 사용하면 메시지가 메시지 큐 컴퓨터에 들어가거나 나올 때마다 보고서 메시지가 만들어진 후 보고서 큐로 보내집니다.|  
|useSourceJournal|이 바인딩에서 처리하는 메시지의 복사본을 소스 업무 일지에 저장할지 여부를 지정하는 부울 값입니다. 기본값은 `false`입니다.<br /><br /> 대기 중 응용 프로그램에서 컴퓨터의 나가는 큐를 떠난 메시지의 레코드를 보존해야 할 경우 메시지를 업무 일지 큐에 복사할 수 있습니다. 메시지가 보내는 큐를 떠난 후 대상 컴퓨터에 수신되었다는 승인을 받으면 해당 메시지의 복사본이 보낸 컴퓨터의 시스템 업무 일지 큐에 보관됩니다.|  
  
## <a name="serializationformat-attribute"></a>{serializationFormat} 특성  
  
|값|설명|  
|-----------|-----------------|  
|Xml|XML 형식|  
|이항|이진 형식|  
|ActiveX|ActiveX 형식|  
|ByteArray|개체를 바이트 배열로 serialize합니다.|  
|스트림|스트림 형식의 본문|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[<>\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-msmqintegrationbinding.md)|바인딩에 대한 보안 설정을 정의합니다. 이 요소는 형식의 <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[<>\>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.|  
  
## <a name="remarks"></a>설명  
 이 바인딩 요소는 Windows Communication Foundation (WCF) 응용 프로그램이 메시지를 보내고, COM, MSMQ 네이티브 Api 또는에 정의 된 형식을 사용 하는 기존 MSMQ 응용 프로그램에서 메시지를 받을 수 있도록 데 사용할 수는 <xref:System.Messaging?displayProperty=fullName> 네임 스페이스 주소 큐 하는 방법, 전송 보증, 메시지 해야 영구 저장 여부, 및 메시지를 보호 및 인증 방법을 지정 하려면이 구성 요소를 사용할 수 있습니다. 자세한 내용은 참조 [하는 방법: WCF 끝점 및 메시지 큐 응용 프로그램과 메시지를 교환](../../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)합니다.  
  
## <a name="example"></a>예제  
  
```  
<configuration>  
<system.ServiceModel>  
    <bindings>  
       <msmqIntegrationBinding>  
           <binding   
                    closeTimeout="00:00:10"   
                    openTimeout="00:00:20"   
                    receiveTimeout="00:00:30"   
                    sendTimeout="00:00:40"   
                    deadLetterQueue="net.msmq://localhost/blah"   
                    durable="true"   
                    exactlyOnce="true"   
                    maxReceivedMessageSize="1000"   
                    maxImmediateRetries="11"   
                    maxRetryCycles="12"  
                    poisonMessageHandling="Disabled"   
                    rejectAfterLastRetry="false"   
                    retryCycleDelay="00:05:55"   
                    timeToLive="00:11:11"   
                    useSourceJournal="true"   
                    useMsmqTracing="true"   
                    serializationFormat="Binary">  
                    <security mode="None" />  
           </binding>  
       </msmqIntegrationBinding  
   </bindings>  
</system.ServiceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement>   
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>   
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>   
 [<>\>](../../../../../docs/framework/misc/binding.md)   
 [바인딩](../../../../../docs/framework/wcf/bindings.md)   
 [시스템 제공 바인딩 구성](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성](http://msdn.microsoft.com/ko-kr/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [WCF의 큐](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)