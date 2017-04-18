---
title: "방법: 채널 팩터리를 사용하여 비동기로 작업 호출 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cc17dd47-b9ad-451c-a362-e36e0aac7ba0
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# 방법: 채널 팩터리를 사용하여 비동기로 작업 호출
이 항목에서는 <xref:System.ServiceModel.ChannelFactory%601> 기반 클라이언트 응용 프로그램을 사용하여 클라이언트에서 서비스 작업에 비동기적으로 액세스하는 방법에 대해 설명합니다.  서비스를 호출하기 위해 <xref:System.ServiceModel.ClientBase%601?displayProperty=fullName> 개체를 사용하는 경우 이벤트 구동 비동기 호출 모델을 사용할 수 있습니다.  자세한 내용은 [방법: 비동기적으로 서비스 작업 호출](../../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md)을 참조하세요.  이벤트 기반 비동기 호출 모델에 대한 자세한 내용은 [Multithreaded Programming with the Event\-based Asynchronous Pattern](../../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)을 참조하세요.  
  
 이 항목에서 설명하는 서비스에서는 `ICalculator` 인터페이스를 구현합니다.  클라이언트는 이 인터페이스의 작업을 비동기적으로 호출할 수 있는데, 이는 `Add` 등의 작업이 호출을 시작하는 `BeginAdd`와 작업 완료 시 결과를 검색하는 `EndAdd`라는 두 개의 메서드로 나뉨을 의미합니다.  서비스에서 작업을 비동기적으로 구현하는 방법에 대한 예제는 [방법: 비동기 서비스 작업 구현](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)을 참조하세요.  동기 및 비동기 작업에 대한 자세한 내용은 [동기 및 비동기 작업](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md)을 참조하세요.  
  
## 절차  
  
#### WCF 서비스 작업을 비동기적으로 호출하려면  
  
1.  다음 명령과 같이 `/async` 옵션을 사용하여 [ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 도구를 실행합니다.  
  
    ```  
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a  
  
    ```  
  
     그러면 작업에 서비스 계약의 비동기 클라이언트 버전이 생성됩니다.  
  
2.  다음 샘플 코드와 같이 비동기 작업이 완료될 때 호출할 콜백 함수를 만듭니다.  
  
     [!code-csharp[C_How_To_CF_Async#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/client.cs#2)]
     [!code-vb[C_How_To_CF_Async#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/client.vb#2)]  
  
3.  서비스 작업에 비동기적으로 액세스하려면 다음 샘플 코드에서와 같이, 클라이언트를 만들고 `Begin[Operation]`\(예: `BeginAdd`\)을 호출하며 콜백 함수를 지정합니다.  
  
     [!code-csharp[C_How_To_CF_Async#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/client.cs#3)]
     [!code-vb[C_How_To_CF_Async#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/client.vb#3)]  
  
     콜백 함수가 실행될 때 클라이언트는 결과를 검색하기 위해 `End<operation>`\(예: `EndAdd`\)을 호출합니다.  
  
## 예제  
 이전 절차에 사용된 클라이언트 코드와 함께 사용되는 서비스는 다음 코드에서와 같이 `ICalculator` 인터페이스를 구현합니다.  클라이언트가 이전 클라이언트 단계를 비동기적으로 호출하더라도 서비스 쪽에서는 계약의 `Add` 및 `Subtract` 작업을 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 런타임에서 동기적으로 호출합니다.  클라이언트가 `Multiply` 및 `Divide` 작업을 비동기적으로 호출하더라도 서비스 쪽에서는 이 작업을 사용하여 비동기적으로 서비스를 호출합니다.  다음 예제에서는 <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A> 속성을 `true`로 설정합니다.  이 속성 설정을 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 비동기 패턴 구현과 함께 사용하면 런타임에서 작업이 비동기적으로 호출됩니다.  
  
 [!code-csharp[C_How_To_CF_Async#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/service.cs#4)]
 [!code-vb[C_How_To_CF_Async#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/service.vb#4)]  
  
## 참고 항목  
 [Service Contract: Asynchronous Sample](http://msdn.microsoft.com/ko-kr/833db946-f511-4f64-a26f-2759a11217c7)