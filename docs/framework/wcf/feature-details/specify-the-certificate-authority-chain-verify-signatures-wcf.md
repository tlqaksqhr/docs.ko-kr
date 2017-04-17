---
title: "방법: 서명을 확인하는 데 사용되는 인증 기관 인증서 체인 지정(WCF) | Microsoft Docs"
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
  - "인증서 [WCF], 인증 기관 인증서 체인 지정"
  - "인증서 [WCF], 서명 확인"
ms.assetid: 7c719355-aa41-4567-80d0-5115a8cf73fd
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 방법: 서명을 확인하는 데 사용되는 인증 기관 인증서 체인 지정(WCF)
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]는 X.509 인증서를 사용하여 서명된 SOAP 메시지를 받으면 기본적으로 X.509 인증서가 신뢰할 수 있는 인증 기관에서 발급된 것인지 확인합니다.이렇게 하려면 인증서 저장소를 찾고 해당 인증 기관의 인증서가 신뢰할 수 있는 것으로 지정되었는지 확인합니다.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 이러한 결정을 하려면 올바른 인증서 저장소에 인증 기관 인증서 체인을 설치해야 합니다.  
  
### 인증 기관 인증서 체인을 설치하려면  
  
-   SOAP 메시지 받는 사람이 신뢰하는 X.509 인증서를 발급한 각 인증 기관에 대해 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 X.509 인증서를 검색하도록 구성된 인증서 저장소에 인증 기관 인증서 체인을 설치합니다.  
  
     예를 들어, SOAP 메시지 받는 사람이 Microsoft에서 발급한 X.509 인증서를 신뢰하는 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 X.509 인증서를 찾도록 설정된 인증서 저장소에 Microsoft에 대한 인증 기관 인증서 체인을 설치해야 합니다.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 X.509 인증서를 찾는 인증서 저장소는 코드나 구성에 지정할 수 있습니다.예를 들어, 이러한 저장소는 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> 메서드를 사용하여 코드에 지정하거나, [\<serviceCertificate\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)를 비롯한 몇 가지 방법으로 구성에 지정할 수 있습니다.  
  
     Windows는 신뢰할 수 있는 인증 기관에 대한 기본 인증서 체인 집합이 함께 제공되므로 모든 인증 기관에 대한 인증서 체인을 반드시 설치할 필요는 없습니다.  
  
    1.  인증 기관 인증서 체인을 내보냅니다.  
  
         이 작업을 수행하는 방법은 인증 기관에 따라 다릅니다.인증 기관에서 Microsoft 인증서 서비스를 실행하고 있는 경우 **CA 인증서, 인증서 체인 또는 CRL 다운로드**를 선택한 다음 **CA 인증서 다운로드**를 선택합니다.  
  
    2.  인증 기관 인증서 체인을 가져옵니다.  
  
         MMC\(Microsoft Management Console\)에서 인증서 스냅인을 엽니다.X.509 인증서를 검색하도록 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]가 구성된 인증서 저장소의 경우 **신뢰할 수 있는 루트** **인증 기관**폴더를 선택합니다.**신뢰할 수 있는 루트 인증 기관** 폴더에서 **인증서**폴더를 마우스 오른쪽 단추로 클릭하고 **모든 작업**을 가리킨 다음 **가져오기**를 클릭합니다.a 단계에서 내보낸 파일을 제공합니다.  
  
         MMC에 인증서 스냅인을 사용하는 방법[!INCLUDE[crabout](../../../../includes/crabout-md.md)][방법: MMC 스냅인을 사용하여 인증서 보기](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)를 참조하십시오.  
  
## 참고 항목  
 [인증서 작업](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)