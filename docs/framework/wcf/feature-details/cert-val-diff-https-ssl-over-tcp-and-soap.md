---
title: "HTTPS, TCP를 통한 SSL 및 SOAP 보안의 인증서 유효성 검사 차이점 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "인증서 [WCF], 유효성 검사 차이점"
ms.assetid: 953a219f-4745-4019-9894-c70704f352e6
caps.latest.revision: 14
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 14
---
# HTTPS, TCP를 통한 SSL 및 SOAP 보안의 인증서 유효성 검사 차이점
HTTPS\(HTTP를 통한 TLS\(전송 계층 보안\)\) 또는 TCP를 통한 TLS와 함께 메시지 계층\(SOAP\) 보안이 있는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]의 인증서를 사용할 수 있습니다.이 항목에서는 이러한 인증서의 유효성을 검사하는 방법의 차이점에 대해 설명합니다.  
  
## HTTPS 클라이언트 인증서 유효성 검사  
 HTTPS를 사용하여 클라이언트와 서비스 간에 통신하는 경우 클라이언트에서 서비스를 인증하는 데 사용하는 인증서는 신뢰 체인을 지원해야 합니다.즉, 신뢰할 수 있는 루트 인증 기관에 연결되어야 합니다.연결되지 않은 경우 HTTP 계층에서 "원격 서버에서 \(403\) 사용할 수 없음 오류를 반환했습니다."라는 메시지와 함께 <xref:System.Net.WebException>이 발생합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 이 예외를 <xref:System.ServiceModel.Security.MessageSecurityException>으로 표시합니다.  
  
## HTTPS 서비스 인증서 유효성 검사  
 HTTPS를 사용하여 클라이언트와 서비스 간에 통신하는 경우 서버에서 인증하는 데 사용하는 인증서는 신뢰 체인을 기본적으로 지원해야 합니다.즉, 신뢰할 수 있는 루트 인증 기관에 연결되어야 합니다.인증서가 해지되었는지 여부를 확인하기 위해 온라인 확인을 수행하지는 않습니다.다음 코드에서처럼 <xref:System.Net.Security.RemoteCertificateValidationCallback> 콜백을 등록하여 이 동작을 재정의할 수 있습니다.  
  
 [!code-csharp[c_CertificateValidationDifferences#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#1)]
 <!-- TODO: review snippet reference [!code-vb[c_CertificateValidationDifferences#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#1)]  -->  
  
 여기서 `ValidateServerCertificate`의 서명은 다음과 같습니다.  
  
 [!code-csharp[c_CertificateValidationDifferences#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#2)]
 [!code-vb[c_CertificateValidationDifferences#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#2)]  
  
 `ValidateServerCertificate`를 구현하면 클라이언트 응용 프로그램 개발자가 서비스 인증서의 유효성을 검사하는 데 필요하다고 판단하는 확인 사항을 수행할 수 있습니다.  
  
## TCP를 통한 SSL 또는 SOAP 보안에서 클라이언트 인증서 유효성 검사  
 TCP를 통한 SSL\(Secure Sockets Layer\) 또는 SOAP 메시지 보안을 사용하는 경우 <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> 클래스의 <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> 속성 값에 따라 클라이언트 인증서의 유효성을 검사합니다.속성은 <xref:System.ServiceModel.Security.X509CertificateValidationMode> 값 중 하나로 설정됩니다.<xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> 클래스의 <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.RevocationMode%2A> 속성 값에 따라 해지 확인을 수행합니다.속성은 <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> 값 중 하나로 설정됩니다.  
  
 [!code-csharp[c_CertificateValidationDifferences#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#3)]
 [!code-vb[c_CertificateValidationDifferences#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#3)]  
  
## TCP를 통한 SSL 또는 SOAP 보안에서 서비스 인증서 유효성 검사  
 TCP를 통한 SSL 또는 SOAP 메시지 보안을 사용하는 경우 <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication> 클래스의 <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> 속성 값에 따라 서비스 인증서의 유효성을 검사합니다.속성은 <xref:System.ServiceModel.Security.X509CertificateValidationMode> 값 중 하나로 설정됩니다.  
  
 <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication> 클래스의 <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.RevocationMode%2A> 속성 값에 따라 해지 확인을 수행합니다.속성은 <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> 값 중 하나로 설정됩니다.  
  
 [!code-csharp[c_CertificateValidationDifferences#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#4)]
 [!code-vb[c_CertificateValidationDifferences#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#4)]  
  
## 참고 항목  
 <xref:System.Net.Security.RemoteCertificateValidationCallback>   
 [인증서 작업](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)