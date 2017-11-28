---
title: "방법: 사용자 지정 보안 토큰 인증자 만들기"
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
helpviewer_keywords: WCF, authentication
ms.assetid: 10e245f7-d31e-42e7-82a2-d5780325d372
caps.latest.revision: "12"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: cd9511642789cc8b5cade502941d54c5b88f625c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-custom-security-token-authenticator"></a>방법: 사용자 지정 보안 토큰 인증자 만들기
이 항목에서는 사용자 지정 보안 토큰 인증자를 만드는 방법과 이를 사용자 지정 보안 토큰 관리자와 통합하는 방법에 대해 설명합니다. 보안 토큰 인증자는 들어오는 메시지와 함께 제공된 보안 토큰 내용의 유효성을 검사합니다. 유효성 검사에 성공하면, 인증자는 평가 시 클레임 집합이 반환되는 <xref:System.IdentityModel.Policy.IAuthorizationPolicy> 인스턴스 컬렉션을 반환합니다.  
  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서 사용자 지정 보안 토큰 인증자를 사용하려면 먼저 사용자 지정 자격 증명과 보안 토큰 관리자 구현을 만들어야 합니다. 사용자 지정 자격 증명과 보안 토큰 관리자를 만들기에 대 한 자세한 내용은 참조 [연습: 사용자 지정 클라이언트 만들기 및 서비스 자격 증명](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)합니다. 자격 증명, 보안 토큰 관리자 및 공급자 및 인증자 클래스에 대 한 자세한 내용은 참조 [보안 아키텍처](http://msdn.microsoft.com/en-us/16593476-d36a-408d-808c-ae6fd483e28f)합니다.  
  
## <a name="procedures"></a>절차  
  
#### <a name="to-create-a-custom-security-token-authenticator"></a>사용자 지정 보안 토큰 인증자를 만들려면  
  
1.  <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator> 클래스에서 파생된 새 클래스를 정의합니다.  
  
2.  <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator.CanValidateTokenCore%2A> 메서드를 재정의합니다. 사용자 지정 인증자가 들어오는 토큰 형식의 유효성을 검사할 수 있는지 여부에 따라 메서드에서 `true` 또는 `false`를 반환합니다.  
  
3.  <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator.ValidateTokenCore%2A> 메서드를 재정의합니다. 이 메서드는 토큰 내용의 유효성을 검사하는 데 필요합니다. 토큰이 유효성 검사 단계를 통과하면 메서드가 <xref:System.IdentityModel.Policy.IAuthorizationPolicy> 인스턴스의 컬렉션을 반환합니다. 다음 예제에서는 다음 절차에서 만들 사용자 지정 권한 부여 정책 구현이 사용됩니다.  
  
     [!code-csharp[C_CustomTokenAuthenticator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenauthenticator/cs/source.cs#1)]
     [!code-vb[C_CustomTokenAuthenticator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenauthenticator/vb/source.vb#1)]  
  
 이전 코드는 <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator.CanValidateToken%28System.IdentityModel.Tokens.SecurityToken%29> 메서드에서 권한 부여 정책 컬렉션을 반환합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 이 인터페이스의 공용 구현을 제공하지 않습니다. 다음 절차에서는 사용자 요구 사항에 맞게 이를 수행하는 방법을 보여 줍니다.  
  
#### <a name="to-create-a-custom-authorization-policy"></a>사용자 지정 권한 부여 정책을 만들려면  
  
1.  <xref:System.IdentityModel.Policy.IAuthorizationPolicy> 인터페이스를 구현하는 새 클래스를 정의합니다.  
  
2.  <xref:System.IdentityModel.Policy.IAuthorizationComponent.Id%2A> 읽기 전용 속성을 구현합니다. 이 속성을 구현하는 한 가지 방법은 클래스 생성자로 GUID(Globally Unique Identifier)를 만든 다음 이 속성 값이 요청될 때마다 이를 반환하는 것입니다.  
  
3.  <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Issuer%2A> 읽기 전용 속성을 구현합니다. 이 속성은 토큰에서 가져오는 클레임 집합 발급자를 반환하는 데 필요합니다. 이 발급자는 토큰 발급자이거나 토큰 내용의 유효성을 검사하는 인증 기관이어야 합니다. 다음 예제에서는 이전 절차에서 만든 사용자 지정 보안 토큰 인증자로부터 이 클래스에 전달된 발급자 클레임을 사용합니다. 사용자 지정 보안 토큰 인증자는 <xref:System.IdentityModel.Claims.ClaimSet.System%2A> 속성을 통해 반환된 시스템 제공 클레임 집합을 사용하여, 사용자 이름 토큰의 발급자를 나타냅니다.  
  
4.  <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%2A> 메서드를 구현합니다. 이 메서드는 인수로 전달된 <xref:System.IdentityModel.Policy.EvaluationContext> 클래스의 인스턴스를 들어오는 보안 토큰의 내용을 바탕으로 하는 클레임으로 채웁니다. 평가 시 이 작업이 완료되면 메서드는 `true`를 반환합니다. 평가 컨텍스트에 추가 정보를 제공하는 다른 권한 부여 정책을 사용하여 구현하는 경우, 필요한 정보가 평가 컨텍스트에 아직 없으면 이 메서드는 `false`를 반환할 수 있습니다. 이때 권한 부여 정책 중 하나 이상의 정책에 의해 평가 컨텍스트가 수정되면,[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 들어오는 메시지에 대해 생성된 기타 권한 부여 정책을 모두 평가한 후 이 메서드를 다시 호출합니다.  
  
     [!code-csharp[c_CustomTokenAuthenticator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenauthenticator/cs/source.cs#2)]
     [!code-vb[c_CustomTokenAuthenticator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenauthenticator/vb/source.vb#2)]  
  
 [연습: 사용자 지정 클라이언트 및 서비스 자격 증명 만들기](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md) 사용자 지정 자격 증명 및 사용자 지정 보안 토큰 관리자를 만드는 방법을 설명 합니다. 여기에서 만든 사용자 지정 보안 토큰 인증자를 사용하기 위해 <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenAuthenticator%2A> 메서드에서 사용자 지정 인증자를 반환하도록 보안 토큰 관리자의 구현이 수정됩니다. 올바른 보안 토큰 요구 사항이 전달되면 메서드에서 인증자를 반환합니다.  
  
#### <a name="to-integrate-a-custom-security-token-authenticator-with-a-custom-security-token-manager"></a>사용자 지정 보안 토큰 인증자를 사용자 지정 보안 토큰 관리자와 통합하려면  
  
1.  사용자 지정 보안 토큰 관리자 구현에서 <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenAuthenticator%2A> 메서드를 재정의합니다.  
  
2.  메서드에 논리를 추가하여<xref:System.IdentityModel.Selectors.SecurityTokenRequirement> 매개 변수를 기반으로 사용자 지정 보안 토큰 인증자를 반환할 수 있도록 합니다. 다음 예제에서는 토큰에서 요구하는 토큰 형식이 사용자 이름(<xref:System.IdentityModel.Tokens.SecurityTokenTypes.UserName%2A> 속성으로 나타냄)이고 요청되는 보안 토큰 인증자에 대한 메시지 방향이 입력(<xref:System.ServiceModel.Description.MessageDirection.Input> 필드로 나타냄)이면 사용자 지정 보안 토큰 인증자를 반환합니다.  
  
     [!code-csharp[c_CustomTokenAuthenticator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenauthenticator/cs/source.cs#3)]
     [!code-vb[c_CustomTokenAuthenticator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenauthenticator/vb/source.vb#3)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator>  
 <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>  
 <xref:System.IdentityModel.Selectors.SecurityTokenManager>  
 <xref:System.IdentityModel.Tokens.UserNameSecurityToken>  
 [연습: 사용자 지정 클라이언트 및 서비스 자격 증명 만들기](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)  
 [방법: 사용자 지정 보안 토큰 공급자 만들기](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)  
 [보안 아키텍처](http://msdn.microsoft.com/en-us/16593476-d36a-408d-808c-ae6fd483e28f)
