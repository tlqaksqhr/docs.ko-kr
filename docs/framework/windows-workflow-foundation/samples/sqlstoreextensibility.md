---
title: SQLStoreExtensibility
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5da1b5a3-f144-41ba-b9c4-02818b28b15d
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e3e63a11ce87c95a5afc8e7f60c8e262da5c6bd1
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="sqlstoreextensibility"></a>SQLStoreExtensibility
이 샘플에서는 SQL 워크플로 인스턴스 저장소에서 승격된 속성을 사용하고 구성하는 방법을 보여 줍니다. SQL 워크플로 인스턴스 저장소는 인스턴스 저장소의 SQL 기반 구현이며, 이 저장소를 사용하면 인스턴스가 SQL Server 또는 SQL Server Express 데이터베이스 간에 인스턴스 상태를 저장하고 로드할 수 있습니다. 저장소 확장성 기능을 사용하면 사용자가 인스턴스 저장소에 저장되는 속성을 정의할 수 있습니다. 이러한 속성은 승격된 속성 뷰에 표시되며 사용자는 이 뷰에서 속성을 쿼리할 수 있습니다.  
  
 이 샘플은 계산 서비스를 구현하는 워크플로로 구성되어 있습니다. 서비스의 시작 메서드를 호출하면 서비스는 0부터 29까지 계산합니다. 카운터는 2초 간격으로 증가하고, 각 계산 후에 워크플로가 지속됩니다. 현재 카운터 값은 인스턴스 저장소에 승격된 속성으로 저장됩니다.  
  
 계산 워크플로는 워크플로 서비스 호스트에서 자체 호스트합니다. 프로그램의 `Main` 메서드는 다음 동작을 수행합니다.  
  
-   계산 워크플로를 호스트하는 워크플로 서비스 호스트의 인스턴스를 만들고 계산 워크플로가 도달할 수 있는 끝점을 정의합니다.  
  
-   SQL 워크플로 인스턴스 저장소를 구성하는 데 사용되는 SQL 워크플로 인스턴스 저장소 동작을 정의합니다. `CountStatus`를 승격된 속성으로 처리하도록 저장소에 지시합니다.  
  
-   계산 워크플로의 시작 메서드를 호출하는 클라이언트를 만듭니다.  
  
 프로그램을 시작하면 카운터가 자동으로 계산을 시작합니다. 인스턴스를 로드하고 SQL 워크플로 인스턴스 저장소를 구성하는 데는 몇 초 정도 걸릴 수 있습니다.  
  
 카운터 값을 사용자 지정 속성으로 승격하려면 다음 단계를 수행해야 합니다.  
  
1.  클래스 `CounterStatus`는 작업이 상태 변수를 제공하는 데 사용하는 <xref:System.Activities.Persistence.PersistenceParticipant> 형식의 인스턴스 확장을 정의합니다. `Count`는 쓰기 전용 값으로 정의됩니다. 워크플로 인스턴스가 유지 지점에 도달할 경우 인스턴스 확장은 `Count` 속성을 지속성 데이터 컬렉션에 저장합니다.  
  
2.  인스턴스 저장소를 만들 때 새 속성인 `CountStatus`는 `store.Promote()` 메서드를 통해 정의됩니다.  
  
3.  워크플로의 `SaveCounter` 활동은 현재 카운터 값을 `Count` 상태 필드에 할당합니다.  
  
### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  인스턴스 저장소 데이터베이스를 만듭니다.  
  
    1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 명령 프롬프트를 엽니다.  
  
    2.  샘플 디렉터리(\WF\Basic\Persistence\SqlStoreExtensibility\CS)로 이동하고 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 명령 프롬프트에서 CreateInstanceStore.cmd를 실행합니다.  
  
        > [!WARNING]
        >  CreateInstanceStore.cmd 스크립트가 SQL Server 2008 Express의 기본 인스턴스에 데이터베이스를 만들려고 시도합니다. 다른 인스턴스에 데이터베이스를 설치하려면 스크립트를 수정합니다.  
  
2.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 열고 SqlStoreExtensibility.sln 솔루션을 로드한 다음 Ctrl+Shift+B 키를 눌러 솔루션을 빌드합니다.  
  
    > [!WARNING]
    >  SQL Server의 기본 인스턴스가 아닌 인스턴스에 데이터베이스를 설치한 경우 솔루션을 빌드하기 전에 코드에서 연결 문자열을 업데이트합니다.  
  
3.  프로젝트의 bin 디렉터리 (\WF\Basic\Persistence\SqlStoreExtensibility\bin\Debug)로 이동 하 여 관리자 권한으로 샘플을 실행 [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]SqlStoreExtensibility.exe를 마우스 오른쪽 단추로 클릭 하 고 선택 하면 **계정으로 실행 관리자**합니다.  
  
### <a name="to-verify-the-sample-is-working-correctly"></a>샘플이 올바르게 작동하고 있는지 확인하려면  
  
1.  SQL Server Management Studio를 사용 하 여 선택 하 여 인스턴스 테이블의 내용을 보려면 **데이터베이스**, **InstanceStore**, 차례로  **System.ServiceModel.Activities.DurableInstancing.InstanceTable** 개체 탐색기에서 마우스 오른쪽 단추로 클릭 **System.ServiceModel.Activities.DurableInstancing.InstanceTable** 선택 **상위 1000 개 행 선택**합니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]SQL Server Management Studio 참조 [SQL Server Management Studio 소개](http://go.microsoft.com/fwlink/?LinkId=165645)  
  
2.  나열된 워크플로 인스턴스를 확인합니다.  
  
3.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 명령 프롬프트에서 샘플 디렉터리(\WF\Basic\Persistence\SqlStoreExtensibility)에 있는 QueryInstanceStore.cmd 스크립트를 실행합니다.  
  
4.  아래 표시 된 카운터 값을 관찰 **CountStatus**합니다.  
  
5.  스크립트를 여러 번 실행 볼 수는 **CountStats** 값 변경 합니다.  
  
6.  Enter 키를 눌러 워크플로 응용 프로그램을 종료합니다.  
  
### <a name="to-uninstall-the-sample"></a>샘플을 제거하려면  
  
1.  샘플 디렉터리(\WF\Basic\Persistence\SqlStoreExtensibility)에 있는 RemoveInstanceStore.cmd 스크립트를 실행하여 인스턴스 저장소 데이터베이스를 제거합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\SQLStoreExtensibility`  
  
## <a name="see-also"></a>참고 항목  
 [워크플로 유지](../../../../docs/framework/windows-workflow-foundation/workflow-persistence.md)  
 [워크플로 서비스](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [AppFabric 호스팅 및 지 속성 샘플](http://go.microsoft.com/fwlink/?LinkId=193961)
