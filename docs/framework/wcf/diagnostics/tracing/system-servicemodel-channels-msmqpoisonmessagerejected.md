---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 55ae2ed6ac8a02218fa4c13063fb8b8a8c474fd8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a>System.ServiceModel.Channels.MsmqPoisonMessageRejected
포이즌 메시지가 거부되었습니다.  
  
## <a name="description"></a>설명  
 이 추적은 포이즌 메시지가 발생되어 거부되었음을 나타냅니다. 이는 NetMsmqBinding 또는 MsmqIntegrationBinding의 `ReceiveErrorHandling` 속성을 `Reject`로 설정할 경우 발생합니다. 거부 된 메시지가 보낸 사람의에 다시 배달 [배달 못 한 편지 큐](http://go.microsoft.com/fwlink/?LinkId=99544)합니다.  
  
 참조 [포이즌 메시지 처리](http://go.microsoft.com/fwlink/?LinkId=99546) 경우 메시지가 포이즌이 되 고 적절히 처리 하도록 서비스를 구성 하는 방법에 대 한 자세한 내용은 합니다. 참조 [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkId=99548) MSMQ의 의미는 거부 된 메시지에 대 한 자세한 내용은 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [추적](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [추적을 사용 하 여 응용 프로그램 문제를 해결 하려면](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [관리 및 진단](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [포이즌 메시지 처리](http://go.microsoft.com/fwlink/?LinkId=99546)  
 [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkId=99548)
