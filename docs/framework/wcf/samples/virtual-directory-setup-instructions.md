---
title: 가상 디렉터리 설치 지침
ms.date: 03/30/2017
ms.assetid: 3c62cab5-81a4-48b6-ac8c-9ce33a85a157
ms.openlocfilehash: 3ff578b69590071ef2135e777b3105e7c226563e
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="virtual-directory-setup-instructions"></a><span data-ttu-id="daf8d-102">가상 디렉터리 설치 지침</span><span class="sxs-lookup"><span data-stu-id="daf8d-102">Virtual Directory Setup Instructions</span></span>
<span data-ttu-id="daf8d-103">Windows Communication Foundation (WCF) 샘플은 %SystemDrive%\inetpub\wwwroot\servicemodelsamples 폴더에 매핑되어 있는 servicemodelsamples 라는 공용 가상 디렉터리를 공유 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-103">The Windows Communication Foundation (WCF) samples are intended to share a common virtual directory named servicemodelsamples that is mapped to the %SystemDrive%\inetpub\wwwroot\servicemodelsamples folder.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="daf8d-104">%SystemDrive%는 일반적으로 C: 또는 D:이며 IIS(인터넷 정보 서비스)가 설치된 드라이브 위치에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-104">%SystemDrive% is usually C: or D:, depending on the drive location where Internet Information Services (IIS) is installed.</span></span>  
  
 <span data-ttu-id="daf8d-105">Setupvroot.bat 및 Cleanupvroot.bat 파일을 실행할 수는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) 가상 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-105">You can run the Setupvroot.bat and Cleanupvroot.bat files from the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) to create the virtual directory.</span></span> <span data-ttu-id="daf8d-106">가상 디렉터리를 수동으로 만들려면 다음 절차를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-106">If you prefer to create the virtual directory manually, use the following procedures.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="daf8d-107">절차</span><span class="sxs-lookup"><span data-stu-id="daf8d-107">Procedures</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-70-or-75"></a><span data-ttu-id="daf8d-108">IIS 7.0 또는 7.5에서 가상 디렉터리를 만들려면</span><span class="sxs-lookup"><span data-stu-id="daf8d-108">To create a virtual directory in IIS 7.0 or 7.5</span></span>  
  
1.  <span data-ttu-id="daf8d-109">**시작** 메뉴를 클릭 **실행**, 다음 입력 **inetmgr** 를 인터넷 정보 서비스 (IIS) MMC 스냅인을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-109">From the **Start** menu, click **Run**, then type **inetmgr** to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2.  <span data-ttu-id="daf8d-110">왼쪽된 창에서 컴퓨터의 이름이 있는 노드를 확장 한 다음 확장은 **사이트** 노드.</span><span class="sxs-lookup"><span data-stu-id="daf8d-110">In the left pane, expand the node with the computer's name, and then expand the **Sites** node.</span></span>  
  
3.  <span data-ttu-id="daf8d-111">마우스 오른쪽 단추로 클릭 **기본 웹 사이트**를 선택한 후 **응용 프로그램 추가** 열려는 **추가 응용 프로그램 창**합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-111">Right-click **Default Web Site**, and then select **Add Application** to open the **Add Application window**.</span></span>  
  
4.  <span data-ttu-id="daf8d-112">창에서 입력 `servicemodelsamples` 만들고 있는 가상 디렉터리에 대 한 별칭으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-112">In the window, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5.  <span data-ttu-id="daf8d-113">%SystemDrive%\inetpub\wwwroot\servicemodelsamples 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-113">Create the following directory: %SystemDrive%\inetpub\wwwroot\servicemodelsamples</span></span>  
  
6.  <span data-ttu-id="daf8d-114">실제 경로를 %SystemDrive%\inetpub\wwwroot\servicemodelsamples로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-114">Set the physical path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  <span data-ttu-id="daf8d-115">대부분의 WCF 샘플은 빌드 시 서비스 실행 파일을 이 위치에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-115">Most of the WCF samples copy service executable files to this location when built.</span></span>  
  
7.  <span data-ttu-id="daf8d-116">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-116">Click **OK**.</span></span> <span data-ttu-id="daf8d-117">WCF 샘플에 웹 응용 프로그램이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-117">The Web application is now created for the WCF samples.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="daf8d-118">모든 WCF 샘플에서는 동일한 servicemodelsamples 웹 응용 프로그램을 사용 하기 때문에이 작업을 한 번만 수행 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-118">This task must be performed only once, because all of the WCF samples use the same servicemodelsamples Web application.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="daf8d-119">이 문서에서는 `virtual directory`라는 용어는 `Web application`과 동의어입니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-119">For the purpose of this documentation, the term `virtual directory` is synonymous with `Web application`.</span></span>  
  
     <span data-ttu-id="daf8d-120">가상 디렉터리를 만드는 것 이외에 WCF 서비스를 실행할 수 있도록 해당 속성을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-120">In addition to creating the virtual directory, you must also set its properties to enable WCF services to run.</span></span> <span data-ttu-id="daf8d-121">자세한 내용은 다음을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="daf8d-121">See below for details.</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-51-or-60"></a><span data-ttu-id="daf8d-122">IIS 5.1 또는 6.0에서 가상 디렉터리를 만들려면</span><span class="sxs-lookup"><span data-stu-id="daf8d-122">To create a virtual directory in IIS 5.1 or 6.0</span></span>  
  
1.  <span data-ttu-id="daf8d-123">명령 프롬프트 창을 열고 형식 `start inetmgr` 를 인터넷 정보 서비스 (IIS) MMC 스냅인을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-123">Open a command prompt window and type `start inetmgr` to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2.  <span data-ttu-id="daf8d-124">왼쪽된 창에서 컴퓨터의 이름이 있는 노드를 확장 한 다음 확장은 **웹사이트** 노드.</span><span class="sxs-lookup"><span data-stu-id="daf8d-124">In the left pane, expand the node with the computer's name, and then expand the **Web Sites** node.</span></span>  
  
3.  <span data-ttu-id="daf8d-125">마우스 오른쪽 단추로 클릭 **기본 웹 사이트** 선택 **새로 만들기, 가상 디렉터리** 가상 디렉터리 만들기 마법사를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-125">Right-click **Default Web Site** and select **New, Virtual Directory** to open the Virtual Directory Creation wizard.</span></span>  
  
4.  <span data-ttu-id="daf8d-126">마법사에서 입력 `servicemodelsamples` 만들고 있는 가상 디렉터리에 대 한 별칭으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-126">In the wizard, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5.  <span data-ttu-id="daf8d-127">경로를 %SystemDrive%\inetpub\wwwroot\servicemodelsamples로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-127">Set the path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span> <span data-ttu-id="daf8d-128">대부분의 WCF 샘플은 빌드 시 서비스 실행 파일을 이 위치에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-128">Most of the WCF samples copy service executable files to this location when built.</span></span>  
  
6.  <span data-ttu-id="daf8d-129">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-129">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="daf8d-130">기본적으로 다음 확인란이 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-130">By default, the following check boxes are selected:</span></span>  
  
    -   <span data-ttu-id="daf8d-131">**읽기**</span><span class="sxs-lookup"><span data-stu-id="daf8d-131">**Read**</span></span>  
  
    -   <span data-ttu-id="daf8d-132">**스크립트 실행 (예: ASP)**</span><span class="sxs-lookup"><span data-stu-id="daf8d-132">**Run scripts (such as ASP)**</span></span>  
  
8.  <span data-ttu-id="daf8d-133">클릭 **다음**, 클릭 하 고 **마침** 마법사를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-133">Click **Next**, and then click **Finish** to complete the wizard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="daf8d-134">모든 WCF 샘플에서는 동일한 servicemodelsamples 가상 디렉터리를 사용 하기 때문에이 작업을 한 번만 수행 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-134">This task must be performed only once because all of the WCF samples use the same servicemodelsamples virtual directory.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-70-or-75"></a><span data-ttu-id="daf8d-135">7.5 또는 IIS 7.0에서 추가 가상 디렉터리 속성을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="daf8d-135">To set additional virtual directory properties in IIS 7.0 or 7.5</span></span>  
  
1.  <span data-ttu-id="daf8d-136">servicemodelsamples 노드를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-136">Click the servicemodelsamples node.</span></span> <span data-ttu-id="daf8d-137">창 아래쪽에 두 개의 뷰가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-137">Along the bottom of the window, two views are listed.</span></span> <span data-ttu-id="daf8d-138">선택 **기능 보기** 아직 선택 되지 않은 경우.</span><span class="sxs-lookup"><span data-stu-id="daf8d-138">Select **Features View** if it isn’t already selected.</span></span>  
  
2.  <span data-ttu-id="daf8d-139">에 대 한 항목을 두 번 클릭 **디렉터리 검색**합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-139">Double-click the entry for **Directory Browsing**.</span></span>  
  
3.  <span data-ttu-id="daf8d-140">작업 창에서 선택 된 **사용** 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-140">In the Actions pane, select the **Enable** option.</span></span> <span data-ttu-id="daf8d-141">이렇게 하면 Internet Explorer를 사용하는 디렉터리의 디렉터리에 액세스할 수 있어 서비스를 디버깅할 때 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-141">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
 <span data-ttu-id="daf8d-142">마지막으로 다른 사용자가 액세스할 수 있도록 servicemodelsamples 폴더의 보안 속성을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-142">Finally, you must set the security properties of the servicemodelsamples folder to allow it to be accessed by others.</span></span> <span data-ttu-id="daf8d-143">자세한 내용은 다음을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="daf8d-143">See below for details.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-51-or-60"></a><span data-ttu-id="daf8d-144">IIS 5.1 또는 6.0에서 추가 가상 디렉터리 속성을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="daf8d-144">To set additional virtual directory properties in IIS 5.1 or 6.0</span></span>  
  
1.  <span data-ttu-id="daf8d-145">Servicemodelsamples 노드를 마우스 오른쪽 단추로 누른 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-145">Right-click the servicemodelsamples node and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="daf8d-146">기본적으로 다음 확인란이 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-146">By default, the following check boxes are selected:</span></span>  
  
    -   <span data-ttu-id="daf8d-147">**읽기**</span><span class="sxs-lookup"><span data-stu-id="daf8d-147">**Read**</span></span>  
  
    -   <span data-ttu-id="daf8d-148">**방문 기록**</span><span class="sxs-lookup"><span data-stu-id="daf8d-148">**Log visits**</span></span>  
  
    -   <span data-ttu-id="daf8d-149">**이 리소스 색인화**</span><span class="sxs-lookup"><span data-stu-id="daf8d-149">**Index this resource**</span></span>  
  
3.  <span data-ttu-id="daf8d-150">선택 된 **디렉터리 검색** 확인란 합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-150">Select the **Directory browsing** check box.</span></span> <span data-ttu-id="daf8d-151">이렇게 하면 Internet Explorer를 사용하는 디렉터리의 디렉터리에 액세스할 수 있어 서비스를 디버깅할 때 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-151">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-70-or-75"></a><span data-ttu-id="daf8d-152">IIS 7.0 또는 7.5에서 폴더의 보안 속성을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="daf8d-152">To set security properties of the folder in IIS 7.0 or 7.5</span></span>  
  
1.  <span data-ttu-id="daf8d-153">%SystemDrive%\inetpub\wwwroot\servicemodelsamples로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-153">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2.  <span data-ttu-id="daf8d-154">Servicemodelsamples 폴더를 마우스 오른쪽 단추로 클릭 하 고 클릭 **공유** 또는 **공유**합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-154">Right-click the servicemodelsamples folder and click **Share** or **Share With**.</span></span>  
  
3.  <span data-ttu-id="daf8d-155">왼쪽의 아래쪽 화살표를 클릭는 **추가** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-155">Click the down arrow to the left of the **Add** button.</span></span>  
  
4.  <span data-ttu-id="daf8d-156">선택 된 **찾을** 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-156">Select the **Find** entry.</span></span> <span data-ttu-id="daf8d-157">**사용자 또는 그룹 선택** 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-157">The **Select Users or Groups** window opens.</span></span>  
  
5.  <span data-ttu-id="daf8d-158">**고급**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-158">Click **Advanced**.</span></span>  
  
6.  <span data-ttu-id="daf8d-159">클릭 **위치**합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-159">Click **Locations**.</span></span> <span data-ttu-id="daf8d-160">**위치** 창이 열려 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-160">The **Locations** window is now open.</span></span>  
  
7.  <span data-ttu-id="daf8d-161">사용 중인 컴퓨터에 대한 항목을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-161">Select the entry for the computer being used.</span></span> <span data-ttu-id="daf8d-162">표시되어 있는 도메인이나 네트워크에 대한 항목이 아닌 로컬 컴퓨터를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-162">It is important to select the local computer and not an entry for any domains or networks that are listed.</span></span> <span data-ttu-id="daf8d-163">사용자가 컴퓨터를 선택한 후 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-163">After you have selected the computer, click **OK**.</span></span>  
  
8.  <span data-ttu-id="daf8d-164">클릭 **지금 찾기**합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-164">Click **Find Now**.</span></span> <span data-ttu-id="daf8d-165">그러면 검색 결과가 로컬 컴퓨터와 연결된 개체로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-165">This populates the search results with objects associated with the local computer.</span></span>  
  
9. <span data-ttu-id="daf8d-166">찾을 **IIS_IUSRS** 항목에는 **이름 (상대 고유 이름)** 열입니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-166">Find the **IIS_IUSRS** entry in the **Name (Relative Distinguished Name)** column.</span></span> <span data-ttu-id="daf8d-167">항목을 선택 하 고 클릭 **확인** 결과 창을 닫으려면 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-167">Select that entry and click **OK** to close the search results window.</span></span>  
  
10. <span data-ttu-id="daf8d-168">클릭 **확인** 를 닫으려면는 **사용자 또는 그룹 선택** 창.</span><span class="sxs-lookup"><span data-stu-id="daf8d-168">Click **OK** to close the **Select Users or Groups** window.</span></span>  
  
11. <span data-ttu-id="daf8d-169">클릭 **공유** 의 변경 사항을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-169">Click **Share** to persist the changes.</span></span>  
  
12. <span data-ttu-id="daf8d-170">공유할 수 있도록 변경이 완료 후 클릭 **수행** 를 닫으려면는 **파일 공유** 창.</span><span class="sxs-lookup"><span data-stu-id="daf8d-170">After the changes to enable sharing are complete, click **Done** to close the **File Sharing** window.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-51-or-60"></a><span data-ttu-id="daf8d-171">IIS 5.1 또는 6.0에서 폴더의 보안 속성을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="daf8d-171">To set security properties of the folder in IIS 5.1 or 6.0</span></span>  
  
1.  <span data-ttu-id="daf8d-172">%SystemDrive%\inetpub\wwwroot\servicemodelsamples로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-172">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2.  <span data-ttu-id="daf8d-173">마우스 오른쪽 단추로 클릭는 **servicemodelsamples** 폴더와 클릭 **공유 및 보안 합니다.**</span><span class="sxs-lookup"><span data-stu-id="daf8d-173">Right-click the **servicemodelsamples** folder and then click **Sharing and Security.**</span></span>  
  
3.  <span data-ttu-id="daf8d-174">**보안** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-174">Click the **Security** tab.</span></span>  
  
4.  <span data-ttu-id="daf8d-175">IIS 6.0을 사용 하는 경우는 **그룹 또는 사용자 이름** 상자에서 확인 여부 **인터넷 게스트 계정** 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-175">If you are using IIS 6.0, in the **Group or user names** box, check whether **Internet Guest Account** is listed.</span></span>  
  
     <span data-ttu-id="daf8d-176">인터넷 게스트 계정이 표시되어 있지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="daf8d-176">If it is not listed:</span></span>  
  
    1.  <span data-ttu-id="daf8d-177">클릭 **시작** 클릭 하 고 **제어판**합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-177">Click **Start** and then click **Control Panel**.</span></span>  
  
    2.  <span data-ttu-id="daf8d-178">표시 되지 않으면는 **사용자 계정** 아이콘을 클릭 하 여 **종류별 보기로 전환**합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-178">If you do not see the **User Accounts** icon, click **Switch to Category View**.</span></span>  
  
    3.  <span data-ttu-id="daf8d-179">클릭는 **사용자 계정** 아이콘입니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-179">Click the **User Accounts** icon.</span></span>  
  
    4.  <span data-ttu-id="daf8d-180">아래에서 "또는 제어판 아이콘 선택" 클릭 **사용자 계정**합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-180">Under "or pick a Control Panel icon," click **User Accounts**.</span></span>  
  
    5.  <span data-ttu-id="daf8d-181">에 **사용자 계정** 대화 상자를 클릭는 **고급** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-181">In the **User Accounts** dialog box, click the **Advanced** tab.</span></span>  
  
    6.  <span data-ttu-id="daf8d-182">**고급**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-182">Click **Advanced**.</span></span>  
  
    7.  <span data-ttu-id="daf8d-183">에 **로컬 사용자 및 그룹** 대화 상자를 클릭 하 여 확장 하 고는 **사용자** 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-183">In the **Local Users and Groups** dialog box, click to expand the **Users** folder.</span></span>  
  
    8.  <span data-ttu-id="daf8d-184">오른쪽 창에서 두 번 클릭 **인터넷 게스트 계정**합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-184">In the right pane, double-click **Internet Guest Account**.</span></span>  
  
    9. <span data-ttu-id="daf8d-185">에 **속성** 이름이 인터넷 게스트 계정으로 사용 대화 상자, 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-185">In the **Properties** dialog box, copy the name used as the Internet guest account.</span></span> <span data-ttu-id="daf8d-186">기본적으로 이름은 "USR_" 다음에 컴퓨터의 이름이 옵니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-186">By default, the name begins with "USR_" followed by the name of the computer.</span></span>  
  
    10. <span data-ttu-id="daf8d-187">**속성** 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-187">Close the **Properties** dialog box.</span></span>  
  
    11. <span data-ttu-id="daf8d-188">닫기는 **로컬 사용자 및 그룹** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="daf8d-188">Close the **Local Users and Groups** dialog box.</span></span>  
  
    12. <span data-ttu-id="daf8d-189">닫기는 **사용자 계정** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="daf8d-189">Close the **User Accounts** dialog box.</span></span>  
  
    13. <span data-ttu-id="daf8d-190">다른 닫습니다 **사용자 계정** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="daf8d-190">Close the other **User Accounts** dialog box.</span></span>  
  
    14. <span data-ttu-id="daf8d-191">에 **servicemodelsamples 속성** 대화 상자의 **보안** 탭을 클릭 **추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-191">In the **servicemodelsamples Properties** dialog box, on the **Security** tab, click **Add**.</span></span>  
  
    15. <span data-ttu-id="daf8d-192">뒤에 백슬래시가 오는 컴퓨터의 이름을 입력 하 고 예를 들어 myMachineName 인터넷 사용자 계정의 이름을 붙여\\% InternetGuestAccountName %</span><span class="sxs-lookup"><span data-stu-id="daf8d-192">Type the name of the computer followed by a backslash, then paste the name of the Internet user account, for example, myMachineName\\%InternetGuestAccountName%</span></span>  
  
    16. <span data-ttu-id="daf8d-193">클릭 **이름 확인** 에 추가 된 내용을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-193">Click **Check Names** to verify the addition.</span></span> <span data-ttu-id="daf8d-194">이름이 올바른 경우 모두 밑줄이 있는 대문자입니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-194">If it is valid, the name is in all capital letters and is underlined.</span></span>  
  
5.  <span data-ttu-id="daf8d-195">IIS 6.0에 대해서도 확인 네트워크 서비스에 나열 되어 있는지는 **그룹 또는 사용자 이름** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-195">For IIS 6.0, also check that NETWORK SERVICE is listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="daf8d-196">NETWORK SERVICE가 표시되어 있지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="daf8d-196">If NETWORK SERVICE is not listed:</span></span>  
  
    1.  <span data-ttu-id="daf8d-197">**추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-197">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="daf8d-198">에 **사용자 또는 그룹 선택** 컴퓨터의 이름 뒤에 백슬래시가 오는 대화 상자를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-198">In the **Select Users or Groups** dialog box, type the name of the computer followed by a backslash.</span></span>  
  
    3.  <span data-ttu-id="daf8d-199">형식 **서비스** 뒤의 백슬래시 (공백 없음).</span><span class="sxs-lookup"><span data-stu-id="daf8d-199">Type **service** after the backslash (no space).</span></span>  
  
    4.  <span data-ttu-id="daf8d-200">클릭 **이름 확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-200">Click **Check names**.</span></span>  
  
    5.  <span data-ttu-id="daf8d-201">이름이 여러 개 있는 경우 선택 **네트워크 서비스** 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-201">If multiple names are found, select **NETWORK SERVICE** and click **OK**.</span></span>  
  
    6.  <span data-ttu-id="daf8d-202">클릭 **확인** 를 닫으려면는 **사용자 또는 그룹 선택** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="daf8d-202">Click **OK** to close the **Select Users or Groups** dialog box.</span></span>  
  
6.  <span data-ttu-id="daf8d-203">IIS 5.1과 Windows XP s p 2를 사용 하는 경우 인터넷 게스트 계정 및 ASPNET 모두에 나열 되어 있는지 확인은 **그룹 또는 사용자 이름** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-203">If you are using Windows XP SP2 with IIS 5.1, check that both Internet Guest Account and ASPNET are listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="daf8d-204">ASPNET 사용자는 멤버의 기본 제공 될 수 있습니다 **사용자** 보안 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-204">Note that the ASPNET user may be a member of the built-in **Users** security group.</span></span> <span data-ttu-id="daf8d-205">이 경우 다음 경우는 **사용자** 그룹 대화 상자에 표시 됩니다, 허용 된 사용자 목록에 별도 항목으로 추가할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-205">If so, then if the **Users** group is listed in the dialog box, you do not need to add it as a separate item to the list of permitted users.</span></span>  
  
     <span data-ttu-id="daf8d-206">ASPNET의 일부 인지 확인 하기는 **사용자** 보안 그룹:</span><span class="sxs-lookup"><span data-stu-id="daf8d-206">To check if ASPNET is part of the **Users** security group:</span></span>  
  
    1.  <span data-ttu-id="daf8d-207">에 **시작** 메뉴를 클릭 하 여 **제어판**합니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-207">On the **Start** menu, click **Control Panel**.</span></span>  
  
    2.  <span data-ttu-id="daf8d-208">클릭는 **사용자 계정** 아이콘입니다.</span><span class="sxs-lookup"><span data-stu-id="daf8d-208">Click the **User Accounts** icon.</span></span>  
  
    3.  <span data-ttu-id="daf8d-209">에 **그룹** 열에 있는지 여부를 확인에 대 한 값 **ASPNET** 가 "Users"</span><span class="sxs-lookup"><span data-stu-id="daf8d-209">In the **Group** column, check that the value for **ASPNET** is "Users."</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daf8d-210">참고 항목</span><span class="sxs-lookup"><span data-stu-id="daf8d-210">See Also</span></span>  
 [<span data-ttu-id="daf8d-211">인터넷 정보 서비스 호스팅 지침</span><span class="sxs-lookup"><span data-stu-id="daf8d-211">Internet Information Service Hosting Instructions</span></span>](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)
