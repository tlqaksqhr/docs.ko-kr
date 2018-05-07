---
title: 워크플로 서비스에 보안 설정
ms.date: 03/30/2017
ms.assetid: 53f84ad5-1ed1-4114-8d0d-b12e8a021c6e
ms.openlocfilehash: ac02b5ffcfc14ea4aab9e8aafd5f6a4cbcdef3b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="securing-workflow-services"></a>워크플로 서비스에 보안 설정
보안 워크플로 서비스 샘플에서는 다음 절차를 보여 줍니다.  
  
-   <xref:System.ServiceModel.Activities.Receive> 및 <xref:System.ServiceModel.Activities.SendReply> 활동을 사용하여 기본 워크플로 서비스 만들기  
  
-   Windows Communication Foundation (WCF) 구성을 사용 하 여 워크플로 서비스에서 사용할 보안 끝점을 정의할 수 있습니다.  
  
-   사용자 지정 정책 내부에 클레임을 만들고 <xref:System.ServiceModel.ServiceAuthorizationManager>를 사용하여 클레임의 유효성 검사  
  
## <a name="demonstrates"></a>세부 항목  
 WCF 보안(클레임 기반 권한 부여)을 사용하여 클라이언트와 워크플로 서비스 간 통신에 보안 설정  
  
## <a name="discussion"></a>토론  
 이 샘플에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 보안 인프라를 사용하여 일반 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에서와 동일하게 워크플로 서비스에 보안을 설정하는 방법을 보여 줍니다. 특히 여기에서는 권한 부여에 사용자 지정 클레임을 사용합니다. 이 경우 Windows 자격 증명에 <xref:System.ServiceModel.WSHttpBinding> 및 메시지 모드 보안을 사용합니다.  
  
 사용자 지정 <xref:System.IdentityModel.Policy.IAuthorizationPolicy>(`CustomNameCheckerPolicy`)는 클라이언트의 Windows 사용자 이름에 특정 문자가 있는지 확인합니다. 해당 문자가 있으면 클레임을 만들어 <xref:System.IdentityModel.Policy.EvaluationContext>에 추가합니다. 이렇게 하여 사용자 지정 정책이 클라이언트의 사용자 이름에 이 문자가 있음을 나타내는 문을 만듭니다. 호출의 수명 주기 전체에 걸쳐 이 클레임을 쿼리할 수 있습니다. `Constants.cs`에서 해당 문자를 찾을 수 있습니다.  
  
 권한 부여 정책은 `SecureWorkFlowAuthZManager` 내부에서 클레임을 찾습니다. 클레임을 찾으면 `true`를 반환하고 워크플로가 계속되도록 합니다. 그렇지 않으면 `false`를 반환합니다. 그러면 클라이언트에 '액세스 거부' 메시지가 반환됩니다. 다른 클레임은 컨텍스트에 있으며 이 클레임도 `SecureWorkFlowAuthZManager` 내부에서 검사할 수 있습니다.  
  
#### <a name="to-run-this-sample"></a>이 샘플을 실행하려면  
  
1.  관리자 권한으로 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 실행합니다.  
  
2.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 SecuringWorkflowServices.sln을 로드합니다.  
  
3.  Ctrl+Shift+B를 눌러 솔루션을 컴파일합니다.  
  
4.  서비스 프로젝트를 솔루션의 시작 프로젝트로 설정합니다.  
  
5.  Ctrl+F5를 눌러 디버깅 없이 서비스를 시작합니다.  
  
6.  클라이언트 프로젝트를 솔루션의 시작 프로젝트로 설정합니다.  
  
7.  Ctrl+F5를 눌러 디버깅 없이 클라이언트를 시작합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\SecuringWorkflowServices`
