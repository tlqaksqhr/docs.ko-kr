---
title: "방법: 비동기적으로 WCF 서비스 작업 호출"
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
ms.assetid: 0face17f-43ca-417b-9b33-737c0fc360df
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 549510d4d2b2ae0ee031b1c5426e7e28ab902bcd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-call-wcf-service-operations-asynchronously"></a>방법: 비동기적으로 WCF 서비스 작업 호출
이 항목에서는 클라이언트에서 서비스 작업에 비동기적으로 액세스하는 방법에 대해 설명합니다. 이 항목에서 설명하는 서비스에서는 `ICalculator` 인터페이스를 구현합니다. 클라이언트는 이벤트 구동 비동기 호출 모델을 사용하여 이 인터페이스에서 작업을 비동기적으로 호출할 수 있습니다. (이벤트 기반 비동기 호출 모델에 대 한 자세한 내용은 참조 [이벤트 기반 비동기 패턴을 사용한 다중 스레드 프로그래밍](http://go.microsoft.com/fwlink/?LinkId=248184)). 서비스에서 작업을 비동기적으로 구현 하는 방법을 보여 주는 예제를 참조 하십시오. [하는 방법: 비동기 서비스 작업 구현](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)합니다. 동기 및 비동기 작업에 대 한 자세한 내용은 참조 [동기 및 비동기 작업](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md)합니다.  
  
> [!NOTE]
>  <xref:System.ServiceModel.ChannelFactory%601>를 사용하는 경우 이벤트 구동 비동기 호출 모델이 지원되지 않습니다. 사용 하 여 비동기 호출에 대 한 내용은 <xref:System.ServiceModel.ChannelFactory%601>, 참조 [하는 방법: 호출 작업이 비동기적으로 사용 하 여 채널 팩터리](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md)합니다.  
  
## <a name="procedure"></a>프로시저  
  
#### <a name="to-call-wcf-service-operations-asynchronously"></a>WCF 서비스 작업을 비동기적으로 호출하려면  
  
1.  실행의 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 둘 다와 함께 도구는 `/async` 및 `/tcv:Version35` 다음 명령에 표시 된 대로 옵션을 함께 명령입니다.  
  
    ```  
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a /tcv:Version35  
    ```  
  
     이렇게 하면 동기 작업 및 표준 대리자 기반 비동기 작업 이외에 다음을 포함하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 클래스가 생성됩니다.  
  
    -   두 개의 <`operationName` > `Async` 이벤트 기반 비동기 호출 접근 방식으로 사용 하기 위한 작업입니다. 예:  
  
         [!code-csharp[EventAsync#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#1)]
         [!code-vb[EventAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#1)]  
  
    -   폼의 र ् ण 이벤트가 <`operationName` > `Completed` 이벤트 기반 비동기 호출 접근 방식으로 사용 합니다. 예:  
  
         [!code-csharp[EventAsync#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#2)]
         [!code-vb[EventAsync#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#2)]  
  
    -   <xref:System.EventArgs?displayProperty=nameWithType>각 작업에 대 한 형식 (형식의 <`operationName`>`CompletedEventArgs`) 이벤트 기반 비동기 호출 접근 방식으로 사용 합니다. 예:  
  
         [!code-csharp[EventAsync#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#3)]
         [!code-vb[EventAsync#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#3)]  
  
2.  호출 응용 프로그램은 다음 샘플 코드에서처럼 비동기 작업이 완료될 때 호출할 콜백 메서드를 만듭니다.  
  
     [!code-csharp[EventAsync#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#4)]
     [!code-vb[EventAsync#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#4)]  
  
3.  작업을 호출 하기 전에 새 제네릭을 사용 하 여 <xref:System.EventHandler%601?displayProperty=nameWithType> 형식의 <`operationName` > `EventArgs` (이전 단계에서 만든) 처리기 메서드를 추가 하는 <`operationName` > `Completed` 이벤트입니다. 그런 다음 호출에서 <`operationName` > `Async` 메서드. 예:  
  
     [!code-csharp[EventAsync#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#5)]
     [!code-vb[EventAsync#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#5)]  
  
## <a name="example"></a>예제  
  
> [!NOTE]
>  이벤트 기반 비동기 모델에 대한 디자인 지침에 따르면 둘 이상의 값이 반환될 경우 그 중 하나는 `Result` 속성으로 반환되고 나머지 값은 <xref:System.EventArgs> 개체의 속성으로 반환됩니다. 따라서 클라이언트가 이벤트 기반 비동기 명령 옵션을 사용하여 메타데이터를 가져오고 작업이 둘 이상의 값을 반환할 경우 기본 <xref:System.EventArgs> 개체는 그 중 하나를 `Result` 속성으로 반환하고, 나머지 값은 <xref:System.EventArgs> 개체의 속성으로 반환됩니다. 메시지 개체를 `Result` 속성으로 수신하고 반환된 값을 해당 개체의 속성으로 포함하려면 `/messageContract` 명령 옵션을 사용합니다. 이렇게 하면 응답 메시지를 `Result` 개체의 <xref:System.EventArgs> 속성으로 반환하는 서명이 생성됩니다. 모든 내부 반환 값은 응답 메시지 개체의 속성이 됩니다.  
  
 [!code-csharp[EventAsync#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#6)]
 [!code-vb[EventAsync#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#6)]  
  
## <a name="see-also"></a>참고 항목  
 [방법: 비동기 서비스 작업 구현](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)
