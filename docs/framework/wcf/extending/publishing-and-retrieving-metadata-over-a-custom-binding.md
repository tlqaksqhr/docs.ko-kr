---
title: 사용자 지정 바인딩을 통해 메타데이터 게시 및 검색
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 904e11b4-d90e-45c6-9ee5-c3472c90008c
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f6226f01a284a9a24593c1be4fed2f96f3eae730
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="publishing-and-retrieving-metadata-over-a-custom-binding"></a>사용자 지정 바인딩을 통해 메타데이터 게시 및 검색
<xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType>에서는 메타데이터 끝점을 서비스에 추가할 수 있도록 지원합니다. 이러한 메타 데이터 끝점에서 URL HTTP GET 요청에 응답할 수는 `?wsdl` querystring 및 Ws-metadataexchange (MEX) 사양에 정의 된 대로 Ws-transfer GET 요청을 합니다. MEX 끝점은 <xref:System.ServiceModel.Description.IMetadataExchange?displayProperty=nameWithType> 계약을 구현합니다.  
  
## <a name="publishing-metadata-over-a-custom-binding"></a>사용자 지정 바인딩을 통해 메타데이터 게시  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A?displayProperty=nameWithType> 또는 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A?displayProperty=nameWithType> 속성을 `true`로 설정하여 HTTP GET 메타데이터 끝점 및 HTTPS GET 메타데이터 끝점을 사용할 수 있습니다. 이러한 끝점에 대한 바인딩은 구성할 수 없습니다.  
  
 그러나 <xref:System.ServiceModel.Description.IMetadataExchange> 끝점이 다른 <xref:System.ServiceModel.Description.IMetadataExchange> 서비스 끝점과 동일하기 때문에 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 계약을 사용자 지정 바인딩을 사용하는 끝점을 비롯하여 모든 끝점과 함께 사용할 수 있습니다. 시스템 제공 바인딩의 구성을 수정하는 방법을 알고 있거나 <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>을 구성하는 방법을 알고 있는 경우 <xref:System.ServiceModel.Description.IMetadataExchange> 끝점에 사용할 바인딩을 구성할 수 있습니다.  
  
## <a name="retrieving-metadata-over-a-custom-binding"></a>사용자 지정 바인딩을 통해 메타데이터 검색  
 표준 HTTP 또는 HTTPS GET 요청을 사용하여 HTTP Get 및 HTTPS Get 메타데이터 끝점에서 메타데이터를 검색할 수 있습니다.  
  
 MEX 메타데이터 끝점에서 메타데이터를 검색하기 위해 일반적으로 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 지원하는 표준 MEX 바인딩 중 하나를 사용할 수 있습니다. 자세한 내용은 <xref:System.ServiceModel.Description.MetadataExchangeBindings?displayProperty=nameWithType>을 참조하세요. <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> 형식 및 Svcutil.exe 도구에서는 지정된 메타데이터 끝점의 주소에 따라 이러한 표준 MEX 바인딩 중 하나를 자동으로 선택합니다.  
  
 MEX 메타데이터 끝점에서 표준 MEX 바인딩과 다른 바인딩을 사용하는 경우 코드를 사용하거나 <xref:System.ServiceModel.Description.MetadataExchangeClient> 클라이언트 끝점 구성을 제공하여 <xref:System.ServiceModel.Description.IMetadataExchange>에서 사용하는 바인딩을 구성할 수 있습니다. Svcutil.exe 도구는 메타데이터 끝점 주소의 URI 스키마와 이름이 같은 <xref:System.ServiceModel.Description.IMetadataExchange> 클라이언트 끝점 구성을 구성 파일에서 자동으로 로드합니다.  
  
## <a name="security"></a>보안  
 사용자 지정 바인딩을 통해 메타데이터를 게시하는 경우 바인딩에서 메타데이터가 필요로 하는 보안 지원을 제공하는지 확인합니다. 예를 들어, 정보 공개를 방지하고 클라이언트에 메타데이터를 가져올 권한이 있는지 확인하려면 인증 및 암호화가 필요한 <xref:System.ServiceModel.Description.IMetadataExchange> 끝점을 구성하여 메타데이터 및 응용 프로그램의 보안을 더욱 향상시킬 수 있습니다. 샘플 [메타 데이터 끝점을 보호 하는 사용자 지정](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) 이 시나리오를 보여 줍니다.  
  
## <a name="see-also"></a>참고 항목  
 [서비스에 보안 설정](../../../../docs/framework/wcf/securing-services.md)  
 [WS-MetadataExchange 바인딩](../../../../docs/framework/wcf/extending/ws-metadataexchange-bindings.md)  
 [방법: 사용자 지정 WS-Metadata Exchange 바인딩 구성](../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)  
 [방법: MEX가 아닌 바인딩을 통해 메타데이터 검색](../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)
