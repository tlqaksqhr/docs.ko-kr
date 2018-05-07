---
title: '방법: 프로브 요청의 검색 버전 확인'
ms.date: 03/30/2017
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
ms.openlocfilehash: 8ac9804b0fe46ca5fbe580d713ec82a2f9bb0128
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a>방법: 프로브 요청의 검색 버전 확인
검색 프록시는 여러 검색 버전을 사용하여 검색 끝점을 노출할 수 있습니다. UDP 멀티캐스트 프로브 요청이 프록시에 도달하면 프록시는 멀티캐스트 비표시 오류(Suppression) 메시지로 응답해야 합니다. 이렇게 응답하려면 요청의 검색 버전을 알아야 합니다.  
  
### <a name="to-determine-the-discovery-version-of-a-probe-request"></a>프로브 요청의 검색 버전을 확인하려면  
  
1.  프로브 요청(예: <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A>)에 응답하는 메서드에서 다음 코드와 같이 정적 <xref:System.ServiceModel.OperationContext.Current%2A> 속성을 사용하여 <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension>을 검색합니다.  
  
    ```  
    DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();  
    // Access the discovery version from the DiscoveryOperationContextExtension  
    doce.DiscoveryVersion;  
    ```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>  
 [검색 프록시 구현](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)  
 [검색 프록시 샘플](../../../../docs/framework/wcf/samples/discovery-proxy-sample.md)
