---
title: 사용자 정의 바인딩 만들기
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- user-defined bindings [WCF]
ms.assetid: c4960675-d701-4bc9-b400-36a752fdd08b
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 05476adccca0deb5fd82b62f99f06939664cc876
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="creating-user-defined-bindings"></a>사용자 정의 바인딩 만들기
시스템에서 제공하지 않는 바인딩은 다음과 같은 여러 가지 방법으로 만들 수 있습니다.  
  
-   바인딩 요소로 채워지는 컨테이너인 <xref:System.ServiceModel.Channels.CustomBinding> 클래스에 따라 사용자 지정 바인딩을 만듭니다. 그런 다음 사용자 지정 바인딩을 서비스 끝점에 추가합니다. 프로그램 방식이나 응용 프로그램 구성 파일을 통해 사용자 지정 바인딩을 만들 수 있습니다. 응용 프로그램 구성 파일에서 바인딩 요소를 사용하려면 바인딩 요소가 <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>를 확장해야 합니다. 사용자 지정 바인딩에 대 한 자세한 내용은 참조 하십시오. [사용자 지정 바인딩을](../../../../docs/framework/wcf/extending/custom-bindings.md) 및 <xref:System.ServiceModel.Channels.CustomBinding>합니다.  
  
-   표준 바인딩에서 파생되는 클래스를 만들 수 있습니다. 예를 들어, <xref:System.ServiceModel.WSHttpBinding>에서 클래스를 파생하고 <xref:System.ServiceModel.Channels.CustomBinding.CreateBindingElements%2A> 메서드를 재정의하여 바인딩 요소를 가져온 후 사용자 지정 바인딩 요소를 삽입하거나 특정 보안 값을 설정할 수 있습니다.  
  
-   전체 바인딩 구현을 완벽하게 제어하도록 새 <xref:System.ServiceModel.Channels.Binding> 형식을 만들 수 있습니다.  
  
## <a name="the-order-of-binding-elements"></a>바인딩 요소 순서  
 각 바인딩 요소는 메시지를 보내거나 받을 때의 처리 단계를 나타냅니다. 런타임에 바인딩 요소는 나가고 들어오는 채널 스택을 빌드하는 데 필요한 채널 및 수신기를 만듭니다.  
  
 프로토콜 바인딩 요소, 인코딩 바인딩 요소 및 전송 바인딩 요소의 세 가지 주요 바인딩 요소 형식이 있습니다.  
  
 프로토콜 바인딩 요소 – 이 요소는 메시지에 대해 수행하는 높은 수준의 처리 단계를 나타냅니다. 이러한 바인딩 요소로 만들어진 채널 및 수신기는 메시지 내용을 추가, 제거 또는 수정할 수 있습니다. 제공된 바인딩에는 임의의 개수의 프로토콜 바인딩 요소가 포함될 수 있으며 각 요소는 <xref:System.ServiceModel.Channels.BindingElement>에서 상속됩니다. [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에는 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> 및 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>를 비롯한 여러 프로토콜 바인딩 요소가 있습니다.  
  
 인코딩 바인딩 요소 – 이 요소는 네트워크에서 전송 대기 중인 메시지와 인코딩 간의 변환을 나타냅니다. 일반적인 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 바인딩에는 하나의 인코딩 바인딩 요소만 포함됩니다. 인코딩 바인딩 요소의 예로는 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>, <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement> 및 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>가 있습니다. 바인딩에 대해 인코딩 바인딩 요소를 지정하지 않으면 기본 인코딩이 사용됩니다. 기본값은 HTTP 전송이면 텍스트이고, 그렇지 않으면 이진입니다.  
  
 전송 바인딩 요소 – 이 요소는 전송 프로토콜에서 인코딩 메시지의 전송을 나타냅니다. 일반적인 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 바인딩에는 하나의 전송 바인딩 요소만 포함되며, 이 요소는 <xref:System.ServiceModel.Channels.TransportBindingElement>에서 상속됩니다. 전송 바인딩 요소의 예로는 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>, <xref:System.ServiceModel.Channels.HttpTransportBindingElement> 및 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>가 있습니다.  
  
 새 바인딩을 만들 때 추가되는 바인딩 요소의 순서가 중요합니다. 항상 다음 순서대로 바인딩 요소를 추가합니다.  
  
|계층|옵션|필수|  
|-----------|-------------|--------------|  
|트랜잭션 흐름|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement?displayProperty=nameWithType>|아니요|  
|안정성|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement?displayProperty=nameWithType>|아니요|  
|보안|<xref:System.ServiceModel.Channels.SecurityBindingElement?displayProperty=nameWithType>|아니요|  
|복합 이중|<xref:System.ServiceModel.Channels.CompositeDuplexBindingElement?displayProperty=nameWithType>|아니요|  
|Encoding|텍스트, 이진, MTOM, 사용자 지정|예*|  
|전송|TCP, 명명된 파이프, HTTP, HTTPS, MSMQ, 사용자 지정|예|  
  
 *인코딩은 각 바인딩의 필수적 요소이므로 인코딩을 지정하지 않으면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 기본 인코딩을 자동으로 추가합니다. 기본값은 HTTP 및 HTTPS 전송의 경우 텍스트/XML이고 그렇지 않은 경우 이진입니다.  
  
## <a name="creating-a-new-binding-element"></a>새 바인딩 요소 만들기  
 <xref:System.ServiceModel.Channels.BindingElement>가 제공하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 파생되는 형식 이외에 바인딩 요소를 만들 수 있습니다. 따라서 바인딩 스택을 만드는 방법 및 스택에서 기타 시스템 제공 형식으로 구성할 수 있는 <xref:System.ServiceModel.Channels.BindingElement>를 만들어 이 스택에 삽입되는 구성 요소를 사용자 지정할 수 있습니다.  
  
 예를 들어, 메시지를 데이터베이스에 기록하는 기능을 제공하는 `LoggingBindingElement`를 구현하는 경우 채널 스택의 전송 채널 위에 요소를 배치해야 합니다. 이 경우 응용 프로그램은 다음 예제에서처럼 `LoggingBindingElement`로 `TcpTransportBindingElement`를 구성한 사용자 지정 바인딩을 만듭니다.  
  
```csharp  
Binding customBinding = new CustomBinding(  
  new LoggingBindingElement(),   
  new TcpTransportBindingElement()  
);  
```  
  
 새 바인딩 요소를 작성하는 방법은 정확한 기능에 따라 달라집니다. 샘플 중 하나 [전송: UDP](../../../../docs/framework/wcf/samples/transport-udp.md), 한 종류의 바인딩 요소를 구현 하는 방법에 대 한 자세한 설명을 제공 합니다.  
  
## <a name="creating-a-new-binding"></a>새 바인딩 만들기  
 사용자가 만든 바인딩 요소는 두 가지 방법으로 사용할 수 있습니다. 이전 단원에서는 사용자 지정 바인딩을 통해 사용하는 첫 번째 방법을 보여 줍니다. 사용자 지정 바인딩에서는 사용자가 만든 바인딩을 비롯한 임의의 바인딩 요소 집합에 따라 직접 바인딩을 만들 수 있습니다.  
  
 둘 이상의 응용 프로그램에서 바인딩을 사용하는 경우 직접 바인딩을 만들어 <xref:System.ServiceModel.Channels.Binding>을 확장합니다. 이렇게 하면 사용할 때마다 사용자 지정 바인딩을 수동으로 만들지 않아도 됩니다. 사용자 정의 바인딩을 사용하여 바인딩의 동작을 정의하고 사용자 정의 바인딩 요소를 포함시킬 수 있습니다. 있고 그것이 *사전 패키지*: 사용할 때마다 바인딩을 다시 필요가 없습니다.  
  
 최소한 사용자 정의 바인딩은 <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> 메서드 및 <xref:System.ServiceModel.Channels.Binding.Scheme%2A> 속성을 구현해야 합니다.  
  
 <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> 메서드는 바인딩의 바인딩 요소가 포함된 새 <xref:System.ServiceModel.Channels.BindingElementCollection>을 반환합니다. 컬렉션에는 먼저 프로토콜 바인딩 요소 그리고 인코딩 바인딩 요소와 전송 바인딩 요소가 순서대로 포함되어 있어야 합니다. 사용 하는 경우는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 시스템 제공 바인딩 요소를 정렬 규칙에 지정 된 바인딩 요소를 수행 해야 [사용자 지정 바인딩](../../../../docs/framework/wcf/extending/custom-bindings.md)합니다. 이 컬렉션은 사용자 정의 바인딩 클래스 내에서 참조된 개체를 참조하지 않아야 합니다. 따라서 바인딩 작성자는 `Clone()`를 호출할 때마다 <xref:System.ServiceModel.Channels.BindingElementCollection>의 <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A>을 반환해야 합니다.  
  
 <xref:System.ServiceModel.Channels.Binding.Scheme%2A> 속성은 바인딩에서 사용 중인 전송 프로토콜의 URI 스키마를 나타냅니다. 예를 들어는 *WSHttpBinding* 및 *NetTcpBinding* 는 각각의 "http" 및 "net.tcp"를 반환할 <xref:System.ServiceModel.Channels.Binding.Scheme%2A> 속성입니다.  
  
 사용자 정의 인코딩 바인딩에 대한 선택적 메서드 및 속성의 전체 목록은 <xref:System.ServiceModel.Channels.Binding>을 참조하세요.  
  
### <a name="example"></a>예제  
 이 예제에서는 `SampleProfileUdpBinding`에서 파생되는 <xref:System.ServiceModel.Channels.Binding>의 프로필 바인딩을 구현합니다. `SampleProfileUdpBinding` 최대 4 개의 바인딩 요소가 포함: 하나는 사용자가 만든 `UdpTransportBindingElement`;과 3 시스템 제공: `TextMessageEncodingBindingElement`, `CompositeDuplexBindingElement`, 및 `ReliableSessionBindingElement`합니다.  
  
```  
public override BindingElementCollection CreateBindingElements()  
{     
    BindingElementCollection bindingElements = new BindingElementCollection();  
    if (ReliableSessionEnabled)  
    {  
        bindingElements.Add(session);  
        bindingElements.Add(compositeDuplex);  
    }  
    bindingElements.Add(encoding);  
    bindingElements.Add(transport);  
    return bindingElements.Clone();  
}  
```  
  
## <a name="security-restrictions-with-duplex-contracts"></a>이중 계약을 사용하여 보안 제한  
 일부 바인딩 요소는 서로 간에 호환되지 않습니다. 특히 이중 계약에서 사용하는 경우 보안 바인딩 요소에 대한 몇 가지 제한이 있습니다.  
  
### <a name="one-shot-security"></a>원샷 보안  
 "원 샷" 보안을 설정 하 여 단일 메시지에서 모든 필요한 보안 자격 증명 전송 되는 위치를 구현할 수는 `negotiateServiceCredential` 특성에는 \<메시지 > 구성 요소를 `false`합니다.  
  
 원샷 인증은 이중 계약에서 사용할 수 없습니다.  
  
 요청-회신 계약의 경우 보안 바인딩 요소 아래에 있는 바인딩 스택에서 <xref:System.ServiceModel.Channels.IRequestChannel> 또는 <xref:System.ServiceModel.Channels.IRequestSessionChannel> 인스턴스를 만들 수 있는 경우에만 원샷 인증을 사용할 수 있습니다.  
  
 단방향 계약의 경우 보안 바인딩 요소 아래에 있는 바인딩 스택에서 <xref:System.ServiceModel.Channels.IRequestChannel>, <xref:System.ServiceModel.Channels.IRequestSessionChannel>, <xref:System.ServiceModel.Channels.IOutputChannel> 또는 <xref:System.ServiceModel.Channels.IOutputSessionChannel> 인스턴스를 만들 수 있는 경우 원샷 인증을 사용할 수 있습니다.  
  
### <a name="cookie-mode-security-context-tokens"></a>쿠키 모드 보안 컨텍스트 토큰  
 쿠키 모드 보안 컨텍스트 토큰은 이중 계약에서 사용할 수 없습니다.  
  
 요청-회신 계약의 경우 보안 바인딩 요소 아래에 있는 바인딩 스택에서 <xref:System.ServiceModel.Channels.IRequestChannel> 또는 <xref:System.ServiceModel.Channels.IRequestSessionChannel> 인스턴스를 만들 수 있는 경우에만 쿠키 모드 보안 컨텍스트 토큰을 사용할 수 있습니다.  
  
 단방향 계약의 경우 보안 바인딩 요소 아래에 있는 바인딩 스택에서 <xref:System.ServiceModel.Channels.IRequestChannel> 또는 <xref:System.ServiceModel.Channels.IRequestSessionChannel> 인스턴스를 만들 수 있는 경우 쿠키 모드 보안 컨텍스트 토큰을 사용할 수 있습니다.  
  
### <a name="session-mode-security-context-tokens"></a>세션 모드 보안 컨텍스트 토큰  
 세션 모드 SCT는 보안 바인딩 요소 아래에 있는 바인딩 스택에서 <xref:System.ServiceModel.Channels.IDuplexChannel> 또는 <xref:System.ServiceModel.Channels.IDuplexSessionChannel> 인스턴스를 만들 수 있는 경우 이중 계약에 사용할 수 있습니다.  
  
 세션 모드 SCT는 보안 바인딩 요소 아래에 있는 바인딩 스택에서 <xref:System.ServiceModel.Channels.IDuplexChannel>, <xref:System.ServiceModel.Channels.IDuplexSessionChannel>, <xref:System.ServiceModel.Channels.IRequestChannel> 또는 <xref:System.ServiceModel.Channels.IRequestSessionChannel> 인스턴스를 만들 수 있는 경우 요청-회신 계약에 사용할 수 있습니다.  
  
 세션 모드 SCT는 보안 바인딩 요소 아래에 있는 바인딩 스택에서 <xref:System.ServiceModel.Channels.IDuplexChannel>, <xref:System.ServiceModel.Channels.IDuplexSessionChannel>, <xref:System.ServiceModel.Channels.IRequestChannel> 또는 <xref:System.ServiceModel.Channels.IRequestSessionChannel> 인스턴스를 만들 수 있는 경우 단방향 계약에 사용할 수 있습니다.  
  
## <a name="deriving-from-a-standard-binding"></a>표준 바인딩에서 파생  
 완전히 새로운 바인딩 클래스를 만드는 대신 기존의 시스템 제공 바인딩 중 하나를 확장할 수 있습니다. 앞의 경우와 마찬가지로 <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> 메서드 및 <xref:System.ServiceModel.Channels.Binding.Scheme%2A> 속성을 재정의해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Channels.Binding>  
 [사용자 지정 바인딩](../../../../docs/framework/wcf/extending/custom-bindings.md)
