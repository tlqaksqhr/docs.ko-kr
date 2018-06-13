---
title: WorkflowApplication ReadLine 호스트
ms.date: 03/30/2017
ms.assetid: f7b362be-cb42-40d7-b9ef-cfc4aed2455b
ms.openlocfilehash: 8da8a5bb4c80a86fe5ae9e133ea545c00ee17fba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33518540"
---
# <a name="workflowapplication-readline-host"></a>WorkflowApplication ReadLine 호스트
이 샘플은 제네릭 ReadLine 호스트입니다. 포함된 `ReadLine` 활동(또는 문자열을 사용하여 다시 시작된 책갈피에서 데이터를 가져오는 활동과 같은 기타 활동)을 사용하여 워크플로를 로드하고 실행할 수 있습니다. `WriteLine` 활동의 출력이나 <xref:System.Activities.Statements.WriteLine.TextWriter%2A> 확장에 기록하는 내용은 호스트 창에 표시됩니다. 유휴 상태인 인스턴스에 사용할 수 있는 책갈피는 콤보 상자에 나타납니다. 책갈피를 선택하고 텍스트를 입력한 다음 책갈피 다시 시작 단추를 누르면 워크플로 실행이 계속됩니다. 선택한 워크플로를 취소하거나 중단하거나 종료할 수도 있습니다. 기본적으로 지속성이 설정되어 있으므로, 호스트를 종료하고 다시 가져올 수 있으며 인스턴스 목록은 데이터베이스에 저장된 인스턴스로 채워집니다. 추적 기능은 활동 수준에 자세한 추적을 추가하는 옵션을 사용하여 <xref:System.Activities.WorkflowApplication> 수준 이벤트를 호스트에 출력하는 데 사용됩니다.   
  
## <a name="sample-details"></a>샘플 세부 정보  
 이 호스트에는 뷰와 인스턴스 관리자라는 두 계층이 있습니다. 뷰는 `HostView` 및 `WorkflowApplicationInfo` 클래스로 구성됩니다. 이 호스트의 일반 패턴은 `HostView` 클래스가 `WorkflowApplicationInfo` 개체에서 표시하는 인스턴스와의 동기화 상태가 적절하게 유지되는 해당 개체를 기반으로 사용자에게 사용 가능한 옵션을 표시하는 데 사용됩니다. 인스턴스 관리자 계층은 모든 호스트 통신의 핵심인 `WorkflowApplicationManager` 클래스와 인스턴스 및 인스턴스가 시작된 프로그램 정의 간 관계를 유지하는 `WorkflowDefinitionExtension` 클래스와 그 외 몇 가지 클래스로 구성됩니다. `HostView`는 `WorkflowApplicationManager`에서 제어 작업을 호출합니다. 응답 사용자 인터페이스를 유지하기 위하여 이러한 호출은 일반적으로 비동기 호출입니다. 비동기 호출이 완료되면 `WorkflowApplicationManager`는 잘 정의된 인터페이스(`IHostView`)를 통해 뷰 계층을 다시 호출합니다. `HostView` 클래스는 이러한 호출을 `WorkflowApplicationManager` 클래스에서 사용자 인터페이스 스레드로 가장 자주 디스패치합니다.  텍스트 작성은 <xref:System.Activities.Statements.WriteLine.TextWriter%2A> 클래스에서 제공하는 스레드로부터 안전한 `HostView` 개체에 대해 수행됩니다. 사용자 인터페이스를 통해서만 이벤트가 생성되는 것은 아닙니다. 예를 들어 <xref:System.Activities.WorkflowApplication> 개체도 `WorkflowApplicationManager`, `Idle` 또는 `Complete` 상태가 되면 `Aborted`에 알립니다. `WorkflowApplicationManager` 클래스는 정리를 디스패치하거나 호스트에 대한 작업을 업데이트하여 이벤트 스레드에서 벗어납니다.  
  
 <xref:System.Activities.WorkflowApplication>을 시작하는 데 사용된 파일을 기록하는 작업은 `WorkflowDefinitionExtension` 클래스를 통해 쉽게 수행할 수 있습니다. 이 클래스는 지속성에 참가하고 워크플로 정의에 대한 경로를 유지하도록 <xref:System.Activities.Persistence.PersistenceIOParticipant> 인터페이스를 구현합니다.  
  
 `WorkflowApplicationManager.Load` 메서드는 저장된 경로를 사용하여 완료되지 않은 <xref:System.Activities.WorkflowApplication> 개체를 로드하는 데 필요한 워크플로 프로그램을 인스턴스화합니다.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  이 샘플을 실행하려면 SQL Express가 설치되어 있어야 하며, SQL Express는 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에 포함되어 있습니다.  
  
2.  Visual Studio 2010 명령 프롬프트를 엽니다.  
  
3.  샘플 디렉터리(\WF\Basic\Execution\ControllingWorkflowApplications)로 이동하여 CreateInstanceStore.cmd를 실행합니다.  
  
4.  CreateInstanceStore.cmd 스크립트가 SQL Server 2008 Express의 기본 인스턴스에 데이터베이스를 만들려고 시도합니다. 다른 인스턴스에 데이터베이스를 설치하려면 스크립트를 수정합니다.  
  
5.  WorkflowApplicationReadLineHost 프로젝트를 컴파일한 다음 명령줄에서 이 프로젝트를 실행합니다.  
  
6.  실행한 후 지속성을 설정하거나 해제할 수 있습니다. 또한 자세한 활동 추적 기능도 설정하거나 해제할 수 있습니다.  
  
7.  옆에 있는 줄임표 단추를 눌러는 **실행** XAML 파일에 정의 된 워크플로에 대 한 찾아보기 단추  
  
     SampleWorkflows 폴더에 두 개의 샘플이 있습니다. parallel1.xaml 예제는 유휴 상태가 됩니다.  
  
8.  예를 선택한 후 키를 눌러는 **실행** 단추입니다.  
  
9. 워크플로가 유휴 상태가 되 면 하는 경우는 **책갈피** 콤보 상자가 사용 가능한 책갈피로 채워집니다.  
  
10. 이때 책갈피를 다시 시작하거나 워크플로를 취소, 중단 또는 종료할 수 있습니다. 호스트를 종료한 후 다시 시작할 수도 있습니다. 지속성이 설정되어 있으면 종료할 때 인스턴스가 언로드되고 시작할 때 다시 로드됩니다.  
  
     책갈피를 다시 시작 하려면 원하는 책갈피를 선택, 콤보 상자 및 키를 눌러 옆에 있는 텍스트 상자에 값을 입력 **책갈피 다시 시작**합니다.  
  
#### <a name="to-remove-the-instance-store-database"></a>인스턴스 저장소 데이터베이스를 제거하려면  
  
1.  Visual Studio 2010 명령 프롬프트를 엽니다.  
  
2.  샘플 디렉터리(\WF\Basic\Execution\ControllingWorkflowApplications)로 이동하여 RemoveInstanceStore.cmd를 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\ControllingWorkflowApplications`