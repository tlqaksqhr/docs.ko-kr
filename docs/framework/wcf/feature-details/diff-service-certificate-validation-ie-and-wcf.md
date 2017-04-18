---
title: "Internet Explorer와 WCF로 완료된 서비스 인증서 유효성 검사의 차이점 | Microsoft Docs"
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
  - "인증서 [WCF], 서비스 인증서 유효성 검사"
  - "서비스 인증서 유효성 검사 [WCF]"
ms.assetid: 9dffcab2-70a9-40f0-99fd-d3a0b296028f
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Internet Explorer와 WCF로 완료된 서비스 인증서 유효성 검사의 차이점
HTTPS 사용 시 Internet Explorer와 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]의 서비스 인증서 유효성 검사의 차이로 인해 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트가 메시지를 서비스 끝점에 성공적으로 보낼 수 있는 경우에도 Internet Explorer에서는 서비스의 도움말 페이지나 WSDL\(웹 서비스 기술 언어\)에 액세스할 수 없습니다.이는 Internet Explorer의 경우 서비스 인증서에 향상된 사용 플래그의 `ServerAuthentication` OID\(Object Identifier\)가 있는지 여부를 확인하지만, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 경우 이러한 제약 조건을 적용하지 않기 때문입니다.Internet Explorer에서 서비스 도움말 페이지나 서비스의 WSDL에 액세스할 수 없는 경우 [ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)를 사용하여 서비스 메타데이터에 액세스합니다.  
  
## 참고 항목  
 [HTTPS, TCP를 통한 SSL 및 SOAP 보안의 인증서 유효성 검사 차이점](../../../../docs/framework/wcf/feature-details/cert-val-diff-https-ssl-over-tcp-and-soap.md)   
 [방법: 메타데이터 검색 및 규격 서비스 구현](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)