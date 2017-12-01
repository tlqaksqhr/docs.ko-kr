---
title: "채용 프로세스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d5fcacbb-c884-4b37-a5d6-02b1b8eec7b4
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1f9f201e14abdcfb98c33e947428137eca3caeaf
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2017
---
# <a name="hiring-process"></a>채용 프로세스
이 샘플에서는 워크플로 서비스로 호스트되는 두 개의 워크플로와 메시징 활동을 사용하여 비즈니스 프로세스를 구현하는 방법을 보여 줍니다. 이 워크플로는 Contoso, Inc라는 가상 회사의 IT 인프라 중 일부입니다.  
  
 `HiringRequest`로 구현된 <xref:System.Activities.Statements.Flowchart> 워크플로 프로세스는 조직에 있는 여러 관리자의 권한 부여를 요구합니다. 이를 위해 워크플로에서는 조직에 있는 다른 기존 서비스를 사용하며 이 샘플에서는 기본 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스로 구현된 조직 데이터 서비스와 받은 편지함 서비스를 사용합니다.  
  
 `ResumeRequest`로 구현된 <xref:System.Activities.Statements.Sequence> 워크플로에서는 Contoso의 외부 채용 웹 사이트에 직원 모집 공고를 게시하고 이력서 접수를 관리합니다. 직원 모집 공고는 마감 시한이 되거나 Contoso의 담당자가 삭제할 때까지 일정 기간 동안 외부 웹 사이트에서 볼 수 있습니다.  
  
 이 샘플에서는 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]의 다음과 같은 기능을 보여 줍니다.  
  
-   비즈니스 프로세스를 모델링하기 위한 <xref:System.Activities.Statements.Flowchart> 및 <xref:System.Activities.Statements.Sequence> 워크플로  
  
-   워크플로 서비스  
  
-   메시징 활동  
  
-   내용 기반 상관 관계  
  
-   사용자 지정 활동(선언적 및 코드 기반)  
  
-   시스템 제공 SQL Server 지속성  
  
-   사용자 지정 <xref:System.Activities.Persistence.PersistenceParticipant>  
  
-   사용자 지정 추적  
  
-   ETW(Windows용 이벤트 추적) 추적  
  
-   활동의 컴퍼지션  
  
-   <xref:System.Activities.Statements.Parallel> 활동  
  
-   <xref:System.Activities.Statements.CancellationScope> 활동  
  
-   지속적인 타이머(<xref:System.Activities.Statements.Delay> 활동)  
  
-   트랜잭션  
  
-   같은 솔루션에 있는 두 개 이상의 워크플로  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Application\HiringProcess`  
  
## <a name="description-of-the-process"></a>프로세스 설명  
 Contoso, Inc.는 부서별 인원수를 엄격하게 통제하려고 합니다. 따라서 담당자가 새로운 채용 프로세스를 시작하려는 경우 항상 실제로 직원을 채용하기 전에 채용 요청 프로세스를 거쳐야 합니다. 채용 프로세스 요청(HiringRequestService 프로젝트에 정의)이라고 하는 이 프로세스는 다음 단계로 구성됩니다.  
  
1.  담당자(요청자)가 채용 프로세스 요청을 시작합니다.  
  
2.  요청자의 관리자가 요청을 승인해야 합니다.  
  
    1.  관리자는 요청을 거부할 수 있습니다.  
  
    2.  관리자는 요청자에게 요청을 반환하여 추가 정보를 요구할 수 있습니다.  
  
        1.  요청자가 요청을 검토한 후 관리자에게 다시 보냅니다.  
  
    3.  관리자는 승인할 수 있습니다.  
  
3.  요청자의 관리자가 승인한 후 부서 소유자가 요청을 승인해야 합니다.  
  
    1.  부서 소유자는 거부할 수 있습니다.  
  
    2.  부서 소유자는 승인할 수 있습니다.  
  
4.  부서 소유자가 승인하면 두 명의 HR 관리자나 CEO가 프로세스를 승인해야 합니다.  
  
    1.  프로세스는 수락 또는 거부 상태로 전환될 수 있습니다.  
  
    2.  프로세스가 수락되면 `ResumeRequest` 워크플로의 새 인스턴스가 시작되고 `ResumeRequest`가 서비스 참조를 통해 HiringRequest.csproj에 연결됩니다.  
  
 관리자가 신입 직원 채용을 승인하면 HR에서 적합한 후보를 찾아야 합니다. 이 프로세스는 두 번째 워크플로(ResumeRequestService.csproj에 정의된`ResumeRequest`)에 의해 수행됩니다. 이 워크플로는 채용 내용을 명시한 직원 모집 공고를 Contoso의 외부 채용 웹 사이트에 전송하는 프로세스를 정의하고, 지원자의 이력서를 받고, 직원 모집 상태를 모니터링합니다. 지원자는 마감 시한이 되거나 Contoso의 담당자가 삭제할 때까지 일정 기간 동안 지원할 수 있습니다. `ResumeRequest` 워크플로는 다음 단계로 구성됩니다.  
  
1.  Contoso 담당자가 채용에 대한 정보와 마감 시한을 입력합니다. 담당자가 이 정보를 입력하면 직원 모집 웹 사이트에 모집 공고가 게시됩니다.  
  
2.  정보를 게시하면 관심 있는 지원자는 이력서를 제출할 수 있습니다. 제출한 이력서는 직원 모집과 연결된 레코드에 저장됩니다.  
  
3.  지원자는 마감 시한이 되거나 Contoso HR 부서 담당자가 프로세스를 중지하여 모집 공고를 삭제할 때까지 이력서를 제출할 수 있습니다.  
  
## <a name="projects-in-the-sample"></a>샘플의 프로젝트  
 다음 표에서는 샘플 솔루션의 프로젝트를 보여 줍니다.  
  
|Project|설명|  
|-------------|-----------------|  
|ContosoHR|데이터 계약, 비즈니스 개체 및 리포지토리 클래스를 포함합니다.|  
|HiringRequestService|채용 요청 프로세스 워크플로의 정의를 포함합니다.<br /><br /> 이 프로젝트는 워크플로(xaml 파일)를 서비스로 자체 호스트하는 콘솔 응용 프로그램으로 구현됩니다.|  
|ResumeRequestService|마감 시한이 되거나 담당자가 프로세스를 중지할 때까지 채용 후보로부터 이력서를 접수하는 워크플로 서비스입니다.<br /><br /> 이 프로젝트는 선언적 워크플로 서비스(xamlx)로 구현됩니다.|  
|OrgService|조직 정보(직원, 직무, 직무 종류 및 부서)를 노출하는 서비스입니다. 이 서비스는 ERP(Enterprise Resource Plan)의 회사 조직 모듈로 생각하면 됩니다.<br /><br /> 이 프로젝트는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스를 노출하는 콘솔 응용 프로그램으로 구현됩니다.|  
|InboxService|직원이 조치 가능한 작업이 들어 있는 받은 편지함입니다.<br /><br /> 이 프로젝트는 WCF 서비스를 노출하는 콘솔 응용 프로그램으로 구현됩니다.|  
|InternalClient|프로세스와 상호 작용하기 위한 웹 응용 프로그램입니다. 사용자는 HiringProcess 워크플로를 시작하고 참여하고 볼 수 있습니다. 사용자는 이 응용 프로그램을 사용하여 ResumeRequest 프로세스를 시작하고 모니터링할 수도 있습니다.<br /><br /> 이 사이트는 Contoso의 인트라넷에 내부적으로 구현되고 이 프로젝트는 ASP.NET 웹 사이트로 구현됩니다.|  
|CareersWebSite|Contoso의 채용 정보를 노출하는 외부 웹 사이트입니다. 지원 의사가 있는 후보는 누구나 이 사이트로 이동하여 이력서를 제출할 수 있습니다.|  
  
## <a name="feature-summary"></a>기능 요약  
 다음 표에는 이 샘플에서 각각의 기능이 사용되는 방식에 대한 설명이 나와 있습니다.  
  
|기능|설명|Project|  
|-------------|-----------------|-------------|  
|Flowchart|비즈니스 프로세스는 순서도로 표현되며, 이 순서도 설명은 화이트보드에 비즈니스를 그리는 방식과 동일하게 프로세스를 표현합니다.|HiringRequestService|  
|워크플로 서비스|프로세스 정의가 포함된 순서도는 서비스에서 호스트됩니다. 이 예에서는 서비스가 콘솔 응용 프로그램에서 호스트됩니다.|HiringRequestService|  
|메시징 활동|순서도는 다음 두 가지 방식으로 메시징 활동을 사용합니다.<br /><br /> 대상 (각 승인 단계에서 결정 사항 및 관련된 정보를 수신) 하는 사용자 로부터 정보를 가져옵니다.<br />대상 (InboxService 및 OrgDataService 서비스 참조를 통해 사용 되는) 다른 기존 서비스와 상호 작용 합니다.|HiringRequestService|  
|내용 기반 상관 관계|승인 메시지는 채용 요청의 ID 속성과 상관 관계가 있습니다.<br /><br /> -프로세스가 시작 되 면 상관 관계 핸들이 요청 ID로 초기화 됩니다.<br />-들어오는 승인 메시지 (각 승인 메시지의 첫 번째 매개 변수는 요청의 ID)의 ID에 연결 합니다.|HiringRequestService/ResumeRequestService|  
|사용자 지정 활동(선언적 및 코드 기반)|이 샘플에는 다음과 같은 몇 가지 사용자 지정 활동이 있습니다.<br /><br /> -   `SaveActionTracking`:이 활동에서 사용자 지정 <xref:System.Activities.Tracking.TrackingRecord> (사용 하 여 <xref:System.Activities.NativeActivityContext.Track%2A>). 이 활동은 <xref:System.Activities.NativeActivity>를 확장하는 명령적 코드를 사용하여 작성되었습니다.<br />-   `GetEmployeesByPositionTypes`:이 활동은 직무 종류 Id 목록을 받아 Contoso에서 해당 직무를가지고 있는 직원의 목록을 반환 합니다. 이 활동은 활동 디자이너를 사용하여 선언적으로 작성되었습니다.<br />-   `SaveHiringRequestInfo`:이 활동의 정보를 저장 한 `HiringRequest` (사용 하 여 `HiringRequestRepository.Save`). 이 활동은 <xref:System.Activities.CodeActivity>를 확장하는 명령적 코드를 사용하여 작성되었습니다.|HiringRequestService|  
|시스템 제공 SQL Server 지속성|순서도 프로세스 정의를 호스트하는 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 인스턴스는 시스템 제공 SQL Server 지속성을 사용하도록 구성됩니다.|HiringRequestService/ResumeRequestService|  
|사용자 지정 추적|샘플에는 `HiringRequestProcess`의 기록을 저장하는 사용자 지정 추적 참가자가 포함되어 있으며, 이 참가자는 어떤 조치가 취해졌는지와 조치를 취한 사람 및 시기를 기록합니다. 소스 코드는 HiringRequestService의 Tracking 폴더에 있습니다.|HiringRequestService|  
|ETW 추적|시스템 제공 ETW 추적은 HiringRequestService 서비스의 App.config 파일에 구성되어 있습니다.|HiringRequestService|  
|활동의 컴퍼지션|프로세스 정의는 <xref:System.Activities.Activity>의 자유 컴퍼지션을 사용합니다. 순서도에는 다른 활동과 함께 여러 개의 시퀀스 활동 및 병렬 활동이 포함되어 있습니다.|HiringRequestService|  
|병렬 활동|-   <xref:System.Activities.Statements.ParallelForEach%601>(두 명의 HR 관리자의 승인 단계를 기다리는 중) 병렬로 CEO 및 HR 관리자의 수신함에 등록 하는 데 사용 됩니다.<br />-   <xref:System.Activities.Statements.Parallel>완료 됨 및 거부 된 단계에서 몇 가지 정리 작업을 수행 하는 데 사용|HiringRequestService|  
|모델 취소|순서도는 <xref:System.Activities.Statements.CancellationScope>를 사용하여 취소 동작을 만들며, 몇 가지 정리 작업을 수행합니다.|HiringRequestService|  
|고객 지속성 참가자|`HiringRequestPersistenceParticipant`는 워크플로 변수의 데이터를 Contoso HR 데이터베이스에 저장된 테이블에 저장합니다.|HiringRequestService|  
|워크플로 서비스|`ResumeRequestService`는 워크플로 서비스를 사용하여 구현됩니다. 워크플로 정의와 서비스 정보는 ResumeRequestService.xamlx에 포함되어 있습니다. 서비스는 지속성과 추적을 사용하도록 구성됩니다.|ResumeRequestService|  
|지속적인 타이머|`ResumeRequestService`는 지속적인 타이머를 사용하여 직원 모집 공고 기간을 정의하며 직원 모집 공고는 마감 시한이 되면 마감됩니다.|ResumeRequestService|  
|트랜잭션|<xref:System.Activities.Statements.TransactionScope>는 새 이력서를 받는 경우 몇 가지 활동 실행 내에서 데이터의 일관성을 유지하는 데 사용됩니다.|ResumeRequestService|  
|트랜잭션|사용자 지정 지속성 참가자(`HiringRequestPersistenceParticipant`)와 사용자 지정 추적 참가자(`HistoryFileTrackingParticipant`)는 같은 트랜잭션을 사용합니다.|HiringRequestService|  
|[!INCLUDE[wf1](../../../../includes/wf1-md.md)] 응용 프로그램에서 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]을 사용합니다.|두 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램에서 워크플로에 액세스합니다.|InternalClient/CareersWebSite|  
  
## <a name="data-storage"></a>데이터 저장소  
 데이터는 `ContosoHR`이라는 SQL Server 데이터베이스에 저장되며, 이 데이터베이스를 만드는 데 사용되는 스크립트는 `DbSetup` 폴더에 있습니다. 워크플로 인스턴스는 `InstanceStore`라는 SQL Server 데이터베이스에 저장되며, 인스턴스 저장소를 만드는 데 사용되는 스크립트는 [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] 배포의 일부입니다.  
  
 두 데이터베이스 모두 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 명령 프롬프트에서 Setup.cmd 스크립트를 실행하여 만들어집니다.  
  
## <a name="running-the-sample"></a>샘플 실행  
  
#### <a name="to-create-the-databases"></a>데이터베이스를 만들려면  
  
1.  [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 명령 프롬프트를 엽니다.  
  
2.  샘플 폴더로 이동합니다.  
  
3.  Setup.cmd.를 실행합니다.  
  
4.  SQL Express에서 `ContosoHR` 및 `InstanceStore` 데이터베이스가 만들어졌는지 확인합니다.  
  
#### <a name="to-set-up-the-solution-for-execution"></a>실행할 솔루션을 설치하려면  
  
1.  관리자 권한으로 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]을 실행합니다. HiringRequest.sln을 엽니다.  
  
2.  솔루션을 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택 **속성**합니다.  
  
3.  옵션을 선택 **여러 개의 시작 프로젝트** 설정 하 고는 **CareersWebSite**, **InternalClient**, **HiringRequestService**, 및 **ResumeRequestService** 를 **시작**합니다. 둡니다 **ContosoHR**, **InboxService**, 및 **OrgService** n o n입니다.  
  
4.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다. 빌드가 성공적으로 수행되었는지 확인합니다.  
  
#### <a name="to-run-the-solution"></a>솔루션을 실행하려면  
  
1.  솔루션을 빌드한 후 Ctrl+F5를 눌러 디버깅 없이 실행합니다. 모든 서비스가 시작되었는지 확인합니다.  
  
2.  마우스 오른쪽 단추로 클릭 **InternalClient** 선택 고 솔루션에서 **브라우저에서 보기**합니다. `InternalClient`의 기본 페이지가 표시됩니다. 서비스가 실행되고 있는지 확인한 다음 링크를 클릭합니다.  
  
3.  **HiringRequest** 모듈이 표시 됩니다. 여기에서 자세히 설명된 시나리오를 따르면 됩니다.  
  
4.  `HiringRequest`가 완료되면 `ResumeRequest`를 시작할 수 있습니다. 여기에서 자세히 설명된 시나리오를 따르면 됩니다.  
  
5.  `ResumeRequest`가 게시되면 공용 웹 사이트인 Contoso 직원 채용 사이트에서 볼 수 있습니다. 직원 모집 공고 내용을 보고 지원하려면 직원 채용 사이트로 이동합니다.  
  
6.  마우스 오른쪽 단추로 클릭 **CareersWebSite** 고 솔루션에서 **브라우저에서 보기**합니다.  
  
7.  로 돌아가 `InternalClient` 마우스 오른쪽 단추로 클릭 하 여 **InternalClient** 솔루션에서 선택 하 고 **브라우저에서 보기**합니다.  
  
8.  이동 하는 **job Postings** 클릭 하 여 섹션은 **Job Postings** 받은 편지함 최상위 메뉴에 링크 합니다. 여기에서 자세히 설명된 시나리오를 따르면 됩니다.  
  
## <a name="scenarios"></a>시나리오  
  
### <a name="hiring-request"></a>채용 요청  
  
1.  Michael Alexander(소프트웨어 엔지니어)는 C# 업무 경력이 3년 이상인 Software Engineer in Test(SDET)를 엔지니어링 부서에 채용하기 위해 새로운 직무를 요청하려고 합니다.  
  
2.  만든 후 요청 Michael의 받은 편지함에 표시 (클릭 **새로 고침** 요청이 표시 되지 않으면) Michael의 관리자 인 Peter Brehm의 승인을 기다리는 합니다.  
  
3.  Peter는 Michael의 요청에 대한 조치를 취하려고 합니다. Peter는 직무에 C# 사용 경력이 3년이 아닌 5년 경력이 필요하다고 판단하고 자신의 의견을 다시 보내 검토하도록 합니다.  
  
4.  Michael은 받은 편지함에서 관리자가 보낸 메시지를 확인하고 조치를 취하려고 합니다. Michael은 직무 요청 기록을 확인한 후 Peter의 의견에 동의합니다. Michael은 C# 경력 5년이 필요하다는 내용으로 설명을 수정하고 수정 내용을 수락합니다.  
  
5.  Peter는 Michael이 수정한 요청에 대한 조치를 취한 후 수락합니다. 이제 엔지니어링 부서 책임자인 Tsvi Reiter가 이 요청을 승인해야 합니다.  
  
6.  Tsvi Reiter는 요청을 신속하게 처리하려고 하기 때문에 긴급 요청이라는 내용을 메모에 포함하고 요청을 수락합니다.  
  
7.  이제 두 명의 HR 관리자나 CEO가 요청을 승인해야 합니다. CEO인 Brian Richard Goldstein은 Tsvi의 긴급 요청을 확인한 후 요청을 수락하고 두 명의 HR 관리자의 승인을 건너뛰어 요청에 대한 조치를 취합니다.  
  
8.  이제 이 요청은 Michael의 받은 편지함에서 제거되고 SDET 채용 프로세스가 시작되었습니다.  
  
### <a name="start-resume-request"></a>이력서 요청 시작  
  
1.  이제는 작업 대기 중 이며 외부 웹 사이트에 게시 될 수 (클릭 하면 볼 수는 **Job Postings** 링크)입니다. 현재 직무를 종료하고 게시하는 HR 담당자가 직무에 대한 처리를 담당합니다.  
  
2.  HR 직무를 편집 하려고 (클릭 하 여는 **편집** 링크) 60 분의 제한 시간을 설정 하 여 (실제로이 일 수 며칠 또는 몇 주). 시간 제한을 통해 지정한 시간에 따라 외부 웹 사이트에서 직무를 중단할 수 있습니다.  
  
3.  편집한 직무를 저장 한 후에 표시 된 **Receiving Resumes** 탭 (새 작업 위치를 확인 하려면 웹 페이지 새로 고침).  
  
### <a name="collecting-resumes"></a>이력서 접수  
  
1.  외부 웹 사이트에 직무가 표시되어야 합니다. 구직하려는 지원자는 이 직무에 지원하고 이력서를 제출할 수 있습니다.  
  
2.  Job Postings List 서비스로 돌아가면를 볼 수 있습니다"이력서" 지금까지 수집 된입니다.  
  
3.  HR에서는 적합한 지원자를 찾은 때와 같은 경우 이력서 접수를 중지할 수도 있습니다.  
  
## <a name="troubleshooting"></a>문제 해결  
  
1.  관리자 권한으로 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]을 실행 중인지 확인합니다.  
  
2.  솔루션이 제대로 빌드되지 않으면 다음 내용을 확인합니다.  
  
    -   에 대 한 참조 `ContosoHR` 에서 누락 되지 않았는지는 `InternalClient` 또는 `CareersWebSite` 프로젝트.  
  
3.  솔루션이 제대로 실행되지 않으면 다음 내용을 확인합니다.  
  
    1.  모든 서비스가 실행되고 있는지 여부  
  
    2.  서비스 참조가 업데이트되었는지 여부  
  
        1.  App_WebReferences 폴더를 엽니다.  
  
        2.  마우스 오른쪽 단추로 클릭 **Contoso** 선택 **웹/서비스 참조 업데이트**합니다.  
  
        3.  [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]에서 Ctrl+Shift+B를 눌러 솔루션을 다시 빌드합니다.  
  
## <a name="uninstalling"></a>제거  
  
1.  DbSetup 폴더에 있는 Cleanup.bat를 실행하여 SQL Server 인스턴스 저장소를 삭제합니다.  
  
2.  하드 드라이브에서 소스 코드를 삭제합니다.