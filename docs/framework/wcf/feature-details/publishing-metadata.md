---
title: "메타데이터 게시"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- meatadata [WCF], publishing
ms.assetid: 3a56831a-cabc-45c0-bd02-12e2e9bd7313
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 86d9eb8e7e7c78f091deea55322cbef6e6d0f3c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="publishing-metadata"></a>메타데이터 게시
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스는 하나 이상의 메타데이터 끝점을 게시하여 메타데이터를 게시합니다. 서비스 메타데이터를 게시하면 WS-MetadataExchange(MEX) 및 HTTP/GET 요청과 같이 표준화된 프로토콜을 통해 메타데이터를 사용할 수 있습니다. 메타데이터 끝점은 주소, 바인딩 및 계약에 포함된 다른 서비스 끝점과 유사하며 구성 또는 명령 코드를 통해 서비스 호스트에 추가할 수 있습니다.  
  
## <a name="publishing-metadata-endpoints"></a>메타데이터 끝점 게시  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스의 메타데이터 끝점을 게시하려면 먼저 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 서비스 동작을 해당 서비스에 추가해야 합니다. <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> 인스턴스를 추가하면 서비스가 메타데이터 끝점을 노출할 수 있습니다. <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> 서비스 동작을 추가하면 MEX 프로토콜을 지원하거나 HTTP/GET 요청에 응답하는 메타데이터 끝점을 노출할 수 있습니다.  
  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType>는 <xref:System.ServiceModel.Description.WsdlExporter>를 사용하여 서비스의 모든 서비스 끝점에 대한 메타데이터를 내보냅니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]참조는 서비스에서 메타 데이터 내보내기 [내보내기 및 가져오기는 메타 데이터](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md)합니다.  
  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType>  A <xref:System.ServiceModel.Description.ServiceMetadataExtension> 인스턴스를 서비스 호스트에 대한 확장으로 추가합니다. <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType>은 메타데이터 게시 프로토콜에 대한 구현을 제공합니다. 또한 <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType>을 통해 <xref:System.ServiceModel.Description.ServiceMetadataExtension.Metadata%2A?displayProperty=nameWithType> 속성에 액세스하여 서비스 메타데이터를 런타임에 가져올 수 있습니다.  
  
### <a name="mex-metadata-endpoints"></a>MEX 메타데이터 끝점  
 MEX 프로토콜을 사용하는 메타데이터 끝점을 추가하려면 `IMetadataExchange` 서비스 계약을 사용하는 서비스 호스트에 서비스 끝점을 추가하십시오. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에는 <xref:System.ServiceModel.Description.IMetadataExchange> 프로그래밍 모델의 일부로 사용할 수 있는 이 서비스 계약 이름을 가진 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 인터페이스가 포함되어 있습니다. WS-MetadataExchange 끝점 또는 MEX 끝점은 <xref:System.ServiceModel.Description.MetadataExchangeBindings> 클래스에서 정적 팩터리 메서드가 노출하는 4개의 기본 바인딩 중 하나를 사용하여 Svcutil.exe와 같이 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 도구에서 사용하는 기본 바인딩과 일치시킬 수 있습니다. 또한 사용자 지정 바인딩을 사용하여 MEX 메타데이터 끝점을 구성할 수도 있습니다.  
  
### <a name="http-get-metadata-endpoints"></a>HTTP GET 메타데이터 끝점  
 HTTP/GET 요청에 응답하는 서비스에 메타데이터 끝점을 추가하려면 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A>의 <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> 속성을 `true`로 설정합니다. 또한 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A>의 <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> 속성을 `true`로 설정하여 HTTPS를 사용하는 메타데이터 끝점을 구성할 수도 있습니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [방법: 구성 파일을 사용하여 서비스의 메타데이터 게시](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스가 메타데이터를 게시하여 클라이언트가 WS-MetadataExchange를 사용하는 메타데이터 또는 `?wsdl` 쿼리 문자열을 사용하는 HTTP/GET 요청을 검색할 수 있도록 구성하는 방법을 보여 줍니다.  
  
 [방법: 코드를 사용하여 서비스에 대한 메타데이터 게시](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 클라이언트가 WS-MetadataExchange를 사용하는 메타데이터 또는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 쿼리 문자열을 사용하는 HTTP/GET 요청을 검색할 수 있도록 메타데이터가 코드에서 `?wsdl` 서비스를 게시할 수 있는 방법을 보여 줍니다.  
  
## <a name="reference"></a>참조  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>  
  
 <xref:System.ServiceModel.Description.IMetadataExchange>  
  
 <xref:System.ServiceModel.Description.ServiceMetadataExtension>  
  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings>  
  
## <a name="see-also"></a>참고 항목  
 [메타데이터 내보내기 및 가져오기](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md)
