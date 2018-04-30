---
title: '방법: WCF에서 X.509 인증서에 액세스할 수 있도록 설정'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- X.509 certificates [WCF]
- certificates [WCF], making X.509 certificates accessible to WCF
- X.509 certificates [WCF], making accessible to WCF
ms.assetid: a54e407c-c2b5-4319-a648-60e43413664b
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 77ee21074b6f1bb5a2f5bd4ee653100d3534075d
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-make-x509-certificates-accessible-to-wcf"></a><span data-ttu-id="507cb-102">방법: WCF에서 X.509 인증서에 액세스할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="507cb-102">How to: Make X.509 Certificates Accessible to WCF</span></span>
<span data-ttu-id="507cb-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서 X.509 인증서에 액세스할 수 있게 만들려면 응용 프로그램 코드에서 인증서 저장소 이름과 위치를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="507cb-103">To make an X.509 certificate accessible to [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], application code must specify the certificate store name and location.</span></span> <span data-ttu-id="507cb-104">상황에 따라, X.509 인증서와 연결된 개인 키를 포함하는 파일에 대한 액세스가 프로세스 ID에 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="507cb-104">In certain circumstances, the process identity must have access to the file that contains the private key associated with the X.509 certificate.</span></span> <span data-ttu-id="507cb-105">인증서 저장소에서 X.509 인증서와 연결된 개인 키를 가져오려면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에 해당 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="507cb-105">To obtain the private key associated with an X.509 certificate in a certificate store, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] must have permission to do so.</span></span> <span data-ttu-id="507cb-106">기본적으로 소유자와 시스템 계정에서만 인증서의 개인 키에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="507cb-106">By default, only the owner and the System account can access the private key of a certificate.</span></span>  
  
### <a name="to-make-x509-certificates-accessible-to-wcf"></a><span data-ttu-id="507cb-107">WCF에서 X.509 인증서에 액세스할 수 있도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="507cb-107">To make X.509 certificates accessible to WCF</span></span>  
  
1.  <span data-ttu-id="507cb-108">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 실행 중인 계정에 X.509 인증서와 연결된 개인 키를 포함하는 파일에 대한 읽기 액세스 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="507cb-108">Give the account under which [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is running read access to the file that contains the private key associated with the X.509 certificate.</span></span>  
  
    1.  <span data-ttu-id="507cb-109">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에 X.509 인증서의 개인 키에 대한 읽기 액세스 권한이 필요한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="507cb-109">Determine whether [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requires read access to the private key for the X.509 certificate.</span></span>  
  
         <span data-ttu-id="507cb-110">다음 표에는 X.509 인증서를 사용하는 경우 개인 키를 사용할 수 있어야 하는지 여부가 자세히 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="507cb-110">The following table details whether a private key must be available when using an X.509 certificate.</span></span>  
  
        |<span data-ttu-id="507cb-111">X.509 인증서 사용</span><span class="sxs-lookup"><span data-stu-id="507cb-111">X.509 certificate use</span></span>|<span data-ttu-id="507cb-112">개인 키</span><span class="sxs-lookup"><span data-stu-id="507cb-112">Private key</span></span>|  
        |---------------------------|-----------------|  
        |<span data-ttu-id="507cb-113">아웃바운드 SOAP 메시지 디지털 서명.</span><span class="sxs-lookup"><span data-stu-id="507cb-113">Digitally signing an outbound SOAP message.</span></span>|<span data-ttu-id="507cb-114">예</span><span class="sxs-lookup"><span data-stu-id="507cb-114">Yes</span></span>|  
        |<span data-ttu-id="507cb-115">인바운드 SOAP 메시지 서명 확인.</span><span class="sxs-lookup"><span data-stu-id="507cb-115">Verifying the signature of an inbound SOAP message.</span></span>|<span data-ttu-id="507cb-116">아니요</span><span class="sxs-lookup"><span data-stu-id="507cb-116">No</span></span>|  
        |<span data-ttu-id="507cb-117">아웃바운드 SOAP 메시지 암호화.</span><span class="sxs-lookup"><span data-stu-id="507cb-117">Encrypting an outbound SOAP message.</span></span>|<span data-ttu-id="507cb-118">아니요</span><span class="sxs-lookup"><span data-stu-id="507cb-118">No</span></span>|  
        |<span data-ttu-id="507cb-119">인바운드 SOAP 메시지 암호 해독.</span><span class="sxs-lookup"><span data-stu-id="507cb-119">Decrypting an inbound SOAP message.</span></span>|<span data-ttu-id="507cb-120">예</span><span class="sxs-lookup"><span data-stu-id="507cb-120">Yes</span></span>|  
  
    2.  <span data-ttu-id="507cb-121">인증서가 저장되는 인증서 저장소 위치와 이름을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="507cb-121">Determine the certificate store location and name in which the certificate is stored.</span></span>  
  
         <span data-ttu-id="507cb-122">인증서가 저장되는 인증서 저장소는 응용 프로그램 코드 또는 구성에 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="507cb-122">The certificate store in which the certificate is stored is specified either in application code or in configuration.</span></span> <span data-ttu-id="507cb-123">예를 들어, 다음 예에서는 인증서 위치를 이름이 `CurrentUser`인 `My` 인증서 저장소로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="507cb-123">For example, the following example specifies that the certificate is located in the `CurrentUser` certificate store named `My`.</span></span>  
  
         [!code-csharp[x509Accessible#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/x509accessible/cs/source.cs#1)]
         [!code-vb[x509Accessible#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/x509accessible/vb/source.vb#1)]  
  
    3.  <span data-ttu-id="507cb-124">사용 하 여 개인 키 인증서에 대 한 컴퓨터에 있는 위치 결정는 [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="507cb-124">Determine where the private key for the certificate is located on the computer by using the [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool.</span></span>  
  
         <span data-ttu-id="507cb-125">[FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) 도구에 필요한 인증서 저장소 이름, 인증서 저장소 위치 및 인증서를 고유 하 게 식별 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="507cb-125">The [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool requires the certificate store name, certificate store location, and something that uniquely identifies the certificate.</span></span> <span data-ttu-id="507cb-126">도구에서는 인증서의 제목 이름이나 지문을 고유 식별자로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="507cb-126">The tool accepts either the certificate's subject name or its thumbprint as a unique identifier.</span></span> <span data-ttu-id="507cb-127">인증서의 지문을 확인 하는 방법에 대 한 자세한 내용은 참조 [하는 방법: 인증서의 지문을 검색](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="507cb-127">For more information about how to determine the thumbprint for a certificate, see [How to: Retrieve the Thumbprint of a Certificate](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
         <span data-ttu-id="507cb-128">다음 코드 예제에서는 [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) 에서 인증서 개인 키의 위치를 확인 하는 도구는 `My` 에 저장할 `CurrentUser` 지문이 있는 `46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d`합니다.</span><span class="sxs-lookup"><span data-stu-id="507cb-128">The following code example uses the [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool to determine the location of the private key for a certificate in the `My` store in `CurrentUser` with a thumbprint of `46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d`.</span></span>  
  
        ```  
        findprivatekey.exe My CurrentUser -t "46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d" -a  
        ```  
  
    4.  <span data-ttu-id="507cb-129">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 실행하는 계정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="507cb-129">Determine the account that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is running under.</span></span>  
  
         <span data-ttu-id="507cb-130">다음 표에서는 지정된 시나리오의 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 실행하는 계정에 대해 자세히 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="507cb-130">The following table details the account under which [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is running for a given scenario.</span></span>  
  
        |<span data-ttu-id="507cb-131">시나리오</span><span class="sxs-lookup"><span data-stu-id="507cb-131">Scenario</span></span>|<span data-ttu-id="507cb-132">프로세스 ID</span><span class="sxs-lookup"><span data-stu-id="507cb-132">Process identity</span></span>|  
        |--------------|----------------------|  
        |<span data-ttu-id="507cb-133">클라이언트(콘솔 또는 WinForms 응용 프로그램).</span><span class="sxs-lookup"><span data-stu-id="507cb-133">Client (console or WinForms application).</span></span>|<span data-ttu-id="507cb-134">현재 로그인한 사용자.</span><span class="sxs-lookup"><span data-stu-id="507cb-134">Currently logged in user.</span></span>|  
        |<span data-ttu-id="507cb-135">자체 호스팅된 서비스.</span><span class="sxs-lookup"><span data-stu-id="507cb-135">Service that is self-hosted.</span></span>|<span data-ttu-id="507cb-136">현재 로그인한 사용자.</span><span class="sxs-lookup"><span data-stu-id="507cb-136">Currently logged in user.</span></span>|  
        |<span data-ttu-id="507cb-137">IIS 6.0([!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]) 또는 IIS 7.0([!INCLUDE[wv](../../../../includes/wv-md.md)])에서 호스팅되는 서비스.</span><span class="sxs-lookup"><span data-stu-id="507cb-137">Service that is hosted in IIS 6.0 ([!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]) or IIS 7.0 ([!INCLUDE[wv](../../../../includes/wv-md.md)]).</span></span>|<span data-ttu-id="507cb-138">NETWORK SERVICE</span><span class="sxs-lookup"><span data-stu-id="507cb-138">NETWORK SERVICE</span></span>|  
        |<span data-ttu-id="507cb-139">IIS 5.X([!INCLUDE[wxp](../../../../includes/wxp-md.md)])에서 호스팅되는 서비스.</span><span class="sxs-lookup"><span data-stu-id="507cb-139">Service that is hosted in IIS 5.X ([!INCLUDE[wxp](../../../../includes/wxp-md.md)]).</span></span>|<span data-ttu-id="507cb-140">Machine.config 파일의 `<processModel>` 요소로 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="507cb-140">Controlled by the `<processModel>` element in the Machine.config file.</span></span> <span data-ttu-id="507cb-141">기본 계정은 ASPNET입니다.</span><span class="sxs-lookup"><span data-stu-id="507cb-141">The default account is ASPNET.</span></span>|  
  
    5.  <span data-ttu-id="507cb-142">cacls.exe 등의 도구를 사용하여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 실행하는 계정에 개인 키를 포함하는 파일에 대한 읽기 액세스 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="507cb-142">Grant read access to the file that contains the private key to the account that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is running under, using a tool such as cacls.exe.</span></span>  
  
         <span data-ttu-id="507cb-143">다음 코드 예제에서는 지정된 파일의 ACL(액세스 제어 목록)을 편집(/E)하여 NETWORK SERVICE 계정에 파일에 대한 읽기(:R) 액세스 권한을 부여(/G)합니다.</span><span class="sxs-lookup"><span data-stu-id="507cb-143">The following code example edits (/E) the access control list (ACL) for the specified file to grant (/G) the NETWORK SERVICE account read (:R) access to the file.</span></span>  
  
        ```  
        cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R  
        ```  
  
## <a name="see-also"></a><span data-ttu-id="507cb-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="507cb-144">See Also</span></span>  
 [<span data-ttu-id="507cb-145">FindPrivateKey</span><span class="sxs-lookup"><span data-stu-id="507cb-145">FindPrivateKey</span></span>](../../../../docs/framework/wcf/samples/findprivatekey.md)  
 [<span data-ttu-id="507cb-146">방법: 인증서의 지문 검색</span><span class="sxs-lookup"><span data-stu-id="507cb-146">How to: Retrieve the Thumbprint of a Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)  
 [<span data-ttu-id="507cb-147">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="507cb-147">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
