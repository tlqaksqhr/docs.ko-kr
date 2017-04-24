---
title: "방법: 서비스에서 메시지 검사 및 수정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9c5b1cc7-84f3-45f8-9226-d59c278e8c42
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 방법: 서비스에서 메시지 검사 및 수정
검사 하거나에서 들어오거나 나가는 메시지를 수정할 수는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 를 구현 하 여 클라이언트는 <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=fullName> 서비스 런타임에 삽입 하 고 있습니다. 자세한 내용은 참조 [디스패처 확장](../../../../docs/framework/wcf/extending/extending-dispatchers.md)합니다. 서비스에 해당 하는 기능은 <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=fullName>합니다.  
  
### <a name="to-inspect-or-modify-messages"></a>메시지를 검사하거나 수정하려면  
  
1.  구현 된 <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=fullName> 인터페이스입니다.  
  
2.  구현 된 <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=fullName>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=fullName>, 또는 <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=fullName> 서비스 메시지 검사자를 쉽게 삽입 하려는 범위에 따라 인터페이스입니다.  
  
3.  호출 하기 전에 동작을 삽입은 <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=fullName> 메서드는 <xref:System.ServiceModel.ServiceHost?displayProperty=fullName>합니다. 자세한 내용은 다음을 참조 하십시오. [구성 및 동작을 사용 하 여 런타임 확장](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제는 아래 순서대로 나열되어 있습니다.  
  
-   서비스 검사자 구현  
  
-   검사자를 삽입하는 서비스 동작  
  
-   서비스 응용 프로그램에서 동작을 로드 및 실행하는 구성 파일  
  
 [!code-csharp[Interceptors#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#7)]
 [!code-vb[Interceptors#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#7)]  
  
 [!code-csharp[Interceptors#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#8)]
 [!code-vb[Interceptors#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#8)]  
  
 <!-- TODO: review snippet reference [!code[Interceptors#9](../../../../samples/snippets/common/VS_Snippets_CFX/interceptors/common/hostapplication.exe.config#9)]  -->
 <!-- TODO: review snippet reference [!code-csharp[Interceptors#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/hostapplication.exe.config#9)]  -->
 <!-- TODO: review snippet reference [!code-vb[Interceptors#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/hostapplication.exe.config#9)]  -->  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=fullName>   
 <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=fullName>   
 [구성 및 동작을 사용 하 여 런타임 확장](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)