---
title: "서비스 내에 TransactionScope 중첩 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e7e1ba64-1384-4eba-add8-415636e2d6d0
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# 서비스 내에 TransactionScope 중첩
이 샘플은 한 서비스 내의 <xref:System.Activities.Statements.TransactionScope> 활동 인스턴스 여러 개를 처리하는 방법을 보여 주는 두 개의 시나리오로 구성되어 있습니다.우선 <xref:System.Activities.Statements.TransactionScope> 활동을 사용하여 클라이언트에 새 트랜잭션을 만들어 트랜잭션을 시작하고 <xref:System.ServiceModel.Activities.TransactedReceiveScope>를 사용하여 서버에서 트랜잭션을 받고 트랜잭션 수명의 범위를 정합니다.서비스 내의 첫째 시나리오는 보조 <xref:System.Activities.Statements.TransactionScope> 활동을 실행하여 서비스 내에 중첩되는 <xref:System.Activities.Statements.TransactionScope> 활동을 보여 줍니다.둘째 시나리오에서는 중첩된 <xref:System.Activities.Statements.TransactionScope> 활동 내에 제한 시간이 적용되는 방식을 보여 줍니다.  
  
## 클라이언트 응용 프로그램  
 클라이언트 응용 프로그램에서는 <xref:System.Activities.Statements.TransactionScope> 활동을 시작하고, 분산 트랜잭션 ID를 출력하고, 서버로 메시지를 보내고, 트랜잭션을 이동하고, 회신을 받고, 분산 트랜잭션 ID를 다시 출력한 후 완료되는 워크플로를 실행합니다.이 응용 프로그램에서는 각 서비스 시나리오에 대해 이를 한 번씩 수행합니다.  
  
## 서버 응용 프로그램  
 서버 프로젝트는 <xref:System.ServiceModel.Activities.WorkflowServiceHost>에 호스팅되며, 클라이언트에서 보낸 메시지를 수신할 끝점을 만듭니다.이 워크플로는 클라이언트에서 이동한 트랜잭션을 받고, 분산 트랜잭션 ID를 출력한 다음 둘째 <xref:System.Activities.Statements.TransactionScope> 활동을 실행하는 <xref:System.ServiceModel.Activities.TransactedReceiveScope>를 중심으로 합니다.첫째 시나리오에서는 트랜잭션이 성공적으로 완료됩니다.둘째 시나리오에서는 <xref:System.Activities.Statements.TransactionScope> 활동의 본문이 5초 지연되며 트랜잭션 제한 시간은 2초로 설정됩니다.트랜잭션 제한 시간을 초과하면 트랜잭션이 중단됩니다.  
  
#### 샘플을 실행하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 TransactionServiceExample.sln 솔루션을 엽니다.  
  
2.  솔루션을 빌드하려면 Ctrl\+Shift\+B를 누르거나 **빌드** 메뉴에서 **솔루션 빌드**를 선택합니다.  
  
3.  성공적으로 빌드되면 솔루션을 마우스 오른쪽 단추로 클릭하고 **시작 프로젝트 설정**을 선택합니다.대화 상자에서 **여러 개의 시작 프로젝트**를 선택하고 두 프로젝트의 동작이 **시작**으로 설정되어 있는지 확인합니다.  
  
4.  F5 키를 누르거나 **디버그** 메뉴에서 **디버깅 시작**을 선택합니다.또는 Ctrl\+F5를 누르거나 **디버그** 메뉴에서 **디버깅하지 않고 시작**을 선택하여 디버깅 없이 실행할 수도 있습니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Transactions\TRSComposability`