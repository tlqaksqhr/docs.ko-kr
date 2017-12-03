---
title: "트랜잭션된 큐"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b1b011dd-5e0b-482c-9bb0-9d8727038f14
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 11d1d0d3481fb575abd01894db631e24c50b6d56
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="transacted-queues"></a>트랜잭션된 큐
이 샘플에서는 [!INCLUDE[wf](../../../../includes/wf-md.md)]에서 큐와 트랜잭션을 통합하여 안정적이고 확장 가능한 서비스를 만드는 방법을 보여 줍니다. A <!--zz <xref:System.Activities.TransactionScope>--> `System.Activities.TransactionScope` 클라이언트 워크플로에서 사용 하 여 트랜잭션 중인 큐로 메시지를 보내는 데 사용 된 <xref:System.ServiceModel.NetMsmqBinding>합니다. 서버에서는 큐로부터 메시지를 받고 동일한 트랜잭션을 진행 중인 워크플로의 상태를 업데이트하기 위해 <xref:System.ServiceModel.Activities.TransactedReceiveScope>를 사용합니다.  
  
## <a name="demonstrates"></a>세부 항목  
 <xref:System.Activities.Statements.TransactionScope>, <xref:System.ServiceModel.Activities.TransactedReceiveScope>, <xref:System.ServiceModel.NetMsmqBinding>, <xref:System.ServiceModel.Activities.Receive> 및 내용 기반 상관 관계  
  
## <a name="discussion"></a>토론  
 이 샘플에서 다룰 기능을 보여 주기 위해 `RewardsPoints` 워크플로 서비스를 만듭니다. 이 워크플로 서비스는 특정 계정이 획득하고 사용한 점수를 추적하는 역할을 합니다. 클라이언트에서는 <xref:System.Activities.WorkflowInvoker>를 사용하여 큐에 다양한 요청을 게시하는 과정을 시뮬레이션합니다. 트랜잭션 중인 큐에 메시지를 게시하기 위해 <xref:System.ServiceModel.Activities.Send>의 <xref:System.Activities.Statements.TransactionScope.Body%2A> 내에 <xref:System.Activities.Statements.TransactionScope> 활동을 배치할 수 있습니다. 이 샘플에서는 큐에 대기 중인 메시지를 통해 클라이언트 및 서버 응용 프로그램이 어떻게 분리되는지 보여 주기 위해 클라이언트를 먼저 실행한 다음 서버를 실행합니다.  
  
 클라이언트가 완료되고 나면 서비스가 구성 및 호스트됩니다. 서비스가 열리는 즉시 큐에 이미 대기 중이던 메시지의 처리가 시작됩니다. 각 메시지는 동일한 서버 트랜잭션 내에서 수신 및 처리됩니다. 이 샘플에서 수신되는 첫 메시지는 인스턴스를 만들고 요청 메시지의 일부로 전달된 계정 이름을 기준으로 내용 상관 관계를 초기화하는 `CreateAccount` 요청입니다. 실제 상황에서 충분히 예상할 수 있는 종류의 서비스를 모델링하기 위해 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 및 `AddPoints` 메시지를 처리하는 두 가지 `UsePoints` 활동을 `while` 루프 내의 병렬 분기에 배치하고 해당 메시지를 순서에 관계 없이 반복하여 처리할 수 있도록 했습니다.  
  
 <xref:System.Activities.Statements.TransactionScope> 및 <xref:System.ServiceModel.Activities.TransactedReceiveScope>의 각 범위 끝에는 암시적 지속성 지점이 있습니다. 따라서 큐와 함께 [!INCLUDE[wf1](../../../../includes/wf1-md.md)]에서 이러한 활동을 사용하면 해당 메시지를 잃지 않으면서 특정 지속성 상태로부터 다음 상태로 워크플로를 안정적으로 이동할 수 있습니다.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  MSMQ를 설치하고 구성합니다. 참조 [메시지 큐 설치](http://go.microsoft.com/fwlink/?LinkId=178526) 대 한 자세한 내용은 합니다.  
  
2.  명령줄에서 다음 명령을 실행하여 MSDTC가 실행되고 있는지 확인합니다. `net start msdtc`  
  
3.  프로젝트를 컴파일하고 실행 파일을 열거나 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 프로젝트를 열고 디버그 메뉴에서 시작 옵션을 선택합니다. 제일 먼저 큐가 만들어진 다음 클라이언트가 실행되고 큐에 메시지가 게시됩니다. 마지막으로 서비스가 시작되고 메시지가 처리됩니다. 프로그램을 끝내려면 Enter 키를 누릅니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\TransactedQueues`
