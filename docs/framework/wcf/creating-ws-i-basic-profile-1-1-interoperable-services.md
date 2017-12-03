---
title: "WS-I Basic Profile 1.1 상호 운용할 수 있는 서비스 만들기"
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
helpviewer_keywords: configuration [WCF], interoperable services
ms.assetid: 91b70a21-8f5c-4679-808c-2ed5fa6b2013
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 500e57b36bbbdd1d23e6efb2c50421e3e134bcb3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="creating-ws-i-basic-profile-11-interoperable-services"></a>WS-I Basic Profile 1.1 상호 운용할 수 있는 서비스 만들기
[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 끝점을 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 웹 서비스 클라이언트와 상호 운용할 수 있도록 구성하려면  
  
-   <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> 형식을 서비스 끝점의 바인딩 형식으로 사용합니다.  
  
-   서비스 끝점에서 콜백 및 세션 계약 기능이나 트랜잭션 동작을 사용하면 안 됩니다.  
  
 바인딩에서 HTTPS 및 전송 수준 클라이언트 인증에 대한 지원을 선택적으로 사용할 수 있습니다.  
  
 <xref:System.ServiceModel.BasicHttpBinding> 클래스의 다음 기능에는 WS-I Basic Profile 1.1 이상의 기능이 필요합니다.  
  
-   <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> 속성을 사용하여 제어하는 MTOM(Message Transmission Optimization Mechanism) 메시지 인코딩입니다. MTOM을 사용하지 않으려면 이 속성을 기본값인 <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType>로 둡니다.  
  
-   <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> 값을 사용하여 제어하는 메시지 보안에서는 WS-I Basic Security Profile 1.0과 호환되는 WS-Security를 지원합니다. WS-Security를 사용하지 않으려면 이 속성을 기본값인 <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType>로 둡니다.  
  
 에 대 한 메타 데이터를 확인 하는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 를 사용할 수 있는 서비스 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], 웹 서비스 클라이언트 생성 도구를 사용 하 여: [웹 서비스 설명 언어 도구 (Wsdl.exe)](http://msdn.microsoft.com/en-us/b9210348-8bc2-4367-8c91-d1a04b403e88), [웹 서비스 검색 도구 ( Disco.exe)](http://msdn.microsoft.com/en-us/acd88078-c581-42bc-94ca-6633e2851979), 및 `Add Web Reference` 기능 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]; 메타 데이터 게시를 사용 하도록 설정 해야 합니다. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][메타 데이터 끝점 게시](../../../docs/framework/wcf/publishing-metadata-endpoints.md)합니다.  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 다음 예제 코드에 추가 하는 방법을 보여 줍니다는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 와 호환 되는 끝점 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 웹 서비스 클라이언트 코드에서 또는 구성 파일에 있습니다.  
  
### <a name="code"></a>코드  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]  
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]  
  
## <a name="see-also"></a>참고 항목  
 [ASP.NET 웹 서비스와의 상호 운용성](../../../docs/framework/wcf/feature-details/interop-with-aspnet-web-services.md)
