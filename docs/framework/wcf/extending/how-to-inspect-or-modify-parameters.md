---
title: "방법: 매개 변수 검사 또는 수정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ab6c0ac7-aac4-45ba-93d6-a0e9afd1756f
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# 방법: 매개 변수 검사 또는 수정
검사 하거나에서 한 번의 작업에 대 한 들어오는 메시지나 나가는 메시지를 수정할 수는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 클라이언트 개체 또는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 를 구현 하 여 서비스는 <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=fullName> 인터페이스와 클라이언트 또는 서비스 런타임에 삽입 하 합니다. 일반적으로 작업 동작을 사용하여 단일 작업에 매개 변수 검사자를 추가하지만, 다른 동작을 사용하여 더 넓은 범위의 런타임에 쉬운 액세스를 제공할 수도 있습니다. 자세한 내용은 참조 [확장 클라이언트](../../../../docs/framework/wcf/extending/extending-clients.md) 및 [발송자 확장](../../../../docs/framework/wcf/extending/extending-dispatchers.md)합니다.  
  
### <a name="inspecting-or-modifying-parameters"></a>매개 변수 검사 또는 수정  
  
1.  구현 된 <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=fullName> 인터페이스입니다.  
  
2.  구현 된 <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=fullName>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=fullName>, <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=fullName> 또는 <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=fullName> (필요한 범위에 따라 다름) 매개 변수 검사자를 추가 하는 <xref:System.ServiceModel.Dispatcher.ClientOperation.ParameterInspectors%2A?displayProperty=fullName> 또는 <xref:System.ServiceModel.Dispatcher.DispatchOperation.ParameterInspectors%2A?displayProperty=fullName> 속성.  
  
3.  호출 하기 전에 동작을 삽입 <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=fullName> 또는 <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=fullName> 메서드는 <xref:System.ServiceModel.ChannelFactory%601?displayProperty=fullName>합니다. 자세한 내용은 다음을 참조 하십시오. [구성 및 동작을 사용 하 여 런타임 확장](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제는 아래 순서대로 나열되어 있습니다.  
  
-   매개 변수 검사자 구현.  
  
-   사용 하 여 매개 변수 검사자를 삽입 하는 동작 구현은 <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=fullName>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=fullName>, 및 <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=fullName>합니다.  
  
-   클라이언트 응용 프로그램에서 끝점 동작을 로드하고 실행하여 클라이언트에 매개 변수 검사자를 삽입하는 구성 파일.  
  
 [!code-csharp[Interceptors#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#4)]
 [!code-vb[Interceptors#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#4)]  
  
 [!code-csharp[Interceptors#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#5)]
 [!code-vb[Interceptors#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#5)]  
  
 <!-- TODO: review snippet reference [!code[Interceptors#3](../../../../samples/snippets/common/VS_Snippets_CFX/interceptors/common/client.exe.config#3)]  -->
 <!-- TODO: review snippet reference [!code-csharp[Interceptors#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/client.exe.config#3)]  -->
 <!-- TODO: review snippet reference [!code-vb[Interceptors#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/client.exe.config#3)]  -->  
  
## <a name="see-also"></a>참고 항목  
 [구성 및 동작을 사용 하 여 런타임 확장](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)