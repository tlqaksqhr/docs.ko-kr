---
title: "방법: 서명을 확인하는 데 사용되는 인증 기관 인증서 체인 지정(WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates [WCF], specifying the certificate authority certificate chain
- certificates [WCF], verifying signatures
ms.assetid: 7c719355-aa41-4567-80d0-5115a8cf73fd
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6cba37a82174ab255cb6814e296154485fbdd54c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-specify-the-certificate-authority-certificate-chain-used-to-verify-signatures-wcf"></a><span data-ttu-id="fed94-102">방법: 서명을 확인하는 데 사용되는 인증 기관 인증서 체인 지정(WCF)</span><span class="sxs-lookup"><span data-stu-id="fed94-102">How to: Specify the Certificate Authority Certificate Chain Used to Verify Signatures (WCF)</span></span>
<span data-ttu-id="fed94-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]는 X.509 인증서를 사용하여 서명된 SOAP 메시지를 받으면 기본적으로 X.509 인증서가 신뢰할 수 있는 인증 기관에서 발급된 것인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fed94-103">When [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] receives a SOAP message signed using an X.509 certificate, by default it verifies that the X.509 certificate was issued by a trusted certification authority.</span></span> <span data-ttu-id="fed94-104">이렇게 하려면 인증서 저장소를 찾고 해당 인증 기관의 인증서가 신뢰할 수 있는 것으로 지정되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fed94-104">This is done by looking in a certificate store and determining if the certificate for that certification authority has been designated as trusted.</span></span> <span data-ttu-id="fed94-105">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 이러한 결정을 하려면 올바른 인증서 저장소에 인증 기관 인증서 체인을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fed94-105">In order for [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] to make this determination, the certification authority certificate chain must be installed in the correct certificate store.</span></span>  
  
### <a name="to-install-a-certification-authority-certificate-chain"></a><span data-ttu-id="fed94-106">인증 기관 인증서 체인을 설치하려면</span><span class="sxs-lookup"><span data-stu-id="fed94-106">To install a certification authority certificate chain</span></span>  
  
-   <span data-ttu-id="fed94-107">SOAP 메시지 받는 사람이 신뢰하는 X.509 인증서를 발급한 각 인증 기관에 대해 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 X.509 인증서를 검색하도록 구성된 인증서 저장소에 인증 기관 인증서 체인을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="fed94-107">For each certification authority that a SOAP message recipient intends to trust X.509 certificates issued from, install the certification authority certificate chain into the certificate store that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is configured to retrieve X.509 certificates from.</span></span>  
  
     <span data-ttu-id="fed94-108">예를 들어, SOAP 메시지 받는 사람이 Microsoft에서 발급한 X.509 인증서를 신뢰하는 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 X.509 인증서를 찾도록 설정된 인증서 저장소에 Microsoft에 대한 인증 기관 인증서 체인을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fed94-108">For instance, if a SOAP message recipient intends to trust X.509 certificates issued by Microsoft, the certification authority certificate chain for Microsoft must be installed in the certificate store that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is set up to look for X.509 certificates from.</span></span> <span data-ttu-id="fed94-109">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 X.509 인증서를 찾는 인증서 저장소는 코드나 구성에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fed94-109">The certificate store in which [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] looks for X.509 certificates can be specified in code or configuration.</span></span> <span data-ttu-id="fed94-110">예를 들어, 사용 하 여 코드에서 지정할 수 있습니다는 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> 메서드 또는 구성 등의 몇 가지 방법으로 [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="fed94-110">For example, this can be specified in code using the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> method or in configuration a few ways, including the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) .</span></span>  
  
     <span data-ttu-id="fed94-111">Windows는 신뢰할 수 있는 인증 기관에 대한 기본 인증서 체인 집합이 함께 제공되므로 모든 인증 기관에 대한 인증서 체인을 반드시 설치할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fed94-111">Because Windows ships with a set of default certificate chains for trusted certificate authorities, it may not be necessary to install the certificate chain for all certificate authorities.</span></span>  
  
    1.  <span data-ttu-id="fed94-112">인증 기관 인증서 체인을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="fed94-112">Export the certification authority certificate chain.</span></span>  
  
         <span data-ttu-id="fed94-113">이 작업을 수행하는 방법은 인증 기관에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="fed94-113">Exactly how this is done depends on the certification authority.</span></span> <span data-ttu-id="fed94-114">인증 기관에서 Microsoft 인증서 서비스를 실행 중인 경우 선택 **CA 인증서, 인증서 체인 또는 CRL 다운로드**를 선택한 후 **CA 인증서 다운로드**합니다.</span><span class="sxs-lookup"><span data-stu-id="fed94-114">If the certification authority is running Microsoft Certificate Services, select **Download a CA certificate, certificate chain, or CRL**, and then choose **Download CA certificate**.</span></span>  
  
    2.  <span data-ttu-id="fed94-115">인증 기관 인증서 체인을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fed94-115">Import the certification authority certificate chain.</span></span>  
  
         <span data-ttu-id="fed94-116">MMC(Microsoft Management Console)에서 인증서 스냅인을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fed94-116">In the Microsoft Management Console (MMC), open the Certificates snap-in.</span></span> <span data-ttu-id="fed94-117">인증서에 대 한 저장소를 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 선택에서 X.509 인증서를 검색 하도록 구성 된는 **신뢰할 수 있는 루트** **인증 기관**폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="fed94-117">For the certificate store that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is configured to retrieve X.509 certificates from, select the **Trusted Root** **Certification Authorities**folder.</span></span> <span data-ttu-id="fed94-118">아래는 **신뢰할 수 있는 루트 인증 기관** 폴더를 마우스 오른쪽 단추로 클릭는 **인증서**폴더를 가리키도록 **모든 작업**, 클릭 하 고 **가져오기** .</span><span class="sxs-lookup"><span data-stu-id="fed94-118">Under the **Trusted Root Certification Authorities** folder, right-click the **Certificates**folder, point to **All Tasks**, and then click **Import**.</span></span> <span data-ttu-id="fed94-119">a 단계에서 내보낸 파일을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fed94-119">Provide the file exported in step a.</span></span>  
  
         [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="fed94-120">인증서 스냅인 mmc를 사용 하 여 참조 [하는 방법: MMC 스냅인을 사용 하 여 보기 인증서](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fed94-120"> using the Certificates snap-in with MMC, see [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fed94-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fed94-121">See Also</span></span>  
 [<span data-ttu-id="fed94-122">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="fed94-122">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
