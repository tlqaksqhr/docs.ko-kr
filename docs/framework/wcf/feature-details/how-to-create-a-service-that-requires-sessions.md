---
title: "방법: 세션이 필요한 서비스 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8a7613ef-0df9-47c3-b8dc-47f42cb1fd8b
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# 방법: 세션이 필요한 서비스 만들기
세션은 콜백, 다중 홉 보안 및 클라이언트와 서비스 인스턴스 간의 연결과 같은 유용한 기능을 사용하는 둘 이상의 끝점 사이에서 공유 상태를 만듭니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]세션의 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 응용 프로그램 참조 [를 사용 하 여 세션](../../../../docs/framework/wcf/using-sessions.md)합니다.  
  
### <a name="to-specify-that-a-contract-require-its-binding-to-support-sessions"></a>계약에서 바인딩이 세션을 지원하도록 지정하려면  
  
1.  작업을 하나 이상 포함하는 서비스 계약을 만듭니다. 서비스 계약을 작성 하는 방법의 예제를 참조 하십시오. [하는 방법: 서비스 계약을 정의](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)합니다.  
  
2.  수정 된 <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=fullName> 설정 하 여 계약을 선언 하는 <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=fullName> 속성을 합니다.  
  
    -   <xref:System.ServiceModel.SessionMode?displayProperty=fullName> 이 계약을 세션 내에서 실행 해야 하는 경우.  
  
    -   <xref:System.ServiceModel.SessionMode?displayProperty=fullName> 이 계약을 세션 내에서 실행할 수 있는 경우.  
  
    -   <xref:System.ServiceModel.SessionMode?displayProperty=fullName> 이 계약을 세션 내에서 실행 하지 않아야 하는 경우.  
  
3.  세션을 지원하는 바인딩을 사용하도록 서비스 끝점을 구성합니다. 다음 구성 예제에서는 <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=fullName>를 지 원하는 WS`-`ReliableMessaging 세션입니다.  
  
     <!-- TODO: review snippet reference [!code[SCA.Session#2](../../../../samples/snippets/common/VS_Snippets_CFX/sca.session/common/hostapplication.exe.config#2)]  -->
     <!-- TODO: review snippet reference [!code-csharp[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]  -->
     <!-- TODO: review snippet reference [!code-vb[SCA.Session#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.session/vb/hostapplication.exe.config#2)]  -->  
  
## <a name="example"></a>예제  
 다음 예제 코드에서는 계약 수준 세션 요구 사항을 지정 하 고 함께 해당 요구 사항을 지원 하기 위해 구성 파일을 사용 하는 방법을 보여 줍니다.는 <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=fullName> 바인딩.  
  
 [!code-csharp[SCA.Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/services.cs#1)]
 [!code-vb[SCA.Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.session/vb/services.vb#1)]  
  
 <!-- TODO: review snippet reference [!code[SCA.Session#2](../../../../samples/snippets/common/VS_Snippets_CFX/sca.session/common/hostapplication.exe.config#2)]  -->
 <!-- TODO: review snippet reference [!code-csharp[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]  -->
 <!-- TODO: review snippet reference [!code-vb[SCA.Session#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.session/vb/hostapplication.exe.config#2)]  -->  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=fullName>   
 <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=fullName>   
 <xref:System.ServiceModel.SessionMode?displayProperty=fullName>