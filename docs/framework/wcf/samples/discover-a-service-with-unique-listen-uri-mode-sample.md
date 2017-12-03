---
title: "Discover a Service with Unique Listen Uri Mode 샘플"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a6d35b2-0469-43c8-a0c9-63623e3d2733
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 82f47fb0b789e41c332ebae2cfeaeb350ff0fddd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="discover-a-service-with-unique-listen-uri-mode-sample"></a>Discover a Service with Unique Listen Uri Mode 샘플
이 샘플에서는 <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> 속성이 <xref:System.ServiceModel.Description.ListenUriMode.Unique>로 설정된 서비스를 검색하는 방법을 보여 줍니다. <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> 속성이 <xref:System.ServiceModel.Description.ListenUriMode.Unique>로 설정된 경우 포트를 고유하게 설정하거나 경로를 고유하게 하기 위해 GUID를 추가하는 방법으로 ListenUri를 고유하게 설정해야 합니다.  
  
### <a name="features-on-the-service"></a>서비스의 기능  
 TCP 끝점에 대해 <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> 속성을  <xref:System.ServiceModel.Description.ListenUriMode.Unique>로 설정합니다. 그런 다음 서비스를 <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> 끝점을 통해 검색할 수 있게 만듭니다.  
  
### <a name="features-on-the-client"></a>클라이언트의 기능  
 이 클라이언트는 `Via.Uri` 메서드를 사용하여 올바른 <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>를 사용하는 서비스에 연결합니다. 그런 다음 메서드에서 반환되는 <xref:System.ServiceModel.Discovery.FindResponse>를 쿼리하여 올바른 <xref:System.ServiceModel.Endpoint.ListenUri%2A>가 들어 있는지 여부와 이 URI가 `Address.Uri`와 다른지 여부를 확인합니다. 그 다음에는 적절한 정보가 `InvokeCalculatorService` 메서드에 전달됩니다. `InvokeCalculatorService` 메서드에서 <xref:System.ServiceModel.Endpoint.ListenUri%2A>는 호출자가 전달한 것이며, 올바른 `ClientViaBehavior`가 있는 `Via.Uri`가 클라이언트의 끝점에 추가됩니다.  
  
##### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 UniqueListenUriMode.sln을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  [solution base directory]\service\bin\debug에 생성된 서비스 응용 프로그램을 실행합니다.  
  
4.  [solution base directory]\Client\bin\debug에 생성된 클라이언트 응용 프로그램을 실행합니다.  
  
     클라이언트가 실행 중인 서비스를 찾고 서비스의 끝점에서 게시한 메타데이터를 콘솔에 씁니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\UniqueListenUriMode`  
  
## <a name="see-also"></a>참고 항목
