---
title: '방법: ASP.NET 웹 서비스 클라이언트와 상호 운용하도록 WCF 서비스 구성'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 48e1cd90-de80-4d6c-846e-631878955762
ms.openlocfilehash: 12c5645b53e8e931edabc1a13fc1749e40538044
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-configure-wcf-service-to-interoperate-with-aspnet-web-service-clients"></a>방법: ASP.NET 웹 서비스 클라이언트와 상호 운용하도록 WCF 서비스 구성
상호 운용 가능 하도록 Windows Communication Foundation (WCF) 서비스 끝점을 구성 하려면 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 웹 서비스 클라이언트를 사용 하 여는 <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> 형식을 서비스 끝점에 대 한 바인딩 형식으로.  
  
 바인딩에서 HTTPS 및 전송 수준 클라이언트 인증에 대한 지원을 선택적으로 사용할 수 있습니다. [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 웹 서비스 클라이언트는 MTOM 메시지 인코딩을 지원하지 않기 때문에 <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> 속성을 기본값인 <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType>로 두어야 합니다. ASP.Net 웹 서비스 클라이언트는 WS-Security를 지원하지 않기 때문에 <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType>를 <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>로 설정해야 합니다.  
  
 WCF 서비스에 대 한 메타 데이터를 사용할 수 있도록 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 웹 서비스 프록시 생성 도구 (즉, [웹 서비스 설명 언어 도구 (Wsdl.exe)](http://go.microsoft.com/fwlink/?LinkId=73833), [웹 서비스 검색 도구 (Disco.exe)](http://go.microsoft.com/fwlink/?LinkId=73834), 및 Visual Studio에서 웹 참조 추가 기능), HTTP/GET 메타 데이터 끝점을 제공 해야 합니다.  
  
### <a name="to-add-a-wcf-endpoint-that-is-compatible-with-aspnet-web-service-clients-in-code"></a>코드에서 ASP.NET 웹 서비스 클라이언트와 호환되는 WCF 끝점을 추가하려면  
  
1.  새 <xref:System.ServiceModel.BasicHttpBinding> 인스턴스를 만듭니다.  
  
2.  바인딩의 보안 모드를 <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>로 설정하여 이 서비스 끝점 바인딩에 대한 전송 보안을 선택적으로 사용할 수 있습니다. 자세한 내용은 참조 하세요 [전송 보안](../../../../docs/framework/wcf/feature-details/transport-security.md)합니다.  
  
3.  방금 만든 바인딩 인스턴스를 사용하여 새 응용 프로그램 끝점을 서비스 호스트에 추가합니다. 코드에서 서비스 끝점을 추가 하는 방법에 대 한 세부 정보를 참조 하십시오.는 [하는 방법: 코드에서 서비스 끝점을 만드는](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)합니다.  
  
4.  서비스에 대해 HTTP/GET 메타데이터 끝점을 사용합니다. 자세한 내용은 [하는 방법: 서비스를 사용 하 여 코드에 대 한 메타 데이터 게시](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)합니다.  
  
### <a name="to-add-a-wcf-endpoint-that-is-compatible-with-aspnet-web-service-clients-in-a-configuration-file"></a>구성 파일에서 ASP.NET 웹 서비스 클라이언트와 호환되는 WCF 끝점을 추가하려면  
  
1.  새 <xref:System.ServiceModel.BasicHttpBinding> 바인딩 구성을 만듭니다. 자세한 내용은 참조는 [하는 방법: 구성에서 서비스 바인딩 지정](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)합니다.  
  
2.  바인딩의 보안 모드를 <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>로 설정하여 이 서비스 끝점 바인딩 구성에 대한 전송 보안을 선택적으로 사용할 수 있습니다. 자세한 내용은 참조 [전송 보안](../../../../docs/framework/wcf/feature-details/transport-security.md)합니다.  
  
3.  방금 만든 바인딩 구성을 사용하여 서비스에 대한 새 응용 프로그램 끝점을 구성합니다. 구성 파일에서 서비스 끝점을 추가 하는 방법에 대 한 세부 정보를 참조 하십시오.는 [하는 방법: 구성에서 서비스 끝점을 만드는](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)합니다.  
  
4.  서비스에 대해 HTTP/GET 메타데이터 끝점을 사용합니다. 자세한 내용은 참조는 [하는 방법: 구성 파일을 사용 하 여 서비스에 대 한 메타 데이터 게시](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제 코드와 호환 되는 WCF 끝점을 추가 하는 방법을 보여 줍니다 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 웹 서비스 클라이언트 코드에서 또는 구성 파일에 있습니다.  
  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)] 
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)] 
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]     
  
## <a name="see-also"></a>참고 항목  
 [방법: 코드에서 서비스 끝점 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 [방법: 코드를 사용하여 서비스에 대한 메타데이터 게시](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 [방법: 구성에서 서비스 바인딩 지정](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)  
 [방법: 구성에서 서비스 끝점 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 [방법: 구성 파일을 사용하여 서비스의 메타데이터 게시](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [전송 보안](../../../../docs/framework/wcf/feature-details/transport-security.md)  
 [메타데이터 사용](../../../../docs/framework/wcf/feature-details/using-metadata.md)
