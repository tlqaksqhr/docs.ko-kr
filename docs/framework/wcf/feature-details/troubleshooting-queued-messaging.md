---
title: "대기 중인 메시지 문제 해결 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a5f2836f-018d-42f5-a571-1e97e64ea5b0
caps.latest.revision: 19
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 19
---
# 대기 중인 메시지 문제 해결
이 단원에는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서 큐를 사용하는 경우에 관한 일반적인 질문과 문제 해결 도움말이 있습니다.  
  
## 자주 묻는 질문  
 **질문:** [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Beta 1을 사용하던 중에 MSMQ 핫픽스를 설치했습니다.핫픽스를 제거해야 합니까?  
  
 @FSHO1@**대답:** 예.이 핫픽스는 더 이상 지원되지 않습니다.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 이제 핫픽스 없이도 MSMQ에서 사용할 수 있습니다.  
  
 **질문:** MSMQ에 <xref:System.ServiceModel.NetMsmqBinding> 및 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>의 두 가지 바인딩이 있습니다.어느 것을 언제 사용해야 합니까?  
  
 **대답:** <xref:System.ServiceModel.NetMsmqBinding>은 MSMQ를 사용하여 두 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램 사이에서 대기 중인 통신을 전송하려는 경우에 사용합니다.<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>은 기존 MSMQ 응용 프로그램을 사용하여 새 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램과 통신하려는 경우에 사용합니다.  
  
 **질문:** <xref:System.ServiceModel.NetMsmqBinding> 및 `MsmqIntegration` 바인딩을 사용하려면 MSMQ를 업그레이드해야 합니까?  
  
 **대답:** 아니요.두 바인딩은 모두 [!INCLUDE[wxp](../../../../includes/wxp-md.md)] 및 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]에서 MSMQ 3.0에 사용됩니다.바인딩의 일부 기능은 [!INCLUDE[wv](../../../../includes/wv-md.md)]에서 MSMQ 4.0으로 업그레이드하면 사용할 수 있게 됩니다.  
  
 **질문:** <xref:System.ServiceModel.NetMsmqBinding> 및 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> 바인딩의 기능 중 MSMQ 4.0에서는 사용할 수 있지만 MSMQ 3.0에서는 사용할 수 없는 것은 무엇입니까?  
  
 **대답:** 다음 기능은 MSMQ 4.0에서 사용할 수 있지만 MSMQ 3.0에서 사용할 수 없습니다.  
  
-   사용자 지정 배달 못한 편지 큐는 MSMQ 4.0에서만 지원됩니다.  
  
-   MSMQ 3.0과 4.0은 포이즌 메시지를 처리하는 방식이 다릅니다.  
  
-   MSMQ 4.0에서만 트랜잭션된 원격 읽기를 지원합니다.  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Windows Vista, Windows Server 2003 및 Windows XP의 큐 기능 차이점](../../../../docs/framework/wcf/feature-details/diff-in-queue-in-vista-server-2003-windows-xp.md).  
  
 **질문:** 대기 중인 통신의 한쪽에서는 MSMQ 3.0을 사용하고 다른 쪽에서는 MSMQ 4.0을 사용할 수 있습니까?  
  
 @FSHO1@**대답:** 예.  
  
 **질문:** 기존 MSMQ 응용 프로그램을 새 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 또는 서버와 통합하고 싶습니다.MSMQ 인프라의 양쪽을 모두 업그레이드해야 합니까?  
  
 **대답:** 아니요.어느 쪽에서도 MSMQ 4.0으로 업그레이드할 필요는 없습니다.  
  
## 문제 해결  
 이 단원에는 일반적인 문제 해결 관련 질문의 답이 있습니다.알려진 제한에 관한 몇 가지 문제는 릴리스 정보를 참조하십시오.  
  
 **질문:** 개인 큐를 사용하려고 하면 다음 예외 메시지가 표시됩니다. `System.InvalidOperationException`: URL이 잘못되었습니다.큐의 URL에는 '$' 문자가 포함될 수 없습니다.net.msmq:\/\/machine\/private\/queueName의 구문을 사용하여 개인 큐의 주소를 지정하십시오.  
  
 **대답:** 구성 및 코드에 있는 큐 URI\(Uniform Resource Identifier\)를 확인하십시오.URI에는 "$" 문자를 사용하지 마십시오.예를 들어 OrdersQueue라는 개인 큐를 지정하려면 URI를 net.msmq:\/\/localhost\/private\/ordersQueue로 지정합니다.  
  
 **질문:** 대기 중인 응용 프로그램에서 `ServiceHost.Open()`을 호출하면 다음 예외가 throw됩니다. `System.ArgumentException`: 기본 주소에는 URI 쿼리 문자열을 포함할 수 없습니다.이유  
  
 **대답:** 구성 및 코드에 있는 큐 URI를 확인하십시오.MSMQ 큐에서는 '?' 문자 사용을 지원하지만 URI에서는 이 문자를 문자열 쿼리의 시작으로 해석합니다.이 문제를 방지하려면 '?' 문자가 포함되지 않은 큐 이름을 사용합니다.  
  
 **질문:** 보내기에 성공했는데 수신기에서 서비스 작업이 호출되지 않습니다.이유  
  
 **대답:** 대답을 결정하려면 다음 검사 목록을 확인하십시오.  
  
-   트랜잭션 큐 요구 사항이 지정된 보증과 호환되는지 확인합니다.다음 원칙에 주의하십시오.  
  
    -   "한 번만" 보증이\(<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> \= `true`\) 지정된 지속성 메시지\(데이터그램 및 세션\)는 트랜잭션 큐로만 보낼 수 있습니다.  
  
    -   "한 번만" 보증이 지정된 세션만 보낼 수 있습니다.  
  
    -   트랜잭션 큐의 세션에서 메시지를 받으려면 트랜잭션이 필요합니다.  
  
    -   보증이 없는\(<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> \= `false`\) 일시적 또는 지속성 메시지\(데이터그램만 해당\)는 비트랜잭션 큐로만 보내고 받을 수 있습니다.  
  
-   배달 못한 편지 큐를 확인합니다.거기에서 메시지를 찾은 경우에는 배달되지 않은 이유를 확인합니다.  
  
-   보내는 큐에서 연결 또는 주소 지정 문제를 확인합니다.  
  
 **질문:** 사용자 지정 배달 못한 편지 큐를 지정했지만 송신 응용 프로그램을 시작하면 배달 못한 편지 큐를 찾을 수 없거나 송신 응용 프로그램에 배달 못한 편지 큐를 사용할 권한이 없다는 내용의 예외가 발생합니다.이유가 무엇입니까?  
  
 **대답:** 사용자 지정 배달 못한 편지 큐 URI의 첫 세그먼트에 "localhost" 또는 net.msmq:\/\/localhost\/private\/myAppdead\-letter queue와 같은 컴퓨터 이름이 포함되어 있어야 합니다.  
  
 **질문:** 항상 사용자 지정 배달 못한 편지 큐를 정의해야 합니까, 아니면 기본 배달 못한 편지 큐가 있습니까?  
  
 **대답:** 보증이 "한 번만"이고\(<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> \= `true`\) 사용자 지정 배달 못한 편지 큐가 지정되지 않은 경우 기본값은 시스템 차원의 배달 못한 트랜잭션 큐입니다.  
  
 보증이 없는\(<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> \= `false`\) 경우의 기본값은 배달 못한 편지 큐 기능을 사용하지 않는 것입니다.  
  
 **질문:** SvcHost.Open을 실행하면 서비스에서 "EndpointListener 요구 사항을 ListenerFactory에서 충족시킬 수 없습니다"라는 메시지와 함께 오류를 throw합니다.이유  
  
 대답.서비스 계약을 확인하십시오.모든 서비스 작업에 "IsOneWay\=`true`"를 지정하는 것을 잊었을 수도 있습니다.큐에서는 단방향 서비스 작업만 지원합니다.  
  
 **질문:** 큐에 메시지가 있지만 서비스 작업이 호출되지 않습니다.무엇이 문제입니까?  
  
 **대답:** 서비스 호스트에 오류가 있는지 확인하십시오.추적을 검토하거나 `IErrorHandler`를 구현하면 확인할 수 있습니다.포이즌 메시지가 검색되면 기본적으로 서비스 호스트 오류가 발생합니다.  
  
 **질문:** 큐에 메시지가 있지만 대기 중인 웹 호스팅 서비스가 활성화되지 않습니다.이유  
  
 **대답:** 가장 일반적인 이유는 권한입니다.  
  
1.  `NetMsmqActivator` 프로세스가 실행되고 있으며 `NetMsmqActivator` 프로세스의 ID에 큐에 대한 읽기 및 검색 권한이 있는지 확인하십시오.  
  
2.  `NetMsmqActivator`에서 원격 시스템에 있는 큐를 모니터링하는 경우에는 `NetMsmqActivator`가 제한된 토큰에서 실행되고 있지 않은지 확인합니다.제한되지 않은 토큰으로 `NetMsmqActivator`를 실행하려면:  
  
    ```  
    sc sidtype NetMsmqActivator unrestricted  
    ```  
  
 비보안 관련 웹 호스트 문제에 대해서는 [대기 중인 응용 프로그램 웹 호스팅](../../../../docs/framework/wcf/feature-details/web-hosting-a-queued-application.md)을 참조하십시오.  
  
 **질문:** 세션에 가장 쉽게 액세스할 수 있는 방법은 무엇입니까?  
  
 **대답:** 세션의 마지막 메시지에 해당되는 작업에 AutoComplete\=`true`를 설정하고 모든 나머지 서비스 작업에 AutoComplete\=`false`를 설정합니다.  
  
 **질문:** MSMQ에 대한 일반적인 질문의 대답은 어디에서 찾을 수 있습니까?  
  
 **대답:** MSMQ[!INCLUDE[crabout](../../../../includes/crabout-md.md)][Microsoft Message Queuing](http://go.microsoft.com/fwlink/?LinkId=87810)을 참조하십시오.  
  
 **질문:** 대기 중인 세션 메시지와 대기 중인 데이터그램 메시지를 모두 포함한 큐에서 읽는 경우 서비스에서 `ProtocolException`을 throw하는 이유는 무엇입니까?  
  
 **대답:** 대기 중인 세션 메시지와 대기 중인 데이터그램 메시지의 작성 방식에는 근본적인 차이가 있습니다.따라서 대기 중인 세션 메시지를 읽으려는 서비스에서 대기 중인 데이터그램 메시지를 받을 수 없고, 대기 중인 데이터그램 메시지를 읽으려는 서비스에서 대기 중인 세션 메시지를 받을 수 없습니다.같은 큐에서 두 형식의 메시지를 모두 읽으려고 하면 다음 예외가 throw됩니다.  
  
```  
System.ServiceModel.MsmqPoisonMessageException: The transport channel detected a poison message. This occurred because the message exceeded the maximum number of delivery attempts or because the channel detected a fundamental problem with the message. The inner exception may contain additional information.   
---> System.ServiceModel.ProtocolException: An incoming MSMQ message contained invalid or unexpected .NET Message Framing information in its body. The message cannot be received. Ensure that the sender is using a compatible service contract with a matching SessionMode.  
```  
  
 응용 프로그램에서 같은 컴퓨터로부터 대기 중인 세션 메시지와 대기 중인 데이터그램 메시지를 모두 보내는 경우, 사용자 지정 배달 못한 편지 큐와 시스템 배달 못한 편지 큐에서 특히 이 문제가 잘 발생합니다.메시지를 보낼 수 없는 경우, 메시지는 배달 못한 편지 큐로 이동합니다.이 경우 세션 메시지와 데이터그램 메시지가 모두 배달 못한 편지 큐에 들어갈 수 있습니다.실행 중에 큐에서 읽는 동안 두 형식의 메시지를 구분할 방법이 없기 때문에, 응용 프로그램에서 같은 컴퓨터로부터 대기 중인 세션 메시지와 대기 중인 데이터그램 메시지를 모두 보내면 안 됩니다.  
  
### MSMQ 통합: 특정 문제 해결  
 **질문:** 메시지를 보내거나 서비스 호스트를 열면 체계가 잘못되었음을 알리는 오류가 표시됩니다.이유  
  
 **대답:** MSMQ 통합 바인딩을 사용하는 경우에는 msmq.formatname 체계를 사용해야 합니다.예를 들어 msmq.formatname:DIRECT\=OS:.\\private$\\OrdersQueue입니다.하지만 사용자 지정 배달 못한 편지 큐를 지정하는 경우에는 net.msmq 체계를 사용해야 합니다.  
  
 **질문:** 공개 또는 개인 형식 이름을 사용하는 경우 [!INCLUDE[wv](../../../../includes/wv-md.md)]에서 서비스 호스트를 열면 오류가 발생합니다.이유  
  
 **대답:** [!INCLUDE[wv](../../../../includes/wv-md.md)]의 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 통합 채널은 포이즌 메시지 처리를 위해 주 응용 프로그램 큐에 하위 큐를 열 수 있는지 확인합니다.하위 큐의 이름은 수신기에 전달되는 msmq.formatname URI에서 파생됩니다.MSMQ에서 하위 큐 이름에는 직접 형식 이름만 사용할 수 있습니다.따라서 오류가 발생합니다.큐 URI를 직접 형식 이름으로 변경하십시오.  
  
 **질문:** MSMQ 응용 프로그램에서 메시지를 받을 때 메시지가 큐에 들어간 후 수신 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램에 읽히지 않습니다.이유  
  
 **대답:** 메시지에 본문이 있는지 확인하십시오.메시지에 본문이 없으면 MSMQ 통합 채널에서 메시지를 무시합니다.예외에 대한 알림을 받고 추적을 확인하려면 `IErrorHandler`를 구현하십시오.  
  
### 보안 관련 문제 해결  
 **질문:** 작업 그룹 모드에서 기본 바인딩을 사용하는 샘플을 실행하면 메시지가 보내지는 것 같지만 수신자에게 전달되지 않습니다.  
  
 **대답:** 기본적으로 메시지는 Active Directory 디렉터리 서비스가 필요한 MSMQ 내부 인증서를 사용하여 서명됩니다.작업 그룹 모드에서는 Active Directory를 사용할 수 없기 때문에 메시지 서명이 실패합니다.이에 따라 배달 못 한 편지 큐에 메시지가 삽입되고 "잘못된 서명" 등의 오류가 표시됩니다.  
  
 해결 방법은 보안을 해제하는 것입니다.보안을 해제하려면 <xref:System.ServiceModel.NetMsmqSecurity.Mode%2A> \= <xref:System.ServiceModel.NetMsmqSecurityMode>으로 설정하여 작업 그룹 모드에서 작동하도록 합니다.  
  
 다른 해결 방법은 <xref:System.ServiceModel.MsmqTransportSecurity>를 <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A> 속성에서 가져와서 <xref:System.ServiceModel.MsmqAuthenticationMode>로 설정하고 클라이언트 인증서를 설정하는 것입니다.  
  
 또 다른 해결 방법은 Active Directory 통합을 사용하는 MSMQ를 설치하는 것입니다.  
  
 **질문:** Active Directory에서 기본 바인딩\(전송 보안 설정됨\)을 통해 큐에 메시지를 보내면 "내부 인증서를 찾을 수 없다"는 메시지가 표시됩니다.이 문제를 해결하려면 어떻게 해야 합니까?  
  
 **대답:** Active Directory에 있는 발신자 인증서를 갱신해야 합니다.그러려면 **제어판**, **관리 도구**, **컴퓨터 관리**를 연 다음 **MSMQ**를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.**사용자 인증서** 탭을 선택하고 **갱신** 단추를 클릭합니다.  
  
 **질문:** <xref:System.ServiceModel.MsmqAuthenticationMode>를 사용하여 메시지를 보낼 때 사용할 인증서를 지정하면 "잘못된 인증서" 메시지가 표시됩니다.이 문제를 해결하려면 어떻게 해야 합니까?  
  
 **대답:** 인증서 모드에서는 로컬 시스템 인증서 저장소를 사용할 수 없습니다.인증서 스냅인을 사용하여 시스템 인증서 저장소에서 현재 사용자 저장소로 인증서를 복사해야 합니다.인증서 스냅인을 가져오려면 다음을 수행하십시오.  
  
1.  **시작**을 클릭하고 **실행**을 선택한 다음 `mmc`를 입력하고 **확인**을 클릭합니다.  
  
2.  **Microsoft Management Console**에서 **파일** 메뉴를 열고 **스냅인 추가\/제거**를 선택합니다.  
  
3.  **스냅인 추가\/제거** 대화 상자에서 **추가** 단추를 클릭합니다.  
  
4.  **독립 실행형 스냅인 추가** 대화 상자에서 인증서를 선택하고 **추가**를 클릭합니다.  
  
5.  **인증서** 스냅인 대화 상자에서 **내 사용자 계정**을 선택하고 **마침**을 클릭합니다.  
  
6.  다음으로 이전 단계를 사용해서 두 번째 인증서 스냅인을 추가하는데, 이번에는 **컴퓨터 계정**을 선택하고 **다음**을 클릭합니다.  
  
7.  **로컬 컴퓨터**를 선택하고 **마침**을 클릭합니다.이제 시스템 인증서 저장소에서 현재 사용자 저장소로 인증서를 끌어서 놓을 수 있습니다.  
  
 **질문:** 서비스가 작업 그룹 모드에서 다른 컴퓨터에 있는 큐를 읽으면 "액세스 거부" 예외가 발생합니다.  
  
 **대답:** 작업 그룹 모드에서 원격 응용 프로그램이 큐에 액세스하려면 응용 프로그램에 큐 액세스 권한이 있어야 합니다.큐의 ACL\(액세스 제어 목록\)에 "익명 로그인"을 추가하고 익명 로그인에 읽기 권한을 부여합니다.  
  
 **질문:** 네트워크 서비스 클라이언트 또는 도메인 계정이 없는 임의의 클라이언트에서 대기 중인 메시지를 보내면 잘못된 인증서라는 메시지가 표시되면서 보내기가 실패합니다.이 문제를 해결하려면 어떻게 해야 합니까?  
  
 **대답:** 바인딩 구성을 확인합니다.기본 바인딩에는 메시지 서명을 위해 MSMQ 전송 보안이 설정되어 있습니다.MSMQ 전송 보안을 해제하십시오.  
  
### 트랜잭션된 원격 수신  
 **질문:** 시스템 A에 큐가 있고 시스템 B에 큐에서 메시지를 읽는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스가 있는데\(트랜잭션된 원격 수신 시나리오\) 큐에서 메시지를 읽을 수 없습니다.추적 정보를 보면 "트랜잭션을 가져올 수 없다"는 메시지로 인해 수신이 실패했음을 확인할 수 있습니다. 이 문제를 해결하려면 어떻게 해야 합니까?  
  
 **대답:** 세 가지 원인이 있을 수 있습니다.  
  
-   도메인 모드에 있는 경우 트랜잭션된 원격 수신을 수행하려면 MSDTC\(Microsoft Distributed Transaction Coordinator\) 네트워크 액세스가 필요합니다.이 설정은 **구성 요소 추가\/제거**를 사용하여 활성화할 수 있습니다.  
  
     ![네트워크 DTC 액세스 사용](../../../../docs/framework/wcf/feature-details/media/applicationserveraddcomps.jpg "ApplicationServerAddComps")  
  
-   트랜잭션 관리자와의 통신을 위한 인증 모드를 확인합니다.작업 그룹 모드에 있는 경우에는 "인증 필요 없음"을 선택해야 합니다.도메인 모드에 있는 경우에는 "수동 인증 필요"를 선택해야 합니다.  
  
     ![XA 트랜잭션 사용](../../../../docs/framework/wcf/feature-details/media/4f3695e0-fb0b-4c5b-afac-75f8860d2bb0.jpg "4f3695e0\-fb0b\-4c5b\-afac\-75f8860d2bb0")  
  
-   **인터넷 연결 방화벽** 설정에서 예외 목록에 MSDTC가 있는지 확인하십시오.  
  
-   [!INCLUDE[wv](../../../../includes/wv-md.md)]를 사용하고 있는지 확인하십시오.[!INCLUDE[wv](../../../../includes/wv-md.md)]의 MSMQ에서는 트랜잭션된 원격 읽기를 지원합니다.이전 Windows 릴리스의 MSMQ에서는 트랜잭션된 원격 읽기를 지원하지 않습니다.  
  
 **질문:** 큐에서 읽는 서비스가 네트워크 서비스인 경우 웹 호스트 등에서 큐에서 읽을 때 액세스 거부 예외가 발생하는 이유는 무엇입니까?  
  
 **대답:** 큐 ACL에 네트워크 서비스 읽기 권한을 추가해야 네트워크 서비스가 큐에서 읽을 수 있습니다.  
  
 **질문:** 원격 시스템의 큐에 있는 메시지를 기반으로 MSMQ 정품 인증 서비스를 사용하여 응용 프로그램을 활성화할 수 있습니까?  
  
 @FSHO1@**대답:** 예.이렇게 하려면 네트워크 서비스로 실행되도록 MSMQ 정품 인증 서비스를 구성하고 원격 시스템의 큐에 대한 네트워크 서비스 액세스 권한을 추가해야 합니다.  
  
## ReceiveContext를 사용하는 사용자 지정 MSMQ 바인딩 사용  
 <xref:System.ServiceModel.Channels.ReceiveContext>를 사용하는 사용자 지정 MSMQ 바인딩을 사용하는 경우 네이티브 MSMQ가 비동기 <xref:System.ServiceModel.Channels.ReceiveContext>에 대한 I\/O 완료를 지원하지 않기 때문에 들어오는 메시지 처리에서 스레드 풀 스레드를 사용합니다.이는 이러한 메시지 처리에서 <xref:System.ServiceModel.Channels.ReceiveContext>에 내부 트랜잭션을 사용하고 MSMQ가 비동기 처리를 지원하지 않기 때문입니다.이 문제를 해결하려면 <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>를 끝점에 추가하여 동기 처리를 강제로 수행하거나 <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior.MaxPendingReceives%2A>를 1로 설정하면 됩니다.