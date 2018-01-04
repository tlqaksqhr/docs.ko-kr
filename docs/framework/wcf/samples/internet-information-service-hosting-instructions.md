---
title: "인터넷 정보 서비스 호스팅 지침"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 959a21c8-9d9d-4757-b255-4e57793ae9d6
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: de7dc897aa435d62c04c2e6a3ca82adf3a637a2a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="internet-information-service-hosting-instructions"></a><span data-ttu-id="ce71a-102">인터넷 정보 서비스 호스팅 지침</span><span class="sxs-lookup"><span data-stu-id="ce71a-102">Internet Information Service Hosting Instructions</span></span>
<span data-ttu-id="ce71a-103">IIS(인터넷 정보 서비스)에서 호스팅하는 샘플을 실행하려면 IIS가 올바르게 설치되어 있고 실행 중인지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-103">To run the samples that are hosted by Internet Information Services (IIS), you must make sure that IIS is properly installed and is running.</span></span>  
  
### <a name="to-install-iis-version-75-on-windows-server-2008-r2"></a><span data-ttu-id="ce71a-104">Windows Server 2008 R2에서 IIS 버전 7.5를 설치하려면</span><span class="sxs-lookup"><span data-stu-id="ce71a-104">To install IIS version 7.5 on Windows Server 2008 R2</span></span>  
  
1.  <span data-ttu-id="ce71a-105">**서버 관리자**선택, **역할입니다.**</span><span class="sxs-lookup"><span data-stu-id="ce71a-105">From **Server Manager**, select **Roles.**</span></span> <span data-ttu-id="ce71a-106">아래 **역할 요약**, 클릭 **역할 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-106">Under **Roles Summary**, click **Add Roles**.</span></span>  
  
2.  <span data-ttu-id="ce71a-107">클릭 **다음** 표시 하는 **서버 역할 선택** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="ce71a-107">Click **Next** to display the **Select Server Roles** dialog.</span></span>  
  
3.  <span data-ttu-id="ce71a-108">선택 **응용 프로그램 서버** 에서 **역할** 목록으로 이동한 다음 클릭 **다음** 두 번 표시 하는 **역할 서비스 선택** 대화 상자는 응용 프로그램 서버 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-108">Select **Application Server** from the **Roles** list, and then click **Next** twice to display the **Select Role Services** dialog for the Application Server role.</span></span>  
  
4.  <span data-ttu-id="ce71a-109">선택 된 **웹 서버 (IIS)** 확인란 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-109">Select the **Web Server (IIS)** check box.</span></span> <span data-ttu-id="ce71a-110">추가 역할 서비스 및 기능을 설치 하는 메시지가 클릭 **필요한 기능 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-110">If you are prompted to install additional role services and features, click **Add Required Features**.</span></span> <span data-ttu-id="ce71a-111">클릭 **다음** 두 번 표시 하는 **역할 서비스 선택** 웹 서버 (IIS) 역할에 대 한 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="ce71a-111">Click **Next** twice to display the **Select Role Services** dialog for the Web Server (IIS) role.</span></span>  
  
5.  <span data-ttu-id="ce71a-112">확장 **관리 도구**을 펼친 다음 **IIS 6 관리 호환성**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-112">Expand **Management Tools**, and then expand **IIS 6 Management Compatibility**.</span></span> <span data-ttu-id="ce71a-113">선택 **IIS 6 스크립팅 도구**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-113">Select **IIS 6 Scripting Tools**.</span></span> <span data-ttu-id="ce71a-114">추가 역할 서비스 및 기능을 설치 하는 메시지가 클릭 **필요한 역할 서비스 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-114">If you are prompted to install additional role services and features, click **Add Required Role Services**.</span></span> <span data-ttu-id="ce71a-115">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-115">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="ce71a-116">선택 사항 요약 올바르면 클릭 **설치**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-116">If the summary of selections is correct, click **Install**.</span></span>  
  
7.  <span data-ttu-id="ce71a-117">설치가 완료 되 면 클릭 **닫기**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-117">When installation completes, click **Close**.</span></span>  
  
### <a name="to-install-iis-version-75-on-windows-7"></a><span data-ttu-id="ce71a-118">Windows 7에서 IIS 버전 7.5를 설치하려면</span><span class="sxs-lookup"><span data-stu-id="ce71a-118">To install IIS version 7.5 on Windows 7</span></span>  
  
1.  <span data-ttu-id="ce71a-119">클릭 **시작**, 클릭 하 고 **제어판**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-119">Click **Start**, and then click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="ce71a-120">열기는 **프로그램** 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-120">Open the **Programs** group.</span></span>  
  
3.  <span data-ttu-id="ce71a-121">아래 **프로그램 및 기능**, 클릭 **Windows 기능 사용 / 사용 해제**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-121">Under **Programs and Features**, click **Turn Windows Features on or off**.</span></span>  
  
4.  <span data-ttu-id="ce71a-122">**사용자 계정 컨트롤** 대화 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-122">The **User Account Control** dialog is displayed.</span></span> <span data-ttu-id="ce71a-123">**계속**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-123">Click **Continue**.</span></span>  
  
5.  <span data-ttu-id="ce71a-124">**Windows 기능** 대화 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-124">The **Windows Features** dialog is displayed.</span></span> <span data-ttu-id="ce71a-125">항목을 확장 **인터넷 정보 서비스**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-125">Expand the item labeled **Internet Information Services**.</span></span>  
  
6.  <span data-ttu-id="ce71a-126">항목을 확장 **World Wide Web 서비스**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-126">Expand the item labeled **World Wide Web Services**.</span></span>  
  
7.  <span data-ttu-id="ce71a-127">항목을 확장 **응용 프로그램 개발 기능**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-127">Expand the item labeled **Application Development Features**.</span></span>  
  
8.  <span data-ttu-id="ce71a-128">다음 항목이 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-128">Make sure the following items are selected:</span></span>  
  
    1.  <span data-ttu-id="ce71a-129">**.NET 확장성**</span><span class="sxs-lookup"><span data-stu-id="ce71a-129">**.NET Extensibility**</span></span>  
  
    2.  <span data-ttu-id="ce71a-130">**ASP.NET**</span><span class="sxs-lookup"><span data-stu-id="ce71a-130">**ASP.NET**</span></span>  
  
    3.  <span data-ttu-id="ce71a-131">**ISAPI 확장**</span><span class="sxs-lookup"><span data-stu-id="ce71a-131">**ISAPI Extensions**</span></span>  
  
    4.  <span data-ttu-id="ce71a-132">**ISAPI 필터**</span><span class="sxs-lookup"><span data-stu-id="ce71a-132">**ISAPI Filters**</span></span>  
  
9. <span data-ttu-id="ce71a-133">항목 아래 **World Wide Web 서비스**를 확장 하 고 **일반 Http 기능**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-133">Under the item labeled **World Wide Web Services**, expand **Common Http Features**.</span></span>  
  
10. <span data-ttu-id="ce71a-134">확인 **정적 콘텐츠** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-134">Make sure **Static Content** is selected.</span></span>  
  
11. <span data-ttu-id="ce71a-135">항목 아래 **World Wide Web 서비스**를 확장 하 고 **보안**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-135">Under the item labeled **World Wide Web Services**, expand **Security**.</span></span>  
  
12. <span data-ttu-id="ce71a-136">다음 사항을 확인 **Windows 인증** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-136">Make sure that **Windows Authentication** is selected.</span></span>  
  
13. <span data-ttu-id="ce71a-137">아래는 **인터넷 정보 서비스** 디렉터리 항목을 확장 **웹 관리 도구**를 선택한 후 **IIS 관리 콘솔**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-137">Under the **Internet Information Services** directory, expand the item labeled **Web Management Tools**, and then select **IIS Management Console**.</span></span>  
  
14. <span data-ttu-id="ce71a-138">항목을 확장 **IIS 6 관리 호환성**를 선택한 후 **IIS 6 스크립팅 도구**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-138">Expand the item labeled **IIS 6 Management Compatibility**, and then select **IIS 6 Scripting Tools**.</span></span>  
  
15. <span data-ttu-id="ce71a-139">아래는 **인터넷 정보 서비스** 디렉터리 항목을 확장 **Microsoft.NET Framework 3.5.1**를 선택한 후 **Windows Communication Foundation Http 활성화**.</span><span class="sxs-lookup"><span data-stu-id="ce71a-139">Under the **Internet Information Services** directory, expand the item labeled **Microsoft .NET Framework 3.5.1**, and then select **Windows Communication Foundation Http Activation**.</span></span>  
  
16. <span data-ttu-id="ce71a-140">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-140">Click **OK**.</span></span>  
  
### <a name="to-install-iis-version-70-on-windows-server-2008"></a><span data-ttu-id="ce71a-141">Windows Server 2008에서 IIS 버전 7.0을 설치하려면</span><span class="sxs-lookup"><span data-stu-id="ce71a-141">To install IIS version 7.0 on Windows Server 2008</span></span>  
  
1.  <span data-ttu-id="ce71a-142">**서버 관리자**선택, **역할**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-142">From **Server Manager**, select **Roles**.</span></span> <span data-ttu-id="ce71a-143">아래 **역할 요약**, 클릭 **역할 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-143">Under **Roles Summary**, click **Add Roles**.</span></span>  
  
2.  <span data-ttu-id="ce71a-144">클릭 **다음** 표시 하는 **서버 역할 선택** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="ce71a-144">Click **Next** to display the **Select Server Roles** dialog.</span></span>  
  
3.  <span data-ttu-id="ce71a-145">선택 **응용 프로그램 서버** 에서 **역할** 목록으로 이동한 다음 클릭 **다음** 두 번 표시 하는 **역할 서비스 선택** 대화 상자는 응용 프로그램 서버 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-145">Select **Application Server** from the **Roles** list, and then click **Next** twice to display the **Select Role Services** dialog for the Application Server role.</span></span>  
  
4.  <span data-ttu-id="ce71a-146">선택 **웹 서버 (IIS)** 확인란 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-146">Select **Web Server (IIS)** check box.</span></span> <span data-ttu-id="ce71a-147">추가 역할 서비스 및 기능을 설치 하는 메시지가 클릭 **필요한 기능 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-147">If you are prompted to install additional role services and features, click **Add Required Features**.</span></span> <span data-ttu-id="ce71a-148">클릭 **다음** 두 번 표시 하는 **역할 서비스 선택** 웹 서버 (IIS) 역할에 대 한 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="ce71a-148">Click **Next** twice to display the **Select Role Services** dialog for the Web Server (IIS) role.</span></span>  
  
5.  <span data-ttu-id="ce71a-149">확장 **관리 도구**을 펼친 다음 **IIS 6 관리 호환성**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-149">Expand **Management Tools**, and then expand **IIS 6 Management Compatibility**.</span></span> <span data-ttu-id="ce71a-150">선택 **IIS 6 스크립팅 도구**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-150">Select **IIS 6 Scripting Tools**.</span></span> <span data-ttu-id="ce71a-151">추가 역할 서비스 및 기능을 설치 하는 메시지가 클릭 **필요한 역할 서비스 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-151">If you are prompted to install additional role services and features, click **Add Required Role Services**.</span></span> <span data-ttu-id="ce71a-152">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-152">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="ce71a-153">선택 사항 요약 올바르면 클릭 **설치**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-153">If the summary of selections is correct, click **Install**.</span></span>  
  
7.  <span data-ttu-id="ce71a-154">설치가 완료 되 면 클릭 **닫기**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-154">When installation completes, click **Close**.</span></span>  
  
### <a name="to-install-iis-version-70-on-windows-vista"></a><span data-ttu-id="ce71a-155">Windows Vista에서 IIS 버전 7.0을 설치하려면</span><span class="sxs-lookup"><span data-stu-id="ce71a-155">To install IIS version 7.0 on Windows Vista</span></span>  
  
1.  <span data-ttu-id="ce71a-156">시작을 클릭한 다음 제어판을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-156">Click Start, and then click Control Panel.</span></span>  
  
2.  <span data-ttu-id="ce71a-157">선택 된 **프로그램** 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-157">Select the **Programs** group.</span></span>  
  
3.  <span data-ttu-id="ce71a-158">아래 **프로그램 및 기능**, 클릭 **Windows 기능 사용 / 사용 해제**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-158">Under **Programs and Features**, click **Turn Windows Features on or off**.</span></span>  
  
4.  <span data-ttu-id="ce71a-159">**사용자 계정 컨트롤** 대화 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-159">The **User Account Control** dialog is displayed.</span></span> <span data-ttu-id="ce71a-160">**계속**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-160">Click **Continue**.</span></span>  
  
5.  <span data-ttu-id="ce71a-161">**Windows 기능** 대화 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-161">The **Windows Features** dialog is displayed.</span></span> <span data-ttu-id="ce71a-162">항목을 확장 **인터넷 정보 서비스**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-162">Expand the item labeled **Internet Information Services**.</span></span>  
  
6.  <span data-ttu-id="ce71a-163">항목을 확장 **World Wide Web 서비스**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-163">Expand the item labeled **World Wide Web Services**.</span></span>  
  
7.  <span data-ttu-id="ce71a-164">항목을 확장 **응용 프로그램 개발 기능**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-164">Expand the item labeled **Application Development Features**.</span></span>  
  
8.  <span data-ttu-id="ce71a-165">다음 항목이 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-165">Make sure the following items are selected:</span></span>  
  
    1.  <span data-ttu-id="ce71a-166">**.NET 확장성**</span><span class="sxs-lookup"><span data-stu-id="ce71a-166">**.NET Extensibility**</span></span>  
  
    2.  <span data-ttu-id="ce71a-167">**ASP.NET**</span><span class="sxs-lookup"><span data-stu-id="ce71a-167">**ASP.NET**</span></span>  
  
    3.  <span data-ttu-id="ce71a-168">**ISAPI 확장**</span><span class="sxs-lookup"><span data-stu-id="ce71a-168">**ISAPI Extensions**</span></span>  
  
    4.  <span data-ttu-id="ce71a-169">**ISAPI 필터**</span><span class="sxs-lookup"><span data-stu-id="ce71a-169">**ISAPI Filters**</span></span>  
  
9. <span data-ttu-id="ce71a-170">항목을 확장 **웹 관리 도구**를 선택한 후 **IIS 관리 콘솔**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-170">Expand the item labeled **Web Management Tools**, and then select **IIS Management Console**.</span></span>  
  
10. <span data-ttu-id="ce71a-171">항목 아래 **World Wide Web 서비스**를 확장 하 고 **일반 Http 기능**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-171">Under the item labeled **World Wide Web Services**, expand **Common Http Features**.</span></span>  
  
11. <span data-ttu-id="ce71a-172">확인 **정적 콘텐츠** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-172">Make sure **Static Content** is selected.</span></span>  
  
12. <span data-ttu-id="ce71a-173">항목 아래 **World Wide Web 서비스**를 확장 하 고 **보안**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-173">Under the item labeled **World Wide Web Services**, expand **Security**.</span></span>  
  
13. <span data-ttu-id="ce71a-174">확인 **Windows 인증** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-174">Make sure **Windows Authentication** is selected.</span></span>  
  
14. <span data-ttu-id="ce71a-175">항목을 확장 **IIS 6 관리 호환성**를 선택한 후 **IIS 6 스크립팅 도구**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-175">Expand the item labeled **IIS 6 Management Compatibility**, and then select **IIS 6 Scripting Tools**.</span></span>  
  
15. <span data-ttu-id="ce71a-176">항목을 확장 **Microsoft.NET Framework 3.0**를 선택한 후 **Windows Communication Foundation Http Activation**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-176">Expand the item labeled **Microsoft .NET Framework 3.0**, and then select **Windows Communication Foundation Http Activation**.</span></span>  
  
16. <span data-ttu-id="ce71a-177">클릭**확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-177">Click**OK**.</span></span>  
  
### <a name="to-install-iis-version-60-on-windows-server-2003"></a><span data-ttu-id="ce71a-178">Windows Server 2003에서 IIS 버전 6.0을 설치하려면</span><span class="sxs-lookup"><span data-stu-id="ce71a-178">To install IIS version 6.0 on Windows Server 2003</span></span>  
  
1.  <span data-ttu-id="ce71a-179">**사용자 서버 관리**, 클릭 **추가 또는 제거 하는 역할**, 클릭 하 고 **다음**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-179">From **Manage Your Server**, click **Add or remove a role**, and then click **Next**.</span></span>  
  
2.  <span data-ttu-id="ce71a-180">선택 **응용 프로그램 서버 (IIS, ASP.NET)** 에서 **서버 역할** 목록으로 이동한 다음 클릭 **다음**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-180">Select **Application server (IIS, ASP.NET)** from the **Server Role** list, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="ce71a-181">선택 **ASP.NET 사용** 확인란을 선택한 다음 클릭 **다음**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-181">Select **Enable ASP.NET** check box, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="ce71a-182">선택 항목에 대한 요약이 모두 올바르면 다음을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-182">If the summary of selections is correct, click Next.</span></span>  
  
### <a name="to-install-iis-version-51-on-windows-xp-with-service-pack-2-and-service-pack-3-installed"></a><span data-ttu-id="ce71a-183">Windows XP 서비스 팩 2 및 서비스 팩 3에서 IIS 버전 5.1을 설치하려면</span><span class="sxs-lookup"><span data-stu-id="ce71a-183">To install IIS version 5.1 on Windows XP with Service Pack 2 and Service Pack 3 installed</span></span>  
  
1.  <span data-ttu-id="ce71a-184">제어판에서 클릭 **프로그램 추가 / 제거**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-184">In Control Panel, click **Add or Remove Programs**.</span></span>  
  
2.  <span data-ttu-id="ce71a-185">에 **프로그램 추가 / 제거** 대화 상자를 클릭 **Windows 구성 요소 추가/제거**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-185">In the **Add or Remove Programs** dialog box, click **Add/Remove Windows Components**.</span></span>  
  
3.  <span data-ttu-id="ce71a-186">에 **Windows 구성 요소 마법사**, 선택는 **인터넷 정보 서비스 (IIS)** 확인란을 선택한 다음 클릭 **다음**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-186">In the **Windows Components Wizard**, select the **Internet Information Services (IIS)** check box, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="ce71a-187">경우는 **필요한 파일** 대화 상자가 표시 됩니다, 운영 체제 설치 디스크를 삽입, i386 폴더로 및 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-187">If the **Files Needed** dialog box is displayed, insert your operating system installation disc, browse to the i386 folder, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="ce71a-188">설치가 완료 되 면 클릭 **마침**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-188">When installation completes, click **Finish**.</span></span>  
  
6.  <span data-ttu-id="ce71a-189">닫습니다는 **프로그램 추가 / 제거** 대화 상자를 닫은 다음 **제어판**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-189">Close the **Add or Remove Programs** dialog box, and then close **Control Panel**.</span></span>  
  
### <a name="to-verify-the-installation-of-iis-and-aspnet"></a><span data-ttu-id="ce71a-190">IIS 및 ASP.NET의 설치를 확인하려면</span><span class="sxs-lookup"><span data-stu-id="ce71a-190">To verify the installation of IIS and ASP.NET</span></span>  
  
1.  <span data-ttu-id="ce71a-191">이 항목의 끝에 있는 HTML 파일을 루트 \InetPub\wwwroot 디렉터리에 저장하고 이름을 Default.aspx로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-191">Save the HTML file found at the end of this topic in the root \InetPub\wwwroot directory and name it Default.aspx.</span></span>  
  
2.  <span data-ttu-id="ce71a-192">브라우저 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-192">Open a browser window.</span></span>  
  
3.  <span data-ttu-id="ce71a-193">형식 `http://localhost/Default.aspx` 주소 상자에 다음 ENTER 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-193">Type `http://localhost/Default.aspx` in the address box, and then press ENTER.</span></span>  
  
4.  <span data-ttu-id="ce71a-194">"Hello World"라는 텍스트가 포함된 웹 페이지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-194">A Web page with the text "Hello World" should appear.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ce71a-195">새 버전의 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]를 설치할 때마다 aspnet_isapi를 IIS의 웹 서비스 확장으로 다시 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-195">Each time you install a new version of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], you must re-register aspnet_isapi as a Web service extension for IIS.</span></span> <span data-ttu-id="ce71a-196">이렇게 하려면 `aspnet_regiis –I –enable` 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ce71a-196">To do so, issue the `aspnet_regiis –I –enable` command.</span></span>  
  
## <a name="sample-code"></a><span data-ttu-id="ce71a-197">샘플 코드</span><span class="sxs-lookup"><span data-stu-id="ce71a-197">Sample Code</span></span>  
  
```xml  
<html>  
   <body>  
       <form >  
           <h3> Hello World  
           </h3>  
       </form>  
   </body>  
</html>  
```
