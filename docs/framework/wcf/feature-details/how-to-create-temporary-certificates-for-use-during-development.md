---
title: '방법: 개발 중 사용할 임시 인증서 만들기'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates [WCF], creating temporary certificates
- temporary certificates [WCF]
ms.assetid: bc5f6637-5513-4d27-99bb-51aad7741e4a
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ccbc8c6fa638c674dea28c312b2dedbc9d41968a
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="how-to-create-temporary-certificates-for-use-during-development"></a><span data-ttu-id="9348c-102">방법: 개발 중 사용할 임시 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="9348c-102">How to: Create Temporary Certificates for Use During Development</span></span>
<span data-ttu-id="9348c-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]를 사용하여 보안 서비스 또는 클라이언트를 개발하는 경우 자격 증명으로 사용할 X.509 인증서를 제공해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-103">When developing a secure service or client using [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], it is often necessary to supply an X.509 certificate to be used as a credential.</span></span> <span data-ttu-id="9348c-104">일반적으로 인증서는 루트 인증 기관이 컴퓨터의 신뢰할 수 있는 루트 인증 기관 저장소에 있는 인증서 체인의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-104">The certificate typically is part of a chain of certificates with a root authority found in the Trusted Root Certification Authorities store of the computer.</span></span> <span data-ttu-id="9348c-105">인증서 체인을 사용하면 일반적으로 루트 인증 기관이 조직 또는 비즈니스 사업부에 있는 인증서 집합의 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-105">Having a certificate chain enables you to scope a set of certificates where typically the root authority is from your organization or business unit.</span></span> <span data-ttu-id="9348c-106">개발 시 이를 에뮬레이트하려면 보안 요구 사항에 맞는 두 개의 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-106">To emulate this at development time, you can create two certificates to satisfy the security requirements.</span></span> <span data-ttu-id="9348c-107">첫 번째 인증서는 신뢰할 수 있는 루트 인증 기관 저장소에 있는 자체 서명된 인증서이고, 두 번째 인증서는 첫 번째 인증서에서 만들어지고 로컬 컴퓨터 위치의 개인 저장소나 현재 사용자 위치의 개인 저장소에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-107">The first is a self-signed certificate that is placed in the Trusted Root Certification Authorities store, and the second certificate is created from the first and is placed in either the Personal store of the Local Machine location, or the Personal store of the Current User location.</span></span> <span data-ttu-id="9348c-108">이 항목에서는 [SDK에서 제공하는](http://go.microsoft.com/fwlink/?LinkId=248185)인증서 작성 도구(MakeCert.exe) [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 를 사용하여 이러한 두 인증서를 만드는 단계를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-108">This topic walks through the steps to create these two certificates using the [Certificate Creation Tool (MakeCert.exe)](http://go.microsoft.com/fwlink/?LinkId=248185), which is provided by the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] SDK.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9348c-109">인증서 작성 도구가 생성하는 인증서는 테스트 용도로만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-109">The certificates the Certification Creation tool generates are provided for testing purposes only.</span></span> <span data-ttu-id="9348c-110">서비스 또는 클라이언트를 배포할 때는 인증 기관에서 제공하는 적절한 인증서를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-110">When deploying a service or client, be sure to use an appropriate certificate provided by a certification authority.</span></span> <span data-ttu-id="9348c-111">조직의 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 인증서 서버나 타사 인증서일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-111">This could either be from a [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] certificate server in your organization or a third party.</span></span>  
>   
>  <span data-ttu-id="9348c-112">기본적으로는 [Makecert.exe (인증서 작성 도구)](http://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d) 해당 루트 기관 라고 하는 인증서를 만들며 "루트 에이전시 **."**</span><span class="sxs-lookup"><span data-stu-id="9348c-112">By default, the [Makecert.exe (Certificate Creation Tool)](http://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d) creates certificates whose root authority is called "Root Agency **."**</span></span> <span data-ttu-id="9348c-113">라고 하는 인증서를 만듭니다. "루트 에이전시"는 신뢰할 수 있는 루트 인증 기관 저장소에 없으므로 해당 인증서를 신뢰할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-113">Because the "Root Agency" is not in the Trusted Root Certification Authorities store, this makes these certificates insecure.</span></span> <span data-ttu-id="9348c-114">신뢰할 수 있는 루트 인증 기관 저장소에 배치되는 자체 서명된 인증서를 만들면 배포 환경을 보다 근접하게 시뮬레이션하는 개발 환경을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-114">Creating a self-signed certificate that is placed in the Trusted Root Certification Authorities store enables you to create a development environment that more closely simulates your deployment environment.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="9348c-115"> 는 [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9348c-115"> creating and using certificates, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="9348c-116"> 는 [Securing Services and Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9348c-116"> using a certificate as a credential, see [Securing Services and Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md).</span></span> <span data-ttu-id="9348c-117">Microsoft Authenticode 기술을 사용하는 방법에 대한 자습서는 [Authenticode Overviews and Tutorials](http://go.microsoft.com/fwlink/?LinkId=88919)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9348c-117">For a tutorial about using Microsoft Authenticode technology, see [Authenticode Overviews and Tutorials](http://go.microsoft.com/fwlink/?LinkId=88919).</span></span>  
  
### <a name="to-create-a-self-signed-root-authority-certificate-and-export-the-private-key"></a><span data-ttu-id="9348c-118">자체 서명된 루트 인증 기관 인증서를 만들고 개인 키를 내보내려면</span><span class="sxs-lookup"><span data-stu-id="9348c-118">To create a self-signed root authority certificate and export the private key</span></span>  
  
1.  <span data-ttu-id="9348c-119">MakeCert.exe 도구에 다음 스위치를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-119">Use the MakeCert.exe tool with the following switches:</span></span>  
  
    1.  <span data-ttu-id="9348c-120">`-n` `subjectName`.</span><span class="sxs-lookup"><span data-stu-id="9348c-120">`-n` `subjectName`.</span></span> <span data-ttu-id="9348c-121">주체 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-121">Specifies the subject name.</span></span> <span data-ttu-id="9348c-122">규칙에 따라 주체 이름 앞에 "일반 이름"을 나타내는 "CN = "을 붙입니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-122">The convention is to prefix the subject name with "CN = " for "Common Name".</span></span>  
  
    2.  <span data-ttu-id="9348c-123">`-r`.</span><span class="sxs-lookup"><span data-stu-id="9348c-123">`-r`.</span></span> <span data-ttu-id="9348c-124">인증서가 자체 서명되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-124">Specifies that the certificate will be self-signed.</span></span>  
  
    3.  <span data-ttu-id="9348c-125">`-sv` `privateKeyFile`.</span><span class="sxs-lookup"><span data-stu-id="9348c-125">`-sv` `privateKeyFile`.</span></span> <span data-ttu-id="9348c-126">개인 키 컨테이너를 포함하는 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-126">Specifies the file that contains the private key container.</span></span>  
  
     <span data-ttu-id="9348c-127">예를 들어 다음 명령은 주체 이름 "CN=TempCA"를 사용하여 자체 서명된 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-127">For example, the following command creates a self-signed certificate with a subject name of "CN=TempCA."</span></span>  
  
    ```  
    makecert -n "CN=TempCA" -r -sv TempCA.pvk TempCA.cer  
    ```  
  
     <span data-ttu-id="9348c-128">암호를 제공하여 개인 키를 보호하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-128">You will be prompted to provide a password to protect the private key.</span></span> <span data-ttu-id="9348c-129">이 암호는 이 루트 인증서로 서명된 인증서를 만들 때 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-129">This password is required when creating a certificate signed by this root certificate.</span></span>  
  
### <a name="to-create-a-new-certificate-signed-by-a-root-authority-certificate"></a><span data-ttu-id="9348c-130">루트 인증 기관 인증서로 서명된 새 인증서를 만들려면</span><span class="sxs-lookup"><span data-stu-id="9348c-130">To create a new certificate signed by a root authority certificate</span></span>  
  
1.  <span data-ttu-id="9348c-131">MakeCert.exe 도구에 다음 스위치를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-131">Use the MakeCert.exe tool with the following switches:</span></span>  
  
    1.  <span data-ttu-id="9348c-132">`-sk` `subjectKey`.</span><span class="sxs-lookup"><span data-stu-id="9348c-132">`-sk` `subjectKey`.</span></span> <span data-ttu-id="9348c-133">개인 키가 들어 있는 주체의 키 컨테이너 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-133">The location of the subject's key container that holds the private key.</span></span> <span data-ttu-id="9348c-134">키 컨테이너가 없으면 키 컨테이너가 새로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-134">If a key container does not exist, one is created.</span></span> <span data-ttu-id="9348c-135">-sk 또는 -sv 옵션을 사용하지 않으면 기본적으로 JoeSoft라는 키 컨테이너가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-135">If neither of the -sk or -sv options is used, a key container called JoeSoft is created by default.</span></span>  
  
    2.  <span data-ttu-id="9348c-136">`-n` `subjectName`.</span><span class="sxs-lookup"><span data-stu-id="9348c-136">`-n` `subjectName`.</span></span> <span data-ttu-id="9348c-137">주체 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-137">Specifies the subject name.</span></span> <span data-ttu-id="9348c-138">규칙에 따라 주체 이름 앞에 "일반 이름"을 나타내는 "CN = "을 붙입니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-138">The convention is to prefix the subject name with "CN = " for "Common Name".</span></span>  
  
    3.  <span data-ttu-id="9348c-139">`-iv` `issuerKeyFile`.</span><span class="sxs-lookup"><span data-stu-id="9348c-139">`-iv` `issuerKeyFile`.</span></span> <span data-ttu-id="9348c-140">발급자의 개인 키 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-140">Specifies the issuer's private key file.</span></span>  
  
    4.  <span data-ttu-id="9348c-141">`-ic` `issuerCertFile`.</span><span class="sxs-lookup"><span data-stu-id="9348c-141">`-ic` `issuerCertFile`.</span></span> <span data-ttu-id="9348c-142">발급자의 인증서 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-142">Specifies the location of the issuer's certificate.</span></span>  
  
     <span data-ttu-id="9348c-143">예를 들어 다음 명령은 발급자의 개인 키를 사용하여 주체 이름이 `TempCA` 이고 `"CN=SignedByCA"` 루트 인증 기관 인증서로 서명된 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-143">For example, the following command creates a certificate signed by the `TempCA` root authority certificate with a subject name of `"CN=SignedByCA"` using the private key of the issuer.</span></span>  
  
    ```  
    makecert -sk SignedByCA -iv TempCA.pvk -n "CN=SignedByCA" -ic TempCA.cer SignedByCA.cer -sr currentuser -ss My  
    ```  
  
## <a name="installing-a-certificate-in-the-trusted-root-certification-authorities-store"></a><span data-ttu-id="9348c-144">신뢰할 수 있는 루트 인증 기관 저장소에 인증서 설치</span><span class="sxs-lookup"><span data-stu-id="9348c-144">Installing a Certificate in the Trusted Root Certification Authorities Store</span></span>  
 <span data-ttu-id="9348c-145">자체 서명된 인증서를 만들면 신뢰할 수 있는 루트 인증 기관 저장소에 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-145">Once a self-signed certificate is created, you can install it in the Trusted Root Certification Authorities store.</span></span> <span data-ttu-id="9348c-146">이때 인증서로 서명된 모든 인증서는 컴퓨터에 의해 신뢰됩니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-146">Any certificates that are signed with the certificate at this point are trusted by the computer.</span></span> <span data-ttu-id="9348c-147">따라서 인증서가 더 이상 필요하지 않으면 즉시 저장소에서 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-147">For this reason, delete the certificate from the store as soon as you no longer need it.</span></span> <span data-ttu-id="9348c-148">이 루트 인증 기관 인증서를 삭제하면 해당 인증서로 서명된 다른 모든 인증서의 권한이 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-148">When you delete this root authority certificate, all other certificates that signed with it become unauthorized.</span></span> <span data-ttu-id="9348c-149">루트 인증 기관 인증서는 단순히 필요에 따라 인증서 그룹의 범위를 지정할 수 있는 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-149">Root authority certificates are simply a mechanism whereby a group of certificates can be scoped as necessary.</span></span> <span data-ttu-id="9348c-150">예를 들어 피어 투 피어 응용 프로그램에서는 일반적으로 제공된 인증서로 개인의 ID를 신뢰하므로 루트 인증 기관이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-150">For example, in peer-to-peer applications, there is typically no need for a root authority because you simply trust the identity of an individual by its supplied certificate.</span></span>  
  
#### <a name="to-install-a-self-signed-certificate-in-the-trusted-root-certification-authorities"></a><span data-ttu-id="9348c-151">신뢰할 수 있는 루트 인증 기관에 자체 서명된 인증서를 설치하려면</span><span class="sxs-lookup"><span data-stu-id="9348c-151">To install a self-signed certificate in the Trusted Root Certification Authorities</span></span>  
  
1.  <span data-ttu-id="9348c-152">인증서 스냅인을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-152">Open the certificate snap-in.</span></span> <span data-ttu-id="9348c-153">자세한 내용은 참조 [하는 방법: MMC 스냅인을 사용 하 여 보기 인증서](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-153">For more information, see [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>  
  
2.  <span data-ttu-id="9348c-154">인증서를 저장할 폴더( **로컬 컴퓨터** 또는 **현재 사용자**)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-154">Open the folder to store the certificate, either the **Local Computer** or the **Current User**.</span></span>  
  
3.  <span data-ttu-id="9348c-155">**신뢰할 수 있는 루트 인증 기관** 폴더를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-155">Open the **Trusted Root Certification Authorities** folder.</span></span>  
  
4.  <span data-ttu-id="9348c-156">**인증서** 폴더를 마우스 오른쪽 단추로 클릭하고 **모든 작업**을 클릭한 다음 **가져오기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-156">Right-click the **Certificates** folder and click **All Tasks**, then click **Import**.</span></span>  
  
5.  <span data-ttu-id="9348c-157">화면에 표시되는 마법사 지침에 따라 TempCa.cer를 저장소로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-157">Follow the on-screen wizard instructions to import the TempCa.cer into the store.</span></span>  
  
## <a name="using-certificates-with-wcf"></a><span data-ttu-id="9348c-158">WCF에서 인증서 사용</span><span class="sxs-lookup"><span data-stu-id="9348c-158">Using Certificates With WCF</span></span>  
 <span data-ttu-id="9348c-159">임시 인증서를 설정했으면 클라이언트 자격 증명 형식으로 인증서를 지정하는 WCF 솔루션을 이 인증서를 사용하여 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-159">Once you have set up the temporary certificates, you can use them to develop WCF solutions that specify certificates as a client credential type.</span></span> <span data-ttu-id="9348c-160">예를 들어 다음 XML 구성에서는 메시지 보안과 인증서를 클라이언트 자격 증명 형식으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-160">For example, the following XML configuration specifies message security and a certificate as the client credential type.</span></span>  
  
#### <a name="to-specify-a-certificate-as-the-client-credential-type"></a><span data-ttu-id="9348c-161">인증서를 클라이언트 자격 증명 형식으로 지정하려면</span><span class="sxs-lookup"><span data-stu-id="9348c-161">To specify a certificate as the client credential type</span></span>  
  
-   <span data-ttu-id="9348c-162">서비스의 구성 파일에서 다음 XML을 사용하여 보안 모드를 메시지로 설정하고 클라이언트 자격 증명 형식을 인증서로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-162">In the configuration file for a service, use the following XML to set the security mode to message, and the client credential type to certificate.</span></span>  
  
    ```xml  
    <bindings>       
      <wsHttpBinding>  
        <binding name="CertificateForClient">  
          <security>  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    ```  
  
 <span data-ttu-id="9348c-163">인증서는 사용자의 저장소에서 찾을 수 이며 SubjectName 필드에서 "CohoWinery" 값을 검색 하 여 찾을 수를 지정 하는 클라이언트에 대 한 구성 파일에 다음 XML을 사용</span><span class="sxs-lookup"><span data-stu-id="9348c-163">In the configuration file for a client, use the following XML to specify that the certificate is found in the user’s store, and can be found by searching the SubjectName field for the value "CohoWinery."</span></span>  
  
```xml  
<behaviors>  
  <endpointBehaviors>  
    <behavior name="CertForClient">  
      <clientCredentials>  
        <clientCertificate findValue="CohoWinery" x509FindType="FindBySubjectName" />  
       </clientCredentials>  
     </behavior>  
   </endpointBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="9348c-164">WCF에서의 인증서 사용에 대한 자세한 내용은 [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9348c-164">For more information about using certificates in WCF, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="9348c-165">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="9348c-165">.NET Framework Security</span></span>  
 <span data-ttu-id="9348c-166">인증서를 마우스 오른쪽 단추로 클릭한 다음 **삭제** 를 클릭하여 **신뢰할 수 있는 루트 인증 기관** 및 **개인**폴더에서 임시 루트 인증 기관 인증서를 모두 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="9348c-166">Be sure to delete any temporary root authority certificates from the **Trusted Root Certification Authorities** and **Personal** folders by right-clicking the certificate, then clicking **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9348c-167">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9348c-167">See Also</span></span>  
 [<span data-ttu-id="9348c-168">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="9348c-168">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="9348c-169">방법: MMC 스냅인을 사용하여 인증서 보기</span><span class="sxs-lookup"><span data-stu-id="9348c-169">How to: View Certificates with the MMC Snap-in</span></span>](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)  
 [<span data-ttu-id="9348c-170">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="9348c-170">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
