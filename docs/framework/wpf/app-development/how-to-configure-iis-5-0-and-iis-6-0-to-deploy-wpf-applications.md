---
title: "방법: IIS 5.0 및 IIS 6.0을 구성하여 WPF 응용 프로그램 배포"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MIME types [WPF], registering
- adjusting content expiration setting [WPF]
- registering file extensions [WPF]
- deploying applications [WPF]
- applications [WPF], deploying
- Web servers [WPF], configuring to deploy WPF applications
- configuring Web servers to deploy WPF applications [WPF]
- content expiration setting [WPF], adjusting
- file extensions [WPF], registering
- registering MIME types [WPF]
ms.assetid: c6e8c2cb-9ba2-4e75-a0d5-180ec9639433
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: faff58f146aed7b309674157a5990cbce43dfb1f
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-configure-iis-50-and-iis-60-to-deploy-wpf-applications"></a><span data-ttu-id="60a04-102">방법: IIS 5.0 및 IIS 6.0을 구성하여 WPF 응용 프로그램 배포</span><span class="sxs-lookup"><span data-stu-id="60a04-102">How to: Configure IIS 5.0 and IIS 6.0 to Deploy WPF Applications</span></span>
<span data-ttu-id="60a04-103">적절한 [!INCLUDE[TLA#tla_mime](../../../../includes/tlasharptla-mime-md.md)] 형식으로 구성된 경우 대부분의 웹 서버에서 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60a04-103">You can deploy a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application from most Web servers, as long as they are configured with the appropriate [!INCLUDE[TLA#tla_mime](../../../../includes/tlasharptla-mime-md.md)] types.</span></span> <span data-ttu-id="60a04-104">기본적으로 [!INCLUDE[TLA#tla_iis70](../../../../includes/tlasharptla-iis70-md.md)]는 이러한 [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] 형식으로 구성되지만 [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)]과 [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)]은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="60a04-104">By default, [!INCLUDE[TLA#tla_iis70](../../../../includes/tlasharptla-iis70-md.md)] is configured with these [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types, but [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] and [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] are not.</span></span>  
  
 <span data-ttu-id="60a04-105">이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램을 배포하도록 [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)]과 [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)]을 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="60a04-105">This topic describes how to configure [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] and [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] to deploy [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications.</span></span>  
  
  
> [!NOTE]
>  <span data-ttu-id="60a04-106">레지스트리에서 *UserAgent* 문자열을 확인하여 시스템에 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]가 설치되었는지 판별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60a04-106">You can check the *UserAgent* string in the registry to determine whether a system has [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] installed.</span></span> <span data-ttu-id="60a04-107">*UserAgent* 문자열을 검사하여 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]가 시스템에 설치되었는지 판별하는 스크립트 및 자세한 내용은 [.NET Framework 3.0 설치 여부 확인](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="60a04-107">For details and a script that examines the *UserAgent* string to determine whether [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] is installed on a system, see [Detect Whether the .NET Framework 3.0 Is Installed](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md).</span></span>  
  
<a name="content_expiration"></a>   
## <a name="adjust-the-content-expiration-setting"></a><span data-ttu-id="60a04-108">콘텐츠 만료 설정 조정</span><span class="sxs-lookup"><span data-stu-id="60a04-108">Adjust the Content Expiration Setting</span></span>  
 <span data-ttu-id="60a04-109">콘텐츠 만료 설정을 1분으로 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60a04-109">You should adjust the content expiration setting to 1 minute.</span></span> <span data-ttu-id="60a04-110">다음 절차에서는 [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)]로 이 작업을 수행하는 방법을 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="60a04-110">The following procedure outlines how to do this with [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)].</span></span>  
  
1.  <span data-ttu-id="60a04-111">**시작** 메뉴를 클릭하고 **관리 도구**를 가리킨 후 **IIS(인터넷 정보 서비스) 관리자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="60a04-111">Click the **Start** menu, point to **Administrative Tools**, and click **Internet Information Services (IIS) Manager**.</span></span> <span data-ttu-id="60a04-112">명령줄에서도 “%SystemRoot%\system32\inetsrv\iis.msc”로 이 응용 프로그램을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60a04-112">You can also launch this application from the command line with "%SystemRoot%\system32\inetsrv\iis.msc".</span></span>  
  
2.  <span data-ttu-id="60a04-113">**기본 웹 사이트** 노드가 표시될 때까지 [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)] 트리를 펼칩니다.</span><span class="sxs-lookup"><span data-stu-id="60a04-113">Expand the [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)] tree until you find the **Default Web site** node.</span></span>  
  
3.  <span data-ttu-id="60a04-114">**기본 웹 사이트**를 마우스 오른쪽 단추로 클릭하고 컨텍스트 메뉴에서 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="60a04-114">Right-click **Default Web site** and select **Properties** from the context menu.</span></span>  
  
4.  <span data-ttu-id="60a04-115">**HTTP 헤더** 탭을 선택하고 “콘텐츠 만료 사용”을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="60a04-115">Select the **HTTP Headers** tab and click "Enable Content Expiration".</span></span>  
  
5.  <span data-ttu-id="60a04-116">1분 후에 만료하도록 콘텐츠를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="60a04-116">Set the content to expire after 1 minute.</span></span>  
  
<a name="register_mime_types"></a>   
## <a name="register-mime-types-and-file-extensions"></a><span data-ttu-id="60a04-117">MIME 형식과 파일 확장명 등록</span><span class="sxs-lookup"><span data-stu-id="60a04-117">Register MIME Types and File Extensions</span></span>  
 <span data-ttu-id="60a04-118">클라이언트의 시스템에서 브라우저가 올바른 처리기를 로드할 수 있도록 여러 [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] 형식과 파일 확장명을 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60a04-118">You must register several [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types and file extensions so that the browser on the client's system can load the correct handler.</span></span> <span data-ttu-id="60a04-119">다음 형식을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60a04-119">You need to add the following types:</span></span>  
  
|<span data-ttu-id="60a04-120">확장명</span><span class="sxs-lookup"><span data-stu-id="60a04-120">Extension</span></span>|<span data-ttu-id="60a04-121">MIME 형식</span><span class="sxs-lookup"><span data-stu-id="60a04-121">MIME Type</span></span>|  
|---------------|---------------|  
|<span data-ttu-id="60a04-122">.manifest</span><span class="sxs-lookup"><span data-stu-id="60a04-122">.manifest</span></span>|<span data-ttu-id="60a04-123">application/manifest</span><span class="sxs-lookup"><span data-stu-id="60a04-123">application/manifest</span></span>|  
|<span data-ttu-id="60a04-124">.xaml</span><span class="sxs-lookup"><span data-stu-id="60a04-124">.xaml</span></span>|<span data-ttu-id="60a04-125">application/xaml+xml</span><span class="sxs-lookup"><span data-stu-id="60a04-125">application/xaml+xml</span></span>|  
|<span data-ttu-id="60a04-126">.application</span><span class="sxs-lookup"><span data-stu-id="60a04-126">.application</span></span>|<span data-ttu-id="60a04-127">application/x-ms-application</span><span class="sxs-lookup"><span data-stu-id="60a04-127">application/x-ms-application</span></span>|  
|<span data-ttu-id="60a04-128">.xbap</span><span class="sxs-lookup"><span data-stu-id="60a04-128">.xbap</span></span>|<span data-ttu-id="60a04-129">application/x-ms-xbap</span><span class="sxs-lookup"><span data-stu-id="60a04-129">application/x-ms-xbap</span></span>|  
|<span data-ttu-id="60a04-130">.deploy</span><span class="sxs-lookup"><span data-stu-id="60a04-130">.deploy</span></span>|<span data-ttu-id="60a04-131">application/octet-stream</span><span class="sxs-lookup"><span data-stu-id="60a04-131">application/octet-stream</span></span>|  
|<span data-ttu-id="60a04-132">.xps</span><span class="sxs-lookup"><span data-stu-id="60a04-132">.xps</span></span>|<span data-ttu-id="60a04-133">application/vnd.ms-xpsdocument</span><span class="sxs-lookup"><span data-stu-id="60a04-133">application/vnd.ms-xpsdocument</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="60a04-134">클라이언트 시스템에서 [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] 형식 또는 파일 확장명을 등록하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60a04-134">You do not need to register [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types or file extensions on client systems.</span></span> <span data-ttu-id="60a04-135">[!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)]를 설치할 때 자동으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="60a04-135">They are registered automatically when you install [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)].</span></span>  
  
 <span data-ttu-id="60a04-136">다음 [!INCLUDE[TLA#tla_visualbscrpt](../../../../includes/tlasharptla-visualbscrpt-md.md)] 샘플에서는 필수 [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] 형식을 [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)]에 자동으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="60a04-136">The following [!INCLUDE[TLA#tla_visualbscrpt](../../../../includes/tlasharptla-visualbscrpt-md.md)] sample automatically adds the necessary [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types to [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)].</span></span> <span data-ttu-id="60a04-137">스크립트를 사용하려면 서버에서 .vbs 파일을 코드에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="60a04-137">To use the script, copy the code to a .vbs file on your server.</span></span> <span data-ttu-id="60a04-138">그런 다음 명령줄에서 파일을 실행하거나 [!INCLUDE[TLA#tla_winexpl](../../../../includes/tlasharptla-winexpl-md.md)]에서 파일을 두 번 클릭하여 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="60a04-138">Then, run the script by running the file from the command line or double-clicking the file in [!INCLUDE[TLA#tla_winexpl](../../../../includes/tlasharptla-winexpl-md.md)].</span></span>  
  
```  
' This script adds the necessary Windows Presentation Foundation MIME types   
' to an IIS Server.  
' To use this script, just double-click or execute it from a command line.  
' Running this script multiple times results in multiple entries in the IIS MimeMap.  
  
Dim MimeMapObj, MimeMapArray, MimeTypesToAddArray, WshShell, oExec  
Const ADS_PROPERTY_UPDATE = 2   
  
' Set the MIME types to be added  
MimeTypesToAddArray = Array(".manifest", "application/manifest", ".xaml", _  
    "application/xaml+xml", ".application", "application/x-ms-application", _  
    ".deploy", "application/octet-stream", ".xbap", "application/x-ms-xbap", _  
    ".xps", "application/vnd.ms-xpsdocument")   
  
' Get the mimemap object   
Set MimeMapObj = GetObject("IIS://LocalHost/MimeMap")  
  
' Call AddMimeType for every pair of extension/MIME type  
For counter = 0 to UBound(MimeTypesToAddArray) Step 2  
    AddMimeType MimeTypesToAddArray(counter), MimeTypesToAddArray(counter+1)  
Next  
  
' Create a Shell object  
Set WshShell = CreateObject("WScript.Shell")  
  
' Stop and Start the IIS Service  
Set oExec = WshShell.Exec("net stop w3svc")  
Do While oExec.Status = 0  
    WScript.Sleep 100  
Loop  
  
Set oExec = WshShell.Exec("net start w3svc")  
Do While oExec.Status = 0  
    WScript.Sleep 100  
Loop  
  
Set oExec = Nothing  
  
' Report status to user  
WScript.Echo "Windows Presentation Foundation MIME types have been registered."  
  
' AddMimeType Sub  
Sub AddMimeType (Ext, MType)  
  
    ' Get the mappings from the MimeMap property.   
    MimeMapArray = MimeMapObj.GetEx("MimeMap")   
  
    ' Add a new mapping.   
    i = UBound(MimeMapArray) + 1   
    Redim Preserve MimeMapArray(i)   
    Set MimeMapArray(i) = CreateObject("MimeMap")   
    MimeMapArray(i).Extension = Ext   
    MimeMapArray(i).MimeType = MType   
    MimeMapObj.PutEx ADS_PROPERTY_UPDATE, "MimeMap", MimeMapArray  
    MimeMapObj.SetInfo  
  
End Sub  
```  
  
> [!NOTE]
>  <span data-ttu-id="60a04-139">이 스크립트를 여러 번 실행하면 [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] 또는 [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] 메타베이스에서 여러 [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] 맵 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="60a04-139">Running this script multiple times creates multiple [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] map entries in the [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] or [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] metabase.</span></span>  
  
 <span data-ttu-id="60a04-140">이 스크립트는 실행하고 나면 [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] 또는 [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] [!INCLUDE[TLA#tla_mmc](../../../../includes/tlasharptla-mmc-md.md)]에서 추가 [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] 형식이 표시되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60a04-140">After you have run this script, you may not see additional [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types from the [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] or [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] [!INCLUDE[TLA#tla_mmc](../../../../includes/tlasharptla-mmc-md.md)].</span></span> <span data-ttu-id="60a04-141">그러나 이러한 [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] 형식이 [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] 또는 [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] 메타베이스에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="60a04-141">However, these [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types have been added to the [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] or [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] metabase.</span></span> <span data-ttu-id="60a04-142">다음 스크립트는 [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] 또는 [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] 메타베이스의 [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] 형식을 모두 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="60a04-142">The following script will display all the [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types in the [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] or [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] metabase.</span></span>  
  
```  
' This script lists the MIME types for an IIS Server.  
' To use this script, just double-click or execute it from a command line   
' by calling cscript.exe  
  
dim mimeMapEntry, allMimeMaps  
  
' Get the mimemap object.  
Set mimeMapEntry = GetObject("IIS://localhost/MimeMap")  
allMimeMaps = mimeMapEntry.GetEx("MimeMap")  
  
' Display the mappings in the table.  
For Each mimeMap In allMimeMaps  
    WScript.Echo(mimeMap.MimeType & " (" & mimeMap.Extension + ")")  
Next  
```  
  
 <span data-ttu-id="60a04-143">스크립트를 `.vbs` 파일로 저장하고(예: `DiscoverIISMimeTypes.vbs`) 다음 명령을 사용하여 명령 프롬프트에서 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="60a04-143">Save the script as a `.vbs` file (for example, `DiscoverIISMimeTypes.vbs`) and run it from the command prompt using the following command:</span></span>  
  
 `cscript DiscoverIISMimeTypes.vbs`
