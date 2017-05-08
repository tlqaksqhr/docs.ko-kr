---
title: "방법: SOAP 및 웹 클라이언트에 계약 공개 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bb765a48-12f2-430d-a54d-6f0c20f2a23a
caps.latest.revision: 21
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 21
---
# 방법: SOAP 및 웹 클라이언트에 계약 공개
기본적으로 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서는 SOAP 클라이언트에 대해서만 끝점을 사용할 수 있도록 합니다.  [방법: 기본 WCF 웹 HTTP 서비스 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md)에서 비 SOAP 클라이언트에 끝점을 사용할 수 있습니다.  동일한 계약을 웹 끝점 및 SOAP 끝점으로 모두 사용해야 하는 경우가 있습니다.  이 항목에서는 이 작업을 수행하는 방법을 보여 줍니다.  
  
### 서비스 계약을 정의하려면  
  
1.  다음 코드와 같이 <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.Web.WebInvokeAttribute> 및 <xref:System.ServiceModel.Web.WebGetAttribute> 특성으로 표시된 인터페이스를 사용하여 서비스 계약을 정의합니다.  
  
     [!code-csharp[htSoapWeb#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#0)]
     [!code-vb[htSoapWeb#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#0)]  
  
    > [!NOTE]
    >  기본적으로 <xref:System.ServiceModel.Web.WebInvokeAttribute>는 POST 호출을 작업에 매핑합니다.  그러나 "method\=" 매개 변수를 지정하여 작업에 매핑할 메서드를 지정할 수 있습니다.  <xref:System.ServiceModel.Web.WebGetAttribute>는 "method\=" 매개 변수를 사용하지 않고 GET 호출만 서비스 작업에 매핑합니다.  
  
2.  다음 코드와 같이 서비스 계약을 구현합니다.  
  
     [!code-csharp[htSoapWeb#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#1)]
     [!code-vb[htSoapWeb#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#1)]  
  
### 서비스를 호스트하려면  
  
1.  다음 코드와 같이 <xref:System.ServiceModel.ServiceHost> 개체를 만듭니다.  
  
     [!code-csharp[htSoapWeb#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#2)]
     [!code-vb[htSoapWeb#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#2)]  
  
2.  다음 코드와 같이 <xref:System.ServiceModel.BasicHttpBinding>을 사용하여 SOAP 끝점에 대해 <xref:System.ServiceModel.Description.ServiceEndpoint>를 추가합니다.  
  
     [!code-csharp[htSoapWeb#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#3)]
     [!code-vb[htSoapWeb#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#3)]  
  
3.  그리고 다음 코드와 같이 <xref:System.ServiceModel.WebHttpBinding>을 사용하여 비 SOAP 끝점에 대해 <xref:System.ServiceModel.Description.ServiceEndpoint>를 추가하고 끝점에 <xref:System.ServiceModel.Description.WebHttpBehavior>를 추가합니다.  
  
     [!code-csharp[htSoapWeb#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#4)]
     [!code-vb[htSoapWeb#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#4)]  
  
4.  다음 코드와 같이 <xref:System.ServiceModel.ServiceHost> 인스턴스에서 `Open()`을 호출하여 서비스 호스트를 엽니다.  
  
     [!code-csharp[htSoapWeb#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#5)]
     [!code-vb[htSoapWeb#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#5)]  
  
### Internet Explorer에서 GET에 매핑된 서비스 작업을 호출하려면  
  
1.  Internet Explorer를 열고 "`http://localhost:8000/Web/EchoWithGet?s=Hello, world!`"를 입력한 후 Enter 키를 누릅니다.  URL에는 서비스 기준 주소\("http:\/\/localhost:8000\/"\), 끝점 상대 주소\(""\), 호출할 서비스 작업\("EchoWithGet"\) 및 앰퍼샌드\(&\)로 구분된 명명된 매개 변수의 목록 앞에 있는 물음표가 포함됩니다.  
  
### 코드의 웹 끝점에서 서비스 작업을 호출하려면  
  
1.  다음 코드와 같이 `using` 블록 내에서 <xref:System.ServiceModel.Web.WebChannelFactory%601> 인스턴스를 만듭니다.  
  
     [!code-csharp[htSoapWeb#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#6)]
     [!code-vb[htSoapWeb#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#6)]  
  
> [!NOTE]
>  `Close()`는 `using` 블록의 끝에 있는 채널에서 자동으로 호출됩니다.  
  
1.  다음 코드와 같이 채널을 만들고 서비스를 호출합니다.  
  
     [!code-csharp[htSoapWeb#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#8)]
     [!code-vb[htSoapWeb#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#8)]  
  
### SOAP 끝점에서 서비스 작업을 호출하려면  
  
1.  다음 코드와 같이 `using` 블록 내에서 <xref:System.ServiceModel.ChannelFactory> 인스턴스를 만듭니다.  
  
     [!code-csharp[htSoapWeb#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#10)]
     [!code-vb[htSoapWeb#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#10)]  
  
2.  다음 코드와 같이 채널을 만들고 서비스를 호출합니다.  
  
     [!code-csharp[htSoapWeb#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#11)]
     [!code-vb[htSoapWeb#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#11)]  
  
### 서비스 호스트를 닫으려면  
  
1.  다음 코드와 같이 서비스 호스트를 닫습니다.  
  
     [!code-csharp[htSoapWeb#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#9)]
     [!code-vb[htSoapWeb#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#9)]  
  
## 예제  
 다음은 이 항목에 해당되는 전체 코드 목록입니다.  
  
 [!code-csharp[htSoapWeb#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#13)]
 [!code-vb[htSoapWeb#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#13)]  
  
## 코드 컴파일  
 Service.cs를 컴파일할 때 System.ServiceModel.dll 및 System.ServiceModel.Web.dll을 참조합니다.  
  
## 참고 항목  
 <xref:System.ServiceModel.WebHttpBinding>   
 <xref:System.ServiceModel.Web.WebGetAttribute>   
 <xref:System.ServiceModel.Web.WebInvokeAttribute>   
 <xref:System.ServiceModel.Web.WebServiceHost>   
 <xref:System.ServiceModel.ChannelFactory>   
 <xref:System.ServiceModel.Description.WebHttpBehavior>   
 [WCF 웹 HTTP 프로그래밍 모델](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)