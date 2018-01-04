---
title: "명령형 TransactionScope에서 워크플로 실행"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bd0e8686-c1d0-4400-a541-da94ed03afc7
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 530a590931a1cb3994406e5605f8da2853ceddaf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="execute-a-workflow-in-an-imperative-transactionscope"></a>명령형 TransactionScope에서 워크플로 실행
이 샘플에서는 명령형 C# 코드에서 <xref:System.Activities.WorkflowInvoker>의 <xref:System.Transactions.Transaction>를 사용하여 워크플로를 실행하는 방법을 보여 줍니다.  
  
## <a name="sample-details"></a>샘플 세부 정보  
 명령형 C# 코드에서 <xref:System.Transactions.TransactionScope>는 동일한 트랜잭션 내에서 실행되는 작업 집합을 캡슐화하는 데 사용됩니다. <xref:System.Transactions.TransactionScope>는 앰비언트 트랜잭션을 만들고 <xref:System.Transactions.Transaction.Current%2A> 속성을 초기화하는 방식으로 작동합니다. 이렇게 초기화한 속성에는 해당 스레드에서 실행되는 임의의 다른 작업을 통해 액세스할 수 있습니다.  
  
 워크플로에서 이와 같은 동작을 구현하려면 런타임에 각 활동을 실행하기 전에 <xref:System.Transactions.Transaction.Current%2A>를 초기화하는 작업을 추가로 수행해야 합니다. 워크플로의 경우 각 활동 사이에 스레드 선호도가 유지되지 않기 때문입니다. 이와 같은 런타임 지원이 있으면 <xref:System.Activities.WorkflowInvoker> 내의 <xref:System.Transactions.TransactionScope>로 워크플로를 실행할 때 모든 활동을 <xref:System.Transactions.TransactionScope>에서 만든 앰비언트 트랜잭션의 컨텍스트에서 실행할 수 있습니다.  
  
 워크플로는 각 워크플로 인스턴스에 대해 앰비언트 트랜잭션을 하나만 가질 수 있습니다. 중첩된 트랜잭션은 사용할 수 없습니다. 워크플로에 <xref:System.Activities.Statements.TransactionScope> 활동이 포함되어 있더라도 새로운 내부 트랜잭션이 만들어지지 않습니다. 대신, 이와 같은 경우에는 워크플로 외부에 만들어진 앰비언트 트랜잭션이 다시 사용됩니다.  
  
 이 샘플에서는 새 <xref:System.Transactions.TransactionScope>를 시작하고, 트랜잭션 ID를 출력하고, <xref:System.Activities.WorkflowInvoker>를 사용하여 워크플로를 시작합니다. 이 워크플로는 트랜잭션 ID를 다시 출력하여 동일한 트랜잭션 내에서 진행되고 있음을 확인시켜 준 다음 <xref:System.Activities.Statements.TransactionScope>를 실행한 후 과정을 마칩니다. <xref:System.Activities.WorkflowInvoker.Invoke%2A>에 대한 <xref:System.Activities.WorkflowInvoker> 호출은 동기적이므로 워크플로가 완료될 때까지 원래 스레드가 차단됩니다. 워크플로가 완료되고 나면 트랜잭션이 완료되고 리소스가 삭제됩니다.  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 ImperativeTransactionSample.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  F5 키를 눌러 솔루션을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\ImperativeTransaction`