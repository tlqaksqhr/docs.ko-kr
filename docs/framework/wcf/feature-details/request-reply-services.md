---
title: "요청-회신 서비스 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "계약 [WCF], 요청-회신 서비스"
  - "요청-회신 계약 [WCF]"
  - "WCF [WCF], 요청-회신 서비스"
  - "Windows Communication Foundation [WCF], 요청-회신 서비스"
ms.assetid: 2fa710f1-47f4-4598-b063-3ab3bd22ebba
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# 요청-회신 서비스
요청\-회신 서비스는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서 작업 계약의 기본 형식입니다.클라이언트는 서비스 작업에 대한 호출을 만들고 서비스로부터 응답을 기다립니다.사용자는 서비스 작업에 대한 호출을 동기적으로\(클라이언트가 서비스 또는 호출 시간으로부터 응답을 받을 때까지 차단하는 경우\) 또는 비동기적으로\(클라이언트가 서비스 작업에 대한 호출을 만들고, 작업을 계속하고, 다른 스레드의 서비스로부터 응답을 받는 경우\) 수행할 수 있습니다.  
  
 요청\-회신 서비스 계약을 만들려면 다음 샘플 코드에서처럼 서비스 계약을 정의하고 <xref:System.ServiceModel.OperationContractAttribute> 클래스를 각 작업에 적용합니다.  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IRequestReplyCalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
}  
  
```  
  
 기본 동작이므로 <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> 속성을 `false`로 설정할 필요가 없습니다.  
  
## 참고 항목  
 [단방향 서비스](../../../../docs/framework/wcf/feature-details/one-way-services.md)   
 [이중 서비스](../../../../docs/framework/wcf/feature-details/duplex-services.md)