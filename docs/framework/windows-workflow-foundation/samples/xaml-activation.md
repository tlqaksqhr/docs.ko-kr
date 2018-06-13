---
title: XAML Activation
ms.date: 03/30/2017
ms.assetid: 486760e2-bb10-4ed5-8c02-fe7472498d2d
ms.openlocfilehash: 8621b0ea7b390c81e76ac7eeedb0b547b44320d7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517714"
---
# <a name="xaml-activation"></a><span data-ttu-id="8204f-102">XAML Activation</span><span class="sxs-lookup"><span data-stu-id="8204f-102">XAML Activation</span></span>
<span data-ttu-id="8204f-103">이 샘플에서는 IIS에서 선언적 워크플로를 호스트하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-103">This sample demonstrates how to host a declarative workflow in IIS.</span></span> <span data-ttu-id="8204f-104">샘플은 하나의 작업이 있는 `EchoService`라는 기본 워크플로입니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-104">The sample is a basic workflow called `EchoService` that has one operation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8204f-105">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="8204f-106">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="8204f-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8204f-107">이 디렉터리가 없으면 다운로드 페이지로 이동 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-107">If this directory does not exist, go to (download page) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8204f-108">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\XAMLActivation`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8204f-109">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="8204f-109">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="8204f-110">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 XAMLActivation.sln 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-110">Open the XAMLActivation.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="8204f-111">키를 눌러 솔루션을 빌드합니다 **F5**합니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-111">Build the solution by pressing **F5**.</span></span>  
  
3.  <span data-ttu-id="8204f-112">WcfTestClient.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-112">Run WcfTestClient.exe.</span></span> <span data-ttu-id="8204f-113">명령 프롬프트에서 다음과 같이 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-113">From a command prompt, type in the following:</span></span>  
  
    1.  <span data-ttu-id="8204f-114">cd %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE</span><span class="sxs-lookup"><span data-stu-id="8204f-114">cd %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE</span></span>  
  
    2.  <span data-ttu-id="8204f-115">WcfTestClient.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-115">Run WcfTestClient.exe.</span></span>  
  
4.  <span data-ttu-id="8204f-116">CTRL + SHIFT + A를 하는 서비스 주소 설정 하 여 WcfTestClient.exe에 서비스의 주소를 설정 http://localhost:56133/Service.xamlx합니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-116">Set the address of the service on WcfTestClient.exe by pressing CTRL+SHIFT+A and setting the service address to http://localhost:56133/Service.xamlx.</span></span>  
  
5.  <span data-ttu-id="8204f-117">Echo 작업을 수행하여 서비스를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-117">Perform the echo operation to test the service.</span></span>  
  
6.  <span data-ttu-id="8204f-118">관리자 권한으로 명령 프롬프트에서 DeployToIIS.Bat를 사용하여 IIS에 서비스를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-118">Deploy the Service in IIS using DeployToIIS.Bat in a command prompt with administrator privileges.</span></span>  
  
7.  <span data-ttu-id="8204f-119">클라이언트에 서비스 주소 http://localhost/XAMLActivation/Service.xamlx 하 고 WcfTestClient.exe를 사용 하 여 다시 서비스를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="8204f-119">Update the service address in the client to http://localhost/XAMLActivation/Service.xamlx and test the service again using WcfTestClient.exe.</span></span>
