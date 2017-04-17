---
title: "방법: SecurityBindingElement를 사용하여 사용자 지정 바인딩 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "보안 [WCF] 사용자 지정 바인딩 만들기"
ms.assetid: 203a9f9e-3a73-427c-87aa-721c56265b29
caps.latest.revision: 19
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 19
---
# 방법: SecurityBindingElement를 사용하여 사용자 지정 바인딩 만들기
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에는 구성할 수 있지만 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 지원하는 모든 보안 옵션을 구성할 때 완벽한 유연성을 제공하지는 않는 여러 시스템 제공 바인딩이 포함되어 있습니다. 이 항목에서는 개별 바인딩 요소에서 직접 사용자 지정 바인딩을 만드는 방법에 대해 설명하고, 이와 같은 바인딩을 만들 때 지정할 수 있는 일부 보안 설정에 대해 강조합니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]사용자 지정 바인딩 만들기, 참조 [바인딩 확장](../../../../docs/framework/wcf/extending/extending-bindings.md)합니다.  
  
> [!WARNING]
>  <xref:System.ServiceModel.Channels.SecurityBindingElement> 지원 하지 않습니다는 <xref:System.ServiceModel.Channels.IDuplexSessionChannel> 채널 셰이프는 기본 채널 셰이프 사용 하는 TCP가 인 경우 전송 <xref:System.ServiceModel.TransferMode> 로 설정 되어 <xref:System.ServiceModel.TransferMode.Buffered>합니다. 설정 해야 <xref:System.ServiceModel.TransferMode> 를 <xref:System.ServiceModel.TransferMode.Streamed> 사용 하기 위해 <xref:System.ServiceModel.Channels.SecurityBindingElement> 이 시나리오에서는 합니다.  
  
## <a name="creating-a-custom-binding"></a>사용자 지정 바인딩 만들기  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 모든 바인딩이 구성 된 *바인딩 요소의*합니다. 각 바인딩 요소에서 파생 되는 <xref:System.ServiceModel.Channels.BindingElement> 클래스입니다. 표준 시스템 제공 바인딩의 경우 바인딩 요소가 자동으로 생성되어 구성되지만 일부 속성 설정을 사용자 지정할 수 있습니다.  
  
 반면에 사용자 지정 바인딩을 만들려면 바인딩 요소를 만들고 구성 및 <xref:System.ServiceModel.Channels.CustomBinding> 바인딩 요소에서 생성 됩니다.  
  
 개별 바인딩 요소 인스턴스에 의해 표시 되는 컬렉션에 추가 하면이 위해는 <xref:System.ServiceModel.Channels.BindingElementCollection> 클래스를 다음 설정의 `Elements` 속성은 `CustomBinding` 해당 개체와 같지 합니다. 바인딩 요소는 Transaction Flow, Reliable Session, Security, Composite Duplex, One-way, Stream Security, Message Encoding, Transport 순으로 추가해야 합니다. 나열된 모든 바인딩 요소가 모든 바인딩에서 필요한 것은 아닙니다.  
  
## <a name="securitybindingelement"></a>SecurityBindingElement  
 세 개의 바인딩 요소에서 파생 되는 모두 메시지 수준 보안과 관련이 <xref:System.ServiceModel.Channels.SecurityBindingElement> 클래스입니다. 세 가지는 <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>, <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>, 및 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>합니다. <xref:System.ServiceModel.Channels.TransportSecurityBindingElement> 혼합된 모드 보안을 제공 하는 데 사용 됩니다. 다른 두 가지 요소는 메시지 계층이 보안을 제공할 때 사용합니다.  
  
 전송 수준 보안이 제공될 경우 다음과 같은 추가 클래스가 사용됩니다.  
  
-   <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
-   <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
  
-   <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
  
## <a name="required-binding-elements"></a>필요한 바인딩 요소  
 바인딩에 결합하여 사용할 수 있는 바인딩 요소는 많습니다. 그러나 이러한 조합이 모두 올바른 것은 아닙니다. 이 단원에서는 보안 바인딩에 있어야 하는 필수 요소에 대해 설명합니다.  
  
 올바른 보안 바인딩은 다음을 비롯한 많은 요인에 의해 결정됩니다.  
  
-   보안 모드  
  
-   전송 프로토콜  
  
-   계약에 지정된 MEP(메시지 교환 패턴)  
  
 다음 표에서는 위 요인의 조합별로 올바른 바인딩 요소 스택 구성을 보여 줍니다. 이는 최소 요구 사항입니다. 메시지 인코딩 바인딩 요소, 트랜잭션 바인딩 요소 및 기타 바인딩 요소와 같은 추가 바인딩 요소를 바인딩에 추가할 수 있습니다.  
  
|보안 모드|전송|계약 메시지 교환 패턴|계약 메시지 교환 패턴|계약 메시지 교환 패턴|  
|-------------------|---------------|---------------------------------------|---------------------------------------|---------------------------------------|  
|||`Datagram`|`Request Reply`|`Duplex`|  
|전송|Https||||  
|||OneWayBindingElement|||  
|||HttpsTransportBindingElement|HttpsTransportBindingElement||  
||TCP||||  
|||OneWayBindingElement|||  
|||@FSHO1@SSL 또는 Windows StreamSecurityBindingElement|@FSHO1@SSL 또는 Windows StreamSecurityBindingElement|@FSHO1@SSL 또는 Windows StreamSecurityBindingElement|  
|||TcpTransportBindingElement|TcpTransportBindingElement|TcpTransportBindingElement|  
|메시지|Http|SymmetricSecurityBindingElement|SymmetricSecurityBindingElement|@FSHO1@SymmetricSecurityBindingElement(인증 모드 = SecureConversation)|  
|||||CompositeDuplexBindingElement|  
|||OneWayBindingElement||OneWayBindingElement|  
|||HttpTransportBindingElement|HttpTransportBindingElement|HttpTransportBindingElement|  
||Tcp|SecurityBindingElement|SecurityBindingElement|@FSHO1@SymmetricSecurityBindingElement(인증 모드 = SecureConversation)|  
|||TcpTransportBindingElement|TcpTransportBindingElement|TcpTransportBindingElement|  
|혼합(메시지 자격 증명을 사용한 전송)|Https|TransportSecurityBindingElement|TransportSecurityBindingElement||  
|||OneWayBindingElement|||  
|||HttpsTransportBindingElement|HttpsTransportBindingElement||  
||TCP|TransportSecurityBindingElement|@FSHO1@SymmetricSecurityBindingElement(인증 모드 = SecureConversation)|@FSHO1@SymmetricSecurityBindingElement(인증 모드 = SecureConversation)|  
|||OneWayBindingElement|||  
|||@FSHO1@SSL 또는 Windows StreamSecurityBindingElement|@FSHO1@SSL 또는 Windows StreamSecurityBindingElement|@FSHO1@SSL 또는 Windows StreamSecurityBindingElement|  
|||TcpTransportBindingElement|TcpTransportBindingElement|TcpTransportBindingElement|  
  
 SecurityBindingElement에 대해 구성 가능한 설정이 많이 있습니다. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][SecurityBindingElement 인증 모드](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)합니다.  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][보안 대화 및 보안 세션](../../../../docs/framework/wcf/feature-details/secure-conversations-and-secure-sessions.md)합니다.  
  
## <a name="procedures"></a>절차  
  
#### <a name="to-create-a-custom-binding-that-uses-a-symmetricsecuritybindingelement"></a>SymmetricSecurityBindingElement를 사용하여 사용자 지정 바인딩을 만들려면  
  
1.  인스턴스를 만들고는 <xref:System.ServiceModel.Channels.BindingElementCollection> 클래스 이름의 `outputBec`합니다.  
  
2.  정적 메서드를 호출 `M:System.ServiceModel.Channels.SecurityBindingElement.CreateSspiNegotiationBindingElement(true)`의 인스턴스를 반환 하는 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> 클래스입니다.  
  
3.  추가 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> 컬렉션에 (`outputBec`)를 호출 하 여는 `Add` 의 메서드는 <xref:System.Collections.ObjectModel.Collection%601> 의 <xref:System.ServiceModel.Channels.BindingElement> 클래스입니다.  
  
4.  인스턴스를 만들고는 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> 클래스 컬렉션에 추가 합니다 (`outputBec`). 이를 통해 바인딩에서 사용하는 인코딩이 지정됩니다.  
  
5.  만들기는 <xref:System.ServiceModel.Channels.HttpTransportBindingElement> 컬렉션에 추가 합니다 (`outputBec`). 이를 통해 바인딩이 HTTP 전송을 사용하도록 지정됩니다.  
  
6.  인스턴스를 만들어 새 사용자 지정 바인딩 만들기는 <xref:System.ServiceModel.Channels.CustomBinding> 클래스와 컬렉션을 전달 `outputBec` 생성자에 있습니다.  
  
7.  결과 사용자 지정 바인딩은 표준과 동일한 특징을 많이 공유 <xref:System.ServiceModel.WSHttpBinding>합니다. 메시지 수준 보안 및 Windows 자격 증명을 지정하지만 보안 세션은 사용하지 않도록 설정하고, 서비스 자격 증명은 대역 외로 지정되어야 하며, 서명을 암호화하지 않습니다. 마지막 설정을 통해서만 제어할 수는 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A> 4 단계에서와 같이 속성입니다. 다른 두 가지는 표준 바인딩의 설정을 사용하여 제어할 수 있습니다.  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 다음 예에서는 완전 한 함수를 사용 하는 사용자 지정 바인딩을 만드는 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>합니다.  
  
### <a name="code"></a>코드  
 [!code-csharp[c_CustomBinding#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#20)]
 [!code-vb[c_CustomBinding#20](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_custombinding/vb/source.vb#20)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>   
 <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>   
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [바인딩 확장](../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [시스템 제공 바인딩](../../../../docs/framework/wcf/system-provided-bindings.md)