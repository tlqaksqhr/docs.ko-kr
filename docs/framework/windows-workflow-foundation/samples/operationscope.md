---
title: "OperationScope | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 56206a21-1e63-422d-b92a-e5d8b713e707
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# OperationScope
이 샘플에서는 메시징 활동, <xref:System.ServiceModel.Activities.Receive> 및 <xref:System.ServiceModel.Activities.SendReply>를 사용하여 기존 사용자 지정 활동을 워크플로 서비스에 작업으로 노출하는 방법을 보여 줍니다.이 샘플에는 `OperationScope`라는 새 사용자 지정 활동이 포함되어 있습니다.이 활동을 사용하면 사용자가 작업 본문을 사용자 지정 활동과 별도로 작성한 다음 `OperationScope` 활동을 사용하여 해당 작업을 서비스 작업으로 쉽게 노출할 수 있도록 하여 워크플로 서비스를 쉽게 개발할 수 있습니다.예를 들어 두 `in` 인수를 사용하고 하나의 `out` 인수를 반환하는 사용자 지정 `Add` 활동을 `OperationScope`로 끌어 놓아 워크플로 서비스에 `Add` 작업으로 노출할 수 있습니다.  
  
 범위는 본문으로 제공된 활동을 검사하는 방식으로 작동합니다.바인딩되지 않은 `in` 인수는 모두 들어오는 메시지의 입력으로 간주됩니다.모든 `out` 인수는 바인딩되어 있는지 여부에 관계없이 이후 회신 메시지의 출력으로 간주됩니다.노출된 작업의 이름은 `OperationScope` 활동의 표시 이름에서 가져온 것입니다.본문 활동이 활동 인수에 바인딩된 메시지의 매개 변수를 사용하여 <xref:System.ServiceModel.Activities.Receive> 및 <xref:System.ServiceModel.Activities.SendReply>에 래핑되는 것이 최종 결과입니다.  
  
 이 샘플에서는 HTTP 끝점을 사용하여 워크플로 서비스를 노출합니다.실행하려면 적절한 URL ACL을 추가해야 합니다.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Configuring HTTP and HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353)를 참조하십시오.고급 명령 프롬프트에서 다음 명령을 실행하면 적절한 ACL이 추가됩니다. %DOMAIN%\\%UserName% 대신 해당 도메인과 사용자 이름을 사용하는지 확인하십시오.  
  
 **netsh http add urlacl url\=http:\/\/\+:8000\/ user\=%DOMAIN%\\%UserName%**  
  
### 이 샘플을 실행하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 OperationScope.sln 솔루션을 엽니다.  
  
2.  솔루션 탐색기에서 솔루션을 마우스 오른쪽 단추로 클릭하고 **시작 프로젝트 설정**을 선택하여 여러 시작 프로젝트를 설정합니다.Scenario와 Scenario\_Client를 차례로 여러 시작 프로젝트로 추가합니다.  
  
3.  Ctrl\+Shift\+B를 눌러 솔루션을 빌드합니다.  
  
    > [!WARNING]
    >  이 단계는 사용자 지정 활동 `OperationScope`로 인해 BankService.xaml 워크플로를 보는 데 필요합니다.  
  
4.  Ctrl\+F5를 눌러 응용 프로그램을 실행합니다.Scenario\_Client 콘솔에서 입력하라는 메시지가 표시되고 해당 출력은 Scenario 콘솔에 표시됩니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\OperationScope`  
  
## 참고 항목