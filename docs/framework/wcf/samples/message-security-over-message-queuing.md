---
title: 메시지 큐에 대한 메시지 보안
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 329aea9c-fa80-45c0-b2b9-e37fd7b85b38
caps.latest.revision: 22
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: aeb0e66c5bad2b2d03a08560e1021b57e793ad55
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="message-security-over-message-queuing"></a><span data-ttu-id="c12b0-102">메시지 큐에 대한 메시지 보안</span><span class="sxs-lookup"><span data-stu-id="c12b0-102">Message Security over Message Queuing</span></span>
<span data-ttu-id="c12b0-103">이 샘플에서는 클라이언트에 대해 X.509v3 인증서를 통한 WS-Security 인증을 사용하며 MSMQ를 통해 서버의 X.509v3 인증서를 사용한 서버 인증을 수행해야 하는 응용 프로그램의 구현 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-103">This sample demonstrates how to implement an application that uses WS-Security with X.509v3 certificate authentication for the client and requires server authentication using the server's X.509v3 certificate over MSMQ.</span></span> <span data-ttu-id="c12b0-104">메시지 보안에서는 MSMQ 저장소에 있는 메시지의 암호화가 유지되며 응용 프로그램에서 메시지의 자체 인증을 수행할 수 있도록 하는 것이 더 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-104">Message security is sometimes more desirable to ensure that the messages in the MSMQ store stay encrypted and the application can perform its own authentication of the message.</span></span>  
  
 <span data-ttu-id="c12b0-105">이 샘플에 따라는 [트랜잭션 된 MSMQ 바인딩](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="c12b0-105">This sample is based on the [Transacted MSMQ Binding](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md) sample.</span></span> <span data-ttu-id="c12b0-106">메시지가 암호화되고 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-106">The messages are encrypted and signed.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c12b0-107">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="c12b0-107">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="c12b0-108">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-108">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="c12b0-109">서비스가 처음 실행되는 경우 서비스에서는 큐가 있는지 확인하고</span><span class="sxs-lookup"><span data-stu-id="c12b0-109">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="c12b0-110">큐가 없으면 큐를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-110">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="c12b0-111">서비스를 처음 실행하여 큐를 만들거나 MSMQ 큐 관리자를 통해 큐를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-111">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="c12b0-112">Windows 2008에서 큐를 만들려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="c12b0-112">Follow these steps to create a queue in Windows 2008.</span></span>  
  
    1.  <span data-ttu-id="c12b0-113">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 서버 관리자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-113">Open Server Manager in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
    2.  <span data-ttu-id="c12b0-114">확장 된 **기능** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-114">Expand the **Features** tab.</span></span>  
  
    3.  <span data-ttu-id="c12b0-115">마우스 오른쪽 단추로 클릭 **개인 메시지 큐**를 선택 하 고 **새로**, **개인 큐**합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-115">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>  
  
    4.  <span data-ttu-id="c12b0-116">확인 된 **트랜잭션** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-116">Check the **Transactional** box.</span></span>  
  
    5.  <span data-ttu-id="c12b0-117">입력 `ServiceModelSamplesTransacted` 새 큐의 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-117">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>  
  
3.  <span data-ttu-id="c12b0-118">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-118">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="c12b0-119">단일 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="c12b0-119">To run the sample on the same computer</span></span>  
  
1.  <span data-ttu-id="c12b0-120">Makecert.exe 및 FindPrivateKey.exe가 포함된 폴더가 경로에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-120">Ensure that the path includes the folder that contains Makecert.exe and FindPrivateKey.exe.</span></span>  
  
2.  <span data-ttu-id="c12b0-121">샘플 설치 폴더에서 Setup.bat를 실행하여</span><span class="sxs-lookup"><span data-stu-id="c12b0-121">Run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="c12b0-122">이 작업은 샘플 실행에 필요한 모든 인증서를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-122">This installs all the certificates required for running the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c12b0-123">샘플 사용을 마쳤으면 Cleanup.bat를 실행하여 인증서를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-123">Ensure that you remove the certificates by running Cleanup.bat when you have finished with the sample.</span></span> <span data-ttu-id="c12b0-124">다른 보안 샘플에도 동일한 인증서가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-124">Other security samples use the same certificates.</span></span>  
  
3.  <span data-ttu-id="c12b0-125">\service\bin에서 Service.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-125">Launch Service.exe from \service\bin.</span></span>  
  
4.  <span data-ttu-id="c12b0-126">\client\bin에서 Client.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-126">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="c12b0-127">클라이언트 콘솔 응용 프로그램에 클라이언트 동작이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-127">Client activity is displayed on the client console application.</span></span>  
  
5.  <span data-ttu-id="c12b0-128">클라이언트와 서비스가 통신할 수 없는 경우 참조 [문제 해결 팁](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-128">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="c12b0-129">다중 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="c12b0-129">To run the sample across computers</span></span>  
  
1.  <span data-ttu-id="c12b0-130">Setup.bat, Cleanup.bat 및 ImportClientCert.bat 파일을 서비스 컴퓨터에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-130">Copy the Setup.bat, Cleanup.bat, and ImportClientCert.bat files to the service computer.</span></span>  
  
2.  <span data-ttu-id="c12b0-131">클라이언트 컴퓨터에 클라이언트 이진 파일용 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-131">Create a directory on the client computer for the client binaries.</span></span>  
  
3.  <span data-ttu-id="c12b0-132">클라이언트 프로그램 파일을 클라이언트 컴퓨터의 클라이언트 디렉터리로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-132">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="c12b0-133">Setup.bat, Cleanup.bat 및 ImportServiceCert.bat 파일도 클라이언트로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-133">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
4.  <span data-ttu-id="c12b0-134">서버에서 `setup.bat service`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-134">On the server, run `setup.bat service`.</span></span> <span data-ttu-id="c12b0-135">실행 `setup.bat` 와 `service` 인수는 컴퓨터의 정규화 된 도메인 이름으로 서비스 인증서를 만들고 되어 Service.cer 이라는 파일로 서비스 인증서를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-135">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
5.  <span data-ttu-id="c12b0-136">새 인증서 이름을 반영 하도록 service.exe.config 서비스의 편집 (에 `findValue` 특성에 [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) 컴퓨터의 정규화 된 도메인 이름과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-136">Edit service's service.exe.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) which is the same as the fully-qualified domain name of the computer.</span></span>  
  
6.  <span data-ttu-id="c12b0-137">서비스 디렉터리에서 클라이언트 컴퓨터의 클라이언트 디렉터리로 Service.cer 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-137">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
7.  <span data-ttu-id="c12b0-138">클라이언트에서 `setup.bat client`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-138">On the client, run `setup.bat client`.</span></span> <span data-ttu-id="c12b0-139">`setup.bat` 인수를 사용하여 `client`를 실행하면 client.com이라는 클라이언트 인증서가 생성되어 Client.cer이라는 파일로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-139">Running `setup.bat` with the `client` argument creates a client certificate named client.com and exports the client certificate to a file named Client.cer.</span></span>  
  
8.  <span data-ttu-id="c12b0-140">클라이언트 컴퓨터의 Client.exe.config 파일에서 끝점의 주소 값을 서비스의 새 주소와 일치하도록 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-140">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="c12b0-141">이렇게 하려면 localhost를 서버의 정규화된 도메인 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-141">Do this by replacing localhost with the fully-qualified domain name of the server.</span></span>  <span data-ttu-id="c12b0-142">서비스의 인증서 이름도 서비스 컴퓨터의 정규화된 도메인 이름과 일치하게 변경해야 합니다(`findValue`에 있는 `defaultCertificate`의 `serviceCertificate` 요소에 있는 `clientCredentials` 특성).</span><span class="sxs-lookup"><span data-stu-id="c12b0-142">You must also change the certificate name of the service to be the same as the fully-qualified domain name of the service computer (in the `findValue` attribute in the `defaultCertificate` element of `serviceCertificate` under `clientCredentials`).</span></span>  
  
9. <span data-ttu-id="c12b0-143">클라이언트 디렉터리에서 서버의 서비스 디렉터리로 Client.cer 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-143">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>  
  
10. <span data-ttu-id="c12b0-144">클라이언트에서 `ImportServiceCert.bat`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-144">On the client, run `ImportServiceCert.bat`.</span></span> <span data-ttu-id="c12b0-145">이 작업은 Service.cer 파일의 서비스 인증서를 CurrentUser - TrustedPeople 저장소로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-145">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
11. <span data-ttu-id="c12b0-146">서버에서 `ImportClientCert.bat`를 실행하여 Client.cer 파일에서 LocalMachine - TrustedPeople 저장소로 클라이언트 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-146">On the server, run `ImportClientCert.bat`, This imports the client certificate from the Client.cer file into the LocalMachine - TrustedPeople store.</span></span>  
  
12. <span data-ttu-id="c12b0-147">서비스 컴퓨터의 명령 프롬프트에서 Service.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-147">On the service computer, launch Service.exe from the command prompt.</span></span>  
  
13. <span data-ttu-id="c12b0-148">클라이언트 컴퓨터의 명령 프롬프트에서 Client.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-148">On the client computer, launch Client.exe from the command prompt.</span></span> <span data-ttu-id="c12b0-149">클라이언트와 서비스가 통신할 수 없는 경우 참조 [문제 해결 팁](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-149">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="c12b0-150">샘플 실행 후 정리를 수행하려면</span><span class="sxs-lookup"><span data-stu-id="c12b0-150">To clean up after the sample</span></span>  
  
-   <span data-ttu-id="c12b0-151">샘플 실행을 완료했으면 샘플 폴더에서 Cleanup.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-151">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c12b0-152">다중 컴퓨터 구성에서 이 샘플을 실행할 경우에는 이 스크립트로 클라이언트의 서비스 인증서를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-152">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="c12b0-153">다중 컴퓨터 구성의 인증서를 사용하는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 샘플을 실행한 경우 CurrentUser - TrustedPeople 저장소에 설치된 서비스 인증서를 지워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-153">If you have run [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="c12b0-154">이를 수행하려면 `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` 명령을 사용합니다(예: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`).</span><span class="sxs-lookup"><span data-stu-id="c12b0-154">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c12b0-155">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c12b0-155">Requirements</span></span>  
 <span data-ttu-id="c12b0-156">이 샘플을 실행하려면 MSMQ가 설치되어 실행 중이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-156">This sample requires that MSMQ is installed and running.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="c12b0-157">세부 항목</span><span class="sxs-lookup"><span data-stu-id="c12b0-157">Demonstrates</span></span>  
 <span data-ttu-id="c12b0-158">클라이언트는 서비스의 공개 키를 사용하여 메시지를 암호화하고 자체 인증서로 메시지에 서명합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-158">The client encrypts the message using the public key of the service and signs the message using its own certificate.</span></span> <span data-ttu-id="c12b0-159">큐로부터 메시지를 읽는 서비스는 신뢰할 수 있는 사용자 저장소에 포함된 인증서를 사용하여 클라이언트 인증서를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-159">The service reading the message from the queue authenticates the client certificate with the certificate in its trusted people store.</span></span> <span data-ttu-id="c12b0-160">그리고 메시지를 해독한 후 서비스 작업에 디스패치합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-160">It then decrypts the message and dispatches the message to the service operation.</span></span>  
  
 <span data-ttu-id="c12b0-161">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 메시지가 MSMQ 메시지의 본문에 페이로드로 전달되기 때문에 본문은 MSMQ 저장소에 암호화된 상태로 남습니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-161">Because the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] message is carried as a payload in the body of the MSMQ message, the body remains encrypted in the MSMQ store.</span></span> <span data-ttu-id="c12b0-162">그러면 원치 않는 노출로부터 메시지를 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-162">This secures the message from unwanted disclosure of the message.</span></span> <span data-ttu-id="c12b0-163">MSMQ 자체에서는 전달하는 메시지의 암호화 여부를 인식하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-163">Note that MSMQ itself is not aware whether the message it is carrying is encrypted.</span></span>  
  
 <span data-ttu-id="c12b0-164">샘플에서는 MSMQ에서 메시지 수준의 상호 인증을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-164">The sample demonstrates how mutual authentication at the message level can be used with MSMQ.</span></span> <span data-ttu-id="c12b0-165">인증서는 out-of-band로 교환됩니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-165">The certificates are exchanged out-of-band.</span></span> <span data-ttu-id="c12b0-166">대기 중인 응용 프로그램의 경우에는 서비스와 클라이언트가 동시에 실행 중이어야 할 필요가 없기 때문에 항상 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-166">This is always the case with queued application because the service and the client do not have to be up and running at the same time.</span></span>  
  
## <a name="description"></a><span data-ttu-id="c12b0-167">설명</span><span class="sxs-lookup"><span data-stu-id="c12b0-167">Description</span></span>  
 <span data-ttu-id="c12b0-168">샘플 클라이언트 및 서비스 코드는 단계와 동일는 [트랜잭션 된 MSMQ 바인딩](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md) 한 가지 차이점 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-168">The sample client and service code are the same as the [Transacted MSMQ Binding](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md) sample with one difference.</span></span> <span data-ttu-id="c12b0-169">작업 계약에는 보호 수준에서 주석을 달아야 하기 때문에 메시지에 서명과 암호화가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-169">The operation contract is annotated with protection level, which suggests that the message must be signed and encrypted.</span></span>  

```csharp
// Define a service contract.   
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true, ProtectionLevel=ProtectionLevel.EncryptAndSign)]  
    void SubmitPurchaseOrder(PurchaseOrder po);  
}  
```

 <span data-ttu-id="c12b0-170">필수 토큰을 사용하여 서비스 및 클라이언트를 식별하는 방식으로 메시지를 보호할 수 있도록 App.config에는 자격 증명 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-170">To ensure that the message is secured using the required token to identify the service and client, the App.config contains credential information.</span></span>  
  
 <span data-ttu-id="c12b0-171">클라이언트 구성에서는 서비스를 인증할 서비스 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-171">The client configuration specifies the service certificate to authenticate the service.</span></span> <span data-ttu-id="c12b0-172">여기서는 LocalMachine 저장소를 서비스의 유효성에 의존하는 신뢰할 수 있는 저장소로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-172">It uses its LocalMachine store as the trusted store to rely on the validity of the service.</span></span> <span data-ttu-id="c12b0-173">여기서는 클라이언트의 서비스 인증을 위해 메시지와 함께 첨부되는 클라이언트 인증서도 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-173">It also specifies the client certificate that is attached with the message for service authentication of the client.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  
  <system.serviceModel>  
  
    <client>  
      <!-- Define NetMsmqEndpoint -->  
      <endpoint address="net.msmq://localhost/private/ServiceModelSamplesMessageSecurity"   
                binding="netMsmqBinding"   
                bindingConfiguration="messageSecurityBinding"  
                contract="Microsoft.ServiceModel.Samples.IOrderProcessor"  
                behaviorConfiguration="ClientCertificateBehavior" />  
    </client>  
  
    <bindings>  
        <netMsmqBinding>  
            <binding name="messageSecurityBinding">  
                <security mode="Message">  
                    <message clientCredentialType="Certificate"/>  
                </security>  
            </binding>  
        </netMsmqBinding>  
    </bindings>  
  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="ClientCertificateBehavior">  
          <!--   
        The clientCredentials behavior allows one to define a certificate to present to a service.  
        A certificate is used by a client to authenticate itself to the service and provide message integrity.  
        This configuration references the "client.com" certificate installed during the setup instructions.  
        -->  
          <clientCredentials>  
            <clientCertificate findValue="client.com" storeLocation="CurrentUser" storeName="My" x509FindType="FindBySubjectName" />  
            <serviceCertificate>  
                <defaultCertificate findValue="localhost" storeLocation="CurrentUser" storeName="TrustedPeople" x509FindType="FindBySubjectName"/>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it is trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certification authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust" />  
            </serviceCertificate>  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="c12b0-174">보안 모드는 Message로 설정되며 ClientCredentialType은 Certificate로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-174">Note that the security mode is set to Message and the ClientCredentialType is set to Certificate.</span></span>  
  
 <span data-ttu-id="c12b0-175">서비스 구성에는 클라이언트에서 서비스를 인증할 때 사용된 서비스의 자격 증명을 지정하는 서비스 동작이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-175">The service configuration includes a service behavior that specifies the service's credentials that are used when the client authenticates the service.</span></span> <span data-ttu-id="c12b0-176">서버 인증서 주체 이름에 지정 되는 `findValue` 특성에 [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-176">The server certificate subject name is specified in the `findValue` attribute in the [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md).</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  
  <appSettings>  
    <!-- Use appSetting to configure MSMQ queue name. -->  
    <add key="queueName" value=".\private$\ServiceModelSamplesMessageSecurity" />  
  </appSettings>  
  
  <system.serviceModel>  
    <services>  
      <service   
          name="Microsoft.ServiceModel.Samples.OrderProcessorService"  
          behaviorConfiguration="PurchaseOrderServiceBehavior">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
          </baseAddresses>  
        </host>  
        <!-- Define NetMsmqEndpoint -->  
        <endpoint address="net.msmq://localhost/private/ServiceModelSamplesMessageSecurity"  
                  binding="netMsmqBinding"  
                  bindingConfiguration="messageSecurityBinding"  
                  contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
        <!-- The mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex. -->  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
  
    <bindings>  
        <netMsmqBinding>  
            <binding name="messageSecurityBinding">  
                <security mode="Message">  
                    <message clientCredentialType="Certificate" />  
                </security>  
            </binding>  
        </netMsmqBinding>  
    </bindings>  
  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="PurchaseOrderServiceBehavior">  
          <serviceMetadata httpGetEnabled="True"/>  
          <!--   
               The serviceCredentials behavior allows one to define a service certificate.  
               A service certificate is used by the service to authenticate itself to its clients and to provide message protection.  
               This configuration references the "localhost" certificate installed during the setup instructions.  
          -->  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
            <clientCertificate>  
                <certificate findValue="client.com" storeLocation="LocalMachine" storeName="TrustedPeople" x509FindType="FindBySubjectName"/>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it is trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certification authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust" />  
            </clientCertificate>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
  
</configuration>  
```  
  
 <span data-ttu-id="c12b0-177">이 샘플에서는 다음 샘플 코드에서와 같이 구성을 이용하여 인증을 제어하는 방법과 보안 컨텍스트에서 호출자의 ID를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-177">The sample demonstrates controlling authentication using configuration, and how to obtain the caller’s identity from the security context, as shown in the following sample code:</span></span>  
  
```csharp
// Service class which implements the service contract.  
// Added code to write output to the console window.  
public class OrderProcessorService : IOrderProcessor  
{  
    private string GetCallerIdentity()  
    {  
        // The client certificate is not mapped to a Windows identity by default.  
        // ServiceSecurityContext.PrimaryIdentity is populated based on the information  
        // in the certificate that the client used to authenticate itself to the service.  
        return ServiceSecurityContext.Current.PrimaryIdentity.Name;  
    }  

    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
    public void SubmitPurchaseOrder(PurchaseOrder po)  
    {  
        Console.WriteLine("Client's Identity {0} ", GetCallerIdentity());  
        Orders.Add(po);  
        Console.WriteLine("Processing {0} ", po);  
    }  
  //…  
}  
```
  
 <span data-ttu-id="c12b0-178">서비스 코드를 실행하면 클라이언트 ID가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-178">When run, the service code displays the client identification.</span></span> <span data-ttu-id="c12b0-179">다음은 서비스 코드의 출력 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-179">The following is a sample output from the service code:</span></span>  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
  
Client's Identity CN=client.com; ECA6629A3C695D01832D77EEE836E04891DE9D3C  
Processing Purchase Order: 6536e097-da96-4773-9da3-77bab4345b5d  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Pending  
```  
  
## <a name="comments"></a><span data-ttu-id="c12b0-180">설명</span><span class="sxs-lookup"><span data-stu-id="c12b0-180">Comments</span></span>  
  
-   <span data-ttu-id="c12b0-181">클라이언트 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="c12b0-181">Creating the client certificate.</span></span>  
  
     <span data-ttu-id="c12b0-182">배치 파일의 다음 줄에서는 클라이언트 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-182">The following line in the batch file creates the client certificate.</span></span> <span data-ttu-id="c12b0-183">지정된 클라이언트 이름은 만든 인증서의 제목 이름에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-183">The client name specified is used in the subject name of the certificate created.</span></span> <span data-ttu-id="c12b0-184">인증서는 `My` 저장소 위치에 있는 `CurrentUser` 저장소에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-184">The certificate is stored in `My` store at the `CurrentUser` store location.</span></span>  
  
    ```bat
    echo ************  
    echo making client cert  
    echo ************  
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe  
    ```  
  
-   <span data-ttu-id="c12b0-185">서버의 신뢰할 수 있는 인증서 저장소에 클라이언트 인증서 설치.</span><span class="sxs-lookup"><span data-stu-id="c12b0-185">Installing the client certificate into server’s trusted certificate store.</span></span>  
  
     <span data-ttu-id="c12b0-186">배치 파일의 다음 줄에서는 서버에서 관련된 신뢰 여부를 결정할 수 있도록 서버의 TrustedPeople 저장소에 클라이언트 인증서를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-186">The following line in the batch file copies the client certificate into the server's TrustedPeople store so that the server can make the relevant trust or no-trust decisions.</span></span> <span data-ttu-id="c12b0-187">TrustedPeople 저장소에 설치된 인증서를 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스에서 신뢰하려면 클라이언트 인증서 유효성 검사 모드를 `PeerOrChainTrust` 또는 `PeerTrust` 값으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-187">For a certificate installed in the TrustedPeople store to be trusted by a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service, the client certificate validation mode must be set to `PeerOrChainTrust` or `PeerTrust` value.</span></span> <span data-ttu-id="c12b0-188">구성 파일을 사용하여 이런 작업을 수행하는 방법을 보려면 앞서 소개된 서비스 구성 샘플을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c12b0-188">See the previous service configuration sample to learn how this can be done using a configuration file.</span></span>  
  
    ```bat
    echo ************  
    echo copying client cert to server's LocalMachine store  
    echo ************  
    certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople  
    ```  
  
-   <span data-ttu-id="c12b0-189">서버 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="c12b0-189">Creating the server certificate.</span></span>  
  
     <span data-ttu-id="c12b0-190">Setup.bat 배치 파일에서 다음 줄은 사용할 서버 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-190">The following lines from the Setup.bat batch file create the server certificate to be used:</span></span>  
  
    ```bat  
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
     <span data-ttu-id="c12b0-191">%SERVER_NAME% 변수는 서버 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-191">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="c12b0-192">인증서는 LocalMachine 저장소에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-192">The certificate is stored in the LocalMachine store.</span></span> <span data-ttu-id="c12b0-193">서비스의 인수와 함께 설치 배치 파일을 실행할 경우 (예: `setup.bat service`) % SERVER_NAME %는 컴퓨터의 정규화 된 도메인 이름을 포함 합니다. 그렇지 않은 경우 기본적으로 localhost</span><span class="sxs-lookup"><span data-stu-id="c12b0-193">If the setup batch file is run with an argument of service (such as, `setup.bat service`) the %SERVER_NAME% contains the fully-qualified domain name of the computer.Otherwise it defaults to localhost</span></span>  
  
-   <span data-ttu-id="c12b0-194">클라이언트의 신뢰할 수 있는 인증서 저장소에 서버 인증서 설치</span><span class="sxs-lookup"><span data-stu-id="c12b0-194">Installing server certificate into the client’s trusted certificate store.</span></span>  
  
     <span data-ttu-id="c12b0-195">다음 줄은 클라이언트의 신뢰할 수 있는 사용자 저장소에 서버 인증서를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-195">The following line copies the server certificate into the client trusted people store.</span></span> <span data-ttu-id="c12b0-196">이 단계는 Makecert.exe에서 생성한 인증서를 클라이언트 컴퓨터에서 절대적으로 신뢰하지는 않기 때문에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-196">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="c12b0-197">Microsoft에서 발급한 인증서와 같이 클라이언트가 신뢰할 수 있는 루트 인증서를 기반으로 하는 인증서가 이미 있는 경우 클라이언트 인증서 저장소를 서버 인증서로 채우는 이 단계를 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-197">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>  
  
    ```  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="c12b0-198">미국 영어 버전이 아닌 Microsoft Windows 버전을 사용하는 경우 Setup.bat 파일을 편집하여 "NT AUTHORITY\NETWORK SERVICE" 계정 이름을 해당 국가별 계정 이름으로 바꿔야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-198">If you are using a non-U.S. English edition of Microsoft Windows you must edit the Setup.bat file and replace the "NT AUTHORITY\NETWORK SERVICE" account name with your regional equivalent.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c12b0-199">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-199">The samples may already be installed on your computer.</span></span> <span data-ttu-id="c12b0-200">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c12b0-200">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c12b0-201">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="c12b0-201">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c12b0-202">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c12b0-202">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\MessageSecurity`  
  
## <a name="see-also"></a><span data-ttu-id="c12b0-203">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c12b0-203">See Also</span></span>
