---
title: "사용자 지정 바인딩을 통해 메타데이터 게시 및 검색 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 904e11b4-d90e-45c6-9ee5-c3472c90008c
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# 사용자 지정 바인딩을 통해 메타데이터 게시 및 검색
<xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=fullName>에서는 메타데이터 끝점을 서비스에 추가할 수 있도록 지원합니다.이러한 메타데이터 끝점은 `?wsdl` 쿼리 문자열이 있는 URL에 있는 HTTP GET 요청 및 WS\-MEX\(WS\-MetadataExchange\) 사양에 정의한 WS\-Transfer GET 요청에 응답할 수 있습니다.MEX 끝점은 <xref:System.ServiceModel.Description.IMetadataExchange?displayProperty=fullName> 계약을 구현합니다.  
  
## 사용자 지정 바인딩을 통해 메타데이터 게시  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A?displayProperty=fullName> 또는 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A?displayProperty=fullName> 속성을 `true`로 설정하여 HTTP GET 메타데이터 끝점 및 HTTPS GET 메타데이터 끝점을 사용할 수 있습니다.이러한 끝점에 대한 바인딩은 구성할 수 없습니다.  
  
 그러나 <xref:System.ServiceModel.Description.IMetadataExchange> 끝점이 다른 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스 끝점과 동일하기 때문에 <xref:System.ServiceModel.Description.IMetadataExchange> 계약을 사용자 지정 바인딩을 사용하는 끝점을 비롯하여 모든 끝점과 함께 사용할 수 있습니다.시스템 제공 바인딩의 구성을 수정하는 방법을 알고 있거나 <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=fullName>을 구성하는 방법을 알고 있는 경우 <xref:System.ServiceModel.Description.IMetadataExchange> 끝점에 사용할 바인딩을 구성할 수 있습니다.  
  
## 사용자 지정 바인딩을 통해 메타데이터 검색  
 표준 HTTP 또는 HTTPS GET 요청을 사용하여 HTTP Get 및 HTTPS Get 메타데이터 끝점에서 메타데이터를 검색할 수 있습니다.  
  
 MEX 메타데이터 끝점에서 메타데이터를 검색하기 위해 일반적으로 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 지원하는 표준 MEX 바인딩 중 하나를 사용할 수 있습니다.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<xref:System.ServiceModel.Description.MetadataExchangeBindings?displayProperty=fullName>.<xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=fullName> 형식 및 Svcutil.exe 도구에서는 지정된 메타데이터 끝점의 주소에 따라 이러한 표준 MEX 바인딩 중 하나를 자동으로 선택합니다.  
  
 MEX 메타데이터 끝점에서 표준 MEX 바인딩과 다른 바인딩을 사용하는 경우 코드를 사용하거나 <xref:System.ServiceModel.Description.IMetadataExchange> 클라이언트 끝점 구성을 제공하여 <xref:System.ServiceModel.Description.MetadataExchangeClient>에서 사용하는 바인딩을 구성할 수 있습니다.Svcutil.exe 도구는 메타데이터 끝점 주소의 URI 스키마와 이름이 같은 <xref:System.ServiceModel.Description.IMetadataExchange> 클라이언트 끝점 구성을 구성 파일에서 자동으로 로드합니다.  
  
## 보안  
 사용자 지정 바인딩을 통해 메타데이터를 게시하는 경우 바인딩에서 메타데이터가 필요로 하는 보안 지원을 제공하는지 확인합니다.예를 들어, 정보 공개를 방지하고 클라이언트에 메타데이터를 가져올 권한이 있는지 확인하려면 인증 및 암호화가 필요한 <xref:System.ServiceModel.Description.IMetadataExchange> 끝점을 구성하여 메타데이터 및 응용 프로그램의 보안을 더욱 향상시킬 수 있습니다.샘플 [Custom Secure Metadata Endpoint](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md)에서는 이러한 경우를 보여 줍니다.  
  
## 참고 항목  
 [서비스에 보안 설정](../../../../docs/framework/wcf/securing-services.md)   
 [WS\-MetadataExchange 바인딩](../../../../docs/framework/wcf/extending/ws-metadataexchange-bindings.md)   
 [방법: 사용자 지정 WS\-Metadata Exchange 바인딩 구성](../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)   
 [방법: MEX가 아닌 바인딩을 통해 메타데이터 검색](../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)