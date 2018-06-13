---
title: '방법: WSE3.0 서비스와 상호 운용하도록 WCF 클라이언트 구성'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3dadd7f1-d207-4ea5-a73b-3e8aa44407f8
ms.openlocfilehash: e30403f9c97f31e93c22a9658ffb74d4d02a49ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33490645"
---
# <a name="how-to-configure-a-wcf-client-to-interoperate-with-wse30-services"></a>방법: WSE3.0 서비스와 상호 운용하도록 WCF 클라이언트 구성
Windows Communication Foundation (WCF) 클라이언트는 2004 년 8 월 버전의 Ws-addressing 사양 사용 하도록 WCF 클라이언트를 구성 하는 경우 Microsoft.NET (WSE) 서비스에 대 한 Web Services Enhancements 3.0과 유선 수준 호환 합니다.  
  
### <a name="to-configure-a-wcf-client-to-interoperate-with-a-wse-30-web-service"></a>WSE 3.0 웹 서비스와 상호 운용하도록 WCF 클라이언트를 구성하려면  
  
1.  실행 된 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) WSE 3.0 웹 서비스에 대 한 WCF 클라이언트를 만듭니다.  
  
     WSE 웹 서비스에 대 한 WCF 클라이언트 클래스 생성 됩니다.  
  
     WCF 클라이언트 만들기에 대 한 세부 정보를 참조 하십시오.는 [하는 방법: 클라이언트 만들기](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md)합니다.  
  
2.  WSE 3.0 웹 서비스와 통신할 수 있는 바인딩을 나타내는 클래스를 만듭니다.  
  
     다음 클래스의 일부인는 [WSE와의 상호 운용](http://msdn.microsoft.com/library/f6816861-96a0-45f9-8736-8e4e82cd3a41) 샘플.  
  
    1.  <xref:System.ServiceModel.Channels.Binding> 클래스에서 파생되는 클래스를 만듭니다.  
  
         다음 코드 예제에서는 `WseHttpBinding` 클래스로부터 파생되는 <xref:System.ServiceModel.Channels.Binding>이라는 클래스를 만듭니다.  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2.  WSE 턴키 어설션, 파생된 키가 필요한지 여부, 보안 세션이 사용되는지 여부, 서명 확인이 필요한지 여부 및 메시지 보호 설정을 지정하는 클래스에 속성을 추가합니다.  
  
         다음 코드 예제에서는 정의 `SecurityAssertion,``RequireDerivedKeys, EstablishSecurityContext, MessageProtectionOrder` WSE 턴키 어설션, 파생된 키가 필요한 여부, 보안 세션이 사용 되는지 여부, 서명 확인이 필요한 지 여부 및 메시지 보호 설정을 지정 하는 속성 각각.  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3.  <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> 메서드를 재정의하여 바인딩 속성을 설정합니다.  
  
         다음 코드 예제에서는 `SecurityAssertion` 및 `MessageProtectionOrder` 속성의 값을 가져옴으로써 전송, 메시지 인코딩, 메시지 보호 설정을 지정합니다.  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3.  클라이언트 응용 프로그램 코드에서 바인딩 속성을 설정하기 위해 코드를 추가합니다.  
  
     다음 코드 예제에서는 WSE 3.0에 정의 된 대로 메시지 보호 및 인증 WCF 클라이언트 사용 해야 하도록 지정 `AnonymousForCertificate` 턴키 보안 어설션 합니다. 또한 보안 세션 및 파생된 키도 필요합니다.  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 WSE 3.0 턴키 보안 어설션의 속성에 해당하는 속성을 노출하는 사용자 지정 바인딩을 정의합니다. 이름으로 지정 된 사용자 지정 바인딩을 `WseHttpBinding`, 그런 다음 WCF 클라이언트에 대 한 바인딩 속성을 지정 하는 데 사용 됩니다.  
  
  
[!code-csharp[c_WCFClientToWSEService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#0)]
[!code-vb[c_WCFClientToWSEService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#0)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Channels.Binding>  
 [WSE와의 상호 운용](http://msdn.microsoft.com/library/f6816861-96a0-45f9-8736-8e4e82cd3a41)
