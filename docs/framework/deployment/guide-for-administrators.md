---
title: "관리자를 위한 .NET Framework 배포 가이드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- administrator's guide, deploying .NET Framework
- deployment [.NET Framework], administrator's guide
ms.assetid: bee14036-0436-44e8-89f5-4bc61317977a
caps.latest.revision: "40"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3af5e301e57350b72ac0ea50448c7a46ca6c5387
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="net-framework-deployment-guide-for-administrators"></a><span data-ttu-id="f672e-102">관리자를 위한 .NET Framework 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="f672e-102">.NET Framework Deployment Guide for Administrators</span></span>
<span data-ttu-id="f672e-103">이 단계별 문서에서는 시스템 관리자가 Microsoft System Center Configuration Manager를 사용하여 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 및 해당 시스템 종속성을 네트워크 전체에 배포할 수 있는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-103">This step-by-step article describes how a system administrator can deploy the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] and its system dependencies across a network by using Microsoft System Center Configuration Manager.</span></span> <span data-ttu-id="f672e-104">이 문서에서는 .NET Framework 4의 최소 요구 사항이 모든 대상 클라이언트 컴퓨터에서 충족되는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-104">This article assumes that all target client computers meet the minimum requirements for the .NET Framework.</span></span> <span data-ttu-id="f672e-105">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 설치를 위한 소프트웨어와 하드웨어 요구 사항 목록은 [시스템 요구 사항](../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f672e-105">For a list of the software and hardware requirements for installing the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], see [System Requirements](../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f672e-106">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)], System Center Configuration Manager 및 Active Directory를 비롯하여 이 문서에서 언급된 소프트웨어에는 각각 사용권 계약 내용이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-106">The software referenced in this document, including, without limitation, the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], System Center Configuration Manager, and Active Directory, are each subject to license terms and conditions.</span></span> <span data-ttu-id="f672e-107">이 지침에서는 적절한 소프트웨어 라이선스로 이러한 사용권 계약 내용을 검토하고 이에 동의했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-107">These instructions assume that such license terms and conditions have been reviewed and accepted by the appropriate licensees of the software.</span></span> <span data-ttu-id="f672e-108">이 지침에서는 이러한 사용권 계약의 어떠한 내용도 배제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-108">These instructions do not waive any of the terms and conditions of such license agreements.</span></span>  
>   
>  <span data-ttu-id="f672e-109">.NET Framework 지원에 대한 자세한 내용은 Microsoft 지원 웹 사이트의 [Microsoft .NET Framework 지원 기간 정책](http://go.microsoft.com/fwlink/?LinkId=196607)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f672e-109">For information about support for the .NET Framework, see [Microsoft .NET Framework Support Lifecycle Policy](http://go.microsoft.com/fwlink/?LinkId=196607) on the Microsoft Support website.</span></span>  
  
 <span data-ttu-id="f672e-110">이 항목에는 다음과 같은 단원이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-110">This topic contains the following sections:</span></span>  
  
 [<span data-ttu-id="f672e-111">배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="f672e-111">The deployment process</span></span>](#the_deployment_process)  
 [<span data-ttu-id="f672e-112">.NET Framework 배포</span><span class="sxs-lookup"><span data-stu-id="f672e-112">Deploying the .NET Framework</span></span>](#deploying_in_a_test_environment)  
 [<span data-ttu-id="f672e-113">컬렉션 만들기</span><span class="sxs-lookup"><span data-stu-id="f672e-113">Create a collection</span></span>](#creating_a_collection)  
 [<span data-ttu-id="f672e-114">패키지 및 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="f672e-114">Create a package and program</span></span>](#creating_a_package)  
 [<span data-ttu-id="f672e-115">배포 지점 선택</span><span class="sxs-lookup"><span data-stu-id="f672e-115">Select a distribution point</span></span>](#select_dist_point)  
 [<span data-ttu-id="f672e-116">패키지 배포</span><span class="sxs-lookup"><span data-stu-id="f672e-116">Deploy the package</span></span>](#deploying_package)  
[<span data-ttu-id="f672e-117">리소스</span><span class="sxs-lookup"><span data-stu-id="f672e-117">Resources</span></span>](#resources)  
[<span data-ttu-id="f672e-118">문제 해결</span><span class="sxs-lookup"><span data-stu-id="f672e-118">Troubleshooting</span></span>](#troubleshooting)  
  
<a name="the_deployment_process"></a>   
## <a name="the-deployment-process"></a><span data-ttu-id="f672e-119">배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="f672e-119">The deployment process</span></span>  
 <span data-ttu-id="f672e-120">지원 인프라가 갖춰진 경우 System Center 2012 Configuration Manager를 사용하여 .NET Framework 재배포 가능 패키지를 네트워크 상의 컴퓨터에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-120">When you have the supporting infrastructure in place, you use System Center 2012 Configuration Manager to deploy the .NET Framework redistributable package to computers on the network.</span></span> <span data-ttu-id="f672e-121">인프라 구축에는 컬렉션, 소프트웨어에 대한 패키지와 프로그램, 배포 지점, 배포의 5가지 주요 영역을 만들고 정의하는 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-121">Building the infrastructure involves creating and defining five primary areas: collections, a package and program for the software, distribution points, and deployments.</span></span>  
  
-   <span data-ttu-id="f672e-122">**컬렉션**은 .NET Framework가 배포되는 대상인 사용자, 사용자 그룹 또는 컴퓨터와 같은 Configuration Manager 리소스 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-122">**Collections** are groups of Configuration Manager resources, such as users, user groups, or computers, to which the .NET Framework is deployed.</span></span> <span data-ttu-id="f672e-123">자세한 내용은 Configuration Manager 문서 라이브러리의 [Configuration Manager의 컬렉션](http://technet.microsoft.com/library/gg682169.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f672e-123">For more information, see [Collections in Configuration Manager](http://technet.microsoft.com/library/gg682169.aspx) in the Configuration Manager documentation library.</span></span>  
  
-   <span data-ttu-id="f672e-124">**패키지 및 프로그램**은 보통 클라이언트 컴퓨터에 설치할 소프트웨어 응용 프로그램을 나타내지만, 개별 파일, 업데이트 또는 개별 명령까지도 들어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-124">**Packages and programs** typically represent software applications to be installed on a client computer, but they might also contain individual files, updates, or even individual commands.</span></span> <span data-ttu-id="f672e-125">자세한 내용은 Configuration Manager 문서 라이브러리에서 [Configuration Manager의 패키지와 프로그램](http://technet.microsoft.com/library/gg699369.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f672e-125">For more information, see [Packages and Programs in Configuration Manager](http://technet.microsoft.com/library/gg699369.aspx) in the Configuration Manager documentation library.</span></span>  
  
-   <span data-ttu-id="f672e-126">**배포 지점**은 클라이언트 컴퓨터에서 실행할 소프트웨어에 필요한 파일을 저장하는 Configuration Manager 사이트 시스템 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-126">**Distribution points** are Configuration Manager site system roles that store files required for software to run on client computers.</span></span> <span data-ttu-id="f672e-127">Configuration Manager 클라이언트가 소프트웨어 배포를 수신하고 처리할 때, 이 클라이언트는 배포 지점에 연결하여 소프트웨어와 연결된 콘텐츠를 다운로드하고 설치 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-127">When the Configuration Manager client receives and processes a software deployment, it contacts a distribution point to download the content associated with the software and to start the installation process.</span></span> <span data-ttu-id="f672e-128">자세한 내용은 Configuration Manager 문서 라이브러리에서 [Configuration Manager의 콘텐츠 관리 소개](http://technet.microsoft.com/library/gg682083.aspx)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f672e-128">For more information, see [Introduction to content Management in Configuration Manager](http://technet.microsoft.com/library/gg682083.aspx) in the Configuration Manager documentation library.</span></span>  
  
-   <span data-ttu-id="f672e-129">**배포**에서는 지정된 대상 컬렉션의 적절한 멤버에게 소프트웨어 패키지를 설치하라고 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-129">**Deployments** instruct applicable members of the specified target collection to install the software package.</span></span> <span data-ttu-id="f672e-130">자세한 내용은 Configuration Manager 문서 라이브러리에서 [Configuration Manager에 응용 프로그램을 배포하는 방법](http://technet.microsoft.com/library/gg682082.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f672e-130">For more information, see [How to Deploy Applications in Configuration Manager](http://technet.microsoft.com/library/gg682082.aspx) in the Configuration Manager documentation library.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f672e-131">이 항목의 절차에는 패키지와 프로그램을 만들고 배포하기 위한 일반적인 설정이 포함되어 있고, 가능한 모든 설정이 다루어지지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-131">The procedures in this topic contain typical settings for creating and deploying a package and program, and might not cover all possible settings.</span></span> <span data-ttu-id="f672e-132">다른 Configuration Manager 배포 옵션은 [Configuration Manager 문서 라이브러리](http://technet.microsoft.com/library/gg682041.aspx)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f672e-132">For other Configuration Manager deployment options, see the [Configuration Manager Documentation Library](http://technet.microsoft.com/library/gg682041.aspx).</span></span>  
  
<a name="deploying_in_a_test_environment"></a>   
## <a name="deploying-the-net-framework"></a><span data-ttu-id="f672e-133">.NET Framework 배포</span><span class="sxs-lookup"><span data-stu-id="f672e-133">Deploying the .NET Framework</span></span>  
 <span data-ttu-id="f672e-134">System Center 2012 Configuration Manager를 사용하여 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]의 자동 설치를 배포할 수 있고, 이 경우 사용자는 설치 프로세스와 상호 작용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-134">You can use System Center 2012 Configuration Manager to deploy a silent installation of the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], where the users do not interact with the installation process.</span></span> <span data-ttu-id="f672e-135">아래 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-135">Follow these steps:</span></span>  
  
1.  <span data-ttu-id="f672e-136">[컬렉션을 만듭니다](#creating_a_collection).</span><span class="sxs-lookup"><span data-stu-id="f672e-136">[Create a collection](#creating_a_collection).</span></span>  
  
2.  <span data-ttu-id="f672e-137">[.NET Framework 재배포 가능 패키지와 프로그램을 만듭니다](#creating_a_package).</span><span class="sxs-lookup"><span data-stu-id="f672e-137">[Create a package and program for the .NET Framework redistributable](#creating_a_package).</span></span>  
  
3.  <span data-ttu-id="f672e-138">[배포 지점을 선택합니다](#select_dist_point).</span><span class="sxs-lookup"><span data-stu-id="f672e-138">[Select a distribution point](#select_dist_point).</span></span>  
  
4.  <span data-ttu-id="f672e-139">[패키지를 배포합니다](#deploying_package).</span><span class="sxs-lookup"><span data-stu-id="f672e-139">[Deploy the package](#deploying_package).</span></span>  
  
<a name="creating_a_collection"></a>   
### <a name="create-a-collection"></a><span data-ttu-id="f672e-140">컬렉션 만들기</span><span class="sxs-lookup"><span data-stu-id="f672e-140">Create a collection</span></span>  
 <span data-ttu-id="f672e-141">이 단계에서는 패키지와 프로그램을 배포할 컴퓨터를 선택하고 이런 컴퓨터를 장치 컬렉션으로 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-141">In this step, you select the computers to which you will deploy the package and program, and group them into a device collection.</span></span> <span data-ttu-id="f672e-142">Configuration Manager에서 컬렉션을 만들려면 직접 멤버 자격 규칙(컬렉션 멤버를 수동으로 지정함) 또는 쿼리 규칙(사용자가 지정하는 기준을 바탕으로 Configuration Manager가 컬렉션 멤버를 결정함)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-142">To create a collection in Configuration Manager, you can use direct membership rules (where you manually specify the collection members) or query rules (where Configuration Manager determines the collection members based on criteria you specify).</span></span> <span data-ttu-id="f672e-143">쿼리와 직접 규칙을 포함한 멤버 자격 규칙에 대한 자세한 내용은 Configuration Manager 문서 라이브러리에서 [Configuration Manager의 컬렉션 소개](http://technet.microsoft.com/library/gg682177.aspx)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f672e-143">For more information about membership rules, including queries and direct rules, see [Introduction to Collections in Configuration Manager](http://technet.microsoft.com/library/gg682177.aspx) in the Configuration Manager Documentation Library.</span></span>  
  
 <span data-ttu-id="f672e-144">컬렉션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="f672e-144">To create a collection:</span></span>  
  
1.  <span data-ttu-id="f672e-145">Configuration Manager 콘솔에서 **자산 및 준수**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-145">In the Configuration Manager console, choose **Assets and Compliance**.</span></span>  
  
2.  <span data-ttu-id="f672e-146">**자산 및 준수** 작업 영역에서 **장치 컬렉션**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-146">In the **Assets and Compliance** workspace, choose **Device Collections**.</span></span>  
  
3.  <span data-ttu-id="f672e-147">**만들기** 그룹의 **홈** 탭에서 **장치 컬렉션 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-147">On the **Home** tab in the **Create** group, choose **Create Device Collection**.</span></span>  
  
4.  <span data-ttu-id="f672e-148">**장치 컬렉션 만들기 마법사**의 **일반** 페이지에서 컬렉션 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-148">On the **General** page of the **Create Device Collection Wizard**, enter a name for the collection.</span></span>  
  
5.  <span data-ttu-id="f672e-149">**찾아보기**를 선택하여 제한 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-149">Choose **Browse** to specify a limiting collection.</span></span>  
  
6.  <span data-ttu-id="f672e-150">**멤버 자격 규칙** 페이지에서 **규칙 추가**를 선택한 다음 **직접 규칙**을 선택하여 **직접 멤버 자격 규칙 만들기 마법사**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-150">On the **Membership Rules** page, choose **Add Rule**, and then choose **Direct Rule** to open the **Create Direct Membership Rule Wizard**.</span></span> <span data-ttu-id="f672e-151">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-151">Choose **Next**.</span></span>  
  
7.  <span data-ttu-id="f672e-152">**리소스 검색** 페이지의 **리소스 클래스** 목록에서 **시스템 리소스**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-152">On the **Search for Resources** page, in the **Resource class** list, choose **System Resource**.</span></span> <span data-ttu-id="f672e-153">**특성 이름** 목록에서 **이름**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-153">In the **Attribute name** list, choose **Name**.</span></span> <span data-ttu-id="f672e-154">**값** 필드에 `%`를 입력하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-154">In the **Value** field, enter `%`, and then choose **Next**.</span></span>  
  
8.  <span data-ttu-id="f672e-155">**리소스 선택** 페이지에서 .NET Framework를 배포할 각 컴퓨터에 대한 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-155">On the **Select Resources** page, select the check box for each computer that you want to deploy the .NET Framework to.</span></span> <span data-ttu-id="f672e-156">**다음**을 선택한 후 마법사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-156">Choose **Next**, and then complete the wizard.</span></span>  
  
9. <span data-ttu-id="f672e-157">**장치 컬렉션 만들기 마법사**의 **멤버 자격 규칙** 페이지에서 **다음**을 선택한 후 마법사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-157">On the **Membership Rules** page of the **Create Device Collection Wizard**, choose **Next**, and then complete the wizard.</span></span>  
  
 <span data-ttu-id="f672e-158">컬렉션에 대한 자세한 내용은 Configuration Manager 문서 라이브러리에서 [Configuration Manager의 컬렉션](http://technet.microsoft.com/library/bb693730.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f672e-158">For more information about collections, see [Collections in Configuration Manager](http://technet.microsoft.com/library/bb693730.aspx) in the Configuration Manager Documentation Library.</span></span>  
  
<a name="creating_a_package"></a>   
### <a name="create-a-package-and-program-for-the-net-framework-redistributable-package"></a><span data-ttu-id="f672e-159">.NET Framework 재배포 가능 패키지에 대한 프로그램과 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-159">Create a package and program for the .NET Framework redistributable package</span></span>  
 <span data-ttu-id="f672e-160">다음 단계에서는 .NET Framework 재배포 가능 패키지를 수동으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-160">The following steps create a package for the .NET Framework redistributable manually.</span></span> <span data-ttu-id="f672e-161">이 패키지에는 .NET Framework를 설치하기 위해 지정된 매개 변수와 패키지가 대상 컴퓨터에 배포될 시작 위치가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-161">The package contains the specified parameters for installing the .NET Framework and the location from where the package will be distributed to the target computers.</span></span>  
  
 <span data-ttu-id="f672e-162">패키지를 만들려면</span><span class="sxs-lookup"><span data-stu-id="f672e-162">To create a package:</span></span>  
  
1.  <span data-ttu-id="f672e-163">Configuration Manager 콘솔에서 **소프트웨어 라이브러리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-163">In the Configuration Manager console, choose **Software Library**..</span></span>  
  
2.  <span data-ttu-id="f672e-164">**소프트웨어 라이브러리** 작업 영역에서 **응용 프로그램 관리**를 확장한 후 **패키지**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-164">In the **Software Library** workspace, expand **Application Management**, and then choose **Packages**.</span></span>  
  
3.  <span data-ttu-id="f672e-165">**홈** 탭의 **만들기** 그룹에서 **패키지 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-165">On the **Home** tab, in the **Create** group, choose **Create Package**.</span></span>  
  
4.  <span data-ttu-id="f672e-166">**패키지 및 프로그램 만들기 마법사**의 **패키지** 페이지에서 다음 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-166">On the **Package** page of the **Create Package and Program Wizard**, enter the following information:</span></span>  
  
    -   <span data-ttu-id="f672e-167">이름: `.NET Framework 4.5`</span><span class="sxs-lookup"><span data-stu-id="f672e-167">Name: `.NET Framework 4.5`</span></span>  
  
    -   <span data-ttu-id="f672e-168">제조업체: `Microsoft`</span><span class="sxs-lookup"><span data-stu-id="f672e-168">Manufacturer: `Microsoft`</span></span>  
  
    -   <span data-ttu-id="f672e-169">Language:</span><span class="sxs-lookup"><span data-stu-id="f672e-169">Language.</span></span> `English (US)`  
  
5.  <span data-ttu-id="f672e-170">**이 패키지에 소스 파일이 포함됨**을 선택한 후 **찾아보기**를 선택하여 .NET Framework 설치 파일이 들어 있는 로컬 또는 네트워크 폴더를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-170">Choose **This package contains source files**, and then choose **Browse** to select the local or network folder that contains the .NET Framework installation files.</span></span> <span data-ttu-id="f672e-171">폴더를 선택했으면 **확인**을 선택한 후 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-171">When you have selected the folder, choose **OK**, and then choose **Next**.</span></span>  
  
6.  <span data-ttu-id="f672e-172">마법사의 **프로그램 형식** 페이지에서 **표준 프로그램**을 선택한 후 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-172">On the **Program Type** page of the wizard, choose **Standard Program**, and then choose **Next**.</span></span>  
  
7.  <span data-ttu-id="f672e-173">**패키지 및 프로그램 만들기 마법사**의 **프로그램** 페이지에서 다음 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-173">On the **Program** page of the **Create Package and Program Wizard**, enter the following information:</span></span>  
  
    1.  <span data-ttu-id="f672e-174">**이름:** `.NET Framework 4.5`</span><span class="sxs-lookup"><span data-stu-id="f672e-174">**Name:** `.NET Framework 4.5`</span></span>  
  
    2.  <span data-ttu-id="f672e-175">**명령줄:** `dotNetFx45_Full_x86_x64.exe /q /norestart /ChainingPackage ADMINDEPLOYMENT`(명령줄 옵션은 이러한 단계 뒤에 나오는 표에 설명되어 있음)</span><span class="sxs-lookup"><span data-stu-id="f672e-175">**Command line:** `dotNetFx45_Full_x86_x64.exe /q /norestart /ChainingPackage ADMINDEPLOYMENT` (command-line options are described in the table after these steps)</span></span>  
  
    3.  <span data-ttu-id="f672e-176">**실행:** **숨김**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-176">**Run:** Choose **Hidden**.</span></span>  
  
    4.  <span data-ttu-id="f672e-177">**프로그램을 실행할 수 있음:** 사용자의 로그온 여부에 상관없이 프로그램을 실행할 수 있도록 지정하는 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-177">**Program can run:** Choose the option that specifies that the program can run regardless of whether a user is logged on.</span></span>  
  
8.  <span data-ttu-id="f672e-178">**요구 사항** 페이지에서 **다음**을 선택하여 기본값을 수락한 후 마법사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-178">On the **Requirements** page, choose **Next** to accept the default values, and then complete the wizard.</span></span>  
  
 <span data-ttu-id="f672e-179">다음 표에는 7단계에서 지정한 명령줄 옵션이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-179">The following table describes the command-line options specified in step 7.</span></span>  
  
|<span data-ttu-id="f672e-180">옵션</span><span class="sxs-lookup"><span data-stu-id="f672e-180">Option</span></span>|<span data-ttu-id="f672e-181">설명</span><span class="sxs-lookup"><span data-stu-id="f672e-181">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="f672e-182">**/q**</span><span class="sxs-lookup"><span data-stu-id="f672e-182">**/q**</span></span>|<span data-ttu-id="f672e-183">자동 모드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-183">Sets quiet mode.</span></span> <span data-ttu-id="f672e-184">사용자 입력이 필요하지 않으며 아무런 출력도 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-184">No user input is required, and no output is shown.</span></span>|  
|<span data-ttu-id="f672e-185">**/norestart**</span><span class="sxs-lookup"><span data-stu-id="f672e-185">**/norestart**</span></span>|<span data-ttu-id="f672e-186">설치 프로그램이 자동으로 재부팅하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-186">Prevents the Setup program from rebooting automatically.</span></span> <span data-ttu-id="f672e-187">이 옵션을 사용하는 경우 Configuration Manager는 컴퓨터 다시 시작을 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-187">If you use this option, Configuration Manager must handle the computer restart.</span></span>|  
|<span data-ttu-id="f672e-188">**/chainingpackage** *PackageName*</span><span class="sxs-lookup"><span data-stu-id="f672e-188">**/chainingpackage** *PackageName*</span></span>|<span data-ttu-id="f672e-189">연결을 수행하는 패키지의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-189">Specifies the name of the package that is doing the chaining.</span></span> <span data-ttu-id="f672e-190">이 정보는 [Microsoft CEIP(사용자 환경 개선 프로그램)](http://go.microsoft.com/fwlink/p/?LinkId=248244)에 등록한 사용자에 대한 다른 설치 세션 정보와 함께 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-190">This information is reported with other installation session information for those who have signed up for the [Microsoft Customer Experience Improvement Program (CEIP)](http://go.microsoft.com/fwlink/p/?LinkId=248244).</span></span> <span data-ttu-id="f672e-191">패키지 이름에 공백이 포함되어 있으면 **/chainingpackage "Chaining Product"**와 같이 큰따옴표를 구분 기호로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-191">If the package name includes spaces, use double quotation marks as delimiters; for example: **/chainingpackage "Chaining Product"**.</span></span>|  
  
 <span data-ttu-id="f672e-192">위 단계를 통해 .NET Framework 4.5라는 이름의 패키지가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-192">These steps create a package named .NET Framework 4.5.</span></span> <span data-ttu-id="f672e-193">이 프로그램은 .NET Framework 4.5 자동 설치 프로그램을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-193">The program deploys a silent installation of the .NET Framework 4.5.</span></span> <span data-ttu-id="f672e-194">자동 설치에서 사용자는 설치 프로세스와 상호 작용하지 않으며 연결 응용 프로그램은 반환 코드를 캡처하고 재부팅을 처리해야 합니다. [설치 패키지에서 프로세스 진행 정보 가져오기](http://go.microsoft.com/fwlink/?LinkId=179606)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f672e-194">In a silent installation, users do not interact with the installation process, and the chaining application has to capture the return code and handle rebooting; see [Getting Progress Information from an Installation Package](http://go.microsoft.com/fwlink/?LinkId=179606).</span></span>  
 
<a name="select_dist_point"></a>   
### <a name="select-a-distribution-point"></a><span data-ttu-id="f672e-195">배포 지점 선택</span><span class="sxs-lookup"><span data-stu-id="f672e-195">Select a distribution point</span></span>  
 <span data-ttu-id="f672e-196">서버에서 클라이언트 컴퓨터에 패키지와 프로그램을 배포하려면 먼저 사이트 시스템을 배포 지점으로 지정한 다음 배포 지점에 패키지를 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-196">To distribute the package and program to client computers from a server, you must first designate a site system as a distribution point and then distribute the package to the distribution point.</span></span>  
  
 <span data-ttu-id="f672e-197">다음 단계에 따라 이전 섹션에서 만든 .NET Framework 4.5 패키지에 대한 배포 지점을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-197">Use the following steps to select a distribution point for the .NET Framework 4.5 package you created in the previous section:</span></span>  
  
1.  <span data-ttu-id="f672e-198">Configuration Manager 콘솔에서 **소프트웨어 라이브러리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-198">In the Configuration Manager console, choose **Software Library**.</span></span>  
  
2.  <span data-ttu-id="f672e-199">**소프트웨어 라이브러리** 작업 영역에서 **응용 프로그램 관리**를 확장한 후 **패키지**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-199">In the **Software Library** workspace, expand **Application Management**, and then choose **Packages**.</span></span>  
  
3.  <span data-ttu-id="f672e-200">패키지 목록에서 이전 섹션에서 만든 **.NET Framework 4.5** 패키지를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-200">From the list of packages, select the package **.NET Framework 4.5** that you created in the previous section.</span></span>  
  
4.  <span data-ttu-id="f672e-201">**홈** 탭의 **배포** 그룹에서 **콘텐츠 배포**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-201">On the **Home** tab, in the **Deployment** group, choose **Distribute Content**.</span></span>  
  
5.  <span data-ttu-id="f672e-202">**콘텐츠 배포 마법사**의 **일반** 탭에서 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-202">On the **General** tab of the **Distribute Content Wizard**, choose **Next**.</span></span>  
  
6.  <span data-ttu-id="f672e-203">마법사의 **콘텐츠 대상** 페이지에서 **추가**를 선택한 후 **배포 지점**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-203">On the **Content Destination** page of the wizard, choose **Add**, and then choose **Distribution Point**.</span></span>  
  
7.  <span data-ttu-id="f672e-204">**배포 지점 추가** 대화 상자에서 패키지와 프로그램을 호스트하는 배포 지점을 선택한 후 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-204">In the **Add Distribution Points** dialog box, select the distribution point(s) that will host the package and program, and then choose **OK**.</span></span>  
  
8.  <span data-ttu-id="f672e-205">마법사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-205">Complete the wizard.</span></span>  
  
 <span data-ttu-id="f672e-206">이제 패키지에는 .NET Framework 4.5를 자동으로 배포하는 데 필요한 모든 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-206">The packagenow contains all the information you need to silently deploy the .NET Framework 4.5.</span></span> <span data-ttu-id="f672e-207">패키지와 프로그램을 배포하기 전에 배포 지점에 .NET Framework 4.5가 설치되었는지 확인합니다. Configuration Manager 문서 라이브러리에서 [Configuration Manager에서 콘텐츠 관리를 위한 작업과 유지 관리](http://technet.microsoft.com/library/gg712694.aspx#BKMK_MonitorContent)의 "콘텐츠 모니터링" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f672e-207">Before you deploy the package and program, verify that it was installed on the distribution point; see the "Monitor Content" section of [Operations and Maintenance for Content Management in Configuration Manager](http://technet.microsoft.com/library/gg712694.aspx#BKMK_MonitorContent) in the Configuration Manager Documentation Library.</span></span>  
  
<a name="deploying_package"></a>   
### <a name="deploy-the-package"></a><span data-ttu-id="f672e-208">패키지 배포</span><span class="sxs-lookup"><span data-stu-id="f672e-208">Deploy the package</span></span>  
 <span data-ttu-id="f672e-209">.NET Framework 4.5 패키지와 프로그램을 배포하려면</span><span class="sxs-lookup"><span data-stu-id="f672e-209">To deploy the .NET Framework 4.5 package and program:</span></span>  
  
1.  <span data-ttu-id="f672e-210">Configuration Manager 콘솔에서 **소프트웨어 라이브러리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-210">In the Configuration Manager console, choose **Software Library**.</span></span>  
  
2.  <span data-ttu-id="f672e-211">**소프트웨어 라이브러리** 작업 영역에서 **응용 프로그램 관리**를 확장한 후 **패키지**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-211">In the **Software Library** workspace, expand **Application Management**, and then choose **Packages**.</span></span>  
  
3.  <span data-ttu-id="f672e-212">패키지 목록에서 **.NET Framework 4.5**로 명명하여 만든 패키지를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-212">From the list of packages, select the package you created named **.NET Framework 4.5**.</span></span>  
  
4.  <span data-ttu-id="f672e-213">**홈** 탭의 **배포** 그룹에서 **배포**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-213">On the **Home** tab, in the **Deployment** group, choose **Deploy**.</span></span>  
  
5.  <span data-ttu-id="f672e-214">**소프트웨어 배포 마법사**의 **일반** 페이지에서 **찾아보기**를 선택한 후 앞서 만든 컬렉션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-214">On the **General** page of the **Deploy Software Wizard**, choose **Browse**, and then select the collection that you created earlier.</span></span> <span data-ttu-id="f672e-215">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-215">Choose **Next**.</span></span>  
  
6.  <span data-ttu-id="f672e-216">마법사의 **콘텐츠** 페이지에서 소프트웨어를 배포하려는 시작 지점이 표시되는지 확인하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-216">On the **Content** page of the wizard, verify that the point from which you want to distribute the software is displayed, and then choose **Next**.</span></span>  
  
7.  <span data-ttu-id="f672e-217">마법사의 **배포 설정** 페이지에서 **작업**이 **설치**로, **용도**가 **필수**로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-217">On the **Deployment Settings** page of the wizard, confirm that **Action** is set to **Install**, and **Purpose** is set to **Required**.</span></span> <span data-ttu-id="f672e-218">이렇게 하면 소프트웨어 패키지가 대상으로 지정된 컴퓨터에 필수적으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-218">This ensures that the software package will be a mandatory installation on the targeted computers.</span></span> <span data-ttu-id="f672e-219">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-219">Choose **Next**.</span></span>  
  
8.  <span data-ttu-id="f672e-220">마법사의 **일정** 페이지에서 .NET Framework를 설치하려는 시점을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-220">On the **Scheduling** page of the wizard, specify when you want the .NET Framework to be installed.</span></span> <span data-ttu-id="f672e-221">**새로 만들기**를 선택하여 설치 시간을 지정하거나, 사용자가 로그온하거나 로그오프할 때, 또는 최대한 빨리 소프트웨어를 설치하도록 지시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-221">You can choose **New** to assign an installation time, or instruct the software to install when the user logs on or off, or as soon as possible.</span></span> <span data-ttu-id="f672e-222">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-222">Choose **Next**.</span></span>  
  
9. <span data-ttu-id="f672e-223">마법사의 **사용자 경험** 페이지에서 기본값을 사용하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-223">On the **User Experience** page of the wizard, use the default values and choose **Next**.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="f672e-224">프로덕션 환경에는 배포 일정에 대해 다른 선택 항목을 요구하는 정책이 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-224">Your production environment might have policies that require different selections for the deployment schedule.</span></span> <span data-ttu-id="f672e-225">이러한 옵션에 대한 자세한 내용은 TechNet 라이브러리의 [광고 이름 속성: 일정 탭](http://technet.microsoft.com/library/bb694016.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f672e-225">For information about these options, see [Advertisement Name Properties: Schedule Tab](http://technet.microsoft.com/library/bb694016.aspx) in the TechNet Library.</span></span>  
  
10. <span data-ttu-id="f672e-226">마법사의 **배포 지점** 페이지에서 기본값을 사용하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-226">On the **Distribution Points** page of the wizard, use the default values and choose **Next**.</span></span>  
  
11. <span data-ttu-id="f672e-227">마법사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-227">Complete the wizard.</span></span> <span data-ttu-id="f672e-228">**모니터링** 작업 영역의 **배포** 노드에서 배포의 진행 상태를 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-228">You can monitor the progress of the deployment in the **Deployments** node of the **Monitoring** workspace.</span></span>  
  
 <span data-ttu-id="f672e-229">이제 패키지는 대상 컬렉션으로 배포되고 .NET Framework 4.5의 자동 설치가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-229">The package will now be deployed to the targeted collection and the silent installation of .NET Framework 4.5 will begin.</span></span> <span data-ttu-id="f672e-230">.NET Framework 4.5 설치 오류 코드에 대한 자세한 내용은 이 항목의 뒷부분에 있는 [반환 코드](#return_codes) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f672e-230">For information about .NET Framework 4.5 installation error codes, see the [Return Codes](#return_codes) section later in this topic.</span></span>  
  
<a name="resources"></a>   
## <a name="resources"></a><span data-ttu-id="f672e-231">리소스</span><span class="sxs-lookup"><span data-stu-id="f672e-231">Resources</span></span>  
 <span data-ttu-id="f672e-232">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 재배포 가능 패키지의 배포 테스트를 위한 인프라에 대한 자세한 내용은 다음 자료를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f672e-232">For more information about the infrastructure for testing the deployment of the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] redistributable package, see the following resources.</span></span>  
  
 <span data-ttu-id="f672e-233">**Active Directory, DNS, DHCP:**</span><span class="sxs-lookup"><span data-stu-id="f672e-233">**Active Directory, DNS, DHCP:**</span></span>  
  
-   [<span data-ttu-id="f672e-234">Windows Server 2008용 Active Directory Domain Services</span><span class="sxs-lookup"><span data-stu-id="f672e-234">Active Directory Domain Services for Windows Server 2008</span></span>](http://technet.microsoft.com/library/dd378891.aspx)  
  
-   [<span data-ttu-id="f672e-235">DNS 서버</span><span class="sxs-lookup"><span data-stu-id="f672e-235">DNS Server</span></span>](http://technet.microsoft.com/library/cc732997.aspx)  
  
-   [<span data-ttu-id="f672e-236">DHCP 서버</span><span class="sxs-lookup"><span data-stu-id="f672e-236">DHCP Server</span></span>](http://technet.microsoft.com/library/cc896553.aspx)  
  
 <span data-ttu-id="f672e-237">**SQL Server 2008:**</span><span class="sxs-lookup"><span data-stu-id="f672e-237">**SQL Server 2008:**</span></span>  
  
-   [<span data-ttu-id="f672e-238">SQL Server 2008 설치(SQL Server 비디오)</span><span class="sxs-lookup"><span data-stu-id="f672e-238">Installing SQL Server 2008 (SQL Server Video)</span></span>](http://technet.microsoft.com/library/dd299415.aspx)  
  
-   [<span data-ttu-id="f672e-239">데이터베이스 관리자용 SQL Server 2008 보안 개요</span><span class="sxs-lookup"><span data-stu-id="f672e-239">SQL Server 2008 Security Overview for Database Administrators</span></span>](http://download.microsoft.com/download/a/c/d/acd8e043-d69b-4f09-bc9e-4168b65aaa71/SQL2008SecurityOverviewforAdmins.docx)  
  
 <span data-ttu-id="f672e-240">**System Center 2012 Configuration Manager(관리 지점, 배포 지점):**</span><span class="sxs-lookup"><span data-stu-id="f672e-240">**System Center 2012 Configuration Manager (Management Point, Distribution Point):**</span></span>  
  
-   [<span data-ttu-id="f672e-241">System Center 2012 Configuration Manager의 사이트 관리</span><span class="sxs-lookup"><span data-stu-id="f672e-241">Site Administration for System Center 2012 Configuration Manager</span></span>](http://technet.microsoft.com/library/gg681983.aspx)  
  
-   [<span data-ttu-id="f672e-242">Configuration Manager 단일 사이트 계획 및 배포</span><span class="sxs-lookup"><span data-stu-id="f672e-242">Configuration Manager Single Site Planning and Deployment</span></span>](http://technet.microsoft.com/library/bb680961.aspx)  
  
 <span data-ttu-id="f672e-243">**Windows 컴퓨터용 System Center 2012 Configuration Manager 클라이언트:**</span><span class="sxs-lookup"><span data-stu-id="f672e-243">**System Center 2012 Configuration Manager client for Windows computers:**</span></span>  
  
-   [<span data-ttu-id="f672e-244">System Center 2012 Configuration Manager용 클라이언트 배포</span><span class="sxs-lookup"><span data-stu-id="f672e-244">Deploying Clients for System Center 2012 Configuration Manager</span></span>](http://technet.microsoft.com/library/gg699391.aspx)  
  
<a name="troubleshooting"></a>   
## <a name="troubleshooting"></a><span data-ttu-id="f672e-245">문제 해결</span><span class="sxs-lookup"><span data-stu-id="f672e-245">Troubleshooting</span></span>  
  
### <a name="log-file-locations"></a><span data-ttu-id="f672e-246">로그 파일 위치</span><span class="sxs-lookup"><span data-stu-id="f672e-246">Log file locations</span></span>  
 <span data-ttu-id="f672e-247">다음 로그 파일은 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 설치 중에 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-247">The following log files are generated during [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] setup:</span></span>  
  
 <span data-ttu-id="f672e-248">%temp%\Microsoft .NET Framework 4.5\*.txt</span><span class="sxs-lookup"><span data-stu-id="f672e-248">%temp%\Microsoft .NET Framework 4.5\*.txt</span></span>  
 <span data-ttu-id="f672e-249">%temp%\Microsoft .NET Framework 4.5\\*.html</span><span class="sxs-lookup"><span data-stu-id="f672e-249">%temp%\Microsoft .NET Framework 4.5\\*.html</span></span>  
  
 <span data-ttu-id="f672e-250">[로그 수집 도구](http://www.microsoft.com/download/details.aspx?id=12493)를 사용하여 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 로그 파일을 수집하고 파일 크기를 줄여주는 압축된 캐비닛 파일(.cab)을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-250">You can use the [log collection tool](http://www.microsoft.com/download/details.aspx?id=12493) to collect the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] log files and to create a compressed cabinet (.cab) file that reduces the size of the files.</span></span>  
  
<a name="return_codes"></a>   
### <a name="return-codes"></a><span data-ttu-id="f672e-251">반환 코드</span><span class="sxs-lookup"><span data-stu-id="f672e-251">Return codes</span></span>  
 <span data-ttu-id="f672e-252">다음 표에서는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 재배포 가능 설치 프로그램의 가장 일반적인 반환 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-252">The following table lists the most common return codes from the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] redistributable installation program.</span></span> <span data-ttu-id="f672e-253">반환 코드는 설치 관리자 버전에 관계없이 모두 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-253">The return codes are the same for all versions of the installer.</span></span>  
  
 <span data-ttu-id="f672e-254">자세한 정보에 대한 링크는 다음 섹션인 [다운로드 오류 코드](#additional_error_codes)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f672e-254">For links to detailed information, see the next section, [Download error codes](#additional_error_codes).</span></span>  
  
|<span data-ttu-id="f672e-255">반환 코드</span><span class="sxs-lookup"><span data-stu-id="f672e-255">Return code</span></span>|<span data-ttu-id="f672e-256">설명</span><span class="sxs-lookup"><span data-stu-id="f672e-256">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="f672e-257">0</span><span class="sxs-lookup"><span data-stu-id="f672e-257">0</span></span>|<span data-ttu-id="f672e-258">설치되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-258">Installation completed successfully.</span></span>|  
|<span data-ttu-id="f672e-259">1602</span><span class="sxs-lookup"><span data-stu-id="f672e-259">1602</span></span>|<span data-ttu-id="f672e-260">사용자가 설치를 취소했습니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-260">The user canceled installation.</span></span>|  
|<span data-ttu-id="f672e-261">1603</span><span class="sxs-lookup"><span data-stu-id="f672e-261">1603</span></span>|<span data-ttu-id="f672e-262">설치하는 동안 심각한 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-262">A fatal error occurred during installation.</span></span>|  
|<span data-ttu-id="f672e-263">1641</span><span class="sxs-lookup"><span data-stu-id="f672e-263">1641</span></span>|<span data-ttu-id="f672e-264">설치를 완료하려면 컴퓨터를 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-264">A restart is required to complete the installation.</span></span> <span data-ttu-id="f672e-265">이 메시지는 설치가 성공적으로 수행되었음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-265">This message indicates success.</span></span>|  
|<span data-ttu-id="f672e-266">3010</span><span class="sxs-lookup"><span data-stu-id="f672e-266">3010</span></span>|<span data-ttu-id="f672e-267">설치를 완료하려면 컴퓨터를 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-267">A restart is required to complete the installation.</span></span> <span data-ttu-id="f672e-268">이 메시지는 설치가 성공적으로 수행되었음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-268">This message indicates success.</span></span>|  
|<span data-ttu-id="f672e-269">5100</span><span class="sxs-lookup"><span data-stu-id="f672e-269">5100</span></span>|<span data-ttu-id="f672e-270">사용자 컴퓨터가 시스템 요구 사항을 충족하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="f672e-270">The user's computer does not meet system requirements.</span></span>|  
  
<a name="additional_error_codes"></a>   
### <a name="download-error-codes"></a><span data-ttu-id="f672e-271">다운로드 오류 코드</span><span class="sxs-lookup"><span data-stu-id="f672e-271">Download error codes</span></span>  
  
-   [<span data-ttu-id="f672e-272">BITS(Background Intelligent Transfer Service) 오류 코드</span><span class="sxs-lookup"><span data-stu-id="f672e-272">Background Intelligent Transfer Service (BITS) error codes</span></span>](http://msdn.microsoft.com/library/aa362823.aspx)  
  
-   [<span data-ttu-id="f672e-273">URL 모니커 오류 코드</span><span class="sxs-lookup"><span data-stu-id="f672e-273">URL moniker error codes</span></span>](http://msdn.microsoft.com/library/ms775145.aspx)  
  
-   [<span data-ttu-id="f672e-274">WinHttp 오류 코드</span><span class="sxs-lookup"><span data-stu-id="f672e-274">WinHttp error codes</span></span>](http://msdn.microsoft.com/library/aa383770.aspx)  
  
 <span data-ttu-id="f672e-275">기타 오류 코드</span><span class="sxs-lookup"><span data-stu-id="f672e-275">Other error codes:</span></span>  
  
-   [<span data-ttu-id="f672e-276">Windows Installer 오류 코드</span><span class="sxs-lookup"><span data-stu-id="f672e-276">Windows Installer error codes</span></span>](http://msdn.microsoft.com/library/aa368542.aspx)  
  
-   [<span data-ttu-id="f672e-277">Windows 업데이트 에이전트 결과 코드</span><span class="sxs-lookup"><span data-stu-id="f672e-277">Windows Update Agent result codes</span></span>](http://technet.microsoft.com/library/cc720442.aspx)  
  
## <a name="see-also"></a><span data-ttu-id="f672e-278">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f672e-278">See Also</span></span>  
 [<span data-ttu-id="f672e-279">개발자를 위한 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="f672e-279">Deployment Guide for Developers</span></span>](../../../docs/framework/deployment/deployment-guide-for-developers.md)  
 [<span data-ttu-id="f672e-280">시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="f672e-280">System Requirements</span></span>](../../../docs/framework/get-started/system-requirements.md)
