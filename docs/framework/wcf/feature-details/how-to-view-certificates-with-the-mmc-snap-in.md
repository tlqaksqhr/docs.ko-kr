---
title: "방법: MMC 스냅인을 사용하여 인증서 보기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 582eaef518e10acb4c4c356226ce0be24d1b4c35
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a><span data-ttu-id="df0cd-102">방법: MMC 스냅인을 사용하여 인증서 보기</span><span class="sxs-lookup"><span data-stu-id="df0cd-102">How to: View Certificates with the MMC Snap-in</span></span>
<span data-ttu-id="df0cd-103">일반적인 자격 증명 형식은 X.509 인증서입니다.</span><span class="sxs-lookup"><span data-stu-id="df0cd-103">A common type of credential is the X.509 certificate.</span></span> <span data-ttu-id="df0cd-104">보안된 서비스 또는 클라이언트를 만들 때 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>과 같은 메서드를 사용하여 클라이언트 또는 서비스 자격 증명으로 사용할 인증서를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df0cd-104">When creating secure services or clients, you can specify a certificate be used as the client or service credential by using methods such as the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> method.</span></span> <span data-ttu-id="df0cd-105">메서드에는 인증서를 저장할 저장소 및 인증서를 검색할 때 사용할 값과 같은 여러 매개 변수가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="df0cd-105">The method requires various parameters, such as the store where the certificate is stored and a value to use when searching for the certificate.</span></span> <span data-ttu-id="df0cd-106">다음 절차에서는 적절한 인증서를 찾기 위해 컴퓨터에서 저장소를 검사하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="df0cd-106">The following procedure demonstrates how to examine the stores on a computer to find an appropriate certificate.</span></span> <span data-ttu-id="df0cd-107">인증서 지문의 찾을 예제를 보려면 [하는 방법: 인증서의 지문을 검색](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="df0cd-107">For an example of finding the certificate thumbprint, see [How to: Retrieve the Thumbprint of a Certificate](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
### <a name="to-view-certificates-in-the-mmc-snap-in"></a><span data-ttu-id="df0cd-108">MMC 스냅인에서 인증서를 보려면</span><span class="sxs-lookup"><span data-stu-id="df0cd-108">To view certificates in the MMC snap-in</span></span>  
  
1.  <span data-ttu-id="df0cd-109">명령 프롬프트 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="df0cd-109">Open a Command Prompt window.</span></span>  
  
2.  <span data-ttu-id="df0cd-110">형식 `mmc` ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="df0cd-110">Type `mmc` and press the ENTER key.</span></span> <span data-ttu-id="df0cd-111">로컬 컴퓨터 저장소에서 인증서를 보려면 관리자 역할이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df0cd-111">Note that to view certificates in the local machine store, you must be in the Administrator role.</span></span>  
  
3.  <span data-ttu-id="df0cd-112">에 **파일** 메뉴를 클릭 하 여 **스냅인 추가/제거**합니다.</span><span class="sxs-lookup"><span data-stu-id="df0cd-112">On the **File** menu, click **Add/Remove Snap In**.</span></span>  
  
4.  <span data-ttu-id="df0cd-113">**추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="df0cd-113">Click **Add**.</span></span>  
  
5.  <span data-ttu-id="df0cd-114">에 **독립 실행형 스냅인 추가** 대화 상자에서 **인증서**합니다.</span><span class="sxs-lookup"><span data-stu-id="df0cd-114">In the **Add Standalone Snap-in** dialog box, select **Certificates**.</span></span>  
  
6.  <span data-ttu-id="df0cd-115">**추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="df0cd-115">Click **Add**.</span></span>  
  
7.  <span data-ttu-id="df0cd-116">에 **인증서 스냅인** 대화 상자에서 **컴퓨터 계정** 클릭 **다음**합니다.</span><span class="sxs-lookup"><span data-stu-id="df0cd-116">In the **Certificates snap-in** dialog box, select **Computer account** and click **Next**.</span></span> <span data-ttu-id="df0cd-117">선택할 수 있습니다 **내 사용자 계정** 또는 **서비스 계정**합니다.</span><span class="sxs-lookup"><span data-stu-id="df0cd-117">Optionally, you can select **My User account** or **Service account**.</span></span> <span data-ttu-id="df0cd-118">컴퓨터의 관리자가 아닐 경우에는 본인의 사용자 계정에 대해서만 인증서를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df0cd-118">If you are not an administrator of the computer, you can manage certificates only for your user account.</span></span>  
  
8.  <span data-ttu-id="df0cd-119">에 **컴퓨터 선택** 대화 상자를 클릭 **마침**합니다.</span><span class="sxs-lookup"><span data-stu-id="df0cd-119">In the **Select Computer** dialog box, click **Finish**.</span></span>  
  
9. <span data-ttu-id="df0cd-120">에 **독립 실행형 스냅인 추가** 대화 상자를 클릭 **닫기**합니다.</span><span class="sxs-lookup"><span data-stu-id="df0cd-120">In the **Add Standalone Snap-in** dialog box, click **Close**.</span></span>  
  
10. <span data-ttu-id="df0cd-121">에 **스냅인 추가/제거** 대화 상자를 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="df0cd-121">On the **Add/Remove Snap-in** dialog box, click **OK**.</span></span>  
  
11. <span data-ttu-id="df0cd-122">에 **콘솔 루트** 창 클릭 **인증서 (로컬 컴퓨터)** 인증서를 보려면 컴퓨터에 대 한 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="df0cd-122">In the **Console Root** window, click **Certificates (Local Computer)** to view the certificate stores for the computer.</span></span>  
  
12. <span data-ttu-id="df0cd-123">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="df0cd-123">Optional.</span></span> <span data-ttu-id="df0cd-124">사용자 계정에 대한 인증서를 보려면 3 ~ 6단계를 반복하십시오.</span><span class="sxs-lookup"><span data-stu-id="df0cd-124">To view certificates for your account, repeat steps 3 to 6.</span></span> <span data-ttu-id="df0cd-125">선택 하는 대신 7 단계에서 **컴퓨터 계정**, 클릭 **내 사용자 계정** 8 ~ 10 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="df0cd-125">In step 7, instead of selecting **Computer account**, click **My User account** and repeat steps 8 to 10.</span></span>  
  
13. <span data-ttu-id="df0cd-126">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="df0cd-126">Optional.</span></span> <span data-ttu-id="df0cd-127">에 **파일** 메뉴를 클릭 하 여 **저장** 또는 **다른 이름으로 저장**합니다.</span><span class="sxs-lookup"><span data-stu-id="df0cd-127">On the **File** menu, click **Save** or **Save As**.</span></span> <span data-ttu-id="df0cd-128">나중에 다시 사용하기 위해 콘솔 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="df0cd-128">Save the console file for later reuse.</span></span>  
  
## <a name="viewing-certificates-with-internet-explorer"></a><span data-ttu-id="df0cd-129">Internet Explorer로 인증서 보기</span><span class="sxs-lookup"><span data-stu-id="df0cd-129">Viewing Certificates with Internet Explorer</span></span>  
 <span data-ttu-id="df0cd-130">Internet Explorer를 사용하여 인증서를 보고, 내보내고, 가져오고, 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df0cd-130">You can also view, export, import, and delete certificates by using Internet Explorer.</span></span>  
  
#### <a name="to-view-certificates-with-internet-explorer"></a><span data-ttu-id="df0cd-131">Internet Explorer로 인증서를 보려면</span><span class="sxs-lookup"><span data-stu-id="df0cd-131">To view certificates with Internet Explorer</span></span>  
  
1.  <span data-ttu-id="df0cd-132">Internet Explorer에서 클릭 **도구**, 클릭 **인터넷 옵션** 표시 하는 **인터넷 옵션** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="df0cd-132">In Internet Explorer, click **Tools**, then click **Internet Options** to display the **Internet Options** dialog box.</span></span>  
  
2.  <span data-ttu-id="df0cd-133">클릭는 **콘텐츠** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="df0cd-133">Click the **Content** tab.</span></span>  
  
3.  <span data-ttu-id="df0cd-134">아래 **인증서**, 클릭 **인증서**합니다.</span><span class="sxs-lookup"><span data-stu-id="df0cd-134">Under **Certificates**, click **Certificates**.</span></span>  
  
4.  <span data-ttu-id="df0cd-135">모든 인증서의 세부 정보를 보려면 인증서 선택 하 고 클릭을 **보기**합니다.</span><span class="sxs-lookup"><span data-stu-id="df0cd-135">To view details of any certificate, select the certificate and click **View**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df0cd-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="df0cd-136">See Also</span></span>  
 [<span data-ttu-id="df0cd-137">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="df0cd-137">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="df0cd-138">방법: 개발 중 사용할 임시 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="df0cd-138">How to: Create Temporary Certificates for Use During Development</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)  
 [<span data-ttu-id="df0cd-139">방법: 인증서의 지문 검색</span><span class="sxs-lookup"><span data-stu-id="df0cd-139">How to: Retrieve the Thumbprint of a Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)
