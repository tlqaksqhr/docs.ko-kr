---
title: "워크플로 응용 프로그램 유지"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: abcff14c-f047-4195-ba26-d27f4a82c24e
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cf23b8e33766ea7a15135418142082a0e7b715ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="persisting-a-workflow-application"></a>워크플로 응용 프로그램 유지
이 샘플에서는 <xref:System.Activities.WorkflowApplication>을 실행하고, 유휴 상태가 되면 언로드한 다음, 다시 로드하여 실행을 계속하는 방법을 보여 줍니다.  
  
## <a name="sample-details"></a>샘플 세부 정보  
 <xref:System.Activities.WorkflowApplication>은 간단한 인터페이스를 제공하고 더 일반적인 여러 가지 호스팅 시나리오를 지원하는 단일 워크플로 인스턴스에 대한 호스트입니다. 그와 같은 시나리오 중 하나로 지속성의 지원을 받는 장기 실행 워크플로가 있습니다. 지속성의 호스트는 <xref:System.Activities.WorkflowApplication>에 대한 지속성 작업을 호출하거나 <xref:System.Activities.WorkflowApplication> 이벤트를 처리하고 <xref:System.Activities.WorkflowApplication>을 지속하도록 표시하는 방식으로 제어됩니다.  
  
 이 샘플 워크플로는 사용자의 이름을 입력하도록 요구하는 <xref:System.Activities.Statements.WriteLine> 활동, `ReadLine`를 다시 시작하여 이름을 입력으로 받는 <xref:System.Activities.Bookmark> 활동 및 사용자에게 환영 메시지를 표시하는 <xref:System.Activities.Statements.WriteLine>으로 구성되어 있습니다. 워크플로에서 입력을 기다리는 동안이 바로 자연스럽게 지속성을 유지하는 지점입니다. 이를 종종 <xref:System.Workflow.Runtime.Tracking.TrackingWorkflowEvent.Idle> 지점이라고 합니다. <xref:System.Activities.WorkflowApplication>에서는 워크플로 프로그램을 지속할 수 있을 때마다 <xref:System.Workflow.Runtime.Tracking.TrackingWorkflowEvent.Idle> 이벤트를 발생시키고, 책갈피가 다시 시작되기를 기다리며, 다른 어떠한 작업도 수행하지 않습니다. 이 샘플의 워크플로에서 해당 지점은 `ReadLine` 활동의 실행을 시작한 직후에 발생합니다.  
  
 A <xref:System.Activities.WorkflowApplication> 로 지 속성을 수행할 수 있도록 설정 되어 있는 <!--zz <xref:System.Runtime.Persistence.InstanceStore> --> `System.Runtime.Persistence.InstanceStore`합니다. 이 샘플에서는 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>을 사용합니다. <!--zz <xref:System.Runtime.Persistence.InstanceStore> --> `System.Runtime.Persistence.InstanceStore` 에 할당 되어야 합니다는 <xref:System.Activities.WorkflowApplication.InstanceStore%2A> 하기 전에 속성에서 <xref:System.Activities.WorkflowApplication> 를 실행 합니다.  
  
 이 샘플에서는 <xref:System.Activities.WorkflowApplication.PersistableIdle%2A> 이벤트에 대한 처리기를 추가합니다. 이 이벤트 처리기는 <xref:System.Activities.WorkflowApplication>을 반환하여 어떤 <xref:System.Activities.PersistableIdleAction>을 수행할지 지정합니다. <xref:System.Activities.PersistableIdleAction.Unload>가 반환되면 <xref:System.Activities.WorkflowApplication>이 언로드됩니다.  
  
 그런 다음 이 샘플에서는 사용자의 입력을 받은 후 지속 중이던 워크플로를 새 <xref:System.Activities.WorkflowApplication>으로 로드합니다. 새 작업을 수행 <xref:System.Activities.WorkflowApplication>다시 만들고는 <!--zz <xref:System.Runtime.Persistence.InstanceStore> --> `System.Runtime.Persistence.InstanceStore`, 및 완료 후 언로드된 이벤트를 인스턴스에 연결 하 고 호출할 <xref:System.Activities.WorkflowApplication.Load%2A> 대상 워크플로 인스턴스의 식별자를 사용 합니다. 인스턴스를 획득하고 나면 `ReadLine` 활동의 책갈피가 다시 시작됩니다. 워크플로가 `ReadLine` 활동 내에서 실행되고 완료됩니다. 워크플로가 완료 및 언로드되면 때는 <!--zz <xref:System.Runtime.Persistence.InstanceStore> --> `System.Runtime.Persistence.InstanceStore` 워크플로 삭제 하기 위해 마지막으로 한 번 호출 합니다.  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 명령 프롬프트를 엽니다.  
  
     이 샘플에는 SQL Server Express가 필요합니다. SQL Server Express는 기본적으로 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]과 함께 설치됩니다.  
  
2.  샘플 디렉터리(\WF\Basic\Persistence\InstancePersistence\CS)로 이동하여 CreateInstanceStore.cmd를 실행합니다.  
  
    > [!CAUTION]
    >  CreateInstanceStore.cmd 스크립트가 SQL Server 2008 Express의 기본 인스턴스에 데이터베이스를 만들려고 시도합니다. 다른 인스턴스에 데이터베이스를 설치하려면 스크립트를 수정합니다.  
  
3.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 Persistence.sln 솔루션 파일을 열고 Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
    > [!CAUTION]
    >  SQL Server의 기본 인스턴스가 아닌 인스턴스에 데이터베이스를 설치한 경우 솔루션을 빌드하기 전에 코드에서 연결 문자열을 업데이트합니다.  
  
4.  프로젝트의 bin 디렉터리 (\WF\Basic\Persistence\InstancePersistence\bin\Debug)로 이동 하 여 관리자 권한으로 샘플을 실행 [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]Workflow.exe를 마우스 오른쪽 단추로 클릭 하 고 선택 하면 **관리자권한으로실행**.  
  
#### <a name="to-remove-the-instance-store-database"></a>인스턴스 저장소 데이터베이스를 제거하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 명령 프롬프트를 엽니다.  
  
2.  샘플 디렉터리로 이동하여 RemoveInstanceStore.cmd를 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\InstancePersistence`  
  
## <a name="see-also"></a>참고 항목  
 [AppFabric 호스팅 및 지 속성 샘플](http://go.microsoft.com/fwlink/?LinkId=193961)
