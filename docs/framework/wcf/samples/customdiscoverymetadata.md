---
title: CustomDiscoveryMetadata
ms.date: 03/30/2017
ms.assetid: c42455fd-3652-4b7e-b698-ab3a2bb52e48
ms.openlocfilehash: 3e3a173d99f2ba0a2fb33dfd8f91908f03e3e871
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33501051"
---
# <a name="customdiscoverymetadata"></a>CustomDiscoveryMetadata
이 샘플에서는 서비스에서 노출하는 검색 가능한 끝점의 검색 메타데이터에 사용자 지정 XML 메타데이터를 삽입하는 방법을 보여 줍니다. 그런 다음 이 샘플에서는 클라이언트가 서비스를 검색하고 이 사용자 지정 데이터를 추출하는 방법을 보여 줍니다. 이 샘플은 서비스와 클라이언트에 해당하는 두 개의 프로젝트로 구성되어 있습니다.  
  
## <a name="service"></a>서비스  
 샘플의 `main` 메서드에서는 <xref:System.Xml.Linq.XElement> 형식의 개체를 원하는 필드로 채우고 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>에 추가하는 방법을 보여 줍니다. 이 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>는 특정 끝점에 추가됩니다. 해당 특정 끝점이 검색될 때 검색 메타데이터에는 여기서 추가한 사용자 지정 데이터가 포함됩니다.  
  
## <a name="client"></a>클라이언트  
 이 샘플에서는 <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>에서 호출되는 <xref:System.ServiceModel.Discovery.DiscoveryClient> 메서드를 보여 줍니다. 그런 다음 결과 <xref:System.ServiceModel.Discovery.FindResponse>에서 적절한 예상 XML 요소를 쿼리합니다. 그런 다음 이러한 요소를 콘솔에 출력합니다.  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에 프로젝트 솔루션을 로드하고 프로젝트를 빌드합니다.  
  
2.  먼저 [solution base directory]\service\bin\debug에 생성된 Service 응용 프로그램을 실행한 다음 [solution base directory]\Client\bin\debug에 생성된 Client 응용 프로그램을 실행합니다.  
  
3.  서비스가 온라인 상태로 전환되며 클라이언트에서는 서비스를 찾고 끝점에 게시된 메타데이터를 출력합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\DiscoveryExtensibility\CustomDiscoveryMetadata`  
  
## <a name="see-also"></a>참고 항목
