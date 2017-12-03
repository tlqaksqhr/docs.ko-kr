---
title: "방법: 서명 확인 설정"
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
- signature confirmation
- WCF, security
ms.assetid: 2424c137-c7c2-4aa9-8d5d-a066e12fefda
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fced2ddd16ae244e2ea3d945082f48ffd23302e6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-set-up-a-signature-confirmation"></a>방법: 서명 확인 설정
*서명 확인* 수신한 회신 원래 메시지 보낸 사람에 대 한 응답으로 생성 된 메시지 개시자에 대 한 메커니즘입니다. 서명 확인은 WS-Security 1.1 사양에서 정의됩니다. 끝점이 WS-Security 1.0을 지원할 경우, 서명 확인을 사용할 수 없습니다.  
  
 다음 절차에서는 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>를 사용하여 서명 확인을 사용하도록 설정하는 방법을 지정합니다. <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>를 사용하는 경우에도 동일한 절차를 사용할 수 있습니다. 에 기본 단계를 바탕으로 프로시저 [하는 방법: SecurityBindingElement를 사용자 지정 바인딩을 사용 하 여 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)합니다.  
  
### <a name="to-enable-signature-confirmation-in-code"></a>코드에서 서명 확인을 사용하도록 설정하려면  
  
1.  <xref:System.ServiceModel.Channels.BindingElementCollection> 클래스의 인스턴스를 만듭니다.  
  
2.  인스턴스를 만들고는 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> 클래스입니다.  
  
3.  <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A>를 `true`으로 설정합니다.  
  
4.  보안 요소를 바인딩 컬렉션에 추가합니다.  
  
5.  에 지정 된 대로 사용자 지정 바인딩을 만들려면 [하는 방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩을 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)합니다.  
  
### <a name="to-enable-signature-confirmation-in-configuration"></a>구성에서 서명 확인을 사용하도록 설정하려면  
  
1.  `<customBinding>` 요소를 구성 파일의 `<bindings>` 섹션에 추가합니다.  
  
2.  `<binding>` 요소를 추가하고 이름 특성을 적절한 값으로 설정합니다.  
  
3.  적절한 인코딩 요소를 추가합니다. 다음 예제에서는 `<TextMessageEncoding>` 요소를 추가합니다.  
  
4.  `<security>` 자식 요소를 추가하고 `requireSignatureConfirmation` 특성을 `true`로 설정합니다.  
  
5.  선택 사항입니다. 부트스트랩 중 서명 확인을 사용 하려면 추가 [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) 집합과, 자식 요소는 `equireSignatureConfirmation` 특성을 `true`합니다.  
  
6.  적절한 전송 요소를 추가합니다. 다음 예제에서는 추가 [ \<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md):  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="SignatureConfirmationBinding">  
          <security requireSignatureConfirmation="true">  
            <secureConversationBootstrap requireSignatureConfirmation="true" />  
              </security>  
           <textMessageEncoding />  
             <httpTransport />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
## <a name="example"></a>예제  
 다음 코드는 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>의 인스턴스를 만들고 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> 속성을 `true`로 설정합니다. 이 예제에서는 앞의 예제에서 살펴본 `<secureConversationBootstrap>` 요소를 사용하지 않습니다. 이 예제에서는 Windows(Kerberos 프로토콜) 토큰을 사용할 경우의 서명 확인을 보여 줍니다. 이 경우에는 클라이언트의 서명이 서비스로부터의 모든 응답에서 반환되며 클라이언트에 의해 확인됩니다.  
  
 [!code-csharp[c_SignatureConfirmation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_signatureconfirmation/cs/source.cs#1)]
 [!code-vb[c_SignatureConfirmation#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_signatureconfirmation/vb/source.vb#1)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>  
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>  
 [방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩을 만들려면](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [방법: 지정된 된 인증 모드에 대 한 SecurityBindingElement 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
