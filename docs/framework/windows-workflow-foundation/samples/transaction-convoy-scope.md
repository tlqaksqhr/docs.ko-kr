---
title: "트랜잭션 호송 범위"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 37141708-a29f-4b6a-81fe-f8a11f825061
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 854e04c53bf438c3356072d762f129b7f21b7dd5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="transaction-convoy-scope"></a>트랜잭션 호송 범위
이 샘플에서는 <xref:System.ServiceModel.Activities.TransactedReceiveScope>와 함께 Parallel Convoy 메시징 활동 패턴을 만들어 많은 작업이 모두 같은 트랜잭션에서 순서에 관계없이 발생할 수 있는 프로토콜을 모델링하는 방법을 보여 줍니다. 또한 트랜잭션이 서버로 이동되지 않는 경우<xref:System.ServiceModel.Activities.TransactedReceiveScope>가 자동으로 새 트랜잭션을 만들어 클라이언트가 어떤 트랜잭션도 사용하지 않도록 하는 방법도 보여 줍니다.  
  
 이 샘플은 클라이언트와 서버를 나타내는 두 개의 워크플로 프로젝트로 구성되어 있습니다. 클라이언트 프로젝트는 서버 워크플로를 부트스트랩하는 메시지를 보내 시작되는 워크플로를 실행하며, 이 워크플로는 상관 관계를 초기화하고 나머지 메시징 활동에 대해 트랜잭션 범위를 시작합니다. 클라이언트 <xref:System.Activities.Statements.Sequence> 활동에는 <xref:System.ServiceModel.Activities.Send> 및 <xref:System.ServiceModel.Activities.ReceiveReply> 쌍과 세 분기가 있는 <xref:System.Activities.Statements.Parallel> 활동이 포함되어 있습니다. 각 분기는 서버에 단방향 메시지를 보냅니다. <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> 활동의 <xref:System.Activities.Statements.Parallel> 속성은 세 분기가 모두 완료되도록 `false`로 설정됩니다.  
  
 서버 워크플로는 클라이언트 워크플로와 비슷하지만 서버 워크플로의 경우에는 메시징 활동이 통신의 서버측을 향하고, 수행되는 모든 작업이 같은 트랜잭션에서 실행되도록 메시징 활동이 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 활동 내에 포함되어 있습니다. 서버에서 첫 번째 메시지를 받으면 트랜잭션이 만들어지고 이 트랜잭션이 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 본문 범위의 앰비언트 트랜잭션이 되어 이 범위 내의 모든 활동이 해당 트랜잭션에 액세스할 수 있습니다. 그러면 받는 메시지가 모두 병렬로 실행됩니다. 받는 메시지는 모두 병렬 활동의 완료 조건에 설명되어 있는 것처럼 한 번만 실행되어야 합니다. <xref:System.ServiceModel.Activities.TransactedReceiveScope> 본문의 끝에 암시적 유지 지점이 있으며 지속성 작업도 같은 트랜잭션에서 실행됩니다.  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 ParallelConvoySample.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  두 프로젝트 모두 시작되도록 설정되어 있는지 확인합니다.  
  
    1.  **솔루션 탐색기**솔루션을 마우스 오른쪽 단추로 클릭 하 고 선택 **시작 프로젝트 설정**합니다.  
  
    2.  선택 **여러 개의 시작 프로젝트** 두 프로젝트에 대 한 작업으로 설정 되었는지 확인 하 고 **시작**합니다.  
  
4.  Ctrl+F5를 눌러 솔루션을 실행합니다.  
  
     서버에서 `Server is running`이라고 출력되고 이는 서버가 준비되었음을 나타냅니다.  
  
     클라이언트 콘솔 창에서 아무 키나 눌러 샘플을 시작합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\TransactedConvoyScope`