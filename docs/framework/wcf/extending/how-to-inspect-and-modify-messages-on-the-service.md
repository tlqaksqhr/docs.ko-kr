---
title: "방법: 서비스에서 메시지 검사 및 수정"
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
ms.assetid: 9c5b1cc7-84f3-45f8-9226-d59c278e8c42
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4e1c6c6417a9aef1995377657aadc9def7ae4d13
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-inspect-and-modify-messages-on-the-service"></a>방법: 서비스에서 메시지 검사 및 수정
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]를 구현하고 서비스 런타임에 삽입하여 들어오거나 보내는 메시지를 <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> 클라이언트에서 검사하거나 수정할 수 있습니다. 자세한 내용은 참조 [디스패처 확장](../../../../docs/framework/wcf/extending/extending-dispatchers.md)합니다. 서비스의 해당 기능은 <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>입니다.  
  
### <a name="to-inspect-or-modify-messages"></a>메시지를 검사하거나 수정하려면  
  
1.  <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> 인터페이스를 구현합니다.  
  
2.  서비스 메시지 검사자를 쉽게 삽입하려는 범위에 따라 <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> 또는 <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> 인터페이스를 구현합니다.  
  
3.  <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType>에서 <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> 메서드를 호출하기 전에 동작을 삽입합니다. 자세한 내용은 참조 [구성 하 고 런타임 동작을 확장](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제는 아래 순서대로 나열되어 있습니다.  
  
-   서비스 검사자 구현  
  
-   검사자를 삽입하는 서비스 동작  
  
-   서비스 응용 프로그램에서 동작을 로드 및 실행하는 구성 파일  
  
 [!code-csharp[Interceptors#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#7)]
 [!code-vb[Interceptors#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#7)]  
  
 [!code-csharp[Interceptors#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#8)]
 [!code-vb[Interceptors#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#8)]  
  
 [!code-xml[Interceptors#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/hostapplication.exe.config#9)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>  
 <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>  
 [구성 하 고 런타임 동작을 확장](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
