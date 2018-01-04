---
title: "Windows Communication Foundation 샘플 빌드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2899e7a5-9cb2-4e8d-b8d2-f31391549198
caps.latest.revision: "33"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d5de916aa5825625f29efe316571ad5085afb431
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="building-the-windows-communication-foundation-samples"></a><span data-ttu-id="4732e-102">Windows Communication Foundation 샘플 빌드</span><span class="sxs-lookup"><span data-stu-id="4732e-102">Building the Windows Communication Foundation Samples</span></span>
<span data-ttu-id="4732e-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 또는 Visual Studio 2010을 사용 하 여 예제를 빌드할 수 있습니다는 **msbuild** 명령줄에서 명령을 합니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-103">The [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] samples can be built using Visual Studio 2010 or using the **msbuild** command from the command line.</span></span> <span data-ttu-id="4732e-104">이 항목에서는 이 두 절차를 모두 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-104">Both procedures are described in this topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4732e-105">빌드 또는 중 하나를 실행 하기 전에 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 예제를 수행 했는지 확인는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-105">Before building or running any of the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] samples, ensure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
### <a name="to-build-the-sample-using-a-command-prompt"></a><span data-ttu-id="4732e-106">명령 프롬프트를 사용하여 샘플을 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="4732e-106">To build the sample using a command prompt</span></span>  
  
1.  <span data-ttu-id="4732e-107">관리자 권한으로 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 명령 프롬프트를 열고 샘플을 설치한 디렉터리 위치 아래의 언어별 하위 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-107">Open the [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] command prompt with administrator privileges and navigate to the language-specific subdirectory under the directory location where you installed the sample.</span></span>  
  
2.  <span data-ttu-id="4732e-108">형식 `msbuild` 명령줄에서.</span><span class="sxs-lookup"><span data-stu-id="4732e-108">Type `msbuild` at the command line.</span></span> <span data-ttu-id="4732e-109">클라이언트 프로그램 파일이 client\bin에 빌드되고 서비스 프로그램 파일이 service\bin에 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-109">The client program files are built to client\bin and the service program files are built to service\bin.</span></span> <span data-ttu-id="4732e-110">IIS(인터넷 정보 서비스)에서 서비스를 호스팅하는 경우에는 서비스 프로그램 파일이 servicemodelsamples 디렉터리와 \bin 하위 디렉터리에도 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-110">If the service is hosted by Internet Information Services (IIS), the service program files are also copied to the servicemodelsamples directory and its \bin subdirectory.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4732e-111">실행에 사용하는 계정에 수정 권한을 부여하도록 %systemdrive%\inetpub\wwwroot의 ACL을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-111">You must set the ACLs on %systemdrive%\inetpub\wwwroot to grant modify permissions to the account under which you are running.</span></span> <span data-ttu-id="4732e-112">그러지 않으면 일부 빌드 후 이벤트가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-112">Otherwise some post build events fail.</span></span> <span data-ttu-id="4732e-113">또는 ACL을 그대로 두고 관리자로 SDK 명령 프롬프트를 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-113">Alternatively, you can leave the ACLs as they are and run the SDK command prompt as administrator.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="4732e-114">Visual Studio를 사용하여 샘플을 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="4732e-114">To build the sample using Visual Studio</span></span>  
  
1.  <span data-ttu-id="4732e-115">[!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../../includes/lserver-md.md)], Windows 7 또는 Windows Server 2008 R2를 사용하고 있고 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]을 실행하는 경우에는 높은 권한으로 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-115">If you are using [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../../includes/lserver-md.md)], Windows 7, or Windows Server 2008 R2, and running [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], you must run [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] with elevated permission.</span></span> <span data-ttu-id="4732e-116">이렇게 하려면 시작 메뉴에 있는 아이콘을 마우스 오른쪽 단추로 클릭 하 고 클릭 **관리자 권한으로 실행**합니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-116">To do so, right-click the icon on the Start menu and then click **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="4732e-117">**파일** 메뉴 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], 클릭 **열려**, 클릭 **프로젝트/솔루션**합니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-117">From the **File** menu in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], click **Open**, then click **Project/Solution**.</span></span> <span data-ttu-id="4732e-118">샘플을 설치한 디렉터리 아래에 있는 언어별 하위 디렉터리로 이동한 다음 .sln 파일 아이콘을 두 번 클릭하여 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-118">Navigate to the language-specific subdirectory under the directory in which you installed the sample, and double-click the .sln file icon to open the solution in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span></span>  
  
3.  <span data-ttu-id="4732e-119">에 **빌드** 메뉴 선택 **솔루션 다시 빌드**합니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-119">In the **Build** menu, select **Rebuild Solution**.</span></span> <span data-ttu-id="4732e-120">클라이언트 프로그램 파일이 client\bin에 빌드되고 서비스 프로그램 파일이 service\bin에 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-120">The client program files are built to client\bin and the service program files are built to service\bin.</span></span> <span data-ttu-id="4732e-121">IIS에서 서비스를 호스팅하는 경우에는 서비스 프로그램 파일이 servicemodelsamples 디렉터리와 \bin 하위 디렉터리에도 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-121">If the service is hosted in IIS, the service program files are also copied to the servicemodelsamples directory and its \bin subdirectory.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4732e-122">실행에 사용하는 계정에 수정 권한을 부여하도록 %systemdrive%\inetpub\wwwroot의 ACL을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-122">You must set the ACLs on %systemdrive%\inetpub\wwwroot to grant modify permissions to the account under which you are running.</span></span> <span data-ttu-id="4732e-123">그러지 않으면 일부 빌드 후 이벤트가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-123">Otherwise some post build events fail.</span></span> <span data-ttu-id="4732e-124">또는 ACL을 그대로 두고 관리자로 SDK 명령 프롬프트 또는 Visual Studio를 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-124">Alternatively, you can leave the ACLs as they are and run the SDK command prompt or Visual Studio as administrator.</span></span> <span data-ttu-id="4732e-125">ASP.NET 작업자 프로세스에 디버거를 연결하는 등의 일부 Visual Studio 작업을 수행하는 데에도 관리자 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-125">Some Visual Studio actions (such as attaching a debugger to the ASP.Net worker process) also require administrative privileges.</span></span>  
  
## <a name="setup-batch-files-and-scripts"></a><span data-ttu-id="4732e-126">배치 파일 및 스크립트 설치</span><span class="sxs-lookup"><span data-stu-id="4732e-126">Setup Batch Files and Scripts</span></span>  
 <span data-ttu-id="4732e-127">Setup.exe 및 Cleanup.exe 배치 파일과 스크립트는 Visual Studio 명령 프롬프트에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-127">Setup.exe and Cleanup.exe batch files and scripts should be run from a Visual Studio command prompt.</span></span> <span data-ttu-id="4732e-128">일부 설치 및 정리 파일은 관리자 권한이 필요한 작업을 수행하므로 관리자 권한으로 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-128">Several set up and clean up files perform tasks that require administrative privileges and should be launched with administrator privileges.</span></span>  
  
## <a name="important-security-information-about-metadata-endpoints"></a><span data-ttu-id="4732e-129">메타데이터 끝점에 대한 중요한 보안 정보</span><span class="sxs-lookup"><span data-stu-id="4732e-129">Important Security Information about Metadata Endpoints</span></span>  
 <span data-ttu-id="4732e-130">중요한 서비스 메타데이터를 실수로 공개하지 않도록 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스의 기본 구성에서는 메타데이터 게시를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-130">To prevent unintentional disclosure of potentially sensitive service metadata, the default configuration for [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services disables metadata publishing.</span></span> <span data-ttu-id="4732e-131">이 동작은 기본적으로 안전하지만 구성에서 서비스의 메타데이터 게시 동작이 명시적으로 사용하도록 설정되어 있지 않은 경우 Svcutil.exe 등의 메타데이터 가져오기 도구를 사용하여 서비스를 호출하는 데 필요한 클라이언트 코드를 생성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-131">This behavior is secure by default, but also means that you cannot use a metadata import tool (such as Svcutil.exe) to generate the client code required to call the service unless the service’s metadata publishing behavior is explicitly enabled in configuration.</span></span> <span data-ttu-id="4732e-132">샘플로 보다 쉽게 작업할 수 있도록 거의 모든 샘플에서는 보안되지 않은 메타데이터 게시 끝점을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-132">To make experimenting with the samples easier, almost all samples expose an unsecured metadata publishing endpoint.</span></span> <span data-ttu-id="4732e-133">이러한 끝점은 인증되지 않은 익명의 소비자가 사용할 수 있으므로 이러한 끝점을 배포하기 전에 서비스의 메타데이터를 공개하는 것이 적절한지 주의를 기울여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-133">Such endpoints are potentially available to anonymous unauthenticated consumers and care must be taken before deploying such endpoints to ensure that publicly disclosing a service’s metadata is appropriate.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="4732e-134">서비스 메타 데이터 게시 참조는 [메타 데이터 게시 동작이](../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="4732e-134"> publishing service metadata, see the [Metadata Publishing Behavior](../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md) sample.</span></span> <span data-ttu-id="4732e-135">참조는 [메타 데이터 끝점을 보호 하는 사용자 지정](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) 메타 데이터 끝점 보안 샘플에 대 한 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-135">See the [Custom Secure Metadata Endpoint](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) sample for a sample securing a metadata endpoint.</span></span>  
  
## <a name="exception-handling"></a><span data-ttu-id="4732e-136">예외 처리</span><span class="sxs-lookup"><span data-stu-id="4732e-136">Exception Handling</span></span>  
 <span data-ttu-id="4732e-137">일반적으로 이러한 샘플에는 코드가 샘플의 주제 위주로 작동하도록 예외 처리가 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-137">Generally speaking these samples do not include exception handling to keep the code focused on the subject of the sample.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="4732e-138">예외 처리, 참조는 [예상 예외](../../../../docs/framework/wcf/samples/expected-exceptions.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="4732e-138"> exception handling, see the [Expected Exceptions](../../../../docs/framework/wcf/samples/expected-exceptions.md) sample.</span></span>  
  
## <a name="regenerating-clients-and-configuration-with-svcutil"></a><span data-ttu-id="4732e-139">Svcutil을 사용하여 클라이언트 및 구성 다시 생성</span><span class="sxs-lookup"><span data-stu-id="4732e-139">Regenerating Clients and Configuration with Svcutil</span></span>  
 <span data-ttu-id="4732e-140">사용할 수는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 클라이언트 코드와 대부분의 샘플에 대 한 구성을 다시 생성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-140">You can use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to regenerate client code and configuration for most of the samples.</span></span> <span data-ttu-id="4732e-141">일부 샘플에서는 구성을 수동으로 편집해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-141">Some samples require manually edited configuration.</span></span> <span data-ttu-id="4732e-142">예를 들어, Svcutil.exe를 사용하여 클라이언트 인증서 자격 증명을 사용하는 샘플의 구성을 다시 생성하는 경우 이전에 구성된 자격 증명을 수동으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-142">For example, if you use Svcutil.exe to regenerate the configuration for a sample that uses client certificate credentials, you must manually specify the credentials previously configured.</span></span> <span data-ttu-id="4732e-143">일부 샘플에서는 생성된 코드에 영향을 주기 위해 특정 Svcutil.exe 옵션을 사용하며, 이러한 옵션은 특정 샘플 항목에 지정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-143">Some samples use specific Svcutil.exe options to affect the generated code, these options are specified in the specific sample topics.</span></span>  
  
#### <a name="to-regenerate-the-client-and-configuration-files"></a><span data-ttu-id="4732e-144">클라이언트 및 구성 파일을 다시 생성하려면</span><span class="sxs-lookup"><span data-stu-id="4732e-144">To regenerate the client and configuration files</span></span>  
  
1.  <span data-ttu-id="4732e-145">SDK 명령 프롬프트를 열고 샘플을 설치한 디렉터리 위치 아래의 언어별 하위 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-145">Open an SDK command prompt and navigate to the language-specific subdirectory under the directory location where you installed the sample.</span></span>  
  
2.  <span data-ttu-id="4732e-146">웹 호스팅 서비스의 경우 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-146">If the service is a Web-hosted type, use the following command.</span></span>  
  
    ```  
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs  
    ```  
  
     <span data-ttu-id="4732e-147">자체 호스팅 서비스의 경우 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-147">If the service is a self-hosted type the following command.</span></span>  
  
    ```  
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost:8000/servicemodelsamples/service.svc/mex /out:generatedClient.cs  
    ```  
  
     <span data-ttu-id="4732e-148">http://localhost:8000/ServiceModelSamples/service.svc/mex를 자체 호스팅 서비스의 mex 끝점 주소로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-148">Replace http://localhost:8000/ServiceModelSamples/service.svc/mex with the address of the self-hosted service's mex endpoint.</span></span>  
  
     <span data-ttu-id="4732e-149">Visual Basic 형식에서 클라이언트를 생성하려면 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-149">To generate the client in a Visual Basic type, use the following command.</span></span>  
  
    ```  
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb  
    ```  
  
     <span data-ttu-id="4732e-150">자체 호스팅 서비스의 경우 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-150">If the service is a self-hosted type, use the following command.</span></span>  
  
    ```  
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost:8000/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="4732e-151">클라이언트 구성의 생성을 추가 하지 않으려면는 **/noConfig** 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="4732e-151">To skip the generation of client configuration add the **/noConfig** option.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4732e-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4732e-152">See Also</span></span>  
 [<span data-ttu-id="4732e-153">Windows Communication Foundation 샘플 실행</span><span class="sxs-lookup"><span data-stu-id="4732e-153">Running the Windows Communication Foundation Samples</span></span>](../../../../docs/framework/wcf/samples/running-the-samples.md)  
 [<span data-ttu-id="4732e-154">ServiceModel Metadata 유틸리티 도구(Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="4732e-154">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
