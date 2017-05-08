---
title: "컨텍스트 교환 상관 관계 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1e2852be-3601-45ae-b507-ccc465d45c60
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# 컨텍스트 교환 상관 관계
컨텍스트 상관 관계는 [.NET Context Exchange Protocol Specification](http://go.microsoft.com/fwlink/?LinkId=166059)에서 설명하는 컨텍스트 교환 메커니즘을 기반으로 합니다.컨텍스트 상관 관계는 잘 알려진 컨텍스트 헤더나 쿠키를 사용하여 메시지를 올바른 인스턴스와 연결합니다.컨텍스트 상관 관계를 사용하려면 <xref:System.ServiceModel.Activities.WorkflowServiceHost>에 제공된 끝점에서 <xref:System.ServiceModel.BasicHttpContextBinding>, <xref:System.ServiceModel.WSHttpContextBinding> 또는 <xref:System.ServiceModel.NetTcpContextBinding> 같은 컨텍스트 기반 바인딩을 사용해야 합니다.이 항목에서는 워크플로 서비스의 메시징 작업에 컨텍스트 상관 관계를 사용하는 방법에 대해 설명합니다.  
  
## 컨텍스트 상관 관계 사용  
 컨텍스트 상관 관계는 클라이언트가 컨텍스트 바인딩 중 하나를 사용하여 호스팅되는 워크플로 서비스를 반복하여 호출해야 하는 경우 사용됩니다.이 형식의 상관 관계는 워크플로 서비스의 <xref:System.ServiceModel.Activities.Receive>\/<xref:System.ServiceModel.Activities.SendReply> 쌍에 의해 초기화됩니다.컨텍스트는 회신과 함께 클라이언트로 다시 전송됩니다. 그러면 클라이언트는 이 컨텍스트를 서비스에 대한 후속 호출에 연결합니다.  
  
### 워크플로 서비스에서 컨텍스트 상관 관계 구성  
 컨텍스트 상관 관계는 초기 들어오는 메시지에 회신하는 <xref:System.ServiceModel.Activities.SendReply> 작업과 연결된 <xref:System.ServiceModel.Activities.ContextCorrelationInitializer>를 사용하여 초기화됩니다.다음 예제에서는 <xref:System.ServiceModel.Activities.SendReply>가 컨텍스트 상관 관계를 초기화하도록 구성됩니다.  
  
```csharp  
Variable<string> Item = new Variable<string>();  
Variable<CorrelationHandle> OrderHandle = new Variable<CorrelationHandle>();  
  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = "IOrderService",  
    OperationName = "StartOrder"  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    CorrelationInitializers =  
    {  
        new ContextCorrelationInitializer  
        {  
            CorrelationHandle = OrderHandle  
        }  
    }  
};  
```  
  
> [!NOTE]
>  이 예제에서는 컨텍스트 상관 관계와 요청\-회신 상관 관계라는 두 가지 상관 관계가 실제로 사용됩니다.컨텍스트 상관 관계는 클라이언트에서의 호출이 올바른 인스턴스로 라우트되도록 하기 위해 사용됩니다.요청\-회신 상관 관계는 <xref:System.ServiceModel.Activities.Receive> 및 <xref:System.ServiceModel.Activities.SendReply> 작업을 통해 모델링된 양방향 작업을 구현하기 위해 이러한 두 작업에서 함께 사용됩니다.이 예제에서는 컨텍스트 상관 관계만 명시적으로 구성되며 <xref:System.ServiceModel.Activities.Receive>\/<xref:System.ServiceModel.Activities.SendReply> 쌍은 <xref:System.ServiceModel.Activities.WorkflowServiceHost>의 암시적 <xref:System.ServiceModel.Activities.CorrelationHandle> 관리에 의해 제공되는 기본 요청\-회신 상관 관계를 사용합니다.워크플로 디자이너의 **ReceiveAndSendReply** 활동 템플릿을 사용하는 경우 요청\-회신 상관 관계가 명시적으로 구성됩니다.요청\-회신 상관 관계 및 묵시적 상관 관계 처리 관리에 대한 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]는 [요청\-회신](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md) 및 [상관 관계 개요](../../../../docs/framework/wcf/feature-details/correlation-overview.md)를 참조하십시오.**ReceiveAndSendReply** 활동 템플릿에 대한 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]는 [ReceiveAndSendReply](../Topic/ReceiveAndSendReply%20Template%20Designer.md)를 참조하십시오.  
  
 워크플로 서비스의 후속 <xref:System.ServiceModel.Activities.Receive> 작업은 이전 예제에서 <xref:System.ServiceModel.Activities.SendReply>에 의해 초기화된 <xref:System.ServiceModel.Activities.CorrelationHandle>을 참조할 수 있습니다.  
  
```csharp  
Receive AddItem = new Receive  
{  
    ServiceContractName = "IOrderService",  
    OperationName = "AddItem",  
    CorrelatesWith = OrderHandle  
};  
```  
  
 그러면 끝점이 <xref:System.ServiceModel.Activities.WorkflowServiceHost>에서 <xref:System.ServiceModel.BasicHttpContextBinding> 같은 컨텍스트 기반 바인딩을 사용하도록 구성됩니다.  
  
```xml  
<endpoint  
  contract=”IOrderContract”  
  binding = “basicHttpContextBinding”  
  address=”http://localhost:8080/OrderService” />  
```  
  
### 워크플로 클라이언트에서 컨텍스트 상관 관계 구성  
 클라이언트도 워크플로이면 클라이언트에서도 컨텍스트 상관 관계를 구성해야 합니다.클라이언트 워크플로에서 워크플로 서비스를 초기 호출하는 <xref:System.ServiceModel.Activities.Send>\/<xref:System.ServiceModel.Activities.ReceiveReply> 쌍의 <xref:System.ServiceModel.Activities.ReceiveReply>는 <xref:System.ServiceModel.Activities.ContextCorrelationInitializer>를 사용하여 구성해야 합니다.  
  
```csharp  
Variable<CorrelationHandle> cchandle = new Variable<CorrelationHandle>();  
Send request = new Send  
{  
    // Activity configuration omitted.  
};  
  
ReceiveReply reply = new ReceiveReply  
{  
    Request = request,  
    CorrelationInitializers =   
    {  
        new ContextCorrelationInitializer  
        {  
            CorrelationHandle = cchandle  
        }  
    }  
};  
```  
  
 상관 관계가 초기화된 후 후속 <xref:System.ServiceModel.Activities.Send> 작업에서 <xref:System.ServiceModel.Activities.CorrelationHandle>을 사용하여 동일한 서비스 인스턴스에 대한 메서드를 호출할 수 있습니다.  
  
```csharp  
Send request2 = new Send  
{  
    CorrelatesWith = cchandle,  
    // Remaining activity configuration omitted.  
};  
```  
  
 위에 나온 예제들에서는 컨텍스트 상관 관계가 명시적으로 구성되었습니다.클라이언트 워크플로도 <xref:System.ServiceModel.Activities.WorkflowServiceHost>에서 호스팅되지 않는 경우 해당 작업이 <xref:System.ServiceModel.Activities.CorrelationScope> 작업 내에 포함되어 있지 않으면 상관 관계를 명시적으로 구성해야 합니다.컨텍스트 상관 관계에 대한 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]는 [NetContextExchangeCorrelation](http://msdn.microsoft.com/ko-kr/93c74a1a-b9e2-46c6-95c0-c9b0e9472caf) 예제를 참조하십시오.  
  
 워크플로 서비스를 호출하는 클라이언트가 워크플로가 아닌 경우 해당 클라이언트가 첫 번째 호출에서 반환되는 컨텍스트를 워크플로 서비스에 명시적으로 다시 전달한다면 워크플로 서비스를 반복하여 호출할 수 있습니다.[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 서비스 참조를 추가하여 생성된 프록시는 기본적으로 이 컨텍스트를 저장하고 전달합니다.