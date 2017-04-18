---
title: "최선의 방법: 매개자 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2d41b337-8132-4ac2-bea2-6e9ae2f00f8d
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 최선의 방법: 매개자
매개자를 호출하여 매개자의 서비스 측 채널이 올바르게 닫혀 있는지 확인하는 경우에는 오류를 제대로 처리하도록 주의를 기울여야 합니다.  
  
 다음과 같은 시나리오를 생각해 볼 수 있습니다.클라이언트에서 매개자를 호출한 다음 백 엔드 서비스를 호출합니다.백 엔드 서비스는 오류가 없는 계약을 정의하기 때문에 해당 서비스에서 throw된 오류는 형식화되지 않은 오류로 취급됩니다.백 엔드 서비스는 <xref:System.ApplicationException>을 throw하고 WCF는 서비스 측 채널을 올바르게 중단합니다.그런 다음 <xref:System.ApplicationException>에서 매개자로 throw되는 <xref:System.ServiceModel.FaultException>을 표시합니다.매개자는 <xref:System.ApplicationException>을 다시 throw합니다.WCF는 이를 매개자로부터 형식화되지 않은 오류로 해석하고 클라이언트에 전달합니다.오류가 수신되면 매개자 및 클라이언트에서 클라이언트 측 채널을 오류 처리합니다.그러나 WCF에서는 치명적인 오류임을 알 수 없으므로 매개자의 서비스 측 채널이 계속 열려 있습니다.  
  
 이 시나리오의 가장 좋은 방법은 서비스에서 전달되는 오류가 치명적인지 확인하고 치명적인 오류라면 다음 코드 조각과 같이 매개자가 해당 서비스 측 채널을 오류 처리해야 합니다.  
  
```csharp  
catch (Exception e)  
{  
    bool faulted = service.State == CommunicationState.Faulted;  
    service.Abort();  
    if (faulted)  
    {  
        throw new ApplicationException(e.Message);  
    }  
    Else  
    {  
        throw;  
    }  
}  
  
```  
  
## 참고 항목  
 [WCF 오류 처리](../../../docs/framework/wcf/wcf-error-handling.md)   
 [계약 및 서비스에서 오류 지정 및 처리](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)