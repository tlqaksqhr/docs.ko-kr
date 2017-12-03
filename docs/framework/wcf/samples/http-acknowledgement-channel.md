---
title: "HTTP 승인 채널"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 469f3056-5ef2-4753-8acf-b574d23d83cf
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9081b47284b63315d950ef791389312df32815f8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="http-acknowledgement-channel"></a>HTTP 승인 채널
HTTP 승인 채널은 서비스에서 들어오는 메시지를 수신할 때 승인을 자동으로 보내지 않고 들어오는 메시지를 승인하거나 거부할 수 있게 단방향 메시지 패턴을 변경하는 계층화된 채널의 예입니다. 또한 HTTP 승인 채널을 사용하면 서비스에서는 메시지가 처리될 것임을 비즈니스 수준에서 보장할 수 있을 때까지 승인을 지연시킬 수 있습니다.  
  
## <a name="demonstrates"></a>세부 항목  
 계층화된 채널의 예(HTTP 승인 채널)인 <xref:System.ServiceModel.Channels.ReceiveContext>  
  
## <a name="discussion"></a>토론  
 HTTP 승인 채널에서는 <xref:System.ServiceModel.Channels.ReceiveContext>를 구현하여 HTTP 요청-응답 메시징 패턴을 지연 승인을 사용하는 단방향 패턴으로 변형합니다. 이 새 패턴을 사용하면 서비스에서는 메시지 처리가 완료될 때까지 클라이언트를 차단하지 않고 HTTP OK 상태 코드 200 형식으로 승인을 보내 메시지가 처리되도록 하거나, HTTP 내부 서버 오류 상태 코드 500 형식으로 클라이언트에 실패 메시지를 보낼 수 있습니다. 예를 들어 서비스에서는 큐에 메시지를 쓴 후 승인을 보내고, 그런 다음 메시지를 비동기적으로 계속 처리할 수 있습니다. 이 시나리오에서 클라이언트는 서비스로부터 승인을 받을 때까지 각 메시지를 다시 보낸 경우 서비스에서 메시지를 한 번 이상 처리했음을 확인할 수 있습니다. 서비스에서 메시지 처리를 보장하지 않고 HTTP를 통해 신속하게 비동기적으로 메시지를 처리해야 하는 경우에는 <xref:System.ServiceModel.Channels.OneWayBindingElement>가 더 적절합니다.  
  
 <xref:System.ServiceModel.Channels.ReceiveContext>는 메시지를 서비스에서 처리할 수 있는지 여부를 확인하는 동안 메시지를 보관하는 데 사용됩니다. 서비스에서 메시지를 성공적으로 처리할 수 있음을 나타내려면 <xref:System.ServiceModel.Channels.ReceiveContext> 개체에 대해 Complete를 호출하여 HTTP OK 상태 코드를 보내고, 서비스에서 메시지를 처리할 수 있는지 여부를 나타내려면 <xref:System.ServiceModel.Channels.ReceiveContext> 개체에 대해 `Abandon`의 <xref:System.ServiceModel.Channels.ReceiveContext> 메서드를 호출하여 HTTP 내부 서버 오류 상태 코드를 보냅니다.  
  
 이 예제에서 클라이언트는 직원 ID를 보내 정보 처리를 요청합니다. 서비스 쪽에서는 받은 직원 ID가 50보다 크면 HTTP 상태 코드 500(내부 서버 오류)을 클라이언트로 다시 보내고, 그렇지 않으면 처리를 성공적으로 수행할 수 있는 것으로 가정하고 HTTP 상태 코드 200(성공)을 클라이언트로 보냅니다.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  관리자 권한으로 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]을 엽니다.  
  
2.  열기는 **HttpAckChannel** 솔루션입니다.  
  
3.  새 인스턴스를 시작는 **서비스** 프로젝트에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 여 **솔루션 탐색기**를 선택 하 고 **디버그**, **새 인스턴스 시작** 상황에 맞는 메뉴입니다.  
  
4.  새 인스턴스를 시작는 **클라이언트** 프로젝트에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 여 **솔루션 탐색기**를 선택 하 고 **디버그**, 및 **새 인스턴스 시작** 상황에 맞는 메뉴입니다.  
  
5.  서비스가 시작된 후 클라이언트 창에서 Enter 키를 눌러 클라이언트가 서비스로 메시지를 보내도록 합니다.  
  
6.  서비스에서 첫 번째 메시지를 처리하고 HTTP OK 상태 코드를 클라이언트로 다시 보냅니다.  
  
7.  서비스에서 두 번째 메시지를 처리하지 못하고 HTTP 내부 서버 오류 상태 코드를 클라이언트로 다시 보냅니다. 그러면 클라이언트에서 <xref:System.ServiceModel.CommunicationException>이 throw됩니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\HttpAckChannel`
