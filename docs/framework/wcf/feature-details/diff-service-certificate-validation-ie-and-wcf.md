---
title: Internet Explorer와 WCF로 완료된 서비스 인증서 유효성 검사의 차이점
ms.date: 03/30/2017
helpviewer_keywords:
- service certificate validation [WCF]
- certificates [WCF], service certificate validation
ms.assetid: 9dffcab2-70a9-40f0-99fd-d3a0b296028f
ms.openlocfilehash: ecc2b16eae5428e305f5f6096d6d7994256d86c2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33488688"
---
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a><span data-ttu-id="d5639-102">Internet Explorer와 WCF로 완료된 서비스 인증서 유효성 검사의 차이점</span><span class="sxs-lookup"><span data-stu-id="d5639-102">Differences Between Service Certificate Validation Done by Internet Explorer and WCF</span></span>
<span data-ttu-id="d5639-103">Internet Explorer 및 Windows Communication Foundation (WCF) HTTPS 사용 시 서비스 인증서를 확인 하는 방법 간의 차이로 인해 것은 Internet Explorer에서는 도움말 페이지 또는 웹 서비스 기술 언어에 액세스할 수 없습니다. (WSDL) 서비스의 WCF 클라이언트는 성공적으로 수 있지만 메시지를 보내는 서비스 끝점입니다.</span><span class="sxs-lookup"><span data-stu-id="d5639-103">Because of difference between the way Internet Explorer and Windows Communication Foundation (WCF) validate service certificates when HTTPS is used, it is possible that Internet Explorer will not be able to access the Help page or Web Services Description Language (WSDL) of a service even though a WCF client is able to successfully send messages to the service endpoints.</span></span> <span data-ttu-id="d5639-104">이 Internet Explorer 확인 하기 때문에 서비스 인증서에 있는지 여부는 `ServerAuthentication` WCF 이러한 제약 조건을 적용 하지 않는 반면 향상 된 사용 플래그의 개체 식별자 (OID)입니다.</span><span class="sxs-lookup"><span data-stu-id="d5639-104">This is because Internet Explorer checks whether the service certificate has the `ServerAuthentication` object identifiers (OID) in the enhanced usage flags, whereas WCF does not enforce such a constraint.</span></span> <span data-ttu-id="d5639-105">사용 하 여 Internet Explorer 서비스 도움말 페이지 또는 서비스에 대 한 WSDL에 액세스할 수 없는 경우는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 서비스 메타 데이터를 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5639-105">If Internet Explorer is unable to access the service Help page or the WSDL for the service, use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to access the service metadata.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5639-106">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d5639-106">See Also</span></span>  
 [<span data-ttu-id="d5639-107">HTTPS, TCP를 통한 SSL 및 SOAP 보안의 인증서 유효성 검사 차이점</span><span class="sxs-lookup"><span data-stu-id="d5639-107">Certificate Validation Differences Between HTTPS, SSL over TCP, and SOAP Security</span></span>](../../../../docs/framework/wcf/feature-details/cert-val-diff-https-ssl-over-tcp-and-soap.md)  
 [<span data-ttu-id="d5639-108">방법: 메타데이터 검색 및 규격 서비스 구현</span><span class="sxs-lookup"><span data-stu-id="d5639-108">How to: Retrieve Metadata and Implement a Compliant Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)
