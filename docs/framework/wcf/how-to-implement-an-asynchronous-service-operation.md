---
title: "방법: 비동기 서비스 작업 구현 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4e5d2ea5-d8f8-4712-bd18-ea3c5461702c
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# 방법: 비동기 서비스 작업 구현
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 응용 프로그램에서는 클라이언트에게 호출 방법을 지시하지 않고 서비스 작업을 비동기 또는 동기적으로 구현할 수 있습니다.예를 들어 비동기 서비스 작업을 동기적으로 호출하고, 동기 서비스 작업을 비동기적으로 호출할 수 있습니다.클라이언트 응용 프로그램에서 작업을 비동기적으로 호출하는 방법을 보여 주는 예제는 [방법: 비동기적으로 서비스 작업 호출](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md)을 참조하십시오.동기 및 비동기 작업[!INCLUDE[crabout](../../../includes/crabout-md.md)][서비스 계약 디자인](../../../docs/framework/wcf/designing-service-contracts.md) 및 [동기 및 비동기 작업](../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md)을 참조하십시오.이 항목에서는 비동기 서비스 작업의 기본 구조에 대해 설명하지만 코드가 완성되지 않았습니다.서비스 및 클라이언트 쪽의 전체 예제는 [Asynchronous](http://msdn.microsoft.com/ko-kr/833db946-f511-4f64-a26f-2759a11217c7)를 참조하십시오.  
  
### 비동기 서비스 작업 구현  
  
1.  서비스 계약에서 .NET 비동기 디자인 지침에 따라 비동기 메서드 쌍을 선언합니다.`Begin` 메서드는 매개 변수, 콜백 개체 및 상태 개체를 가져와서 <xref:System.IAsyncResult?displayProperty=fullName> 및 <xref:System.IAsyncResult?displayProperty=fullName>를 가져오는 일치하는 `End` 메서드를 반환한 다음 반환 값을 반환합니다.비동기 호출에 대한 자세한 내용은 [비동기 프로그래밍 패턴](http://go.microsoft.com/fwlink/?LinkId=248221)\(영문 페이지일 수 있음\)을 참조하십시오.  
  
2.  <xref:System.ServiceModel.OperationContractAttribute?displayProperty=fullName> 특성을 가진 비동기 메서드 쌍의 `Begin` 메서드를 표시하고 <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A?displayProperty=fullName> 속성을 `true`로 설정합니다.예를 들어 다음 코드에서는 단계 1 및 2를 수행합니다.  
  
     [!code-csharp[C_SyncAsyncClient#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#6)]
     [!code-vb[C_SyncAsyncClient#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#6)]  
  
3.  비동기 디자인 지침에 따라 서비스 클래스에서 `Begin/End` 메서드 쌍을 구현합니다.예를 들어 다음 코드 예제에서는 비동기 서비스 작업의 `Begin` 및 `End` 부분 모두의 콘솔에 기록된 문자열의 구현 및 `End` 작업의 반환 값이 클라이언트에 반환되는 것을 보여 줍니다.전체 코드 예제를 보려면 예제 단원을 참조하십시오.  
  
     [!code-csharp[C_SyncAsyncClient#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#3)]
     [!code-vb[C_SyncAsyncClient#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#3)]  
  
## 예제  
 다음 코드 예제에서는 다음을 보여 줍니다.  
  
1.  다음을 포함한 서비스 계약 인터페이스:  
  
    1.  동기 `SampleMethod` 작업.  
  
    2.  비동기 `BeginSampleMethod` 작업.  
  
    3.  비동기 `BeginServiceAsyncMethod`\/`EndServiceAsyncMethod` 작업 쌍.  
  
2.  <xref:System.IAsyncResult?displayProperty=fullName> 개체를 사용하여 서비스 구현.  
  
 [!code-csharp[C_SyncAsyncClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#1)]
 [!code-vb[C_SyncAsyncClient#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#1)]  
  
## 참고 항목  
 [서비스 계약 디자인](../../../docs/framework/wcf/designing-service-contracts.md)   
 [동기 및 비동기 작업](../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md)