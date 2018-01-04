---
title: "배포 아키텍처"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ed4ca86e-e3d8-4acb-87aa-1921fbc353be
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 22df793bd5873d6f69c3a2e86e96d4a1cefcff0d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="architecture-of-syndication"></a>배포 아키텍처
배포 API는 네트워크에서 배포된 콘텐츠를 다양한 형식으로 작성할 수 있는 형식 중립적 프로그래밍 모델을 제공하기 위해 디자인되었습니다. 추상 데이터 모델은 다음 클래스로 구성됩니다.  
  
-   <xref:System.ServiceModel.Syndication.SyndicationCategory>  
  
-   <xref:System.ServiceModel.Syndication.SyndicationFeed>  
  
-   <xref:System.ServiceModel.Syndication.SyndicationItem>  
  
-   <xref:System.ServiceModel.Syndication.SyndicationLink>  
  
-   <xref:System.ServiceModel.Syndication.SyndicationPerson>  
  
 이러한 클래스는 이름이 다른 경우도 일부 있지만 Atom 1.0 사양에 정의된 구문에 밀접하게 매핑됩니다.  
  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]의 경우 배포 피드는 다른 형식의 서비스 작업으로 모델링되며, 여기서 반환 형식은 <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>의 파생 클래스 중 하나입니다. 피드의 검색은 요청-회신 메시지 교환으로 모델링됩니다. 클라이언트는 서비스에 대한 요청 및 서비스 응답을 보냅니다. 요청 메시지는 원시 HTTP와 같은 인프라 프로토콜을 통해 설정되며, 응답 메시지에는 일반적으로 인식되는 배포 형식(RSS 2.0 또는 Atom 1.0)으로 구성되는 페이로드가 포함됩니다. 이러한 메시지 교환을 구현하는 서비스를 배포 서비스라고 합니다.  
  
 배포 서비스 계약은 <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> 클래스의 인스턴스를 반환하는 작업 집합으로 구성됩니다. 다음 예제에서는 배포 서비스에 대한 인터페이스 선언을 보여 줍니다.  
  
 [!code-csharp[S_UE_SyndicationBoth#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ue_syndicationboth/cs/service.cs#0)]  
  
 배포 지원은 피드를 서비스로 사용할 수 있도록 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]와 함께 사용되는 <xref:System.ServiceModel.WebHttpBinding> 바인딩을 정의하는 <xref:System.ServiceModel.Description.WebHttpBehavior> REST 프로그래밍 모델을 기반으로 빌드됩니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)][!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] REST 프로그래밍 모델 참조 [WCF 웹 HTTP 프로그래밍 모델 개요](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md)합니다.  
  
> [!NOTE]
>  Atom 1.0 사양에 따라 날짜 구문에 소수로 표시된 초를 지정할 수 있습니다. serialize 및 deserialize할 때 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 구현은 소수로 표시된 초를 무시합니다.  
  
## <a name="object-model"></a>개체 모델  
 배포의 개체 모델은 다음 표의 클래스 그룹으로 구성됩니다.  
  
 클래스 형식 지정:  
  
|클래스|설명|  
|-----------|-----------------|  
|<xref:System.ServiceModel.Syndication.Atom10FeedFormatter>|<xref:System.ServiceModel.Syndication.SyndicationFeed> 인스턴스를 Atom 1.0 형식으로 serialize하는 클래스입니다.|  
|<xref:System.ServiceModel.Syndication.Atom10FeedFormatter%601>|<xref:System.ServiceModel.Syndication.SyndicationFeed> 파생 클래스를 Atom 1.0 형식으로 serialize하는 클래스입니다.|  
|<xref:System.ServiceModel.Syndication.Atom10ItemFormatter>|<xref:System.ServiceModel.Syndication.SyndicationItem> 인스턴스를 Atom 1.0 형식으로 serialize하는 클래스입니다.|  
|<xref:System.ServiceModel.Syndication.Atom10ItemFormatter%601>|<xref:System.ServiceModel.Syndication.SyndicationItem> 파생 클래스를 Atom 1.0 형식으로 serialize하는 클래스입니다.|  
|<xref:System.ServiceModel.Syndication.Rss20FeedFormatter>|<xref:System.ServiceModel.Syndication.SyndicationFeed> 인스턴스를 RSS 2.0 형식으로 serialize하는 클래스입니다.|  
|<xref:System.ServiceModel.Syndication.Rss20FeedFormatter%601>|<xref:System.ServiceModel.Syndication.SyndicationFeed> 파생 클래스를 RSS 2.0 형식으로 serialize하는 클래스입니다.|  
|<xref:System.ServiceModel.Syndication.Rss20ItemFormatter>|<xref:System.ServiceModel.Syndication.SyndicationItem> 인스턴스를 RSS 2.0 형식으로 serialize하는 클래스입니다.|  
|<xref:System.ServiceModel.Syndication.Rss20ItemFormatter%601>|<xref:System.ServiceModel.Syndication.SyndicationItem> 파생 클래스를 RSS 2.0 형식으로 serialize하는 클래스입니다.|  
  
 개체 모델 클래스:  
  
|클래스|설명|  
|-----------|-----------------|  
|<xref:System.ServiceModel.Syndication.SyndicationCategory>|배포 피드의 범주를 나타내는 클래스입니다.|  
|<xref:System.ServiceModel.Syndication.SyndicationContent>|배포 콘텐츠를 나타내는 기본 클래스입니다.|  
|<xref:System.ServiceModel.Syndication.SyndicationElementExtension>|배포 요소 확장을 나타내는 클래스입니다.|  
|<xref:System.ServiceModel.Syndication.SyndicationElementExtensionCollection>|<xref:System.ServiceModel.Syndication.SyndicationElementExtension> 개체의 컬렉션입니다.|  
|<xref:System.ServiceModel.Syndication.SyndicationFeed>|최상위 수준 피드 개체를 나타내는 클래스입니다.|  
|<xref:System.ServiceModel.Syndication.SyndicationItem>|피드 항목을 나타내는 클래스입니다.|  
|<xref:System.ServiceModel.Syndication.SyndicationLink>|배포 피드 또는 항목 내에서 링크를 나타내는 클래스입니다.|  
|<xref:System.ServiceModel.Syndication.SyndicationPerson>|Atom Person 구문을 나타내는 클래스입니다.|  
|<xref:System.ServiceModel.Syndication.SyndicationVersions>|지원되는 배포 프로토콜 버전을 나타내는 클래스입니다.|  
|<xref:System.ServiceModel.Syndication.TextSyndicationContent>|최종 사용자에게 표시되는 <xref:System.ServiceModel.Syndication.SyndicationItem> 콘텐츠를 나타내는 클래스입니다.|  
|<xref:System.ServiceModel.Syndication.TextSyndicationContentKind>|지원되는 다른 형식의 텍스트 배포 콘텐츠를 나타내는 열거형입니다.|  
|<xref:System.ServiceModel.Syndication.UrlSyndicationContent>|다른 리소스에 대한 URL로 구성된 배포 콘텐츠를 나타내는 클래스입니다.|  
|<xref:System.ServiceModel.Syndication.XmlSyndicationContent>|브라우저에 표시되지 않는 배포 콘텐츠를 나타내는 클래스입니다.|  
  
 개체 모델의 핵심 데이터 추상화는 <xref:System.ServiceModel.Syndication.SyndicationFeed> 및 <xref:System.ServiceModel.Syndication.SyndicationItem> 클래스에 해당하는 Feed 및 Item입니다. Feed는 제목, 설명 및 만든 이와 같은 피드 수준의 일부 메타데이터, 알 수 없는 확장을 저장하는 위치 및 나머지 피드 정보 콘텐츠를 구성하는 항목 집합을 노출합니다. Item은 제목, 요약 및 게시 날짜와 같은 항목 수준의 일부 메타데이터, 알 수 없는 확장을 저장하는 위치 및 나머지 항목 정보 콘텐츠를 포함하는 콘텐츠 요소를 사용 가능하게 만듭니다. Atom 1.0 및 RSS 사양에 참조되어 있는 일반 데이터 구문을 나타내는 추가 클래스에서는 Feed 및 Item의 핵심 추상화를 지원합니다.  
  
 Feed 인스턴스에 포함되어 있는 정보는 다양한 XML 형식으로 변환할 수 있습니다. XML에서 변환하거나 XML로 변환하는 프로세스는 <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> 클래스에서 관리합니다. 이 클래스는 추상 클래스입니다. 구체적인 구현은 Atom 1.0 및 RSS 2.0, <xref:System.ServiceModel.Syndication.Atom10FeedFormatter> 및 <xref:System.ServiceModel.Syndication.Rss20FeedFormatter>를 위해 제공됩니다. 파생 Feed 클래스를 사용하려면 <xref:System.ServiceModel.Syndication.Atom10FeedFormatter%601> 또는 <xref:System.ServiceModel.Syndication.Rss20FeedFormatter%601> 중 하나를 사용합니다. 그러면 파생 Feed 클래스를 지정할 수 있습니다. 파생 Item 클래스를 사용하려면 <xref:System.ServiceModel.Syndication.Atom10ItemFormatter%601> 또는 <xref:System.ServiceModel.Syndication.Rss20ItemFormatter%601> 중 하나를 사용합니다. 그러면 파생 Item 클래스를 지정할 수 있습니다. 타사에서는 <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>의 자체 구현을 파생하여 다른 배포 형식을 지원할 수 있습니다.  
  
## <a name="extensibility"></a>확장성  
  
-   배포 프로토콜의 주요 기능은 확장성입니다. Atom 1.0 및 RSS 2.0에서는 사양에 정의되지 않은 배포 피드에 특성 및 요소를 추가할 수 있습니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 배포 프로그래밍 모델에서는 사용자 지정 특성 및 확장에 사용할 수 있는 새 클래스 파생 및 자유로운 형식의 액세스라는 두 가지 방식을 제공합니다. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][배포 확장성](../../../../docs/framework/wcf/feature-details/syndication-extensibility.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [WCF 배포 개요](../../../../docs/framework/wcf/feature-details/wcf-syndication-overview.md)  
 [WCF 배포 개체 모델을 Atom 및 RSS로 매핑하는 방법](../../../../docs/framework/wcf/feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md)  
 [WCF 웹 HTTP 프로그래밍 모델](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
