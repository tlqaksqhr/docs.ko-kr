---
title: "방법: 서비스 계약에 오류 선언 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e8da98e7-d22f-4f60-ac82-3fb0928a353f
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 방법: 서비스 계약에 오류 선언
관리 코드에서 오류 조건이 발생하면 예외가 throw됩니다.  그러나 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 응용 프로그램에서는 서비스 계약에 SOAP 오류를 선언하여 서비스 계약이 클라이언트에 반환되는 오류 정보를 지정합니다.  예외와 오류 간의 관계 개요는 [계약 및 서비스에서 오류 지정 및 처리](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)를 참조하세요.  
  
### SOAP 오류를 지정하는 서비스 계약 만들기  
  
1.  작업을 하나 이상 포함하는 서비스 계약을 만듭니다.  예제를 보려면 [방법: 서비스 계약 정의](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)를 참조하세요.  
  
2.  클라이언트가 알림을 받을 수 있는 오류 조건을 지정할 수 있는 작업을 선택합니다.  SOAP 오류를 클라이언트로 반환할 오류 조건을 결정하려면 [계약 및 서비스에서 오류 지정 및 처리](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)를 참조하세요.  
  
3.  선택한 작업에 <xref:System.ServiceModel.FaultContractAttribute?displayProperty=fullName>를 적용하고 serialize할 수 있는 오류 형식을 생성자에 전달합니다.  serialize할 수 있는 형식을 만들고 사용하는 방법에 대한 자세한 내용은 [서비스 계약에서 데이터 전송 지정](../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md)을 참조하세요.  다음 예제에서는 `SampleMethod` 작업으로 인해 `GreetingFault`가 발생하도록 지정하는 방법을 보여 줍니다.  
  
     [!code-csharp[FaultContractAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#4)]
     [!code-vb[FaultContractAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#4)]  
  
4.  오류 조건을 클라이언트에 전달하는 계약의 모든 작업에 대해 2단계와 3단계를 반복합니다.  
  
## 지정한 SOAP 오류를 반환하는 작업 구현  
 앞의 절차와 같이 특정 SOAP 오류를 반환하여 오류 조건을 호출 응용 프로그램에 전달할 수 있도록 작업에서 지정하고 나면 다음 단계로 해당 사양을 구현합니다.  
  
#### 작업에서 지정한 SOAP 오류 throw  
  
1.  <xref:System.ServiceModel.FaultContractAttribute>에 지정된 오류 조건이 작업에서 발생하면 지정한 SOAP 오류가 형식 매개 변수인 새 <xref:System.ServiceModel.FaultException%601?displayProperty=fullName>을 throw합니다.  다음 예제에서는 앞의 절차와 다음 코드 섹션에 표시된 `SampleMethod`에서 `GreetingFault`를 throw하는 방법을 보여 줍니다.  
  
     [!code-csharp[FaultContractAttribute#5](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#5)]
     [!code-vb[FaultContractAttribute#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#5)]  
  
## 예제  
 다음 코드 예제에서는 `SampleMethod` 작업에 대해 `GreetingFault`를 지정하는 단일 작업 구현을 보여 줍니다.  
  
 [!code-csharp[FaultContractAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#1)]
 [!code-vb[FaultContractAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#1)]  
  
## 참고 항목  
 <xref:System.ServiceModel.FaultContractAttribute?displayProperty=fullName>   
 <xref:System.ServiceModel.FaultException%601?displayProperty=fullName>