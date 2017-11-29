---
title: "인증에 대한 확장된 보호 ReadMe 샘플"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 80bf2e97-398d-4db5-9040-d96478a2ccab
caps.latest.revision: "3"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 3981a0d0c82b8bc35536a9afd702e753fcf07db5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="readme-for-extended-protection-authentication-sample"></a><span data-ttu-id="a2657-102">인증에 대한 확장된 보호 ReadMe 샘플</span><span class="sxs-lookup"><span data-stu-id="a2657-102">ReadMe for Extended Protection Authentication Sample</span></span>
<span data-ttu-id="a2657-103">확장 된 보호는 공격자 (에서 "man에서-들기")는 클라이언트의 자격 증명을 가로채 고 하는 클라이언트의 의도 된 서버에서 보안 리소스에 액세스 하는 데 사용 중간자 개입 (mitm 메시지) 공격 으로부터 보호 하려면 보안 이니셔티브입니다.</span><span class="sxs-lookup"><span data-stu-id="a2657-103">Extended Protection is a security initiative to protect against man-in-the-middle (MITM) attacks, in which an attacker (the "man-in-the-middle") intercepts a client’s credentials and uses them to access secure resources on the client’s intended server.</span></span>  
  
 <span data-ttu-id="a2657-104">자세한 내용은 참조 [인증 개요에 대 한 확장 된 보호](../../../../docs/framework/wcf/feature-details/extended-protection-for-authentication-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a2657-104">For more information, see [Extended Protection for Authentication Overview](../../../../docs/framework/wcf/feature-details/extended-protection-for-authentication-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2657-105">이 샘플은 IIS에서 호스팅하는 경우에만 작동하며,</span><span class="sxs-lookup"><span data-stu-id="a2657-105">This sample only works when hosted on IIS.</span></span> <span data-ttu-id="a2657-106">HTTPS를 지원하지 않는 Visual Studio 개발 서버에서는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a2657-106">It does not work on Visual Studio Development Server because that does not support HTTPS.</span></span>  
  
## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a2657-107">샘플 설치, 빌드 및 실행</span><span class="sxs-lookup"><span data-stu-id="a2657-107">To Set Up, Build, and Run the Sample</span></span>  
  
1.  <span data-ttu-id="a2657-108">컴퓨터의 프로그램 추가/제거 -> Windows 기능에서 IIS를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a2657-108">Install IIS on the machine from Add/Remove Programs -> Windows Features.</span></span>  
  
2.  <span data-ttu-id="a2657-109">Windows 기능: 인터넷 정보 서비스 -> World Wide Web 서비스 -> 보안 -> Windows 인증에서 Windows 인증을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2657-109">Turn on Windows Authentication in Windows features: Internet Information Services -> World Wide Web Services -> Security -> Windows Authentication.</span></span>  
  
3.  <span data-ttu-id="a2657-110">Windows 기능: Microsoft .NET Framework 3.5.1 -> Windows Communication Foundation HTTP 활성화에서 HTTP 활성화를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2657-110">Turn on HTTP Activation in Windows features: Microsoft .NET Framework 3.5.1 -> Windows Communication Foundation HTTP Activation.</span></span>  
  
4.  <span data-ttu-id="a2657-111">이 샘플을 사용하려면 클라이언트에서 서버와의 보안 채널을 설정해야 하므로, IIS(인터넷 정보 서비스) 관리자에서 설치할 수 있는 서버 인증서가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2657-111">This sample requires the client to establish a secure channel with the server and so it requires the presence of a server certificate which can be installed from Internet Information Services (IIS) Manager.</span></span>  
  
    1.  <span data-ttu-id="a2657-112">기능 보기 탭에서 IIS 관리자-> 서버 인증서를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a2657-112">Open the IIS manager -> Server certificates (from the feature view tab).</span></span>  
  
    2.  <span data-ttu-id="a2657-113">이 샘플을 테스트하기 위해 자체 서명된 인증서를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2657-113">For the purpose of testing this sample, you can create a self-signed certificate.</span></span> <span data-ttu-id="a2657-114">Internet Explorer에서 인증서가 안전하지 않다는 메시지가 표시되지 않도록 하려면 인증서를 신뢰할 수 있는 인증서 루트 인증 기관 저장소에 설치하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2657-114">(If you don’t want Internet Explorer to prompt you about the certificate not being secure, you can install it in the Trusted Certificate Root authority store).</span></span>  
  
5.  <span data-ttu-id="a2657-115">기본 웹 사이트의 작업 창으로 이동하여</span><span class="sxs-lookup"><span data-stu-id="a2657-115">Go to the Actions pane for the Default Web site.</span></span> <span data-ttu-id="a2657-116">사이트 편집 -> 바인딩을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a2657-116">Click Edit Site -> Bindings.</span></span> <span data-ttu-id="a2657-117">그런 다음 HTTPS 유형이 없으면 포트 번호 443으로 추가하고 위 단계에서 만든 SSL 인증서를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="a2657-117">Add HTTPS as a type if it is not already present, with port number 443, and assign the SSL certificate created in the above step.</span></span>  
  
6.  <span data-ttu-id="a2657-118">서비스를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="a2657-118">Build the service.</span></span> <span data-ttu-id="a2657-119">그러면 프로젝트 속성에 지정된 빌드 후 작업을 통해 IIS에 가상 디렉터리가 자동으로 만들어지며, 필요에 따라 웹에서 호스팅할 서비스에 대해 dll, .svc 및 config 파일이 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2657-119">This creates a virtual directory in IIS for you (from the post build action specified in the project properties) and copies the dll, .svc and config files as needed for a service to be Web hosted.</span></span>  
  
7.  <span data-ttu-id="a2657-120">IIS 관리자를 열고</span><span class="sxs-lookup"><span data-stu-id="a2657-120">Open the IIS Manager.</span></span> <span data-ttu-id="a2657-121">앞 단계에서 만든 가상 디렉터리(ExtendedProtection)를 마우스 오른쪽 단추로 클릭한 다음 응용 프로그램으로 변환을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2657-121">Right-click the virtual directory (ExtendedProtection) that you created in the previous step and select Convert to Application.</span></span>  
  
8.  <span data-ttu-id="a2657-122">IIS 관리자에서 이 가상 디렉터리에 대한 인증 모듈을 열고 Windows 인증을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2657-122">Open the Authentication module in IIS Manager for this virtual directory and enable Windows Authentication.</span></span>  
  
9. <span data-ttu-id="a2657-123">샘플에서는 해당 ExtendedProtection 설정이 항상으로 설정되므로, 이 가상 디렉터리에 대해 Windows 인증의 고급 설정을 열고 필수로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2657-123">Open the Advanced Settings for Windows Authentication for this virtual directory and set it to Required, since, in the sample, the corresponding ExtendedProtection setting is set to Always.</span></span>  
  
10. <span data-ttu-id="a2657-124">브라우저 창에서 URL에 액세스해 서비스를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2657-124">You can test the service by accessing the URL from a browser window.</span></span> <span data-ttu-id="a2657-125">다중 컴퓨터 구성에서 이 URL에 액세스하려면 들어오는 모든 HTTP 및 HTTPS 연결에 대해 방화벽이 열려 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="a2657-125">If you want to access this URL from a cross machine, make sure that the firewall is opened for all incoming HTTP and HTTPS connections.</span></span>  
  
11. <span data-ttu-id="a2657-126">에 대 한 전체 컴퓨터 이름을 제공 하 고 클라이언트 구성 파일을 열고는 \<클라이언트 >- \<끝점 >-address 특성 << full_machine_name >> 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2657-126">Open the client config file and provide a full machine name for the \<client> - \<endpoint> - address attribute, replacing <<full_machine_name>>.</span></span>  
  
12. <span data-ttu-id="a2657-127">클라이언트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a2657-127">Run the client.</span></span> <span data-ttu-id="a2657-128">클라이언트가 보안 채널을 설정하고 자동으로 확장된 보호를 사용하여 서비스와 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="a2657-128">The client communicates to the service by establishing a secure channel and using extended protection under the covers.</span></span>
