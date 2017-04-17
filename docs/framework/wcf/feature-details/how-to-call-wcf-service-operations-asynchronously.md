---
title: "방법: 비동기적으로 WCF 서비스 작업 호출 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0face17f-43ca-417b-9b33-737c0fc360df
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# 방법: 비동기적으로 WCF 서비스 작업 호출
이 항목에서는 클라이언트에서 서비스 작업에 비동기적으로 액세스하는 방법에 대해 설명합니다.이 항목에서 설명하는 서비스에서는 `ICalculator` 인터페이스를 구현합니다.클라이언트는 이벤트 구동 비동기 호출 모델을 사용하여 이 인터페이스에서 작업을 비동기적으로 호출할 수 있습니다.이벤트 기반 비동기 호출에 대한 자세한 내용은 [이벤트 기반 비동기 패턴으로 다중 스레드 프로그래밍](http://go.microsoft.com/fwlink/?LinkId=248184)을 참조하십시오.서비스에서 작업을 비동기적으로 구현하는 방법을 보여 주는 예제는 [방법: 비동기 서비스 작업 구현](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)을 참조하십시오.동기 및 비동기 작업에 대한 자세한 내용은 [동기 및 비동기 작업](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md)을 참조하십시오.  
  
> [!NOTE]
>  <xref:System.ServiceModel.ChannelFactory%601>를 사용하는 경우 이벤트 구동 비동기 호출 모델이 지원되지 않습니다.<xref:System.ServiceModel.ChannelFactory%601>를 사용하는 비동기 호출에 대한 자세한 내용은 [방법: 채널 팩터리를 사용하여 비동기로 작업 호출](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md)을 참조하십시오.  
  
## 절차  
  
#### WCF 서비스 작업을 비동기적으로 호출하려면  
  
1.  다음 명령에서처럼 `/async` 및 `/tcv:Version35` 명령 옵션을 모두 사용하여 [ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)를 실행합니다.  
  
    ```  
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a /tcv:Version35  
    ```  
  
     이렇게 하면 동기 작업 및 표준 대리자 기반 비동기 작업 이외에 다음을 포함하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 클래스가 생성됩니다.  
  
    -   이벤트 기반 비동기 호출 방법에 사용할 두 가지 \<`operationName`\>`Async` 작업.예를 들면 다음과 같습니다.  
  
         [!code-csharp[EventAsync#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#1)]
         [!code-vb[EventAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#1)]  
  
    -   이벤트 기반 비동기 호출 방법에 사용할 \<`operationName`\>`Completed` 형식의 작업 완료된 이벤트.예를 들면 다음과 같습니다.  
  
         [!code-csharp[EventAsync#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#2)]
         [!code-vb[EventAsync#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#2)]  
  
    -   이벤트 기반 비동기 호출 방법에 사용할 \<`operationName`\>`CompletedEventArgs` 형식의 각 작업에 대한 <xref:System.EventArgs?displayProperty=fullName> 형식.예를 들면 다음과 같습니다.  
  
         [!code-csharp[EventAsync#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#3)]
         [!code-vb[EventAsync#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#3)]  
  
2.  호출 응용 프로그램은 다음 샘플 코드에서처럼 비동기 작업이 완료될 때 호출할 콜백 메서드를 만듭니다.  
  
     [!code-csharp[EventAsync#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#4)]
     [!code-vb[EventAsync#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#4)]  
  
3.  작업을 호출하기 전에 \<`operationName`\>`EventArgs` 형식의 새 제네릭 <xref:System.EventHandler%601?displayProperty=fullName>를 사용하여 이전 단계에서 만든 핸들러 메서드를 \<`operationName`\>`Completed` 이벤트에 추가합니다.그런 다음 \<`operationName`\>`Async` 메서드를 호출합니다.예를 들면 다음과 같습니다.  
  
     [!code-csharp[EventAsync#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#5)]
     [!code-vb[EventAsync#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#5)]  
  
## 예제  
  
> [!NOTE]
>  이벤트 기반 비동기 모델에 대한 디자인 지침에 따르면 둘 이상의 값이 반환될 경우 그 중 하나는 `Result` 속성으로 반환되고 나머지 값은 <xref:System.EventArgs> 개체의 속성으로 반환됩니다.따라서 클라이언트가 이벤트 기반 비동기 명령 옵션을 사용하여 메타데이터를 가져오고 작업이 둘 이상의 값을 반환할 경우 기본 <xref:System.EventArgs> 개체는 그 중 하나를 `Result` 속성으로 반환하고, 나머지 값은 <xref:System.EventArgs> 개체의 속성으로 반환됩니다. 메시지 개체를 `Result` 속성으로 수신하고 반환된 값을 해당 개체의 속성으로 포함하려면 `/messageContract` 명령 옵션을 사용합니다.이렇게 하면 응답 메시지를 <xref:System.EventArgs> 개체의 `Result` 속성으로 반환하는 서명이 생성됩니다.모든 내부 반환 값은 응답 메시지 개체의 속성이 됩니다.  
  
 [!code-csharp[EventAsync#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#6)]
 [!code-vb[EventAsync#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#6)]  
  
## 참고 항목  
 [방법: 비동기 서비스 작업 구현](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)