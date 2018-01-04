---
title: "중간 계층 클라이언트 응용 프로그램"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f9714a64-d0ae-4a98-bca0-5d370fdbd631
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 13399243994943ddf853447e2e29f3695702aa35
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="middle-tier-client-applications"></a>중간 계층 클라이언트 응용 프로그램
이 항목에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]를 사용하는 중간 계층 클라이언트 응용 프로그램과 관련된 다양한 문제에 대해 설명합니다.  
  
## <a name="increasing-middle-tier-client-performance"></a>중간 계층 클라이언트 성능 향상  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]을 사용하는 웹 서비스와 같은 이전 통신 기술과 비교하여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 풍부한 기능으로 인해 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 인스턴스를 만들기가 더 복잡할 수 있습니다. 예를 들어, <xref:System.ServiceModel.ChannelFactory%601> 개체가 열릴 때 클라이언트 인스턴스에 대한 시작 시간을 늘리는 절차인 서비스를 사용하여 보안 세션을 설정할 수 있습니다. 일반적으로 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트는 여러 개의 호출을 만들었다가 닫기 때문에 이러한 추가 기능이 클라이언트 응용 프로그램에 큰 영향을 주지는 않습니다.  
  
 그러나 중간 계층 클라이언트 응용 프로그램은 많은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 개체를 빠르게 만들 수 있으므로, 초기화 요구 사항이 향상됩니다. 서비스를 호출할 때 중간 계층 응용 프로그램의 성능을 향상시키는 두 가지 기본적인 방법이 있습니다.  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 개체를 캐시한 다음 이후의 호출에서 다시 사용합니다(가능한 경우).  
  
-   <xref:System.ServiceModel.ChannelFactory%601> 개체를 만든 다음 호출할 때마다 해당 개체를 사용하여 새 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 채널 개체를 만듭니다.  
  
 이러한 방법을 사용할 때 고려해야 할 문제는 다음과 같습니다.  
  
-   서비스에서 세션을 사용하여 클라이언트별 상태를 유지할 경우 서비스의 상태가 중간 계층 클라이언트의 상태에 연결되기 때문에 다중 클라이언트 계층 요청에서 중간 계층 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트를 다시 사용할 수 없습니다.  
  
-   서비스에서 클라이언트 단위로 인증을 수행해야 하는 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 또는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 만든 이후에는 중간 계층의 클라이언트 자격 증명을 수정할 수 없기 때문에 중간 계층 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 또는 <xref:System.ServiceModel.ChannelFactory%601> 클라이언트 채널 개체를 다시 사용하지 않고 중간 계층에 들어오는 요청마다 새로운 클라이언트를 만들어야 합니다.  
  
-   채널과 채널에서 만든 클라이언트는 스레드로부터 안전하므로 네트워크에서 동시에 여러 메시지 쓰기를 지원하지 않을 수 있습니다. 큰 메시지를 보낼 경우, 특히 스트리밍할 경우에는 다른 보내기 작업이 완료되는 동안 보내기 작업이 차단될 수 있습니다. 따라서 채널을 재사용하여 제어의 흐름이 서비스로 반환될 경우 즉, 코드 경로에서 공유 클라이언트에 대한 콜백을 생성하는 서비스를 공유 클라이언트가 호출할 경우 동시성 결여 및 교착 상태의 두 가지 문제가 발생할 수 있습니다. 이는 재사용하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트의 형식에 관계없이 적용됩니다.  
  
-   채널을 공유하는지 여부에 관계없이 오류가 발생한 채널을 처리해야 합니다. 그러나 채널을 다시 사용할 경우 오류 채널에서 대기 중인 여러 요청 또는 보내기를 종료할 수 있습니다.  
  
 여러 개의 요청에 대 한 클라이언트를 다시 사용에 대 한 모범 사례를 보여 주는 예제를 보려면 [ASP.NET 클라이언트에서 데이터 바인딩](../../../../docs/framework/wcf/samples/data-binding-in-an-aspnet-client.md)합니다.  
  
 또한 <xref:System.Xml.Serialization.XmlSerializer>를 사용하여 serialize할 수 있는 데이터 형식을 사용하는 클라이언트가 런타임에 해당 데이터 형식에 대한 serialization 코드를 생성하고 컴파일할 때 시작 성능이 저하될 수 있습니다. 이 시작 성능을 향상시킬 수 있습니다. [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 응용 프로그램에 대해 컴파일된 어셈블리에서 필요한 serialization 코드를 생성 하 여 이러한 응용 프로그램의 시작 성능을 향상 시킬 수 있습니다. 자세한 내용은 참조 [하는 방법: 시작 시간의 WCF 클라이언트 응용 프로그램 XmlSerializer를 사용 하 여 개선](../../../../docs/framework/wcf/feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [WCF 클라이언트를 사용하여 서비스 액세스](../../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md)
