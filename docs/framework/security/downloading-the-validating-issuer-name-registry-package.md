---
title: "발급자 이름 레지스트리 유효성 검사 패키지 다운로드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ff8b0014-c5d4-4614-90f0-13fcc0ba777a
caps.latest.revision: "3"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9bf6869de939ed7eda7cd3de868e712126f71751
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="downloading-the-validating-issuer-name-registry-package"></a><span data-ttu-id="edd12-102">발급자 이름 레지스트리 유효성 검사 패키지 다운로드</span><span class="sxs-lookup"><span data-stu-id="edd12-102">Downloading the Validating Issuer Name Registry Package</span></span>
<span data-ttu-id="edd12-103">이 항목에서는 VINR(발급자 이름 레지스트리 유효성 검사)을 다운로드하고 프로젝트에서 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="edd12-103">This topic discusses how to download and use the Validating Issuer Name Registry (VINR) in your project.</span></span>  
  
## <a name="downloading-the-validating-issuer-name-registry"></a><span data-ttu-id="edd12-104">발급자 이름 레지스트리 유효성 검사 다운로드</span><span class="sxs-lookup"><span data-stu-id="edd12-104">Downloading the Validating Issuer Name Registry</span></span>  
 <span data-ttu-id="edd12-105">VINR은 필요한 어셈블리 및 참조를 프로젝트에 추가하는 NuGet 패키지로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edd12-105">The VINR is available as a NuGet package, which adds the necessary assemblies and references to your project.</span></span> <span data-ttu-id="edd12-106">NuGet이 아직 설치되지 않은 경우 [nuget.org](http://nuget.org)로 이동하여 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="edd12-106">If you do not already have NuGet installed, go to [nuget.org](http://nuget.org) to install it.</span></span> <span data-ttu-id="edd12-107">NuGet의 해당 페이지 [Microsoft Validating Issuer Name Registry on NuGet](https://nuget.org/packages/System.IdentityModel.Tokens.ValidatingIssuerNameRegistry/)(NuGet의 Microsoft 발급자 이름 레지스트리 패키지 유효성 검사)을 방문하여 확장에 대한 버전 관리 기록을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edd12-107">You can see the versioning history for the extension by visiting its page on NuGet: [Microsoft Validating Issuer Name Registry on NuGet](https://nuget.org/packages/System.IdentityModel.Tokens.ValidatingIssuerNameRegistry/)</span></span>  
  
#### <a name="downloading-the-validating-issuer-name-registry-by-using-the-package-manager-gui"></a><span data-ttu-id="edd12-108">패키지 관리자 GUI를 사용하여 발급자 이름 레지스트리 유효성 검사 다운로드</span><span class="sxs-lookup"><span data-stu-id="edd12-108">Downloading the Validating Issuer Name Registry by using the Package Manager GUI</span></span>  
  
1.  <span data-ttu-id="edd12-109">Visual Studio의 **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="edd12-109">In Visual Studio, right-click your project in **Solution Explorer**, and then select **Manage NuGet Packages**.</span></span>  
  
2.  <span data-ttu-id="edd12-110">**NuGet 패키지 관리** 창에서 검색 상자를 클릭하고 `ValidatingIssuerNameRegistry`를 입력하고 **Enter** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="edd12-110">In the **Manage NuGet Packages** window, click the search box and enter `ValidatingIssuerNameRegistry` and press **Enter**.</span></span>  
  
3.  <span data-ttu-id="edd12-111">[결과] 창에서 첫 번째 결과에 대한 **설치** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="edd12-111">From the results pane, click the **Install** button for the first result.</span></span>  
  
4.  <span data-ttu-id="edd12-112">패키지 다운로드가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="edd12-112">The package will begin downloading.</span></span> <span data-ttu-id="edd12-113">프로젝트에 추가되기 전에 [라이선스 승인] 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="edd12-113">Before it is added to your project, the License Acceptance dialog will appear.</span></span> <span data-ttu-id="edd12-114">사용 약관에 동의하면 **동의**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="edd12-114">If you agree to the license terms, click **I Accept**.</span></span>  
  
5.  <span data-ttu-id="edd12-115">최신 VINR 어셈블리가 다운로드되고 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="edd12-115">The latest VINR assemblies will be downloaded and added to your project.</span></span>  
  
#### <a name="downloading-the-validating-issuer-name-registry-by-using-the-package-manager-console"></a><span data-ttu-id="edd12-116">패키지 관리자 콘솔을 사용하여 발급자 이름 레지스트리 유효성 검사 다운로드</span><span class="sxs-lookup"><span data-stu-id="edd12-116">Downloading the Validating Issuer Name Registry by using the Package Manager Console</span></span>  
  
1.  <span data-ttu-id="edd12-117">Visual Studio에서 **도구**, **라이브러리 패키지 관리자**, **패키지 관리자 콘솔**을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="edd12-117">In Visual Studio, click **Tools**, **Library Package Manager**, and then **Package Manager Console**.</span></span>  
  
2.  <span data-ttu-id="edd12-118">**패키지 관리자 콘솔**이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="edd12-118">The **Package Manager Console** appears.</span></span> <span data-ttu-id="edd12-119">다음 텍스트를 입력하고 **Enter** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="edd12-119">Enter the following text and press **Enter**:</span></span>  
  
    ```powershell  
    Install-Package System.IdentityModel.Tokens.ValidatingIssuerNameRegistry  
    ```  
  
3.  <span data-ttu-id="edd12-120">최신 VINR 어셈블리가 다운로드되고 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="edd12-120">The latest VINR assemblies will be downloaded and added to your project.</span></span>
