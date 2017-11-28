---
title: "방법: 세션이 필요한 서비스 만들기"
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
ms.assetid: 8a7613ef-0df9-47c3-b8dc-47f42cb1fd8b
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2e238598ccd33d9e6e77a2d09ea3b19fdefcefbb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-service-that-requires-sessions"></a>방법: 세션이 필요한 서비스 만들기
세션은 콜백, 다중 홉 보안 및 클라이언트와 서비스 인스턴스 간의 연결과 같은 유용한 기능을 사용하는 둘 이상의 끝점 사이에서 공유 상태를 만듭니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]세션의 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 응용 프로그램 참조 [를 사용 하 여 세션](../../../../docs/framework/wcf/using-sessions.md)합니다.  
  
### <a name="to-specify-that-a-contract-require-its-binding-to-support-sessions"></a>계약에서 바인딩이 세션을 지원하도록 지정하려면  
  
1.  작업을 하나 이상 포함하는 서비스 계약을 만듭니다. 서비스 계약을 만드는 방법의 예제를 보려면 [하는 방법: 서비스 계약 정의](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)합니다.  
  
2.  <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType> 속성을 다음으로 설정하여 계약을 선언하는 <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType>를 수정합니다.  
  
    -   이 계약을 세션 내에서 실행해야 하는 경우, <xref:System.ServiceModel.SessionMode.Required?displayProperty=nameWithType>  
  
    -   이 계약을 세션 내에서 실행할 수 있는 경우, <xref:System.ServiceModel.SessionMode.Allowed?displayProperty=nameWithType>  
  
    -   이 계약을 세션 내에서 실행하지 않아야 하는 경우, <xref:System.ServiceModel.SessionMode.NotAllowed?displayProperty=nameWithType>  
  
3.  세션을 지원하는 바인딩을 사용하도록 서비스 끝점을 구성합니다. 다음 구성 예제에서는 WS<xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>ReliableMessaging 세션을 지원하는 `-`을 사용하는 방법을 보여 줍니다.  
  
     [!code-xml[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]   
  
## <a name="example"></a>예제  
 다음 예제 코드에서는 계약 수준 세션 요구 사항을 지정하고 구성 파일을 사용하여 <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType> 바인딩을 통해 해당 요구 사항을 지원하는 방법을 보여 줍니다.  
  
 [!code-csharp[SCA.Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/services.cs#1)] 
 [!code-vb[SCA.Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.session/vb/services.vb#1)]      
 [!code-xml[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]     
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>  
 <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType>  
 <xref:System.ServiceModel.SessionMode?displayProperty=nameWithType>
