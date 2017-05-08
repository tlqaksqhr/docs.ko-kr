---
title: "트랜잭션 범위 무시 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 49fb6dd4-30d4-4067-925c-c5de44c8c740
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# 트랜잭션 범위 무시
이 샘플에서는 앰비언트 런타임 트랜잭션이 있는 경우 이 트랜잭션을 표시하지 않도록 사용자 지정 `SuppressTransactionScope` 활동을 작성하는 방법을 보여 줍니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\SuppressTransactionScope`  
  
## 샘플 세부 정보  
 사용자 지정 활동은 트랜잭션 흐름이 특정 시나리오에 대해 문제가 있는 경우 트랜잭션을 다른 서비스로 이동하지 못하도록 하는 데 유용합니다.워크플로 런타임에는 <xref:System.Activities.NativeActivity> 클래스에 앰비언트 트랜잭션을 표시하지 못하게 하기 위한 기본 제공 지원이 있지만 이 지원을 사용하려면 이 샘플에 있는 것과 같은 사용자 지정 <xref:System.Activities.NativeActivity>를 작성해야 합니다.  
  
 시나리오는 세 부분으로 구성되어 있습니다.먼저 <xref:System.Activities.Statements.TransactionScope>가 앰비언트 트랜잭션이 되는 런타임 트랜잭션을 만듭니다.이 트랜잭션은 트랜잭션의 로컬 및 분산 식별자를 출력하는 사용자 지정 활동에 의해 확인됩니다.그런 다음 두 번째 부분을 시작하기 전에 이 트랜잭션이 원격 서비스로 이동됩니다.두 번째 부분이 진행되는 동안 워크플로는 `SuppressTransactionScope`를 시작하고 트랜잭션 식별자를 출력하고 트랜잭션을 이동하는 프로세스를 다시 반복합니다.그러나 사용자 지정 활동은 앰비언트 트랜잭션을 찾지 않고 서비스로 이동된 메시지에는 트랜잭션이 포함되어 있지 않습니다.결과적으로 서비스는 트랜잭션을 만들며, 이는 클라이언트와 서비스에서 출력된 분산 ID가 일치하지 않음을 의미합니다.마지막 부분은 `SuppressTransactionScope`가 종료된 후 발생하며, 다른 메시지에서 첫 번째 메시지의 식별자와 일치하는 분산 식별자를 가진 서비스로 확인될 때 런타임 트랜잭션이 다시 앰비언트 트랜잭션이 됩니다.  
  
 활동이 자식 활동을 예약하고 실행 속성을 추가해야 하기 때문에 활동 자체는 <xref:System.Activities.NativeActivity>에서 파생됩니다.`SuppressTransactionScope`에는 핸들이 초기화되어야 하기 때문에 <xref:System.Activities.RuntimeTransactionHandle> 형식의 인스턴스 필드 대신 사용되어야 하는 <xref:System.Activities.RuntimeTransactionHandle> 형식의 <xref:System.Activities.Variable>이 있습니다.`Variable<RuntimeTransactionHandle>`은 내부적으로만 사용되므로 활동 메타데이터에 구현 변수로 추가됩니다.  
  
 활동을 실행하면 활동은 먼저 본문이 지정되었는지 여부를 확인하고 지정되었으면 <xref:System.Activities.RuntimeTransactionHandle>에서 `SuppressTransaction` 속성을 설정합니다.설정한 속성은 실행 속성에 추가되고 앰비언트 속성이 됩니다.즉, `SuppressTransactionScope`의 자식인 모든 활동이 속성을 볼 수 있으므로 런타임 트랜잭션을 표시하지 않도록 적용하고 중첩된 <xref:System.Activities.Statements.TransactionScope>에서 예외를 throw하도록 합니다.핸들을 실행 속성에 추가하면 본문이 실행되도록 예약됩니다.  
  
#### 이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 SuppressTransactionScope.sln 솔루션을 엽니다.  
  
2.  솔루션을 빌드하려면 Ctrl\+Shift\+B를 누르거나 **빌드** 메뉴에서 **솔루션 빌드**를 선택합니다.  
  
3.  성공적으로 빌드되면 솔루션을 마우스 오른쪽 단추로 클릭하고 **시작 프로젝트 설정**을 선택합니다.대화 상자에서 **여러 개의 시작 프로젝트**를 선택하고 두 프로젝트의 동작이 **시작**으로 설정되어 있는지 확인합니다.  
  
4.  F5 키를 누르거나 **디버그** 메뉴에서 **디버깅 시작**을 선택합니다.또는 Ctrl\+F5를 누르거나 **디버그** 메뉴에서 **디버깅하지 않고 시작**을 선택하여 디버깅 없이 실행할 수도 있습니다.  
  
    > [!NOTE]
    >  클라이언트를 시작하기 전에 서버를 실행해야 합니다.서비스를 호스팅하는 콘솔 창의 출력을 통해 서비스가 시작되었음을 알 수 있습니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\SuppressTransactionScope`  
  
## 참고 항목