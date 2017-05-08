---
title: "WIF 세션 관리 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 98bce126-18a9-401b-b20d-67ee462a5f8a
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# WIF 세션 관리
먼저 클라이언트는 상대가 호스팅되는 보호 된 리소스에 액세스 하려고 하면 클라이언트는 먼저 자체 상대가 신뢰할 수 있는 보안 토큰 서비스 \(STS\)에 인증 해야 합니다.  다음 sts 보안 토큰은 클라이언트에.  상대가 다음 보호 된 리소스에 대 한 클라이언트 액세스 권한을 부여 하려면이 토큰이 클라이언트를 제공 합니다.  그러나 특히이 경우에 동일한 컴퓨터에서 또는 동일한 도메인에 상대가 될 수 있으므로 STS에 대 한 각 요청을 다시 인증 하는 데 클라이언트를 않을 수 있습니다.  대신 소리치 \(Windows Identity Foundation 더\) 클라이언트와의 세션에 세션 보안 토큰 자체는 상대가 모든 요청에 대 한 첫 번째 요청 후 인증을 클라이언트에서 사용 하는 상대가 있습니다.  상대가 쿠키 내에 저장 되어,이 세션 보안 토큰을 클라이언트의 재구성 수 <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=fullName>.  
  
 STS는 클라이언트가 제공 해야 하는 어떤 인증을 정의 합니다.  그러나 클라이언트는 여러 자격 증명을 그 자체 STS에 인증할 수 있을 수 있습니다.  예를 들어 토큰에서 Windows Live, 사용자 이름 및 암호, 인증서 및 smartkey는 있을 수 있습니다.  STS의 경우 클라이언트를 여러 id를 클라이언트에 제공 하는 자격 증명 중 하나에 해당 하는 각 id 부여 합니다.  이 클라이언트에 게 부여할 액세스 수준을 결정 하는 경우는 상대가 이러한 id 중 하나를 사용할 수 있습니다.  
  
 <xref:System.IdentityModel.Tokens.SessionSecurityToken?displayProperty=fullName> 클라이언트를 다시 만드는 데 사용 됩니다 <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=fullName>를 포함 모든 클라이언트의 id에 <xref:System.Security.Claims.ClaimsPrincipal.Identities%2A>.  각 <xref:System.Security.Claims.ClaimsIdentity?displayProperty=fullName> 해당 id와 연관 된 부트스트랩 토큰 컬렉션에 포함 됩니다.  
  
 새 세션 토큰의 원래 세션 토큰을 세션 ID로 실행 되는 경우 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler?displayProperty=fullName> 세션 토큰을 토큰 캐시에서를 업데이트 하지 않습니다.  항상 고유한 세션 id가 세션 토큰을 인스턴스화하지 않아야  
  
> [!NOTE]
>  Session.SecurityTokenHandler.ReadToken throw 된 <xref:System.Xml.XmlException> 입력, 잘못 된 문자를 수신 하는 경우 예외 예를 들어, 쿠키는 세션 토큰이 손상 되어 있는 경우.  이 예외를 catch 하 고 응용 프로그램별 동작을 제공 하는 것이 좋습니다.  
  
 보호 된 웹 페이지도 보호 된 도메인에 있는 리소스 \(예: 작은 그래픽\) 많이 있으면 클라이언트 리소스를 다운로드 하려면 상대가를 다시 인증 해야 합니다.  STS에 대 한 각 요청을 인증할 필요가 세션 인증 토큰의 사용을 피할 수 있지만 쿠키에서 전송 되는 것도 의미 합니다.  부 항목은 보호 되지 않은 도메인에 저장 되 고 주 웹 페이지에서 연결 하는 동안 중요 한 데이터와 리소스를 보호 된 도메인에 저장 된 웹 페이지를 설정 할 수 있습니다.  또한 보호 된 도메인만 참조 하도록 쿠키 경로 설정 합니다.  
  
 에 대 한 처리기를 제공 하는 것이 좋습니다 참조 모드에서 작동 하는 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SessionSecurityTokenCreated> 이벤트에는  **global.asax.cs** 파일 및 설정의  **IsReferenceMode** 속성에서 토큰을 전달의 <xref:System.IdentityModel.Services.SessionSecurityTokenCreatedEventArgs.SessionToken%2A> 속성.  이러한 업데이트 세션 토큰 모든 요청에 대 한 참조 모드에서 작동 하 고 단지 설정 보다 좋아하는 것은 <xref:System.IdentityModel.Services.SessionAuthenticationModule.IsReferenceMode%2A> 세션 인증 모듈에 대 한 속성.  
  
## 확장성  
 세션 관리 메커니즘을 확장할 수 있습니다.  왜냐하면 성능을 향상 시킬 수 있습니다.  예를 들어, 변환 또는 메모리 상태 및 쿠키로 해결 사이의 세션 보안 토큰을 최적화 하는 사용자 지정 쿠키 처리기를 만들 수 있습니다.  이렇게 하 여 구성할 수 있습니다는 <xref:System.IdentityModel.Services.SessionAuthenticationModule.CookieHandler%2A?displayProperty=fullName> 속성에는 <xref:System.IdentityModel.Services.SessionAuthenticationModule?displayProperty=fullName> 에서 파생 되는 사용자 지정 쿠키 처리기를 사용 하 <xref:System.IdentityModel.Services.CookieHandler?displayProperty=fullName>.  <xref:System.IdentityModel.Services.ChunkedCookieHandler?displayProperty=fullName>쿠키는 HTTP \(하이퍼텍스트 전송 프로토콜에 대 한\) 허용 크기를 초과 하기 때문에 기본 쿠키 처리기가입니다. 대신 사용자 지정 쿠키 처리기를 사용 하는 경우 청크를 구현 해야 합니다.  
  
 자세한 내용은 [ClaimsAwareWebFarm](http://go.microsoft.com/fwlink/?LinkID=248408) \(http:\/\/go.microsoft.com\/fwlink\/?LinkID\=248408\) 샘플입니다.  세션 참조 대신 큰 쿠키를 교환 하 여 사용할 수 있도록이 샘플에서는 팜 준비 세션 캐시를 \(반대는 tokenreplycache\)를 보여 줍니다. 보안 쿠키는 팜에서 쉽게 샘플.  세션 캐시는 WCF 기반입니다.  보안 세션 관련 소리치 더 4.5 쿠키 변환 하기만 하면 해당 코드 조각을 web.config에 붙여넣어 활성화 될 수 있는 한 Machinekey를 기반으로 하는 새로운 기능을 샘플을 보여 줍니다.  팜 샘플 "의 수 없습니다", 하지만 팜 준비 응용 프로그램을 만드는 데 필요한 방법을 보여 줍니다.