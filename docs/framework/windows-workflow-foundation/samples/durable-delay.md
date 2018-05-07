---
title: Durable Delay
ms.date: 03/30/2017
ms.assetid: 220ec240-b958-430c-81ff-b734a6aa97ae
ms.openlocfilehash: 5307b8144e17f91cd3ba8c2e385492f86c167820
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="durable-delay"></a>Durable Delay
이 샘플에서는 지속적 지연을 사용하는 방법을 보여 줍니다. 지속적 지연은 지연되는 동안 워크플로를 영구적인 장치에 유지하는 지연입니다. 샘플 워크플로에는 지연으로 구분되는 콘솔 대상의 두 메시지가 포함되어 있습니다. 지연이 트리거되면 워크플로가 언로드된 다음 메모리에 다시 로드되기 전에 워크플로 인스턴스 저장소에서 5초 동안 기다립니다.  
  
## <a name="workflow-details"></a>워크플로 세부 정보  
 워크플로 서비스 호스트에서는 워크플로를 호스트할 뿐 아니라 워크플로 인스턴스를 로드하거나 언로드하여 워크플로 인스턴스를 관리합니다. 워크플로 정의의 인스턴스를 시작하기 위해 이 샘플에서는 워크플로의 <xref:System.ServiceModel.Activities.Receive> 활동에 메시지를 보내는 프록시를 설정합니다. <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> 속성이 `true`로 설정되어 있으므로 이 활동에서는 메시지를 받으면 워크플로의 새 인스턴스를 만들 수 있습니다.  
  
 다음 목록에서는 초기화 중 워크플로 서비스에 의한 설정 과정을 자세히 설명합니다.  
  
1.  주소는 서비스 호스트를 만듭니다 (http://localhost:8080/Client)합니다.  
  
2.  워크플로 내의 <xref:System.ServiceModel.Activities.Receive> 활동과 통신할 수 있도록 서비스 호스트에 끝점을 만듭니다.  
  
3.  SQL 인스턴스 저장소를 설정합니다.  
  
4.  워크플로 서비스 호스트에서 워크플로 인스턴스를 SQL 지속성 저장소로 언로드할 조건을 지정하는 언로드 인스턴스 동작을 추가합니다. 이 샘플의 경우 지연이 트리거되어 워크플로가 유휴 상태가 되는 직후 인스턴스를 언로드합니다.  
  
5.  워크플로의 <xref:System.ServiceModel.Activities.Receive> 활동에 메시지를 보내는 프록시를 만듭니다.  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  지속성 데이터베이스를 설치합니다.  
  
    1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 명령 프롬프트를 엽니다.  
  
    2.  로 이동 된 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 디렉터리 (C:\Windows\Microsoft.NET\Framework\v4 합니다. X\\).  
  
    3.  WorkflowManagementService.exe.config 파일을 편집하고 다음 연결 문자열을 <`database`> 요소 내에 추가합니다.  
  
        ```xml  
        <database connectionString="Data Source=localhost\SQLEXPRESS;Initial Catalog=DefaultSampleStore;Integrated Security=True;Asynchronous Processing=True" />  
        ```  
  
    4.  DurableDelay\CS 디렉터리로 이동합니다.  
  
    5.  Setup.cmd.를 실행합니다.  
  
2.  실행 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 마우스 오른쪽 단추로 클릭 하 여 승격 된 권한을 사용 하는 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 아이콘을 선택 하면 **관리자 권한으로 실행**합니다.  
  
3.  Delay.sln 솔루션 파일을 엽니다.  
  
4.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
5.  Ctrl+F5를 눌러 솔루션을 실행합니다.  
  
#### <a name="to-uninstall-this-sample"></a>이 샘플을 제거하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 명령 프롬프트를 엽니다.  
  
2.  DurableDelay\CS 디렉터리로 이동합니다.  
  
3.  Cleanup.cmd를 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelay`