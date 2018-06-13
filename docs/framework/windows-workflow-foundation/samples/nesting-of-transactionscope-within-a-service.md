---
title: 서비스 내에 TransactionScope 중첩
ms.date: 03/30/2017
ms.assetid: e7e1ba64-1384-4eba-add8-415636e2d6d0
ms.openlocfilehash: 9c556df417548ab348d1dd5bc642928ae68d8878
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33518271"
---
# <a name="nesting-of-transactionscope-within-a-service"></a>서비스 내에 TransactionScope 중첩
이 샘플은 한 서비스 내의 <xref:System.Activities.Statements.TransactionScope> 활동 인스턴스 여러 개를 처리하는 방법을 보여 주는 두 개의 시나리오로 구성되어 있습니다. 우선 <xref:System.Activities.Statements.TransactionScope> 활동을 사용하여 클라이언트에 새 트랜잭션을 만들어 트랜잭션을 시작하고 <xref:System.ServiceModel.Activities.TransactedReceiveScope>를 사용하여 서버에서 트랜잭션을 받고 트랜잭션 수명의 범위를 정합니다. 서비스 내의 첫째 시나리오는 보조 <xref:System.Activities.Statements.TransactionScope> 활동을 실행하여 서비스 내에 중첩되는 <xref:System.Activities.Statements.TransactionScope> 활동을 보여 줍니다. 둘째 시나리오에서는 중첩된 <xref:System.Activities.Statements.TransactionScope> 활동 내에 제한 시간이 적용되는 방식을 보여 줍니다.  
  
## <a name="client-application"></a>클라이언트 응용 프로그램  
 클라이언트 응용 프로그램에서는 <xref:System.Activities.Statements.TransactionScope> 활동을 시작하고, 분산 트랜잭션 ID를 출력하고, 서버로 메시지를 보내고, 트랜잭션을 이동하고, 회신을 받고, 분산 트랜잭션 ID를 다시 출력한 후 완료되는 워크플로를 실행합니다. 이 응용 프로그램에서는 각 서비스 시나리오에 대해 이를 한 번씩 수행합니다.  
  
## <a name="server-application"></a>서버 응용 프로그램  
 서버 프로젝트는 <xref:System.ServiceModel.Activities.WorkflowServiceHost>에 호스트되며, 클라이언트에서 보낸 메시지를 수신할 끝점을 만듭니다. 이 워크플로는 클라이언트에서 이동한 트랜잭션을 받고, 분산 트랜잭션 ID를 출력한 다음 둘째 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 활동을 실행하는 <xref:System.Activities.Statements.TransactionScope>를 중심으로 합니다. 첫째 시나리오에서는 트랜잭션이 성공적으로 완료됩니다. 둘째 시나리오에서는 <xref:System.Activities.Statements.TransactionScope> 활동의 본문이 5초 지연되며 트랜잭션 제한 시간은 2초로 설정됩니다. 트랜잭션 제한 시간을 초과하면 트랜잭션이 중단됩니다.  
  
#### <a name="to-run-the-sample"></a>이 샘플을 실행하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 TransactionServiceExample.sln 솔루션을 엽니다.  
  
2.  솔루션을 빌드하려면 CTRL + SHIFT + B 키를 누르거나 선택 **솔루션 빌드** 에서 **빌드** 메뉴.  
  
3.  빌드가 성공한 후 솔루션을 마우스 오른쪽 단추로 클릭 하 고 선택 **시작 프로젝트 설정**합니다. 대화 상자에서 선택 **여러 개의 시작 프로젝트** 하 고 두 프로젝트에 대 한 작업 확인 **시작**합니다.  
  
4.  F5 키를 누르거나 선택 **디버깅 시작** 에서 **디버그** 메뉴. 또는 CTRL + f 5를 눌러 수도 있고 선택할 **디버깅 하지 않고 시작** 에서 **디버그** 메뉴 디버깅 없이 실행 합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Transactions\TRSComposability`
