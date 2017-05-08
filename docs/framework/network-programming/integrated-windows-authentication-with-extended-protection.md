---
title: "확장된 보호를 사용하는 Windows 통합 인증 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 81731998-d5e7-49e4-ad38-c8e6d01689d0
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# 확장된 보호를 사용하는 Windows 통합 인증
향상 된 인증을 처리 하는 통합된 Windows에 영향을 주는 사항을 <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpListener>, <xref:System.Net.Mail.SmtpClient>, <xref:System.Net.Security.SslStream>, <xref:System.Net.Security.NegotiateStream>, 및 관련 된 클래스에는 <xref:System.Net> 및 관련 네임 스페이스.  보안을 향상 시키기 위해 확장된 보호에 대 한 지원 기능이 추가 되었습니다.  
  
 이러한 변경 사항은 Windows 통합된 인증이 사용 되는 위치 웹 요청 및 응답을 수신 하려면 이러한 클래스를 사용 하는 응용 프로그램에 영향을 줍니다.  이 변경 웹 서버 및 Windows 통합된 인증을 사용 하도록 구성 된 클라이언트 응용 프로그램에도 떨어질 수 있습니다.  
  
 이러한 변경 사항은 Windows 통합된 인증이 사용 되는 위치에 다른 종류의 요청을 확인 하 고 응답을 받을 이러한 클래스를 사용 하는 응용 프로그램 또한 달라질 수 있습니다.  
  
 확장된 된 보호를 지원 하도록 변경 Windows Server 2008 R2 및 Windows 7에서 응용 프로그램에 대해서만 사용할 수 있습니다.  이전 버전의 Windows에서는 확장된 보호 기능을 사용할 수 없습니다.  
  
## 개요  
 Windows 통합 인증의 디자인은 일부 자격 증명 시도 응답이 유니버설일 수 있도록 허용합니다. 즉 자격 증명 시도 응답을 다시 사용하거나 전달할 수 있습니다.  챌린지 응답도 최소한 특정 대상 정보 알려주고 일부 채널 특정 정보를 구성 해야.  다음 서비스 자격 증명 시도 응답 서비스 정보 등의 SPN \(서비스 사용자 이름\)를 포함할 수 있도록 확장된 보호를 제공할 수 있습니다.  자격 증명 교환에이 정보를 서비스를 부적절 하 게 사용 된 수 있는 자격 증명 챌린지 응답의 악의적인 사용에 대해 더 잘 보호할 수 있습니다.  
  
 확장된 된 보호 디자인 인증 프로토콜 인증 릴레이 공격을 완화 하도록 설계 된 향상입니다.  이 개념을 채널 및 서비스 바인딩 정보를 중심 으로합니다.  
  
 전반적인 목표는 다음과 같습니다.  
  
1.  클라이언트는 확장된 된 보호를 지원 하도록 업데이트 되 면 응용 프로그램 채널 바인딩과 서비스 바인딩 정보에 지원 되는 인증 프로토콜을 모두 제공 해야 합니다.  채널 \(TLS\)에 바인딩할 경우에 채널 바인딩 정보를 제공할 수 있습니다.  서비스 바인딩 정보를 항상 제공 해야 합니다.  
  
2.  제대로 구성 된 업데이트 서버 클라이언트 인증 토큰에 있는 경우 채널 및 서비스 바인딩 정보를 확인 하 고 채널 바인딩이 일치 하지 않을 경우 인증 시도 거부 있습니다.  배포 시나리오에 따라 서버 채널 바인딩, 서비스 바인딩 또는 둘 모두를 확인할 수 있습니다.  
  
3.  업데이트 된 서버 수락 또는 정책에 따라 채널 바인딩 정보를 포함 하지 않는 하위 수준 클라이언트 요청을 거부할 수가 있습니다.  
  
 확장된 된 보호에 사용 되는 정보 중 하나 또는 모두 다음 두 부품의 구성은 다음과 같습니다.  
  
1.  채널 바인딩 토큰 또는 CBT  
  
2.  서비스 사용자 이름 SPN의 형태로 서비스 바인딩 정보.  
  
 서비스 바인딩 정보는 특정 서비스 끝점을 인증 하는 클라이언트의 의도를 나타냅니다.  클라이언트에서 서버는 다음과 같은 속성을 가진 통신입니다.  
  
-   SPN 값은 일반 텍스트 형태로 클라이언트 인증을 수행 하는 서버를 사용할 수 있어야 합니다.  
  
-   SPN은 공용입니다.  
  
-   끼어 들기 공격 삽입, 제거 하거나, 해당 값을 수정할 수 없습니다는 SPN 전송 중에 암호화 방식으로 보호 되어야 합니다.  
  
 CBT에 속성을 연결 하는 데 외부 보안 채널 \(예: TLS\) \(바인딩\) 되는 안쪽의 클라이언트 인증 된 채널을 통해 대화를 합니다.  CBT는 다음 속성 \(IETF RFC 5056에서 정의 됨\) 해야 합니다.  
  
-   외부 채널에 있는 경우는 CBT의 값은 외부 채널 또는 독립적으로 시 대화 클라이언트와 서버 양쪽에서 도착 하지 서버 끝점을 식별 하는 속성 이어야 합니다.  
  
-   클라이언트가 보낸 CBT의 값은 공격자가 영향을 줄 수 수 없습니다.  
  
-   CBT 값의 비밀에 대 한 보장 없음에서 이루어집니다.  하지만이 CBT는 전달 프로토콜은 암호화 될 때 채널 바인딩 정보 뿐만 아니라 서비스 바인딩 값 항상 다른 있지만 서버 인증을 수행 하 여 검토할 수 있습니다 의미 하지는 않습니다.  
  
-   CBT는 암호화 무결성 공격자 삽입, 제거 하거나, 해당 값을 수정할 수 없습니다는 전송 중에 보호 해야 합니다.  
  
 채널 바인딩은 SPN과 CBT를 조작할 수 없게 된 방식으로 서버에 전송 하는 클라이언트에서 수행 됩니다.  서버가 해당 정책에 따라 채널 바인딩 정보의 유효성을 검사 하 고 거부 인증 시도 했을 대상으로 훌륭한 되지 않습니다.  이 이렇게 하면 두 채널 암호화 함께 바인딩되기 때문입니다.  
  
 기존 클라이언트 및 응용 프로그램 호환성을 유지 하기 위해 서버 인증 시도 허용 하도록 확장된 된 보호를 아직 지원 하지 않는 클라이언트에서 구성할 수 있습니다.  이 달리는 "완전히 강화 된" 구성 하는 "부분적으로 강화 된" 구성 이라고 합니다.  
  
 여러 구성 요소에는 <xref:System.Net> 및 <xref:System.Net.Security> 네임 스페이스는 호출 응용 프로그램 대신 Windows 통합된 인증을 수행 합니다.  System.Net 구성 요소를 사용 하는 Windows 통합된 인증에 확장 보호를 변경 내용을 설명 합니다.  
  
 확장된 된 보호는 현재 Windows 7에서 지원 됩니다.  응용 프로그램 운영 체제에서 확장된 된 보호를 지원 하는지 확인할 수 있도록 하는 메커니즘을 제공 합니다.  
  
## 보호 변경 지원 확장  
 인증 프로토콜에 따라 Windows 통합 인증을 사용 하는 인증 프로세스 사용, 발급 대상 컴퓨터에서 클라이언트 컴퓨터로 보낸 챌린지 등이 포함 되기도 합니다.  이 인증 프로세스에 확장된 보호 새로운 기능을 추가  
  
 <xref:System.Security.Authentication.ExtendedProtection> 네임스페이스는 응용 프로그램의 확장된 보호를 사용하여 인증을 지원합니다.  <xref:System.Security.Authentication.ExtendedProtection.ChannelBinding> 이 네임 스페이스의 클래스는 채널 바인딩을 나타냅니다.  <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> 이 네임 스페이스의 클래스를 나타내는 확장된 보호 정책 서버에서 들어오는 클라이언트 연결을 확인 하려면 사용 합니다.  다른 클래스 멤버 확장된 보호를 사용 합니다.  
  
 서버 응용 프로그램의 경우 이러한 클래스는 다음과 같습니다.  
  
 A <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> 는 다음과 같은 요소가 있습니다.  
  
-   <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.OSSupportsExtendedProtection%2A> 속성은 운영 체제에서 windows 통합된 인증에 확장된 보호를 지원 하는지 여부를 나타냅니다.  
  
-   확장 보호 정책을 적용할 시기를 나타내는 <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> 값입니다.  
  
-   A <xref:System.Security.Authentication.ExtendedProtection.ProtectionScenario> 배포 시나리오를 나타내는 값입니다.  이 보호를 확장된 하는 방법에 영향을 주는 검사입니다.  
  
-   선택적인 <xref:System.Security.Authentication.ExtendedProtection.ServiceNameCollection> 인증의 대상으로는 클라이언트가 제공한 SPN에 대해 일치 하는 SPN 목록이 들어 있습니다.  
  
-   선택적인 <xref:System.Security.Authentication.ExtendedProtection.ChannelBinding> 유효성 검사에 사용할 사용자 지정 채널 바인딩이 포함 되어 있습니다.  이 경우 일반적인 경우는 아닙니다.  
  
 <xref:System.Security.Authentication.ExtendedProtection.Configuration> 네임스페이스는 응용 프로그램의 확장된 보호를 사용하여 인증의 구성을 지원합니다.  
  
 기존에 확장된 된 보호를 지원 하도록 기능 변경 사항을 변경한 <xref:System.Net> 네임 스페이스입니다.  이러한 변경 내용은 다음과 같습니다.  
  
-   새 <xref:System.Net.TransportContext> 클래스에 추가 된 <xref:System.Net> 전송 컨텍스트를 나타내는 네임 스페이스.  
  
-   새 <xref:System.Net.HttpWebRequest.EndGetRequestStream%2A> 및 <xref:System.Net.HttpWebRequest.GetRequestStream%2A> 에서 메서드 오버 로드는 <xref:System.Net.HttpWebRequest> 검색을 허용 하는 클래스는 <xref:System.Net.TransportContext> 클라이언트 응용 프로그램에 대 한 확장된 된 보호를 지원 합니다.  
  
-   항목을 추가 하는 <xref:System.Net.HttpListener> 및 <xref:System.Net.HttpListenerRequest> 클래스 서버 응용 프로그램을 지원 합니다.  
  
 기존 SMTP 클라이언트 응용 프로그램에 대 한 확장된 된 보호 지원 기능 변경 했습니다 <xref:System.Net.Mail> 네임 스페이스:  
  
-   A <xref:System.Net.Mail.SmtpClient.TargetName%2A> 속성에는 <xref:System.Net.Mail.SmtpClient> 인증에 사용 하는 경우 사용할 SPN을 나타내는 클래스 확장 보호에 대 한 SMTP 클라이언트 응용 프로그램.  
  
 기존에 확장된 된 보호를 지원 하도록 기능 변경 사항을 변경한 <xref:System.Net.Security> 네임 스페이스입니다.  이러한 변경 내용은 다음과 같습니다.  
  
-   새 <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsClient%2A> 및 <xref:System.Net.Security.NegotiateStream.AuthenticateAsClient%2A> 에 메서드 오버 로드는 <xref:System.Net.Security.NegotiateStream> 클래스는 클라이언트 응용 프로그램에 대 한 확장된 된 보호를 지원 하 여 CBT 전달 되도록 허용 합니다.  
  
-   새 <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsServer%2A> 및 <xref:System.Net.Security.NegotiateStream.AuthenticateAsServer%2A> 에서 메서드 오버 로드는 <xref:System.Net.Security.NegotiateStream> 전달 허용 하는 클래스는 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> 서버 응용 프로그램에 대 한 확장된 된 보호를 지원 합니다.  
  
-   새 <xref:System.Net.Security.SslStream.TransportContext%2A> 속성에는 <xref:System.Net.Security.SslStream> 클래스를 클라이언트 및 서버 응용 프로그램에 대 한 확장된 된 보호를 지원 합니다.  
  
 A <xref:System.Net.Configuration.SmtpNetworkElement> 속성 SMTP 클라이언트에 대 한 확장된 된 보호 구성을 지원 하기 위해 추가 된 <xref:System.Net.Security> 네임 스페이스.  
  
## 클라이언트 응용 프로그램에 대 한 확장된 보호  
 대부분의 클라이언트 응용 프로그램에 대 한 확장된 된 보호 지원이 자동으로 발생합니다.  <xref:System.Net.HttpWebRequest> 및 <xref:System.Net.Mail.SmtpClient> 클래스 기본 버전의 Windows 확장된 된 보호를 지 원하는 때마다 확장된 된 보호를 지원 합니다.  <xref:System.Net.HttpWebRequest> 인스턴스에 보냅니다에서 생성 된 SPN에 <xref:System.Uri>.  기본적으로 <xref:System.Net.Mail.SmtpClient> 인스턴스 구성에서 SMTP 메일 서버 호스트 이름을 SPN을 보냅니다.  
  
 사용자 지정 인증에 대 한 클라이언트 응용 프로그램을 사용할 수 있습니다는 <xref:System.Net.HttpWebRequest.EndGetRequestStream%28System.IAsyncResult%2CSystem.Net.TransportContext%40%29?displayProperty=fullName> 또는 <xref:System.Net.HttpWebRequest.GetRequestStream%28System.Net.TransportContext%40%29?displayProperty=fullName> 방법에는 <xref:System.Net.HttpWebRequest> 검색을 허용 하는 클래스는 <xref:System.Net.TransportContext> 사용 하 여 CBT는 <xref:System.Net.TransportContext.GetChannelBinding%2A> 메서드.  
  
 SPN 보낸 Windows 통합된 인증을 사용 하는 <xref:System.Net.HttpWebRequest> 인스턴스는 지정 된 서비스를 설정 하 여 재정의할 수 있습니다는 <xref:System.Net.AuthenticationManager.CustomTargetNameDictionary%2A> 속성.  
  
 <xref:System.Net.Mail.SmtpClient.TargetName%2A> 속성을 사용 하 여 SMTP 연결에 대해 Windows 통합된 인증을 사용 하는 사용자 지정 SPN을 설정 합니다.  
  
## 서버 응용 프로그램을 위한 확장된 보호  
 <xref:System.Net.HttpListener>자동으로 HTTP 인증을 수행 하는 경우 서비스 바인딩 유효성을 검사 하는 메커니즘을 제공 합니다.  
  
 가장 안전한 시나리오 확장된 보호 HTTPS:\/\/ 접두사에 대 한 것입니다.  이 경우 설정 <xref:System.Net.HttpListener.ExtendedProtectionPolicy%2A?displayProperty=fullName> 에 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> 와 <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> 설정 <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> 또는 <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement>, 및 <xref:System.Security.Authentication.ExtendedProtection.ProtectionScenario> 설정 <xref:System.Security.Authentication.ExtendedProtection.ProtectionScenario> 값이 <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> 배치 <xref:System.Net.HttpListener> 부분적으로 강화 된 모드에서 동안 <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> 완전히 강화 된 모드에 해당.  
  
 이 구성에서 외부 보안 채널을 통해 서버에 요청이 있을 때 외부 채널 채널 바인딩은 쿼리 합니다.  이 채널 바인딩 채널 바인딩은 인증 blob 일치에서 확인 인증 SSPI 호출을 전달 합니다.  세 가지 결과가 나타날 수 있습니다.  
  
1.  기본 운영 체제는 서버 확장된 된 보호를 지원 하지 않습니다.  요청 응용 프로그램에 노출 되는 고가 무단된 \(401\) 응답이 클라이언트에 반환 됩니다.  메시지에 기록 됩니다의 <xref:System.Net.HttpListener> 실패의 원인을 지정 하는 추적 소스입니다.  
  
2.  SSPI 호출 실패 나타내는 외부 채널에서 예상 값이 일치 하지 않는 채널 바인딩을 검색 또는 클라이언트 제공에 대 한 확장된 된 보호 정책을 서버 구성 했을 때 채널 바인딩 실패 두 클라이언트가 지정한 <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement>.  두 경우 모두 요청이 응용 프로그램에 노출 되는 고가 무단된 \(401\) 응답이 클라이언트에 반환 됩니다.  메시지에 기록 됩니다의 <xref:System.Net.HttpListener> 실패의 원인을 지정 하는 추적 소스입니다.  
  
3.  올바른 채널 바인딩을 지정 클라이언트나 서버의 확장된 된 보호 정책이 구성 되어 있으므로 채널 바인딩을 지정 하지 않고 연결할 수 있는 <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> 요청이 처리를 위해 응용 프로그램에 반환 됩니다.  서비스 이름을 확인 하지 자동으로 수행 됩니다.  응용 프로그램 유효성 검사는 고유한 서비스 이름을 사용 하도록 선택할 수 있습니다는 <xref:System.Net.HttpListenerRequest.ServiceName%2A> 속성, 하지만 이러한 상황에서 중복 됩니다.  
  
 응용 프로그램이 HTTP 요청 본문 내에서 앞뒤로 전달 하는 blob에 기반한 인증을 수행 하는 자체 SSPI 호출 및 채널 바인딩을 지원 하려는 경우 예상된 채널 바인딩을 사용 하 여 외부 보안 채널 검색에 필요한 <xref:System.Net.HttpListener> 네이티브 win32에 전달 하기 위해 [AcceptSecurityContext](http://go.microsoft.com/fwlink/?LinkId=147021) 함수입니다.  이렇게 하려면 사용 하는 <xref:System.Net.HttpListenerRequest.TransportContext%2A> 속성 및 호출 <xref:System.Net.TransportContext.GetChannelBinding%2A> CBT를 검색 하는 메서드.  끝점 바인딩 에서만 지원 됩니다.  일을 다른 <xref:System.Security.Authentication.ExtendedProtection.ChannelBindingKind> 지정 된 <xref:System.NotSupportedException> throw 됩니다.  채널 바인딩, 기본 운영 체제를 지 원하는 경우는 <xref:System.Net.TransportContext.GetChannelBinding%2A> 메서드 반환는 <xref:System.Security.Authentication.ExtendedProtection.ChannelBinding><xref:System.Runtime.InteropServices.SafeHandle> 바인딩 전달할 적합 한 채널에 대 한 포인터를 배치 [AcceptSecurityContext](http://go.microsoft.com/fwlink/?LinkId=147021) 전달 SecBuffer 구조체의 pvBuffer 멤버 함수는 `pInput` 매개 변수.   <xref:System.Security.Authentication.ExtendedProtection.ChannelBinding.Size%2A> 속성의 길이 \(바이트\)에서입니다 채널 바인딩 포함 되어 있습니다.  기본 운영 체제 채널 바인딩을 지원 하지 않는 경우 함수 반환 합니다 `null`.  
  
 다른 가능한 시나리오 프록시가 사용 되지 않는 경우 HTTP:\/\/ 접두사에 대 한 확장된 보호 사용 됩니다.  이 경우 설정 <xref:System.Net.HttpListener.ExtendedProtectionPolicy%2A?displayProperty=fullName> 에 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> 와 <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> 설정 <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> 또는 <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement>, 및 <xref:System.Security.Authentication.ExtendedProtection.ProtectionScenario> 설정 <xref:System.Security.Authentication.ExtendedProtection.ProtectionScenario> 값이 <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> 배치 <xref:System.Net.HttpListener> 부분적으로 강화 된 모드에서 동안 <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> 완전히 강화 된 모드에 해당.  
  
 허용 된 서비스 이름 목록을 기본 등록 된 접두 번호에 따라 만들어지는 <xref:System.Net.HttpListener>.  이 기본 목록을 통해 검사할 수 있는 <xref:System.Net.HttpListener.DefaultServiceNames%2A> 속성.  이 목록은 포괄적 이면 응용 프로그램이 사용자 지정 서비스 이름 컬렉션 생성자에 지정할 수 있습니다에서 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> 클래스 기본 서비스 이름 목록 대신 사용 됩니다.  
  
 이 구성에서 채널 인증에는 서버 없이 외부 보안 요청이 있을 때 채널 바인딩을 검사 하지 않고 정상적으로 진행 됩니다.  인증에 성공 하면 클라이언트 제공 및 이름 목록에 허용 되는 서비스에 대해 유효성을 검사할 서비스 이름을 컨텍스트에서 쿼리 됩니다.  네 가지 결과가 나타날 수 있습니다.  
  
1.  기본 운영 체제는 서버 확장된 된 보호를 지원 하지 않습니다.  요청 응용 프로그램에 노출 되는 고가 무단된 \(401\) 응답이 클라이언트에 반환 됩니다.  메시지에 기록 됩니다의 <xref:System.Net.HttpListener> 실패의 원인을 지정 하는 추적 소스입니다.  
  
2.  클라이언트의 기본 운영 체제 확장된 된 보호를 지원 하지 않습니다.  에 <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> 구성, 인증 시도가 실패 하 고 요청 응용 프로그램에 반환 됩니다.  에 <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> 구성, 인증 시도가 실패 합니다.  요청 응용 프로그램에 노출 되는 고가 무단된 \(401\) 응답이 클라이언트에 반환 됩니다.  메시지에 기록 됩니다의 <xref:System.Net.HttpListener> 실패의 원인을 지정 하는 추적 소스입니다.  
  
3.  클라이언트의 기본 운영 체제 확장된 된 보호를 지원 하지만 응용 프로그램에서 서비스 바인딩을 지정 하지 않았습니다.  요청 응용 프로그램에 노출 되는 고가 무단된 \(401\) 응답이 클라이언트에 반환 됩니다.  메시지에 기록 됩니다의 <xref:System.Net.HttpListener> 실패의 원인을 지정 하는 추적 소스입니다.  
  
4.  클라이언트 서비스 바인딩을 지정 합니다.  서비스 바인딩 바인딩 허용 된 서비스 목록에 비교 합니다.  이 일치 하지 않으면 요청이 응용 프로그램에 반환 됩니다.  그렇지 않으면 요청이 응용 프로그램에 노출 되는 및 자동으로 무단된 \(401\) 응답이 클라이언트에 반환 됩니다.  메시지에 기록 됩니다의 <xref:System.Net.HttpListener> 실패의 원인을 지정 하는 추적 소스입니다.  
  
 허용 되는 서비스 이름에 허용 된 목록을 사용 하 여이 간단한 방법은 충분 한 경우 응용 프로그램이 자체 서비스 이름 유효성 검사를 쿼리하여 제공할 수 있습니다는 <xref:System.Net.HttpListenerRequest.ServiceName%2A> 속성.  1 및 2 위의 경우에는 속성을 반환 합니다 `null`.  Case 3이 빈 문자열을 반환 합니다.  클라이언트에서 지정한 서비스 이름을 반환할 경우 4입니다.  
  
 또한 이러한 확장된 보호 기능 요청 및 신뢰할 수 있는 프록시를 사용 하는 경우 다른 형식의 인증을 위해 서버 응용 프로그램에서 사용할 수 있습니다.  
  
## 참고 항목  
 <xref:System.Security.Authentication.ExtendedProtection>   
 <xref:System.Security.Authentication.ExtendedProtection.Configuration>