---
title: "메타데이터 끝점 게시"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 29cd8a60-dfb7-460c-bf5a-c2b31b782671
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 64032fbc675e30e9f01a5db4d56ecc36574e08de
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="publishing-metadata-endpoints"></a>메타데이터 끝점 게시
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 서비스는 하나 이상의 메타데이터 끝점을 게시하여 메타데이터를 게시합니다. 서비스 메타데이터를 게시하면 WS-MetadataExchange(MEX) 및 HTTP/GET 요청과 같이 표준화된 프로토콜을 통해 메타데이터를 사용할 수 있습니다. 메타데이터 끝점은 주소, 바인딩 및 계약에 포함된 다른 서비스 끝점과 유사하며 구성 또는 코드를 통해 서비스 호스트에 추가할 수 있습니다. 메타데이터 끝점 게시를 사용하도록 설정하려면 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 서비스 동작을 서비스에 추가해야 합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [방법: 구성 파일을 사용 하 여 서비스에 대 한 메타 데이터를 게시 합니다.](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스가 메타데이터를 게시하여 클라이언트가 WS-MetadataExchange를 사용하는 메타데이터 또는 `?wsdl` 쿼리 문자열을 사용하는 HTTP/GET 요청을 검색할 수 있도록 구성하는 방법을 보여 줍니다.  
  
 [방법: 코드를 사용 하 여 서비스에 대 한 메타 데이터를 게시 합니다.](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 클라이언트가 WS-MetadataExchange를 사용하는 메타데이터 또는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 쿼리 문자열을 사용하는 HTTP/GET 요청을 검색할 수 있도록 메타데이터가 코드에서 `?wsdl` 서비스를 게시할 수 있는 방법을 보여 줍니다.  
  
## <a name="see-also"></a>참고 항목  
 [메타 데이터 게시](../../../docs/framework/wcf/feature-details/publishing-metadata.md)
