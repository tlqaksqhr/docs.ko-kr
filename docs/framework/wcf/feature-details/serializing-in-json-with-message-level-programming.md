---
title: "메시지 수준의 프로그래밍으로 JSON으로 serialize | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5f940ba2-57ee-4c49-a779-957c5e7e71fa
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 메시지 수준의 프로그래밍으로 JSON으로 serialize
WCF는 JSON 형식의 데이터 serialize를 지원합니다.이 항목에서는 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>를 사용하여 WCF가 형식을 serialize하도록 하는 방법에 대해 설명합니다.  
  
## 형식화된 메시지 프로그래밍  
 서비스 작업에 <xref:System.ServiceModel.Web.WebGetAttribute> 또는 <xref:System.ServiceModel.Web.WebInvokeAttribute>가 적용되면 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>를 사용합니다.두 특성을 사용하여 `RequestFormat` 및 `ResponseFormat`을 지정할 수 있습니다.요청 및 응답에 JSON을 사용하려면 둘 다 `WebMessageFormat.Json`으로 설정합니다.JSON을 사용하려면 <xref:System.ServiceModel.Description.WebHttpBehavior>를 자동으로 구성하는 <xref:System.ServiceModel.WebHttpBinding>을 사용해야 합니다.WCF serialization에 대한 자세한 내용은 [Serialization 및 Deserialization](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md), [WCF\(Windows Communication Foundation\)의 Serialization](http://msdn.microsoft.com/magazine/cc163569.aspx)을 참조하십시오.JSON 및 WCF에 대한 자세한 내용은 [WCF를 사용한 RESTfull 서비스 소개](http://msdn.microsoft.com/magazine/dd315413.aspx), [.NET 3.5에서 JSON 활성화 WCF 서비스 만들기](http://www.pluralsight-training.net/community/blogs/fritz/archive/2008/01/31/50121.aspx) 및 [WCF의 REST 개요](http://msdn.microsoft.com/netframework/dd547388)를 참조하십시오.  
  
> [!IMPORTANT]
>  JSON을 사용하려면 SOAP 통신을 지원하지 않는 <xref:System.ServiceModel.WebHttpBinding> 및 <xref:System.ServiceModel.Description.WebHttpBehavior>를 사용해야 합니다.<xref:System.ServiceModel.WebHttpBinding>과 통신하는 서비스는 서비스 메타데이터 노출을 지원하지 않으므로 Visual Studio의 서비스 참조 추가 기능 또는 svcutil 명령줄 도구를 사용하여 클라이언트 측 프록시를 만들 수 없습니다.<xref:System.ServiceModel.WebHttpBinding>을 사용하는 서비스를 프로그래밍 방식으로 호출하는 방식에 대한 자세한 내용은 [WCF를 사용하여 REST 서비스를 사용하는 방법](http://blogs.msdn.com/b/pedram/archive/2008/04/21/how-to-consume-rest-services-with-wcf.aspx)을 참조하십시오.  
  
## 형식화되지 않은 메시지 프로그래밍  
 형식화되지 않은 메시기 개체로 직접 작업할 때는 형식화되지 않은 메시지의 속성을 명시적으로 설정하여 JSON으로 serialize해야 합니다.다음 코드 조각에서는 이를 수행하는 방법을 보여 줍니다.  
  
```  
 Message response = Message.CreateMessage(  
                  MessageVersion.None,    // No SOAP message version  
                             "*",                     // SOAP action, ignored since this is JSON  
                             "Response string: JSON format specified", // Message body  
                             new DataContractJsonSerializer(typeof(string))); // Specify DataContractJsonSerializer  
      response.Properties.Add( WebBodyFormatMessageProperty.Name,   
                    new WebBodyFormatMessageProperty(WebContentFormat.Json)); // Use JSON format  
  
```  
  
## 참고 항목  
 [AJAX 통합 및 JSON 지원](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)   
 [독립 실행형 JSON Serialization](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)   
 [JSON Serialization](../../../../docs/framework/wcf/samples/json-serialization.md)