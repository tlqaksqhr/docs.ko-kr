---
title: '방법: Atom 및 RSS로 피드 공개'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: fe374932-67f5-487d-9325-f868812b92e4
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5a2ca8d6ce6cf907538c534f97300e418f5e825f
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="how-to-expose-a-feed-as-both-atom-and-rss"></a>방법: Atom 및 RSS로 피드 공개
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서는 배포 피드를 노출하는 서비스를 만들 수 있습니다. 이 항목에서는 Atom 1.0 및 RSS 2.0을 사용하여 배포 피드를 노출하는 배포 서비스를 만드는 방법을 설명합니다. 이 서비스는 배포 형식 중 하나를 반환할 수 있는 하나의 끝점을 노출합니다. 편의를 위해 이 샘플에서 사용되는 서비스는 자체 호스트됩니다. 프로덕션 환경에서 이 형식의 서비스는 IIS 또는 WAS에서 호스트됩니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] 서로 다른 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 참조 호스팅 옵션을 [호스팅](../../../../docs/framework/wcf/feature-details/hosting.md)합니다.  
  
### <a name="to-create-a-basic-syndication-service"></a>기본 배포 서비스를 만들려면  
  
1.  <xref:System.ServiceModel.Web.WebGetAttribute> 특성으로 표시된 인터페이스를 사용하여 서비스 계약을 정의합니다. 배포 피드로 노출된 각 작업은 <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> 개체를 반환합니다. <xref:System.ServiceModel.Web.WebGetAttribute>의 매개 변수를 확인합니다. `UriTemplate`은 이 서비스 작업을 호출하는 데 사용되는 URL을 지정합니다. 이 매개 변수에 대 한 문자열에 리터럴 및 변수 중괄호에서 ({*형식*}). 이 변수는 서비스 작업의 `format` 매개 변수에 해당합니다. 자세한 내용은 <xref:System.UriTemplate>을 참조하세요. `BodyStyle`은 이 서비스 작업이 보내고 받는 메시지가 작성되는 방법에 영향을 줍니다. <xref:System.ServiceModel.Web.WebMessageBodyStyle.Bare>는 이 서비스 작업에서 보내거나 받은 데이터가 인프라 정의 XML 요소로 래핑되지 않도록 지정합니다. 자세한 내용은 <xref:System.ServiceModel.Web.WebMessageBodyStyle>을 참조하세요.  
  
     [!code-csharp[htAtomRss#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#0)]
     [!code-vb[htAtomRss#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#0)]  
  
    > [!NOTE]
    >  <xref:System.ServiceModel.ServiceKnownTypeAttribute>를 사용하여 이 인터페이스의 서비스 작업에서 반환하는 형식을 지정합니다.  
  
2.  서비스 계약을 구현합니다.  
  
     [!code-csharp[htAtomRss#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#1)]
     [!code-vb[htAtomRss#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#1)]  
  
3.  <xref:System.ServiceModel.Syndication.SyndicationFeed> 개체를 만들고 만든 이, 범주 및 설명을 추가합니다.  
  
     [!code-csharp[htAtomRss#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#2)]
     [!code-vb[htAtomRss#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#2)]  
  
4.  여러 <xref:System.ServiceModel.Syndication.SyndicationItem> 개체를 만듭니다.  
  
     [!code-csharp[htAtomRss#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#3)]
     [!code-vb[htAtomRss#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#3)]  
  
5.  <xref:System.ServiceModel.Syndication.SyndicationItem> 개체를 피드에 추가합니다.  
  
     [!code-csharp[htAtomRss#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#4)]
     [!code-vb[htAtomRss#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#4)]  
  
6.  형식 매개 변수를 사용하여 요청된 형식을 반환합니다.  
  
     [!code-csharp[htAtomRss#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#5)]
     [!code-vb[htAtomRss#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#5)]  
  
### <a name="to-host-the-service"></a>서비스를 호스트하려면  
  
1.  <xref:System.ServiceModel.Web.WebServiceHost> 개체를 만듭니다. <xref:System.ServiceModel.Web.WebServiceHost> 클래스는 코드 또는 구성에 끝점이 지정되어 있지 않으면 서비스 기준 주소에 끝점을 자동으로 추가합니다. 이 샘플에서는 끝점이 지정되어 있지 않으므로 기본 끝점이 노출됩니다.  
  
     [!code-csharp[htAtomRss#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#6)]
     [!code-vb[htAtomRss#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#6)]  
  
2.  서비스 호스트를 열고 서비스에서 피드를 로드하여 피드를 표시한 다음 사용자가 Enter 키를 누를 때까지 기다립니다.  
  
     [!code-csharp[htAtomRss#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#8)]
     [!code-vb[htAtomRss#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#8)]  
  
### <a name="to-call-getblog-with-an-http-get"></a>HTTP GET을 사용하여 GetBlog를 호출하려면  
  
1.  Internet Explorer를 열고 http://localhost:8000/BlogService/GetBlog  
  
     서비스의 기본 주소를 포함 하는 URL (http://localhost:8000/BlogService), 끝점 및 호출할 서비스 작업의 상대 주소입니다.  
  
### <a name="to-call-getblog-from-code"></a>코드에서 GetBlog()를 호출하려면  
  
1.  기본 주소 및 호출할 메서드를 사용하여 <xref:System.Xml.XmlReader>를 만듭니다.  
  
     [!code-csharp[htAtomRss#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/snippets.cs#9)]
     [!code-vb[htAtomRss#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/snippets.vb#9)]  
  
2.  지금 만든 <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29>를 전달하는 정적 <xref:System.Xml.XmlReader> 메서드를 호출합니다.  
  
     [!code-csharp[htAtomRss#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/snippets.cs#10)]
     [!code-vb[htAtomRss#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/snippets.vb#10)]  
  
     이렇게 하면 서비스 작업이 호출되고 서비스 작업에서 반환된 포맷터로 새 <xref:System.ServiceModel.Syndication.SyndicationFeed>가 채워집니다.  
  
3.  피드 개체에 액세스합니다.  
  
     [!code-csharp[htAtomRss#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/snippets.cs#11)]
     [!code-vb[htAtomRss#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/snippets.vb#11)]  
  
## <a name="example"></a>예제  
 다음은 이 예제에 해당되는 전체 코드 목록입니다.  
  
 [!code-csharp[htAtomRss#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#12)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 코드를 컴파일할 때 System.ServiceModel.dll 및 System.ServiceModel.Web.dll을 참조합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.WebHttpBinding>  
 <xref:System.ServiceModel.Web.WebGetAttribute>
