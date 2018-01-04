---
title: Client Validation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0c1f805-1a81-4d0d-a112-bf5e2e87a631
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f187e6fb64fd3bbf08b3d0b92917ffc640b02186
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="client-validation"></a><span data-ttu-id="3051d-102">Client Validation</span><span class="sxs-lookup"><span data-stu-id="3051d-102">Client Validation</span></span>
<span data-ttu-id="3051d-103">서비스는 메타데이터를 자주 게시하여 클라이언트 프록시 형식의 자동 생성 및 구성을 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-103">Services frequently publish metadata to enable automatic generation and configuration of client proxy types.</span></span> <span data-ttu-id="3051d-104">서비스를 신뢰할 수 없으면 클라이언트 응용 프로그램에서 메타데이터가 보안, 트랜잭션, 서비스 계약 형식 등에 대한 클라이언트 응용 프로그램의 정책을 준수하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-104">When the service is not trusted, client applications should validate that the metadata conforms to the client application's policy regarding security, transactions, the type of service contract and so on.</span></span> <span data-ttu-id="3051d-105">다음 샘플에서는 서비스 끝점을 안전하게 사용할 수 있도록 서비스 끝점의 유효성을 검사하는 클라이언트 끝점 동작 기록 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-105">The following sample demonstrates how to write a client endpoint behavior that validates the service endpoint to ensure that service endpoint is safe to use.</span></span>  
  
 <span data-ttu-id="3051d-106">서비스는 네 개의 서비스 끝점을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-106">The service exposes four service endpoints.</span></span> <span data-ttu-id="3051d-107">첫 번째 끝점은 WSDualHttpBinding을, 두 번째 끝점은 NTLM 인증을, 세 번째 끝점은 트랜잭션 흐름을, 네 번째 끝점은 인증서 기반 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-107">The first endpoint uses the WSDualHttpBinding, the second endpoint uses NTLM authentication, the third endpoint enables transaction flow, and the fourth endpoint uses certificate-based authentication.</span></span>  
  
 <span data-ttu-id="3051d-108">클라이언트는 <xref:System.ServiceModel.Description.MetadataResolver> 클래스를 사용하여 서비스에 대한 메타데이터를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-108">The client uses the <xref:System.ServiceModel.Description.MetadataResolver> class to retrieve the metadata for the service.</span></span> <span data-ttu-id="3051d-109">클라이언트에서는 이중 바인딩 방지, NTLM 인증 및 유효성 검사 동작을 사용하는 트랜잭션 흐름에 대한 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-109">The client enforces a policy of prohibiting duplex bindings, NTLM authentication, and transaction flow using a validating behavior.</span></span> <span data-ttu-id="3051d-110">클라이언트 응용 프로그램은 서비스의 메타데이터에서 가져온 각 <xref:System.ServiceModel.Description.ServiceEndpoint> 인스턴스에 대해 `InternetClientValidatorBehavior` 끝점 동작의 인스턴스를 <xref:System.ServiceModel.Description.ServiceEndpoint>에 추가한 다음 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 클라이언트를 사용하여 끝점에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-110">For each <xref:System.ServiceModel.Description.ServiceEndpoint> instance imported from the service's metadata, the client application adds an instance of the `InternetClientValidatorBehavior` endpoint behavior to the <xref:System.ServiceModel.Description.ServiceEndpoint> before attempting to use a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client to connect to the endpoint.</span></span> <span data-ttu-id="3051d-111">동작의 `Validate` 메서드는 서비스의 작업이 호출되기 전에 실행되고 `InvalidOperationExceptions`를 throw하여 클라이언트의 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-111">The behavior's `Validate` method runs before any operations on the service are called and enforces the client's policy by throwing `InvalidOperationExceptions`.</span></span>  
  
### <a name="to-build-the-sample"></a><span data-ttu-id="3051d-112">이 샘플을 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="3051d-112">To build the sample</span></span>  
  
1.  <span data-ttu-id="3051d-113">지침에 따라 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-113">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="3051d-114">단일 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="3051d-114">To run the sample on the same computer</span></span>  
  
1.  <span data-ttu-id="3051d-115">관리자 권한으로 Visual Studio 명령 프롬프트를 열고 샘플 설치 폴더의 Setup.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-115">Open a Visual Studio command prompt with administrator privileges and run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="3051d-116">이 작업은 샘플 실행에 필요한 모든 인증서를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-116">This installs all the certificates required for running the sample.</span></span>  
  
2.  <span data-ttu-id="3051d-117">\service\bin\Debug에서 서비스 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-117">Run the service application from \service\bin\Debug.</span></span>  
  
3.  <span data-ttu-id="3051d-118">\client\bin\Debug에서 클라이언트 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-118">Run the client application from \client\bin\Debug.</span></span> <span data-ttu-id="3051d-119">클라이언트 콘솔 응용 프로그램에 클라이언트 동작이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-119">Client activity is displayed on the client console application.</span></span>  
  
4.  <span data-ttu-id="3051d-120">클라이언트와 서비스가 통신할 수 없는 경우 [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3051d-120">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
5.  <span data-ttu-id="3051d-121">샘플 사용을 마치면 Cleanup.bat를 실행하여 인증서를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-121">Remove the certificates by running Cleanup.bat when you have finished with the sample.</span></span> <span data-ttu-id="3051d-122">다른 보안 샘플에도 동일한 인증서가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-122">Other security samples use the same certificates.</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="3051d-123">다중 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="3051d-123">To run the sample across computers</span></span>  
  
1.  <span data-ttu-id="3051d-124">서버에서 관리자 권한으로 실행 되는 Visual Studio 명령 프롬프트에 입력 `setup.bat service`합니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-124">On the server, in a Visual Studio command prompt run with administrator privileges, type `setup.bat service`.</span></span> <span data-ttu-id="3051d-125">실행 `setup.bat` 와 `service` 인수는 컴퓨터의 정규화 된 도메인 이름으로 서비스 인증서를 만들고 되어 Service.cer 이라는 파일로 서비스 인증서를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-125">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
2.  <span data-ttu-id="3051d-126">서버에서 새 인증서 이름을 반영하도록 App.config를 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-126">On the server, edit App.config to reflect the new certificate name.</span></span> <span data-ttu-id="3051d-127">즉, 변경 된 `findValue` 특성에 [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) 요소는 컴퓨터의 정규화 된 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-127">That is, change the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) element to the fully-qualified domain name of the computer.</span></span>  
  
3.  <span data-ttu-id="3051d-128">서비스 디렉터리에서 클라이언트 컴퓨터의 클라이언트 디렉터리로 Service.cer 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-128">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
4.  <span data-ttu-id="3051d-129">클라이언트에서 관리자 권한 및 형식으로 Visual Studio 명령 프롬프트를 열고 `setup.bat client`합니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-129">On the client, open a Visual Studio command prompt with administrator privileges, and type `setup.bat client`.</span></span> <span data-ttu-id="3051d-130">실행 `setup.bat` 와 `client` 인수 Client.com 이라는 클라이언트 인증서를 만들고 클라이언트 인증서 Client.cer 이라는 파일로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-130">Running `setup.bat` with the `client` argument creates a client certificate named Client.com and exports the client certificate to a file named Client.cer.</span></span>  
  
5.  <span data-ttu-id="3051d-131">client.cs 파일에서 MEX 끝점의 주소 값과 `findValue`를 변경하여 서비스의 새 주소와 일치하도록 기본 서버 인증서를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-131">In the client.cs file change the address value of the MEX endpoint and the `findValue` for setting the default server certificate to match the new address of your service.</span></span> <span data-ttu-id="3051d-132">이 작업을 수행하려면 localhost를 서버의 정규화된 도메인 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-132">You do this by replacing localhost with the fully-qualified domain name of the server.</span></span> <span data-ttu-id="3051d-133">다시 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-133">Rebuild.</span></span>  
  
6.  <span data-ttu-id="3051d-134">클라이언트 디렉터리에서 서버의 서비스 디렉터리로 Client.cer 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-134">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>  
  
7.  <span data-ttu-id="3051d-135">클라이언트에서 관리자 권한으로 Visual Studio 명령 프롬프트를 열고 ImportServiceCert.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-135">On the client, run ImportServiceCert.bat in a Visual Studio command prompt opened with administrator privileges.</span></span> <span data-ttu-id="3051d-136">이 작업은 Service.cer 파일의 서비스 인증서를 CurrentUser - TrustedPeople 저장소로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-136">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
8.  <span data-ttu-id="3051d-137">서버에서 관리자 권한으로 Visual Studio 명령 프롬프트를 열고 ImportClientCert.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-137">On the server, run ImportClientCert.bat in a Visual Studio command prompt opened with administrator privileges.</span></span> <span data-ttu-id="3051d-138">이 작업은 Client.cer 파일의 클라이언트 인증서를 LocalMachine - TrustedPeople 저장소로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-138">This imports the client certificate from the Client.cer file into the LocalMachine - TrustedPeople store.</span></span>  
  
9. <span data-ttu-id="3051d-139">서비스 컴퓨터에서 Visual Studio로 서비스 프로젝트를 빌드하고 service.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-139">On the service computer, build the service project in Visual Studio and run service.exe.</span></span>  
  
10. <span data-ttu-id="3051d-140">클라이언트 컴퓨터에서 client.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-140">On the client computer, run client.exe.</span></span>  
  
    1.  <span data-ttu-id="3051d-141">클라이언트와 서비스가 통신할 수 없는 경우 [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3051d-141">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="3051d-142">샘플 실행 후 정리를 수행하려면</span><span class="sxs-lookup"><span data-stu-id="3051d-142">To clean up after the sample</span></span>  
  
-   <span data-ttu-id="3051d-143">샘플 실행을 완료했으면 샘플 폴더에서 Cleanup.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-143">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3051d-144">다중 컴퓨터 구성에서 이 샘플을 실행할 경우에는 이 스크립트로 클라이언트의 서비스 인증서를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-144">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="3051d-145">다중 컴퓨터 구성의 인증서를 사용하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 샘플을 실행한 경우 CurrentUser - TrustedPeople 저장소에 설치된 서비스 인증서를 지워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-145">If you have run [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="3051d-146">이렇게 하려면 `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>. For example: certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com` 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3051d-146">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>. For example: certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3051d-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3051d-147">See Also</span></span>  
 [<span data-ttu-id="3051d-148">메타데이터 사용</span><span class="sxs-lookup"><span data-stu-id="3051d-148">Using Metadata</span></span>](../../../../docs/framework/wcf/feature-details/using-metadata.md)
