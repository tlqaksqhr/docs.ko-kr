---
title: "&lt;comContracts&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 42e74148-223d-4888-a8ed-1d928527eb09
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# &lt;comContracts&gt;
`comContracts` 구성 섹션에는 COM\+ 통합 서비스 계약의 다양한 속성을 지정할 수 있게 해 주는 요소가 포함되어 있습니다.  
  
## 네임스페이스 및 계약 지정  
 COM\+ 통합 서비스 계약은 현재 "http:\/\/tempuri.org" 네임스페이스로 제한되며, 계약 이름은 지원 COM 인터페이스에서 파생됩니다.  그러나 구성 파일에서 `comContracts` 섹션을 사용하여 대안을 지정할 수 있습니다.  
  
 예를 들어 다음 구성을 사용하여 서비스 계약의 네임스페이스 및 계약 이름과 세션 바인딩에 사용법을 적용할 옵션을 지정할 수 있습니다.  
  
```  
<comContracts>  
  <comContract  
      contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"  
      namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"  
      name="_Broker"  
      requireSession="true">  
  </comContract>  
</comContracts>  
```  
  
 지정된 네임스페이스와 계약 이름은 서비스가 초기화될 때 생성된 서비스 설명에 적용됩니다.  
  
 이 섹션이 비어 있으면 서비스 초기화에서는 지원 COM 인터페이스 ID에서 가져온 기본 네임스페이스 및 계약 이름을 적용합니다.  
  
 [\<exposedMethod\>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) 요소를 사용하여 COM\+ 구성 요소의 인터페이스가 웹 서비스로 공개되는 경우 노출되는 COM\+ 메서드를 지정할 수도 있습니다.  또한 [\<persistableTypes\>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)을 사용하여 통합에 사용되는 지속 형식을 지정할 수 있습니다.  마지막으로 [\<userDefinedType\>](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md) 요소를 사용하여 서비스 계약에 포함되는 UDT\(사용자 정의 형식\)를 포함할 수 있습니다.  
  
## 참고 항목  
 <xref:System.ServiceModel.Configuration.ComContractElementCollection>   
 <xref:System.ServiceModel.Configuration.ComContractElement>   
 [\<exposedMethod\>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md)   
 [\<persistableTypes\>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)   
 [\<userDefinedType\>](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md)   
 [\<comContract\>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontract.md)   
 [COM\+ 응용 프로그램과 통합](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)   
 [방법: COM\+ 서비스 설정 구성](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)