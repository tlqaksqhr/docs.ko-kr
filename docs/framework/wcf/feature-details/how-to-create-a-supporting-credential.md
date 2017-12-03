---
title: "방법: 지원하는 자격 증명 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0952919-8bb4-4978-926c-9cc108f89806
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a460a3fdd48813801b18af5a896252134687816d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-supporting-credential"></a>방법: 지원하는 자격 증명 만들기
둘 이상의 자격 증명이 필요한 사용자 지정 보안 체계를 사용할 수 있습니다. 예를 들어 서비스는 클라이언트로부터 사용자 이름과 암호뿐 아니라 클라이언트가 18세 이상임을 입증하는 자격 증명을 요구할 수 있습니다. 두 번째 자격 증명은는 *지원 자격 증명*합니다. 이 항목에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 클라이언트에 이러한 자격 증명을 구현하는 방법에 대해 설명합니다.  
  
> [!NOTE]
>  지원 자격 증명의 사양은 WS-SecurityPolicy 사양의 일부입니다. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][웹 서비스 보안 사양](http://go.microsoft.com/fwlink/?LinkId=88537)합니다.  
  
## <a name="supporting-tokens"></a>Supporting Tokens  
 간단히 말해서 사용 하는 경우 메시지 보안을 한 *기본 자격 증명* (예: X.509 인증서 또는 Kerberos 티켓) 메시지 보안을 위해 항상 사용 됩니다.  
  
 보안 바인딩에서 사용 하 여 사양에 정의 된 대로 *토큰* 를 메시지 교환의 보안을 유지 합니다. A *토큰* 보안 자격 증명의 표현입니다.  
  
 보안 바인딩은 보안 바인딩 정책에 식별된 기본 토큰을 사용하여 서명을 만듭니다. 이 서명은 라고는 *메시지 서명에*합니다.  
  
 추가 토큰을 지정하여 메시지 서명과 연결된 토큰이 제공하는 클레임을 증대시킬 수 있습니다.  
  
## <a name="endorsing-signing-and-encrypting"></a>보증, 서명 및 암호화  
 지원 자격 증명으로 인해 한 *지원 토큰* 메시지 내부에서 전송 합니다. WS-SecurityPolicy 사양은 다음 표에 설명된 것처럼 지원 토큰을 메시지에 첨부하는 네 가지 방법을 정의합니다.  
  
|용도|설명|  
|-------------|-----------------|  
|서명|지원 토큰은 보안 헤더에 포함되고 메시지 서명으로 서명됩니다.|  
|보증|*보증 토큰* 메시지 서명에 서명 합니다.|  
|서명 및 보증|서명된 보증 토큰은 메시지 서명에서 생성된 `ds:Signature` 요소에 서명하고 그 자체가 해당 메시지 서명으로 서명됩니다. 즉, 두 토큰(메시지 서명에 사용된 토큰과 서명된 보증 토큰)이 서로에 서명합니다.|  
|서명 및 암호화|서명 및 암호화된 지원 토큰은 `wsse:SecurityHeader`에 나타날 때 암호화되는 서명된 지원 토큰입니다.|  
  
## <a name="programming-supporting-credentials"></a>지원 자격 증명 프로그래밍  
 지원 토큰을 만들어야 합니다를 사용 하는 서비스를 만들려면는 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)합니다. ([!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [하는 방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩을 만들려면](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).)  
  
 사용자 지정 바인딩을 만들 때의 첫 단계는 다음 세 가지 형식 중 하나일 수 있는 보안 바인딩 요소를 만드는 작업입니다.  
  
-   <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>  
  
-   <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>  
  
-   <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>  
  
 모든 클래스는 다음 네 가지 관련 속성을 포함하는 <xref:System.ServiceModel.Channels.SecurityBindingElement>에서 상속됩니다.  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.EndpointSupportingTokenParameters%2A>  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.OperationSupportingTokenParameters%2A>  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.OptionalEndpointSupportingTokenParameters%2A>  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.OptionalOperationSupportingTokenParameters%2A>  
  
#### <a name="scopes"></a>범위  
 지원 자격 증명에 대한 두 가지 범위가 있습니다.  
  
-   *끝점 지원 토큰* 끝점의 모든 작업을 지원 합니다. 즉, 끝점 작업을 호출할 때마다 지원 토큰이 나타내는 자격 증명을 사용할 수 있습니다.  
  
-   *작업 지원 토큰* 특정 끝점 작업만 지원 합니다.  
  
 속성 이름이 나타내는 것처럼 지원 자격 증명은 필수 또는 옵션일 수 있습니다. 즉, 지원 자격 증명이 있으면 필요하지 않아도 사용되지만 없어도 인증이 실패하지 않습니다.  
  
## <a name="procedures"></a>절차  
  
#### <a name="to-create-a-custom-binding-that-includes-supporting-credentials"></a>지원 자격 증명을 포함하는 사용자 지정 바인딩을 만들려면  
  
1.  보안 바인딩 요소를 만듭니다. 아래 예제에서는 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> 인증 모드로 `UserNameForCertificate`를 만듭니다. <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForCertificateBindingElement%2A> 메서드를 사용하세요.  
  
2.  해당 속성(`Endorsing`, `Signed`, `SignedEncrypted` 또는 `SignedEndorsed`)에 의해 반환된 형식 컬렉션에 지원 매개 변수를 추가합니다. <xref:System.ServiceModel.Security.Tokens> 네임스페이스의 형식에는 <xref:System.ServiceModel.Security.Tokens.X509SecurityTokenParameters> 같은 자주 사용되는 형식이 포함됩니다.  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 다음 예제에서는 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>의 인스턴스를 만들고 <xref:System.ServiceModel.Security.Tokens.KerberosSecurityTokenParameters> 클래스의 인스턴스를 반환된 Endorsing 속성 컬렉션에 추가합니다.  
  
### <a name="code"></a>코드  
 [!code-csharp[c_SupportingCredential#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_supportingcredential/cs/source.cs#1)]  
  
## <a name="see-also"></a>참고 항목  
 [방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩을 만들려면](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
