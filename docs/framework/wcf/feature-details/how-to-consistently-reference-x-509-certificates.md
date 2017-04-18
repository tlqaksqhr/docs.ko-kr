---
title: "방법: 일관성 있게 X.509 인증서 참조 | Microsoft Docs"
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
  - "인증서 [WCF], X.509 인증서 참조"
ms.assetid: a6de1c63-e450-4640-ad08-ad7302dbfbfc
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 방법: 일관성 있게 X.509 인증서 참조
인증서의 해시, 발급자와 일련 번호 또는 SKI\(주체 키 식별자\) 등의 다양한 방법으로 인증서를 식별할 수 있습니다.SKI는 인증서 주체 공개 키의 고유 ID를 제공하며 XML 디지털 서명을 사용할 때 주로 사용됩니다.SKI 값은 일반적으로 X.509 인증서에 *X.509 인정서 확장*으로 포함됩니다.[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에는 인증서에 SKI 확장이 없는 경우 발급자와 일련 번호를 사용하는 기본 *참조 스타일*이 있습니다.인증서에 SKI 확장이 있는 경우 기본 참조 스타일에서는 SKI를 사용하여 인증서를 가리킵니다.응용 프로그램을 개발하는 도중에 SKI 확장을 사용하지 않는 인증서에서 SKI 확장을 사용하는 인증서로 전환하는 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 생성된 메시지에 사용되는 참조 스타일도 변경됩니다.  
  
 SKI 확장의 존재 여부에 관계없이 일관성 있는 참조 스타일을 사용해야 하는 경우에는 다음 코드처럼 원하는 참조 스타일을 구성할 수 있습니다.  
  
## 예제  
 다음 예제에서는 일관성 있는 단일 참조 스타일\(발급자 이름과 일련 번호\)을 사용하는 사용자 지정 보안 바인딩 요소를 만듭니다.  
  
 [!code-csharp[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_referencingcertificatesconsistently/cs/source.cs#1)]
 [!code-vb[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_referencingcertificatesconsistently/vb/source.vb#1)]  
  
## 코드 컴파일  
 코드를 컴파일하려면 다음 네임스페이스가 필요합니다.  
  
-   <xref:System>  
  
-   <xref:System.ServiceModel>  
  
-   <xref:System.ServiceModel.Channels>  
  
-   <xref:System.ServiceModel.Security.Tokens>  
  
## 참고 항목  
 [인증서 작업](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)