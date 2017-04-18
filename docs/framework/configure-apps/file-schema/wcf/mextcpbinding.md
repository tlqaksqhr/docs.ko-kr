---
title: "&lt;mexTcpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 01baba8d-d784-4255-9ea2-7afff1482bf0
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# &lt;mexTcpBinding&gt;
TCP를 통한 WS\-MEX\(WS\-MetadataExchange\) 메시지 교환에 사용되는 바인딩의 설정을 지정합니다.  
  
## 구문  
  
```  
  
<mexTcpBinding>  
   <binding   
       closeTimeout="TimeSpan"   
       name="string"   
       openTimeout="TimeSpan"   
       receiveTimeout="TimeSpan"  
       sendTimeout="TimeSpan">  
   </binding>  
</mexTcpBinding>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`closeTimeout`|닫기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.  이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.  기본값은 00:01:00입니다.|  
|`name`|바인딩의 구성 이름을 포함하는 문자열입니다.  이 값은 바인딩의 ID로 사용되므로 고유해야 합니다.  각 바인딩에는 서비스의 메타데이터에서 함께 바인딩을 고유하게 식별하는 `name` 및 `namespace` 특성이 있습니다.  또한 이 이름은 동일한 형식의 바인딩 간에 고유합니다.  [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다.  기본 구성 및 이름 없는 바인딩 및 동작에 대한 자세한 내용은 [단순화된 구성](../../../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스를 위한 단순화된 구성](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)을 참조하세요.|  
|`openTimeout`|열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.  이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.  기본값은 00:01:00입니다.|  
|`receiveTimeout`|받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.  이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.  기본값은 00:10:00입니다.|  
|`sendTimeout`|보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.  이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.  기본값은 00:01:00입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<bindings\>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.Configuration.MexTcpBindingElement>   
 <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexTcpBinding%2A>   
 [방법: 구성 파일을 사용하여 서비스의 메타데이터 게시](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)   
 [사용자 지정 바인딩을 통해 메타데이터 게시 및 검색](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)   
 [메타데이터](../../../../../docs/framework/wcf/feature-details/metadata.md)   
 [바인딩](../../../../../docs/framework/wcf/bindings.md)   
 [시스템 제공 바인딩 구성](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/ko-kr/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<binding\>](../../../../../docs/framework/misc/binding.md)