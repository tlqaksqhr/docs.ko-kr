---
title: "Windows 인증 오류 디버깅"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, authentication
- WCF, Windows authentication
ms.assetid: 181be4bd-79b1-4a66-aee2-931887a6d7cc
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b24d5a8ebccbd454579394a986614e0d40d8d0e6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="debugging-windows-authentication-errors"></a>Windows 인증 오류 디버깅
Windows 인증을 보안 메커니즘으로 사용하면 SSPI(보안 지원 공급자 인터페이스)에서 보안 프로세스를 처리합니다. SSPI 계층에 보안 오류가 발생하면 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에 표시됩니다. 이 항목에서는 오류 진단에 도움이 되는 프레임워크 및 일련의 질문을 제공합니다.  
  
 Kerberos 프로토콜의 개요를 참조 하십시오. [Kerberos 설명](http://go.microsoft.com/fwlink/?LinkID=86946)SSPI의 개요를 참조 하세요. [SSPI](http://go.microsoft.com/fwlink/?LinkId=88941)합니다.  
  
 Windows 인증을 위해 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 일반적으로 사용 하 여는 *Negotiate* 공급자 SSP (Security Support), 클라이언트와 서비스 간의 Kerberos 상호 인증을 수행 하는 합니다. Kerberos 프로토콜을 사용할 수 없는 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 기본적으로 NTLM(NT LAN Manager)으로 대체됩니다. 그러나 Kerberos 프로토콜만 사용하고 Kerberos를 사용할 수 없는 경우 예외를 throw하도록 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 구성할 수 있습니다. 또한 제한된 형식의 Kerberos 프로토콜을 사용하도록 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 구성할 수도 있습니다.  
  
## <a name="debugging-methodology"></a>디버깅 방법  
 기본 방법은 다음과 같습니다.  
  
1.  Windows 인증 사용 여부를 결정합니다. 다른 스키마를 사용할 경우 이 항목이 적용되지 않습니다.  
  
2.  Windows 인증을 사용하는 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 구성에서 Kerberos를 직접 사용할지 또는 협상을 통해 사용할지 결정합니다.  
  
3.  구성에서 Kerberos 프로토콜을 사용할지 또는 NTLM을 사용할지 결정한 다음에는 올바른 컨텍스트에서 오류 메시지를 이해할 수 있습니다.  
  
### <a name="availability-of-the-kerberos-protocol-and-ntlm"></a>Kerberos 프로토콜 및 NTLM 사용 가능성  
 Kerberos SSP에는 Kerberos KDC(키 배포 센터) 역할을 하는 도메인 컨트롤러가 있어야 합니다. Kerberos 프로토콜은 클라이언트와 서비스 둘 다에서 도메인 ID를 사용하는 경우에만 사용할 수 있습니다. 다음 표에 요약된 것처럼 다른 계정 조합의 경우 NTLM이 사용됩니다.  
  
 표 머리글에는 서버에서 사용할 수 있는 계정 형식이 표시되어 있으며, 왼쪽 열에는 클라이언트에서 사용할 수 있는 계정 형식이 표시되어 있습니다.  
  
||로컬 사용자|로컬 시스템|도메인 사용자|도메인 컴퓨터|  
|-|----------------|------------------|-----------------|--------------------|  
|로컬 사용자|NTLM|NTLM|NTLM|NTLM|  
|로컬 시스템|익명 NTLM|익명 NTLM|익명 NTLM|익명 NTLM|  
|도메인 사용자|NTLM|NTLM|Kerberos|Kerberos|  
|도메인 컴퓨터|NTLM|NTLM|Kerberos|Kerberos|  
  
 특히 네 가지 계정 형식에는 다음이 포함됩니다.  
  
-   로컬 사용자: 시스템 전용 사용자 프로필. 예를 들면 `MachineName\Administrator` 또는 `MachineName\ProfileName` 등입니다.  
  
-   로컬 시스템: 도메인에 연결되지 않은 컴퓨터의 기본 제공 계정인 SYSTEM.  
  
-   도메인 사용자: Windows 도메인의 사용자 계정. 예: `DomainName\ProfileName`  
  
-   도메인 컴퓨터: Windows 도메인에 연결된 컴퓨터에서 실행 중인 컴퓨터 ID가 있는 프로세스. 예: `MachineName\Network Service`  
  
> [!NOTE]
>  서비스 자격 증명은 <xref:System.ServiceModel.ICommunicationObject.Open%2A> 클래스의 <xref:System.ServiceModel.ServiceHost> 메서드가 호출될 때 캡처됩니다. 클라이언트 자격 증명은 클라이언트가 메시지를 보낼 때마다 읽어 옵니다.  
  
## <a name="common-windows-authentication-problems"></a>일반적인 Windows 인증 문제  
 이 단원에서는 몇 가지 일반적인 Windows 인증 문제와 그 해결 방법에 대해 설명합니다.  
  
### <a name="kerberos-protocol"></a>Kerberos 프로토콜  
  
#### <a name="spnupn-problems-with-the-kerberos-protocol"></a>Kerberos 프로토콜에 대한 SPN/UPN 문제  
 Windows 인증을 사용할 때 Kerberos 프로토콜을 사용하거나 SSPI 협상을 수행하는 경우, 클라이언트 끝점에 사용되는 URL은 서비스 URL 내에 있는 서비스 호스트의 정규화된 도메인 이름을 포함해야 합니다. 이 가정 아래에 있는 서비스를 실행 하 여 가장 일반적으로 수행 되는 Active Directory 도메인에 컴퓨터 추가 될 때 만들어지는 컴퓨터 (기본값) 서비스 사용자 이름 (SPN) 키에 대 한 액세스 서비스가 실행 중인 계정에는 네트워크 서비스 계정입니다. 서비스에 시스템 SPN 키에 대한 액세스 권한이 없는 경우 클라이언트의 끝점 ID로 서비스가 실행 중인 계정의 올바른 SPN 또는 UPN(User Principal Name)을 제공해야 합니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]어떻게 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] SPN 및 UPN을 사용 하 여 참조 [서비스 Id 및 인증](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)합니다.  
  
 웹 팜 또는 웹 가든과 같은 부하 분산 시나리오에서는 각 응용 프로그램에 대해 고유한 계정을 정의하고, 해당 계정에 SPN을 할당하고, 응용 프로그램의 모든 서비스가 해당 계정으로 실행되도록 하는 것이 일반적입니다.  
  
 서비스 계정에 대한 SPN을 얻으려면 Active Directory 도메인 관리자여야 합니다. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Windows 용 Kerberos 기술 보충 자료](http://go.microsoft.com/fwlink/?LinkID=88330)합니다.  
  
#### <a name="kerberos-protocol-direct-requires-the-service-to-run-under-a-domain-machine-account"></a>Kerberos 프로토콜을 직접 사용하려면 도메인 컴퓨터 계정으로 서비스 실행이 필요  
 이는 다음 코드처럼 `ClientCredentialType` 속성이 `Windows`로 설정되고, <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A> 속성이 `false`로 설정된 경우 발생합니다.  
  
 [!code-csharp[C_DebuggingWindowsAuth#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_debuggingwindowsauth/cs/source.cs#1)]
 [!code-vb[C_DebuggingWindowsAuth#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_debuggingwindowsauth/vb/source.vb#1)]  
  
 이 문제를 해결하려면 도메인과 연결된 컴퓨터에서 Network Service 등의 도메인 컴퓨터 계정을 사용하여 서비스를 실행합니다.  
  
### <a name="delegation-requires-credential-negotiation"></a>위임에 자격 증명 협상 필요  
 Kerberos 인증 프로토콜을 위임과 함께 사용하려면 자격 증명 협상이 포함된 Kerberos 프로토콜("multi-leg" 또는 "multi-step" Kerberos라고 함)을 구현해야 합니다. 자격 증명 협상이 포함되지 않은 Kerberos 프로토콜("one-shot" 또는 "single-leg" Kerberos라고도 함)을 구현하면 예외가 throw됩니다.  
  
 자격 증명 협상이 포함된 Kerberos 프로토콜을 구현하려면 다음 단계를 수행합니다.  
  
1.  <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A>을 <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>으로 설정하여 위임을 구현합니다.  
  
2.  SSPI 협상이 필요합니다.  
  
    1.  표준 바인딩을 사용하는 경우 `NegotiateServiceCredential` 속성을 `true`로 설정합니다.  
  
    2.  사용자 지정 바인딩을 사용하는 경우 `AuthenticationMode` 요소의 `Security` 속성을 `SspiNegotiated`로 설정합니다.  
  
3.  NTLM 사용을 허용하지 않고 Kerberos를 사용하려면 SSPI 협상이 필요합니다.  
  
    1.  `ChannelFactory.Credentials.Windows.AllowNtlm = false` 문과 함께 코드에서 이 작업을 수행합니다.  
  
    2.  `allowNtlm` 특성을 `false`로 설정하여 구성 파일에서 이 작업을 수행할 수도 있습니다. 이 특성에 포함 되어는 [ \<windows >](../../../../docs/framework/configure-apps/file-schema/wcf/windows-of-clientcredentials-element.md)합니다.  
  
### <a name="ntlm-protocol"></a>NTLM 프로토콜  
  
#### <a name="negotiate-ssp-falls-back-to-ntlm-but-ntlm-is-disabled"></a>협상 SSP가 NTLM으로 대체되어도 NTLM을 사용하지 않도록 설정  
 <xref:System.ServiceModel.Security.WindowsClientCredential.AllowNtlm%2A> 속성이 `false`로 설정되어 있어 NTLM이 사용될 경우 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서 예외가 throw됩니다. 이 속성을 `false`로 설정하면 유선을 통해 NTLM 자격 증명을 보낼 수 있습니다.  
  
 다음은 NTLM으로 대체되지 않도록 설정하는 방법을 보여 줍니다.  
  
 [!code-csharp[C_DebuggingWindowsAuth#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_debuggingwindowsauth/cs/source.cs#4)]
 [!code-vb[C_DebuggingWindowsAuth#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_debuggingwindowsauth/vb/source.vb#4)]  
  
#### <a name="ntlm-logon-fails"></a>NTLM 로그온 실패  
 클라이언트 자격 증명이 서비스에 유효하지 않습니다. 사용자 이름과 암호를 올바르게 설정했는지, 서비스를 실행하는 컴퓨터에서 인식하는 계정과 일치하는지 확인합니다. NTLM에서는 서비스의 컴퓨터에 로그온하기 위해 지정된 자격 증명을 사용합니다. 클라이언트를 실행하는 컴퓨터에서 유효한 자격 증명이라도 서비스의 컴퓨터에서 유효하지 않으면 로그온이 실패합니다.  
  
#### <a name="anonymous-ntlm-logon-occurs-but-anonymous-logons-are-disabled-by-default"></a>익명 NTLM 로그온을 수행해도 기본적으로 익명 로그온을 사용하지 않도록 설정  
 클라이언트를 만들 때 다음 예제에서처럼 <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> 속성이 <xref:System.Security.Principal.TokenImpersonationLevel.Anonymous>로 설정되지만 기본적으로 서버에서 익명 로그온을 허용하지 않습니다. 이는 <xref:System.ServiceModel.Security.WindowsServiceCredential.AllowAnonymousLogons%2A> 클래스의 <xref:System.ServiceModel.Security.WindowsServiceCredential> 속성의 기본값이 `false`로 설정되기 때문에 발생합니다.  
  
 다음 클라이언트 코드에서는 익명 로그온을 사용하도록 설정합니다. 기본 속성은 `Identification`입니다.  
  
 [!code-csharp[C_DebuggingWindowsAuth#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_debuggingwindowsauth/cs/source.cs#5)]
 [!code-vb[C_DebuggingWindowsAuth#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_debuggingwindowsauth/vb/source.vb#5)]  
  
 다음 서비스 코드에서는 서버에서 익명 로그온을 사용하도록 기본값을 변경합니다.  
  
 [!code-csharp[C_DebuggingWindowsAuth#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_debuggingwindowsauth/cs/source.cs#6)]
 [!code-vb[C_DebuggingWindowsAuth#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_debuggingwindowsauth/vb/source.vb#6)]  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]가장을 사용 하면 참조 [위임 및 가장](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)합니다.  
  
 또는 기본 제공 계정인 SYSTEM을 사용하여 클라이언트를 Windows 서비스로 실행합니다.  
  
### <a name="other-problems"></a>기타 문제  
  
#### <a name="client-credentials-are-not-set-correctly"></a>클라이언트 자격 증명이 올바르게 설정되지 않음  
 Windows 인증에서는 <xref:System.ServiceModel.Security.WindowsClientCredential>을 사용하지 않고, <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> 클래스의 <xref:System.ServiceModel.ClientBase%601> 속성에서 반환된 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential> 인스턴스를 사용합니다. 다음은 잘못된 예제입니다.  
  
 [!code-csharp[C_DebuggingWindowsAuth#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_debuggingwindowsauth/cs/source.cs#2)]
 [!code-vb[C_DebuggingWindowsAuth#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_debuggingwindowsauth/vb/source.vb#2)]  
  
 다음은 올바른 예제입니다.  
  
 [!code-csharp[C_DebuggingWindowsAuth#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_debuggingwindowsauth/cs/source.cs#3)]
 [!code-vb[C_DebuggingWindowsAuth#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_debuggingwindowsauth/vb/source.vb#3)]  
  
#### <a name="sspi-is-not-available"></a>SSPI를 사용할 수 없음  
 다음 운영 체제 서버로 사용 될 때 Windows 인증을 지원 하지 않습니다: [!INCLUDE[wxp](../../../../includes/wxp-md.md)] Home Edition, [!INCLUDE[wxp](../../../../includes/wxp-md.md)] Media Center Edition 및 [!INCLUDE[wv](../../../../includes/wv-md.md)]Home edition.  
  
#### <a name="developing-and-deploying-with-different-identities"></a>다른 ID로 개발 및 배포  
 응용 프로그램을 한 컴퓨터에서 개발하여 다른 컴퓨터에 배포하고 서로 다른 계정 형식을 사용하여 각 컴퓨터에서 인증을 수행하면 동작이 동일하지 않을 수 있습니다. 예를 들어 `SSPI Negotiated` 인증 모드를 사용하여 Windows XP Pro 컴퓨터에서 응용 프로그램을 개발할 경우 로컬 사용자 계정을 사용하여 인증하면 NTLM 프로토콜이 사용됩니다. 응용 프로그램 개발을 마친 후 도메인 계정으로 실행되는 Windows Server 2003 컴퓨터에 해당 서비스를 배포하면 클라이언트에서는 Kerberos 및 도메인 컨트롤러를 사용할 것이므로 해당 서비스를 인증할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Security.WindowsClientCredential>  
 <xref:System.ServiceModel.Security.WindowsServiceCredential>  
 <xref:System.ServiceModel.Security.WindowsClientCredential>  
 <xref:System.ServiceModel.ClientBase%601>  
 [위임 및 가장](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)  
 [지원되지 않는 시나리오](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)
