---
title: "방법: WCF 클라이언트를 사용하여 WSE 3.0 서비스에 액세스 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1f9bcd9b-8f8f-47fa-8f1e-0d47236eb800
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# 방법: WCF 클라이언트를 사용하여 WSE 3.0 서비스에 액세스
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 클라이언트는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트가 2004년 8월 버전의 WS-Addressing 사양을 사용하도록 구성된 경우 Microsoft .NET 서비스용 WSE(Web Services Enhancements) 3.0과 유선 수준으로 호환됩니다. 그러나 WSE 3.0 서비스 지원 하지 않습니다 메타 데이터 교환 (MEX) 프로토콜은 지금 사용 하는 경우는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 만들려는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 클래스는 보안 설정은 없습니다에 생성 된 적용 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트입니다. 그러므로 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트가 생성된 후에 WSE 3.0 서비스를 사용하도록 보안 설정을 지정해야 합니다.  
  
 사용자 지정 바인딩을 사용하여 이러한 보안 설정을 적용함으로써 WSE 3.0 서비스와 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 간의 상호 운용 가능한 요구 사항 및 WSE 3.0 서비스의 요구 사항을 고려할 수 있습니다. 이러한 상호 운용성 요구 사항 2004 년 8 월의 앞에서 설명한 사용이 포함 Ws-addressing 사양 및 WSE 3.0default 메시지의 보호 <xref:System.ServiceModel.Security.MessageProtectionOrder>합니다. 에 대 한 기본 메시지 보호 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 는 <xref:System.ServiceModel.Security.MessageProtectionOrder>합니다. 이 항목에서는 WSE 3.0 서비스와 상호 운용되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 바인딩을 만드는 방법에 대해 자세히 설명합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 이 바인딩을 통합하는 샘플도 제공합니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]이 샘플에서는 참조 [ASMX 웹 서비스와의 상호 운용](../../../../docs/framework/wcf/samples/interoperating-with-asmx-web-services.md)합니다.  
  
### <a name="to-access-a-wse-30-web-service-with-a-wcf-client"></a>WCF 클라이언트를 사용하여 WSE 3.0 웹 서비스에 액세스하려면  
  
1.  실행 하는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 만들려는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WSE 3.0 웹 서비스에 대 한 클라이언트입니다.  
  
     WSE 3.0 웹 서비스의 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트가 만들어집니다. WSE 3.0이 MEX 프로토콜을 지원하지 않으므로 해당 도구를 사용하여 웹 서비스에 대한 보안 요구 사항을 검색할 수 없습니다. 응용 프로그램 개발자는 해당 클라이언트에 대한 보안 설정을 추가해야 합니다.  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]만들기는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 참조는 [하는 방법: 클라이언트 만들기](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md)합니다.  
  
2.  WSE 3.0 웹 서비스와 통신할 수 있는 바인딩을 나타내는 클래스를 만듭니다.  
  
     다음 클래스의 일부인는 [WSE와의 상호 운용](http://msdn.microsoft.com/ko-kr/f6816861-96a0-45f9-8736-8e4e82cd3a41) 샘플:  
  
    1.  파생 되는 클래스를 만들기는 <xref:System.ServiceModel.Channels.Binding> 클래스입니다.  
  
         다음 코드 예제에서는 라는 클래스를 만듭니다 `WseHttpBinding` 에서 파생 되는 <xref:System.ServiceModel.Channels.Binding> 클래스입니다.  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2.  WSE 서비스에서 사용되는 WSE 턴키 어설션, 파생된 키가 필요한지 여부, 보안 세션이 사용되는지 여부, 서명 확인이 필요한지 여부 및 메시지 보호 설정을 지정하는 클래스에 속성을 추가합니다. WSE 3.0에서는 턴키 어설션이 클라이언트 또는 웹 서비스에 대한 보안 요구 사항을 지정하며, 이는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 바인딩의 인증 모드와 유사합니다.  
  
         다음 코드 예제에서는 WSE 턴키 어설션, 파생된 키가 필요한지 여부, 보안 세션이 사용되는지 여부, 서명 확인이 필요한지 여부 및 메시지 보호 설정을 각각 지정하는 `SecurityAssertion`, `RequireDerivedKeys`, `EstablishSecurityContext` 및 `MessageProtectionOrder` 속성을 정의합니다.  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3.  재정의 <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> 메서드를 바인딩 속성을 설정 합니다.  
  
         다음 코드 예제에서는 `SecurityAssertion` 및 `MessageProtectionOrder` 속성의 값을 가져옴으로써 전송, 메시지 인코딩, 메시지 보호 설정을 지정합니다.  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3.  클라이언트 응용 프로그램 코드에서 바인딩 속성을 설정하기 위해 코드를 추가합니다.  
  
     다음 코드 예제에서는 WSE 3.0 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 턴키 보안 어설션에 정의된 대로 `AnonymousForCertificate` 클라이언트가 반드시 메시지 보호 및 인증을 사용하도록 지정합니다. 또한 보안 세션 및 파생된 키도 필요합니다.  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 WSE 3.0 턴키 보안 어설션의 속성에 해당하는 속성을 노출하는 사용자 지정 바인딩을 정의합니다. 그러면 WSSecurityAnonymous WSE 3.0 QuickStart 샘플과 통신하는 `WseHttpBinding` 클라이언트에 대한 바인딩 속성을 지정하는 데 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]이라는 사용자 지정 바인딩이 사용됩니다.  
  
  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Channels.Binding>   
 [WSE와의 상호 운용](http://msdn.microsoft.com/ko-kr/f6816861-96a0-45f9-8736-8e4e82cd3a41)