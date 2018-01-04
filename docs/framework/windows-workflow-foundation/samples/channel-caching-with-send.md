---
title: "Send를 사용한 채널 캐싱"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e69a2502-25cb-43bf-b8d2-95fbdecb41cb
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b12ebe4cc15629125627253200a95b1f8353bbc8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="channel-caching-with-send"></a>Send를 사용한 채널 캐싱
<xref:System.ServiceModel.Activities.SendMessageChannelCache>를 사용하면 <xref:System.ServiceModel.Activities.Send> 및 <xref:System.ServiceModel.Activities.SendParametersContent> 활동에 각기 다른 채널 캐싱 수준을 적용할 수 있습니다. 기본적으로 인스턴스 수준 캐싱이 사용됩니다. 이 샘플에서는 다음과 같은 기능을 보여 줍니다.  
  
1.  응용 프로그램 도메인에 걸친 <xref:System.ServiceModel.Activities.SendMessageChannelCache> 공유  
  
2.  채널 캐싱 비활성화  
  
3.  <xref:System.ServiceModel.Activities.SendMessageChannelCache>에서 워크플로 인스턴스 사이에 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 공유  
  
## <a name="demonstrates"></a>세부 항목  
 <xref:System.ServiceModel.Activities.SendMessageChannelCache> 확장, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.ReceiveContent> 및 <xref:System.ServiceModel.Activities.SendReply> 활동  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에 프로젝트 솔루션을 로드하고 프로젝트를 빌드합니다.  
  
2.  \EchoWorkflowService\bin\debug에 생성된 EchoWorkflowService 응용 프로그램을 실행합니다.  
  
3.  .\EchoWorkflowClient\bin\debug에 생성된 EchoWorkflowClient 응용 프로그램을 실행합니다.  
  
4.  클라이언트에서 서비스에 대한 Echo 작업을 호출하고 결과를 출력합니다. 결과가 출력되면 Enter 키를 눌러 클라이언트와 서비스를 종료합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\ChannelCache`
