---
title: 기본 제공 구성
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 34e85c9b-088d-4347-816c-0f77cb73ef2f
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0c414f34da0cd4bbf484c0a439f8832f02a5ae58
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="built-in-configuration"></a>기본 제공 구성
이 샘플에서는 SQL 워크플로 인스턴스 저장소를 사용하고 구성하는 방법을 보여 줍니다. SQL 워크플로 인스턴스 저장소는 인스턴스 저장소의 SQL 기반 구현이며, 이 저장소를 사용하면 인스턴스가 SQL Server 또는 SQL Server Express 데이터베이스 간에 인스턴스 상태를 저장하고 로드할 수 있습니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 다운로드 페이지로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\BuiltInConfiguration`  
  
## <a name="sample-details"></a>샘플 세부 정보  
 이 샘플은 계산 서비스를 구현하는 워크플로로 구성되어 있습니다. 서비스의 시작 메서드를 호출하면 서비스는 0부터 59까지 계산합니다. 카운터는 2초 간격으로 증가하고, 각 계산 후에 워크플로가 지속됩니다.  
  
 계산 워크플로는 워크플로 서비스 호스트에서 자체 호스트합니다. 프로그램의 `Main` 메서드는 계산 워크플로를 호스트하는 워크플로 서비스 호스트의 인스턴스를 만들고, 계산 워크플로가 도달할 수 있는 끝점을 정의합니다. 그런 다음 SQL 워크플로 인스턴스 저장소를 구성하는 데 사용되는 SQL 워크플로 인스턴스 저장소 동작을 정의합니다. 그런 다음 프로그램은 계산 워크플로의 시작 메서드를 호출하는 클라이언트를 만듭니다.  
  
 프로그램을 시작하면 카운터가 자동으로 계산을 시작합니다. 인스턴스를 로드하고 SQL 워크플로 인스턴스 저장소를 구성하는 데는 몇 초 정도 걸릴 수 있습니다. 워크플로 인스턴스 저장소에 대 한 자세한 내용은 참조 [SQL 워크플로 인스턴스 저장소](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md)합니다.  
  
 이 샘플은 두 부분으로 구성되어 있습니다.  
  
1.  InstanceStore1에서는 C# 코드를 사용하여 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>를 구성하는 방법을 보여 줍니다(Program.cs 참조).  
  
2.  InstanceStore2에서는 XML을 사용하여 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>를 구성하는 방법을 보여 줍니다(App.config 참조).  
  
 다음 설정은 SQL 워크플로 인스턴스 저장소 동작을 구성하는 데 사용할 수 있습니다.  
  
-   `HostLockRenewalPeriod`을 설정합니다. 이 시간에 따라 호스트가 실행하는 인스턴스의 소유권 잠금을 갱신하는 간격이 정의됩니다. 잠금 정보는 인스턴스 저장소에 저장됩니다. `HostLockRenewalPeriod`에 정의된 간격이 두 번 경과할 때까지 소유권을 갱신하지 않으면 인스턴스는 중단된 것으로 간주됩니다. 다른 <xref:System.ServiceModel.Activities.WorkflowServiceHost>가 같은 컴퓨터나 다른 컴퓨터의 동일한 인스턴스 저장소에 연결되어 있는 상태에서 같은 워크플로를 실행 중이면 해당 인스턴스가 복구됩니다. 인스턴스 복구에 대해서는 이 샘플에서 다루지 않습니다.  
  
-   `RunnableInstancesDetectionPeriod`을 설정합니다. 이 기간에 따라 호스트가 실행 가능하게 된 인스턴스를 폴링하는 간격이 정의됩니다. 인스턴스는 다음 이벤트 중 하나가 발생하는 경우 실행 가능하게 될 수 있습니다.  
  
    -   지속적인 타이머(<xref:System.Activities.Statements.Delay>)가 만료되는 경우  
  
    -   컴퓨터 고장 등의 이유로 다른 호스트에 `HostLockRenewal` 하트비트가 누락되고 인스턴스가 복구되는 경우  
  
-   `InstanceCompletionAction`을 설정합니다. 이 속성을 `DeleteNothing`으로 설정하면 완료된 인스턴스가 인스턴스 저장소에서 유지되고, `DeleteAll`로 설정하면 인스턴스가 완료될 때 저장소에서 삭제됩니다. 다음 사항에 유의하십시오.  
  
    > [!NOTE]
    >  계산이 완료되기 전에 Enter 키를 눌러 호스트를 종료하면 워크플로 인스턴스가 완료되지 않습니다.  
  
-   `InstanceLockedExceptionAction`을 설정합니다. 이 설정에 따라 호스트가 다른 호스트에서 잠근 인스턴스를 로드하려는 경우 수행해야 하는 작업이 정의됩니다. 다음과 같은 옵션이 있습니다.  
  
    -   `NoRetry`로 설정하는 경우: 로드하려고 다시 시도하지 않고 호스트에 `InstanceLockedException`을 반환합니다.  
  
    -   `BasicRetry`로 설정하는 경우: 계속해서 인스턴스를 로드하려고 시도합니다. 단순한 선형 알고리즘에 따라 다시 시도가 예약됩니다. 예를 들면 5초 간격으로 다시 시도합니다.  
  
    -   `AggressiveRetry`로 설정하는 경우: 계속해서 인스턴스를 로드하려고 시도합니다. 적극적인 지수 백오프 알고리즘에 따라 다시 시도가 예약됩니다.  
  
-   인코딩 옵션을 설정합니다. 이 설정에 따라 인스턴스 상태가 SQL 워크플로 인스턴스 저장소에 저장되는 방식이 정의됩니다. 다음과 같은 옵션이 있습니다.  
  
    -   인스턴스 상태가 GZip 압축 알고리즘을 사용하여 압축됩니다.  
  
    -   인스턴스 상태가 압축되지 않습니다.  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  관리자 권한(있는 경우)으로 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 명령 프롬프트를 엽니다.  
  
2.  샘플 디렉터리(\WF\Basic\Persistence\BuiltInConfiguration\CS)로 이동하고 CreateInstanceStore.cmd를 실행합니다.  
  
3.  관리자 권한이 없는 경우 SQL Server 로그인을 만듭니다. 로 이동 `Security`, **로그인**합니다. 마우스 오른쪽 단추로 클릭 **로그인** 새 로그인을 만듭니다.  
  
4.  SQL 역할에 ACL 사용자를 추가합니다. 열기 **데이터베이스**, **InstanceStore**, **보안**합니다. 마우스 오른쪽 단추로 클릭 **사용자** 선택 **새 사용자**합니다. 설정의 **로그인 이름** 이전 단계에서 만든 사용자에 게 합니다. 데이터베이스 역할 멤버 자격 사용자를 추가 **System.Activities.DurableInstancing.InstanceStoreUsers** (및 기타). 사용자가 이미 있을 수도 있습니다(예: 사용자 dbo).  
  
5.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 InstanceStore.sln 파일을 열고 Ctrl 키를 눌러 솔루션을 빌드합니다.  
  
6.  [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], 샘플의 적절 한 bin\debug 디렉터리 (\WF\Basic\Persistence\BuiltInConfiguration\cs\InstanceStore(1 or 2)\bin\debug)로 이동, InstanceStore.exe를 마우스 오른쪽 단추로 클릭 하 고 선택 **관리자권한으로실행**. 이 샘플은 채널 수신기를 열기 때문에 관리자 권한으로 실행해야 합니다.  
  
7.  SQL Server Express 로컬 설치 이외의 데이터베이스에 인스턴스 저장소를 만든 경우에는 샘플에서 데이터베이스 연결 문자열(InstanceStore1 프로젝트의 Program.cs에 있는 `const string ConnectionString` 및 InstanceStore2 프로젝트의 App.config에 있는 `connectionString` 특성)을 업데이트한 다음 샘플을 다시 컴파일해야 합니다.  
  
#### <a name="to-verify-the-sample-is-running-correctly"></a>샘플이 올바르게 실행되고 있는지 확인하려면  
  
1.  샘플이 실행되고 있는 동안 SQL Server Management Studio를 시작합니다.  
  
2.  에 **개체 탐색기**선택, **데이터베이스**, **InstanceStore**, **테이블**, 차례로  **System.Activities.DurableInstancing.InstanceTable**합니다.  
  
3.  마우스 오른쪽 단추로 클릭 **인스턴스 테이블** 선택 **상위 1000 개 행 선택**합니다.  
  
4.  새 항목이 있는지와 없는지 확인는 **잠금 만료** 5 초 간격으로 변경 (작업 표시줄의 클릭 **Execute** 단추를 쿼리를 새로 고칠). 이 설정의 결과 **호스트 잠금 갱신 기간** 5입니다.  
  
5.  계산이 완료된 후 인스턴스 테이블의 항목이 제거되었는지 확인합니다. 이 설정의 **인스턴스 완료 동작** 를 **DeleteAll**합니다.  
  
6.  Enter 키를 눌러 워크플로 호스트 응용 프로그램을 종료 하는 **LockOwnersTable** 삭제 됩니다.  
  
#### <a name="to-uninstall-the-sample"></a>샘플을 제거하려면  
  
1.  샘플 디렉터리(\WF\Basic\Persistence\BuiltInConfiguration)에서 RemoveInstanceStore.cmd를 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\BuiltInConfiguration`  
  
## <a name="see-also"></a>참고 항목  
 [AppFabric 호스팅 및 지 속성 샘플](http://go.microsoft.com/fwlink/?LinkId=193961)
