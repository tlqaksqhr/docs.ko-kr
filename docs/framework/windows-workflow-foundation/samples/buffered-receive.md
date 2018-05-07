---
title: 버퍼링되는 수신
ms.date: 03/30/2017
ms.assetid: 9d46d9b9-96c9-4531-9695-ab526b4d704a
ms.openlocfilehash: ee53edafc94fd5efd4e412b1b9198a8763b79462
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="buffered-receive"></a>버퍼링되는 수신
이 샘플에는 설정 및의 Windows WF (Workflow Foundation) 버퍼링된 된 수신 기능을 구성 하는 방법을 보여 줍니다. 버퍼링된 수신 기능을 사용하면 워크플로 작성자가 메시지의 수신 순서에 신경을 쓰지 않고 워크플로를 만들 수 있습니다. 버퍼링된 수신 기능은 메시지를 로컬로 버퍼링하고 워크플로에서 메시지를 받을 준비가 되었을 때 이를 전달하는 역할을 합니다.  
  
## <a name="demonstrates"></a>세부 항목  
 메시징 활동에 버퍼링된 수신 기능을 사용하여 순서에 상관없이 메시지 처리  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\BufferedReceive`  
  
## <a name="discussion"></a>토론  
 이 샘플에서는 Windows Communication Foundation (WCF) 서비스를 사용 하 여 구현 됩니다 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 일련의 <xref:System.ServiceModel.Activities.Receive> 활동입니다. 이 워크플로는 간단한 대출 승인 프로세스를 모델링하며, 승인 여부를 결정해야 할 대출에 대한 알림 세 건을 받습니다. Windows Communication Foundation (WCF) 클라이언트 응용 프로그램 서비스에서 예상 반대 순서로 상호 관련된 알림 세 건을 보냅니다. 그러나 이 서비스에서는 버퍼링된 수신 기능을 사용하므로 순서가 맞지 않는 각 메시지를 버퍼링한 후 워크플로에서 해당 메시지를 받을 준비가 되었을 때 이를 처리합니다.  
  
 버퍼링된 수신 기능을 사용하려면 바인딩을 통해 <xref:System.ServiceModel.Activities.ReceiveContent>가 지원되어야 하므로 이 서비스에서는 <xref:System.ServiceModel.NetMsmqBinding>을 사용합니다. 이 바인딩에는 특별한 구성이 필요하지 않으므로 기본 설정이 사용됩니다.  
  
```xml  
<endpoint address ="net.msmq://localhost/private/LoanService/Service1.xamlx"  
                  binding="netMsmqBinding"  
                  contract="ILoanService"/>  
```  
  
 이 서비스에서는 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>를 사용하여 서비스에 대한 메타데이터도 노출합니다.  
  
 마찬가지로, 클라이언트 끝점은 <xref:System.ServiceModel.NetMsmqBinding>을 사용하여 구성됩니다. 클라이언트 코드 및 구성을 사용 하 여 생성 되는 **서비스 참조 추가** Visual Studio의 기능입니다. 다음 예제에서는 App.config 파일에 생성된 클라이언트 끝점을 보여 줍니다.  
  
```xml  
<endpoint address="net.msmq://localhost/private/LoanService/Service1.xamlx"  
                binding="netMsmqBinding" bindingConfiguration="NetMsmqBinding_ILoanService"  
                contract="ServiceReference1.ILoanService" name="NetMsmqBinding_ILoanService" />  
```  
  
 이 샘플에는 다음과 같은 Windows 구성 요소를 사용해야 합니다.  
  
1.  [!INCLUDE[iis60](../../../../includes/iis60-md.md)]  
  
2.  [!INCLUDE[iis60](../../../../includes/iis60-md.md)] 관리 호환성, 메타베이스 및 구성 호환성  
  
3.  World Wide Web 서비스, 응용 프로그램 개발 기능 및 ASP.NET  
  
4.  MSMQ(Microsoft Message Queue) Server  
  
#### <a name="to-set-up-and-build-the-sample"></a>샘플을 설치하고 빌드하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 명령 프롬프트에서 `aspnet_regiis –I`을 입력하여 ASP.NET을 등록하고 Enter 키를 누릅니다.  
  
2.  관리자 권한으로 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 실행합니다.  
  
3.  LoanService.sln을 엽니다.  
  
4.  LoanService 프로젝트에 대 한 가상 디렉터리를 만드는 원하면 선택 묻는 메시지가 나타나면 **예**합니다.  
  
#### <a name="to-set-up-the-service-queues"></a>서비스 큐를 설정하려면  
  
1.  F5 키를 눌러 LoanClient 응용 프로그램을 실행합니다. 이 응용 프로그램은 큐를 만들고 Service1.xamlx에 정의되어 있는 서비스를 활성화하는 역할을 합니다.  
  
2.  열기는 **컴퓨터 관리** 명령 프롬프트에서 Compmgmt.msc를 실행 하 여 콘솔.  
  
3.  에 **컴퓨터 관리** 콘솔에서 **서비스**, **응용 프로그램**, **메시지 큐**, **개인 큐** .  
  
4.  Loanservice/service1.xamlx 큐를 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다.  
  
5.  선택 된 **보안** 탭을 추가 **누구나 메시지 받기**, **메시지 보기** 및 **메시지 보내기** 사용 권한.  
  
6.  [!INCLUDE[iis60](../../../../includes/iis60-md.md)] 관리자를 엽니다.  
  
7.  찾아 **서버**, **사이트**, **기본 웹 사이트**, **개인**, **LoanService** 선택 **고급 옵션**  
  
8.  변경 된 **사용할 수 있는 프로토콜** 되도록 **http**, **net.msmq**합니다.  
  
#### <a name="to-run-the-sample"></a>이 샘플을 실행하려면  
  
1.  찾아 http://localhost/private/loanservice/service1.xamlx 를 서비스가 실행 되 고 있는지 확인 합니다.  
  
2.  F5 키를 눌러 LoanClient 응용 프로그램을 실행합니다. 워크플로를 완료하면 메시지 교환 결과가 포함된 out.txt 파일이 C:\Inbox에 저장됩니다.  
  
#### <a name="to-clean-up"></a>정리하려면  
  
1.  열기는 **컴퓨터 관리** 명령 프롬프트에서 Compmgmt.msc를 실행 하 여 콘솔.  
  
2.  확장 **서비스** 및 **응용 프로그램**, **메시지 큐**, **개인 큐**합니다.  
  
3.  loanservice/service1.xamlx 큐를 삭제합니다.  
  
4.  C:\Inbox 디렉터리를 제거합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\BufferedReceive`
