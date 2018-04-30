---
title: 대기 중인 메시지 문제 해결
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5f2836f-018d-42f5-a571-1e97e64ea5b0
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1342f2383e7cf2aa15ea60be03c93044e4332612
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="troubleshooting-queued-messaging"></a>대기 중인 메시지 문제 해결
이 단원에는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서 큐를 사용하는 경우에 관한 일반적인 질문과 문제 해결 도움말이 있습니다.  
  
## <a name="common-questions"></a>자주 묻는 질문  
 **Q:** 사용 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 베타 1과 I MSMQ 핫픽스를 설치 합니다. 핫픽스를 제거해야 합니까?  
  
 **A:** 예. 이 핫픽스는 더 이상 지원되지 않습니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 이제 핫픽스 없이도 MSMQ에서 사용할 수 있습니다.  
  
 **Q:** 두 가지 바인딩 msmq: <xref:System.ServiceModel.NetMsmqBinding> 및 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>합니다. 어느 것을 언제 사용해야 합니까?  
  
 **A:** 사용는 <xref:System.ServiceModel.NetMsmqBinding> 두 큐에 대기 중인된 통신에 MSMQ를 전송으로 사용 하려는 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램입니다. <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>은 기존 MSMQ 응용 프로그램을 사용하여 새 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램과 통신하려는 경우에 사용합니다.  
  
 **Q:** 사용 하려면 MSMQ를 업그레이드 해야는 <xref:System.ServiceModel.NetMsmqBinding> 및 `MsmqIntegration` 바인딩?  
  
 **A:** 아니요. 두 바인딩은 모두 [!INCLUDE[wxp](../../../../includes/wxp-md.md)] 및 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]에서 MSMQ 3.0에 사용됩니다. 바인딩의 일부 기능은 [!INCLUDE[wv](../../../../includes/wv-md.md)]에서 MSMQ 4.0으로 업그레이드하면 사용할 수 있게 됩니다.  
  
 **Q:** 의 어떤 기능은 <xref:System.ServiceModel.NetMsmqBinding> 및 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> 바인딩은 MSMQ 4.0 있지만 속하지 않은 MSMQ 3.0에서 사용할 수는?  
  
 **A:** 다음 기능은 MSMQ 4.0 있지만 속하지 않은 MSMQ 3.0에서 사용할 수 있습니다.  
  
-   사용자 지정 배달 못한 편지 큐는 MSMQ 4.0에서만 지원됩니다.  
  
-   MSMQ 3.0과 4.0은 포이즌 메시지를 처리하는 방식이 다릅니다.  
  
-   MSMQ 4.0에서만 트랜잭션된 원격 읽기를 지원합니다.  
  
 자세한 내용은 참조 [Windows Vista, Windows Server 2003 및 Windows XP의 큐 기능 차이점](../../../../docs/framework/wcf/feature-details/diff-in-queue-in-vista-server-2003-windows-xp.md)합니다.  
  
 **Q:** MSMQ 3.0 다른 쪽에 대기 중인된 통신 및 MSMQ 4.0의 한 쪽에서 사용할 수 있습니까?  
  
 **A:** 예.  
  
 **Q:** new로 기존 MSMQ 응용 프로그램과 통합 하려는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 또는 서버입니다. MSMQ 인프라의 양쪽을 모두 업그레이드해야 합니까?  
  
 **A:** 아니요. 어느 쪽에서도 MSMQ 4.0으로 업그레이드할 필요는 없습니다.  
  
## <a name="troubleshooting"></a>문제 해결  
 이 단원에는 일반적인 문제 해결 관련 질문의 답이 있습니다. 알려진 제한에 관한 몇 가지 문제는 릴리스 정보를 참조하십시오.  
  
 **Q:** 개인 큐를 사용 하 려 하 고 다음과 같은 예외가: `System.InvalidOperationException`: URL이 잘못 되었습니다. 큐의 URL에는 '$' 문자가 포함될 수 없습니다. net.msmq://machine/private/queueName의 구문을 사용하여 개인 큐의 주소를 지정하십시오.  
  
 **A:** 구성 및 코드의 식별자 URI (Uniform Resource) 큐를 확인 하십시오. URI에는 "$" 문자를 사용하지 마십시오. 예를 들어 OrdersQueue라는 개인 큐를 지정하려면 URI를 net.msmq://localhost/private/ordersQueue로 지정합니다.  
  
 **Q:** 호출 `ServiceHost.Open()` 대기 중인 응용 프로그램에 다음과 같은 예외를 throw: `System.ArgumentException`: 기본 주소 URI 쿼리 문자열을 포함할 수 없습니다. 이유  
  
 **A:** URI 프로그램 구성 파일에서 및 코드에 큐를 확인 합니다. MSMQ 큐에서는 '?' 문자 사용을 지원하지만 URI에서는 이 문자를 문자열 쿼리의 시작으로 해석합니다. 이 문제를 방지하려면 '?' 문자가 포함되지 않은 큐 이름을 사용합니다.  
  
 **Q:** 보내기에 성공 했는데 수신기에서 없는 서비스 작업이 호출 됩니다. 이유  
  
 **A:** 다음 검사 목록을 통해 작업에 대 한 대답을 확인 하려면:  
  
-   트랜잭션 큐 요구 사항이 지정된 보증과 호환되는지 확인합니다. 다음 원칙에 주의하십시오.  
  
    -   보낼 수 있습니다 (데이터 그램 및 세션)의 지 속성 메시지 "정확히 한 번 만" 보증이 (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `true`) 트랜잭션 큐로만 합니다.  
  
    -   "한 번만" 보증이 지정된 세션만 보낼 수 있습니다.  
  
    -   트랜잭션 큐의 세션에서 메시지를 받으려면 트랜잭션이 필요합니다.  
  
    -   보내거나 일시적 또는 지 속성 (데이터 그램만 해당) 보증이 없는 메시지를 받을 수 있습니다 (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `false`)는 비트랜잭션 큐로만 합니다.  
  
-   배달 못한 편지 큐를 확인합니다. 거기에서 메시지를 찾은 경우에는 배달되지 않은 이유를 확인합니다.  
  
-   보내는 큐에서 연결 또는 주소 지정 문제를 확인합니다.  
  
 **Q:** 사용자 지정 배달 못 한 편지 큐를 지정 하지만 발신자 응용 프로그램을 시작할 때 배달 못 한 편지 큐를 찾을 수 없다는 내용의 예외가 발생 하거나 발신 응용 프로그램에 배달 못 한 편지 큐 수 있는 권한이 없습니다. 이유가 무엇입니까?  
  
 **A:** 사용자 지정 배달 못 한 편지 큐 URI에 "localhost" 또는 컴퓨터 이름을 첫 번째 세그먼트 예를 들어 net.msmq: //localhost/private/myappdead-letter queue에에서 포함 해야 합니다.  
  
 **Q:** 것 항상 사용자 지정 배달 못 한 편지 큐를 정의 하는 데 필요한 없거나 기본 배달 못 한 편지 큐?  
  
 **A:** 보증 "정확히 한 번 만" 경우 (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `true`), 기본값은 시스템 차원의 트랜잭션 배달 못 한 편지 큐는 사용자 지정 배달 못 한 편지 큐를 지정 하지 않습니다.  
  
 보증이 없는 (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `false`), 기본값은 배달 못 한 편지 큐 기능이 없습니다.  
  
 **Q:** 메시지와 함께 SvcHost.Open에서 "EndpointListener 요구 사항에 맞지 않습니다 ListenerFactory" 서비스에서 throw 합니다. 이유  
  
 대답: 서비스 계약을 확인하십시오. 배치 하지 않았을 수 있습니다 "IsOneWay =`true`"에 있는 모든 서비스 작업입니다. 큐에서는 단방향 서비스 작업만 지원합니다.  
  
 **Q:** 큐에 메시지가 있지만 서비스 작업이 호출 됩니다. 무엇이 문제입니까?  
  
 **A:** 서비스 호스트에 오류가 있는지 확인 합니다. 추적을 검토하거나 `IErrorHandler`를 구현하면 확인할 수 있습니다. 포이즌 메시지가 검색되면 기본적으로 서비스 호스트 오류가 발생합니다.  
  
 **Q:** 큐에 메시지가 있지만 대기 중인 웹 호스팅 서비스가 활성화 되지 않습니다. 이유  
  
 **A:** 가장 일반적인 이유는 권한입니다.  
  
1.  `NetMsmqActivator` 프로세스가 실행되고 있으며 `NetMsmqActivator` 프로세스의 ID에 큐에 대한 읽기 및 검색 권한이 있는지 확인하십시오.  
  
2.  `NetMsmqActivator`에서 원격 시스템에 있는 큐를 모니터링하는 경우에는 `NetMsmqActivator`가 제한된 토큰에서 실행되고 있지 않은지 확인합니다. 제한되지 않은 토큰으로 `NetMsmqActivator`를 실행하려면:  
  
    ```  
    sc sidtype NetMsmqActivator unrestricted  
    ```  
  
 에 대 한 비보안 관련된 웹 호스트 문제를 참조: [대기 중인 응용 프로그램 웹 호스팅](../../../../docs/framework/wcf/feature-details/web-hosting-a-queued-application.md)합니다.  
  
 **Q:** 액세스 세션에는 가장 쉬운 방법은 무엇 인가요?  
  
 **A:** 자동 완성 설정 =`true` 마지막에 해당 하는 작업에는 세션에서 메시지 보내기 및 자동 완성 설정 =`false` 나머지 모든 서비스 작업에 있습니다.  
  
 **Q:** MSMQ에 대 한 일반적인 질문에 답변은 어디서 찾을 수 있습니까?  
  
 **A:** MSMQ에 대 한 자세한 내용은 참조 [Microsoft 메시지 큐](http://go.microsoft.com/fwlink/?LinkId=87810)합니다.  
  
 **Q:** 내 서비스 throw 되는 이유는 `ProtocolException` 모두 포함 된 큐에서 읽는 대기 중인 세션 메시지와 대기 중인 데이터 그램 메시지 때?  
  
 **A:** 방식으로 대기 중인된 세션 메시지에서 근본적인 차이가 대기 중인된 데이터 그램 메시지의 작성 합니다. 따라서 대기 중인 세션 메시지를 읽으려는 서비스에서 대기 중인 데이터그램 메시지를 받을 수 없고, 대기 중인 데이터그램 메시지를 읽으려는 서비스에서 대기 중인 세션 메시지를 받을 수 없습니다. 같은 큐에서 두 형식의 메시지를 모두 읽으려고 하면 다음 예외가 throw됩니다.  
  
```  
System.ServiceModel.MsmqPoisonMessageException: The transport channel detected a poison message. This occurred because the message exceeded the maximum number of delivery attempts or because the channel detected a fundamental problem with the message. The inner exception may contain additional information.   
---> System.ServiceModel.ProtocolException: An incoming MSMQ message contained invalid or unexpected .NET Message Framing information in its body. The message cannot be received. Ensure that the sender is using a compatible service contract with a matching SessionMode.  
```  
  
 응용 프로그램에서 같은 컴퓨터로부터 대기 중인 세션 메시지와 대기 중인 데이터그램 메시지를 모두 보내는 경우, 사용자 지정 배달 못한 편지 큐와 시스템 배달 못한 편지 큐에서 특히 이 문제가 잘 발생합니다. 메시지를 보낼 수 없는 경우, 메시지는 배달 못한 편지 큐로 이동합니다. 이 경우 세션 메시지와 데이터그램 메시지가 모두 배달 못한 편지 큐에 들어갈 수 있습니다. 실행 중에 큐에서 읽는 동안 두 형식의 메시지를 구분할 방법이 없기 때문에, 응용 프로그램에서 같은 컴퓨터로부터 대기 중인 세션 메시지와 대기 중인 데이터그램 메시지를 모두 보내면 안 됩니다.  
  
### <a name="msmq-integration-specific-troubleshooting"></a>MSMQ 통합: 특정 문제 해결  
 **Q:** 메시지를 보낼 때 또는 서비스 호스트를 열 때 오류가 발생 하는 스키마가 잘못 된 나타내는입니다. 이유  
  
 **A:** MSMQ 통합 바인딩을 사용 하는 경우에 msmq.formatname 체계를 사용 하 여 다음 작업을 해야 있습니다. 예를 들어 msmq.formatname:DIRECT=OS:.\private$\OrdersQueue입니다. 하지만 사용자 지정 배달 못한 편지 큐를 지정하는 경우에는 net.msmq 체계를 사용해야 합니다.  
  
 **Q:** 공개 또는 개인 형식 이름을 사용 하 여 I와에서 서비스 호스트를 열고 [!INCLUDE[wv](../../../../includes/wv-md.md)], 오류가 발생 합니다. 이유  
  
 **A:** 는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 통합 채널에서 [!INCLUDE[wv](../../../../includes/wv-md.md)] 포이즌 메시지 처리에 대 한 주 응용 프로그램 큐에 대 한 하위 큐를 열 수는 경우를 확인 합니다. 하위 큐의 이름은 수신기에 전달되는 msmq.formatname URI에서 파생됩니다. MSMQ에서 하위 큐 이름에는 직접 형식 이름만 사용할 수 있습니다. 따라서 오류가 발생합니다. 큐 URI를 직접 형식 이름으로 변경하십시오.  
  
 **Q:** MSMQ 응용 프로그램에서 메시지를 받을 때 메시지 큐에 배치 하 고 수신에서 읽을 수 없습니다 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램입니다. 이유  
  
 **A:** 메시지에 본문이 있는지 여부를 확인 합니다. 메시지에 본문이 없으면 MSMQ 통합 채널에서 메시지를 무시합니다. 예외에 대한 알림을 받고 추적을 확인하려면 `IErrorHandler`를 구현하십시오.  
  
### <a name="security-related-troubleshooting"></a>보안 관련 문제 해결  
 **Q:** 하면 작업 그룹 모드에서 기본 바인딩을 사용 하는 샘플을 실행, 메시지가 보내지는 것 같지만 수신자에 게 전달 되지 않습니다.  
  
 **A:** 기본적으로 메시지에 Active Directory 디렉터리 서비스가 필요한 MSMQ 내부 인증서를 사용 하 여 서명 됩니다. 작업 그룹 모드에서는 Active Directory를 사용할 수 없기 때문에 메시지 서명이 실패합니다. 따라서 배달 못 한 편지 큐에 메시지가 삽입 및 "잘못 된 서명" 등의 실패 원인이 표시 됩니다.  
  
 해결 방법은 보안을 해제하는 것입니다. 이렇게 설정 하 여 <xref:System.ServiceModel.NetMsmqSecurity.Mode%2A>  =  <xref:System.ServiceModel.NetMsmqSecurityMode.None> 작업 그룹 모드에서 작동 하도록 합니다.  
  
 다른 해결 방법은 <xref:System.ServiceModel.MsmqTransportSecurity>를 <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A> 속성에서 가져와서 <xref:System.ServiceModel.MsmqAuthenticationMode.Certificate>로 설정하고 클라이언트 인증서를 설정하는 것입니다.  
  
 또 다른 해결 방법은 Active Directory 통합을 사용하는 MSMQ를 설치하는 것입니다.  
  
 **Q:** 기본 바인딩과 함께 메시지를 전송할 때 (전송 보안 설정 됨) 큐에 Active Directory에는 메시지가 "내부 인증서를 찾을 수 없습니다". 이 문제를 해결하려면 어떻게 해야 합니까?  
  
 **A:** 즉, 보낸 사람에 대 한 Active Directory에 인증서를 갱신 해야 합니다. 이렇게 하려면 열고 **제어판**, **관리 도구**, **컴퓨터 관리**를 마우스 오른쪽 단추로 클릭 **MSMQ**, 를선택하고**속성**합니다. 선택 된 **사용자 인증서** 탭을 클릭는 **갱신** 단추입니다.  
  
 **Q:** 사용 하 여 메시지 보내면 <xref:System.ServiceModel.MsmqAuthenticationMode.Certificate> "잘못 된 인증서" 메시지가 사용할 인증서를 지정 합니다. 이 문제를 해결하려면 어떻게 해야 합니까?  
  
 **A:** 인증서 모드와 로컬 컴퓨터 인증서 저장소를 사용할 수 없습니다. 인증서 스냅인을 사용하여 시스템 인증서 저장소에서 현재 사용자 저장소로 인증서를 복사해야 합니다. 인증서 스냅인을 가져오려면 다음을 수행하십시오.  
  
1.  클릭 **시작**선택, **실행**, 형식 `mmc`를 클릭 하 고 **확인**합니다.  
  
2.  에 **Microsoft Management Console**열고는 **파일** 메뉴와 선택 **스냅인 추가/제거**합니다.  
  
3.  에 **스냅인 추가/제거** 대화 상자를 클릭는 **추가** 단추입니다.  
  
4.  에 **독립 실행형 스냅인 추가** 대화 상자, 인증서 선택 및 클릭 **추가**합니다.  
  
5.  에 **인증서** 스냅인 대화 상자에서 **내 사용자 계정** 클릭 **마침**합니다.  
  
6.  다음에 두 번째 인증서 스냅인에서 이전 단계를 사용 하 여 이지만이 시간을 선택 하는 추가 **컴퓨터 계정** 클릭 **다음**합니다.  
  
7.  선택 **로컬 컴퓨터** 클릭 **마침**합니다. 이제 시스템 인증서 저장소에서 현재 사용자 저장소로 인증서를 끌어서 놓을 수 있습니다.  
  
 **Q:** 내 서비스를 읽을 때 작업 그룹 모드에서 다른 컴퓨터에 있는 큐에서 내용의 "액세스 거부" 예외가 발생 합니다.  
  
 **A:** 큐에 액세스 하는 원격 응용 프로그램에 대 한 작업 그룹 모드에서는 응용 프로그램 큐에 액세스할 수 있는 권한이 있어야 합니다. 큐의 액세스 제어 목록 (ACL)에 "익명 로그인"을 추가 하 고 읽기 권한을 부여 합니다.  
  
 **Q:** 네트워크 서비스 클라이언트 (또는 도메인 계정이 없는 모든 클라이언트) 큐에 대기 중인된 메시지를 보내는 경우 보내기 잘못 된 인증서와 함께 실패 합니다. 이 문제를 해결하려면 어떻게 해야 합니까?  
  
 **A:** 바인딩 구성을 확인 합니다. 기본 바인딩에는 메시지 서명을 위해 MSMQ 전송 보안이 설정되어 있습니다. MSMQ 전송 보안을 해제하십시오.  
  
### <a name="remote-transacted-receives"></a>트랜잭션된 원격 수신  
 **Q:** 컴퓨터 a에서 큐가 있고 및 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 읽는 B (트랜잭션 된 원격 수신 시나리오), 메시지는 컴퓨터에 있는 큐에서 메시지를 큐에서 읽을 수 없습니다. 메시지 "트랜잭션을 가져올 수 없습니다."와 수신 실패 나타냅니다 추적 정보 이 문제를 해결 하려면 어떻게 해야 합니까?  
  
 **A:** 없는 다음이 대 한 세 가지 가능한 이유:  
  
-   도메인 모드에 있는 경우 트랜잭션된 원격 수신을 수행하려면 MSDTC(Microsoft Distributed Transaction Coordinator) 네트워크 액세스가 필요합니다. 사용 하 여 설정할 수 있습니다 **구성 요소 추가/제거**합니다.  
  
     ![네트워크 DTC 액세스 사용](../../../../docs/framework/wcf/feature-details/media/applicationserveraddcomps.jpg "ApplicationServerAddComps")  
  
-   트랜잭션 관리자와의 통신을 위한 인증 모드를 확인합니다. 작업 그룹 모드에 있는 "인증 필요" 선택 해야 합니다. 도메인 모드에 있는 "상호 인증 필요"을 선택 해야 합니다.  
  
     ![XA 트랜잭션 사용](../../../../docs/framework/wcf/feature-details/media/4f3695e0-fb0b-4c5b-afac-75f8860d2bb0.jpg "4f3695e0-fb0b-4c5b-afac-75f8860d2bb0")  
  
-   예외 목록에 MSDTC가 있는지 확인은 **인터넷 연결 방화벽** 설정 합니다.  
  
-   [!INCLUDE[wv](../../../../includes/wv-md.md)]를 사용하고 있는지 확인하십시오. [!INCLUDE[wv](../../../../includes/wv-md.md)]의 MSMQ에서는 트랜잭션된 원격 읽기를 지원합니다. 이전 Windows 릴리스의 MSMQ에서는 트랜잭션된 원격 읽기를 지원하지 않습니다.  
  
 **Q:** 큐에서 읽는 서비스가 네트워크 서비스인 경우 예를 들어 웹에서 호스트, 왜 액세스 거부 예외가 발생 하는 큐에서 읽을 때?  
  
 **A:** 네트워크 서비스 읽기 권한을 큐 ACL에 네트워크 서비스는 큐에서 읽을 수 있도록에 추가 해야 합니다.  
  
 **Q:** MSMQ 활성화 서비스 응용 프로그램을 원격 컴퓨터에 있는 큐에 메시지 기반 활성화를 사용할 수 있습니까?  
  
 **A:** 예. 이렇게 하려면 네트워크 서비스로 실행되도록 MSMQ 정품 인증 서비스를 구성하고 원격 시스템의 큐에 대한 네트워크 서비스 액세스 권한을 추가해야 합니다.  
  
## <a name="using-custom-msmq-bindings-with-receivecontext-enabled"></a>ReceiveContext를 사용하는 사용자 지정 MSMQ 바인딩 사용  
 <xref:System.ServiceModel.Channels.ReceiveContext>를 사용하는 사용자 지정 MSMQ 바인딩을 사용하는 경우 네이티브 MSMQ가 비동기 <xref:System.ServiceModel.Channels.ReceiveContext>에 대한 I/O 완료를 지원하지 않기 때문에 들어오는 메시지 처리에서 스레드 풀 스레드를 사용합니다. 이는 이러한 메시지 처리에서 <xref:System.ServiceModel.Channels.ReceiveContext>에 내부 트랜잭션을 사용하고 MSMQ가 비동기 처리를 지원하지 않기 때문입니다. 이 문제를 해결하려면 <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>를 끝점에 추가하여 동기 처리를 강제로 수행하거나 <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior.MaxPendingReceives%2A>를 1로 설정하면 됩니다.
