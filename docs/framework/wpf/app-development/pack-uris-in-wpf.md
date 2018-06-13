---
title: WPF의 Pack URI
ms.date: 03/30/2017
helpviewer_keywords:
- pack URI scheme [WPF]
- loading embedded resources [WPF]
- URIs (Uniform Resource Identifiers)
- Uniform Resource Identifiers (URIs)
- loading non-resource files
- application management [WPF]
ms.assetid: 43adb517-21a7-4df3-98e8-09e9cdf764c4
ms.openlocfilehash: ae96ec40cbbf0a29f780c059b9873c185b2975d2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558158"
---
# <a name="pack-uris-in-wpf"></a><span data-ttu-id="3945f-102">WPF의 Pack URI</span><span class="sxs-lookup"><span data-stu-id="3945f-102">Pack URIs in WPF</span></span>
<span data-ttu-id="3945f-103">Windows Presentation Foundation (WPF), [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)] 식별 하 고 다음을 포함 한 다양 한 방식 파일을 로드 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-103">In Windows Presentation Foundation (WPF), [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)] are used to identify and load files in many ways, including the following:</span></span>  
  
-   <span data-ttu-id="3945f-104">지정 하는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 표시할 때 응용 프로그램이 처음 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-104">Specifying the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] to show when an application first starts.</span></span>  
  
-   <span data-ttu-id="3945f-105">이미지 로드</span><span class="sxs-lookup"><span data-stu-id="3945f-105">Loading images.</span></span>  
  
-   <span data-ttu-id="3945f-106">페이지 탐색</span><span class="sxs-lookup"><span data-stu-id="3945f-106">Navigating to pages.</span></span>  
  
-   <span data-ttu-id="3945f-107">비실행 데이터 파일 로드</span><span class="sxs-lookup"><span data-stu-id="3945f-107">Loading non-executable data files.</span></span>  
  
 <span data-ttu-id="3945f-108">또한 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 식별 하 고 다양 한 다음을 포함 한 위치에서에서 파일을 로드 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-108">Furthermore, [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] can be used to identify and load files from a variety of locations, including the following:</span></span>  
  
-   <span data-ttu-id="3945f-109">현재 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-109">The current assembly.</span></span>  
  
-   <span data-ttu-id="3945f-110">참조된 어셈블리</span><span class="sxs-lookup"><span data-stu-id="3945f-110">A referenced assembly.</span></span>  
  
-   <span data-ttu-id="3945f-111">어셈블리에 상대적인 위치</span><span class="sxs-lookup"><span data-stu-id="3945f-111">A location relative to an assembly.</span></span>  
  
-   <span data-ttu-id="3945f-112">응용 프로그램의 원본 사이트</span><span class="sxs-lookup"><span data-stu-id="3945f-112">The application's site of origin.</span></span>  
  
 <span data-ttu-id="3945f-113">식별 하 고 이러한 위치에서 이러한 종류의 파일을 로드에 대 한 일관 된 메커니즘을 제공 하려면 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 의 확장성을 이용는 *pack URI 체계*합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-113">To provide a consistent mechanism for identifying and loading these types of files from these locations, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] leverages the extensibility of the *pack URI scheme*.</span></span> <span data-ttu-id="3945f-114">이 항목의 체계의 개요를 제공, 팩을 생성 하는 방법에 설명 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 는 다양 한 시나리오에 대 한 설명 absolute 및 relative [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 및 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 팩을 사용 하는 방법을 보여 주는 하기 전에 해결 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 두 태그에서 및 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-114">This topic provides an overview of the scheme, covers how to construct pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] for a variety of scenarios, discusses absolute and relative [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] and [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] resolution, before showing how to use pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] from both markup and code.</span></span>  
  
  
<a name="The_Pack_URI_Scheme"></a>   
## <a name="the-pack-uri-scheme"></a><span data-ttu-id="3945f-115">Pack URI 체계</span><span class="sxs-lookup"><span data-stu-id="3945f-115">The Pack URI Scheme</span></span>  
 <span data-ttu-id="3945f-116">팩 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 체계를 사용 하 여는 [Open Packaging Conventions](http://go.microsoft.com/fwlink/?LinkID=71255) 을 구성 하 고 내용을 식별 하는 모델을 설명 하는 (OPC) 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-116">The pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] scheme is used by the [Open Packaging Conventions](http://go.microsoft.com/fwlink/?LinkID=71255) (OPC) specification, which describes a model for organizing and identifying content.</span></span> <span data-ttu-id="3945f-117">패키지 및 파트를이 모델의 주요 요소는 여기서는 *패키지* 인지 논리적 컨테이너 하나에 대 한 더 많은 논리 *부분*합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-117">The key elements of this model are packages and parts, where a *package* is a logical container for one or more logical *parts*.</span></span> <span data-ttu-id="3945f-118">다음 그림에서는 이 개념을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-118">The following figure illustrates this concept.</span></span>  
  
 <span data-ttu-id="3945f-119">![패키지 및 파트 다이어그램](../../../../docs/framework/wpf/app-development/media/wpfpackurischemefigure1.PNG "WPFPackURISchemeFigure1")</span><span class="sxs-lookup"><span data-stu-id="3945f-119">![Package and Parts diagram](../../../../docs/framework/wpf/app-development/media/wpfpackurischemefigure1.PNG "WPFPackURISchemeFigure1")</span></span>  
  
 <span data-ttu-id="3945f-120">OPC 사양 파트를 식별 하려면 RFC 2396의 확장성을 이용 (식별자 URI (Uniform Resource): 일반 구문을) pack을 정의 하려면 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 구성표입니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-120">To identify parts, the OPC specification leverages the extensibility of RFC 2396 (Uniform Resource Identifiers (URI): Generic Syntax) to define the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] scheme.</span></span>  
  
 <span data-ttu-id="3945f-121">지정한 구성표는 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 접두사로; 정의 http, ftp 및 파일은 잘 알려진 예입니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-121">The scheme that is specified by a [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] is defined by its prefix; http, ftp, and file are well-known examples.</span></span> <span data-ttu-id="3945f-122">팩 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 체계 "pack"을 사용 하 여 해당 스키마 및 두 개의 구성 요소가 포함 되어: 기관과 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-122">The pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] scheme uses "pack" as its scheme, and contains two components: authority and path.</span></span> <span data-ttu-id="3945f-123">다음은 팩 형식 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-123">The following is the format for a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
 <span data-ttu-id="3945f-124">팩: / /*기관*/*경로*</span><span class="sxs-lookup"><span data-stu-id="3945f-124">pack://*authority*/*path*</span></span>
  
 <span data-ttu-id="3945f-125">*기관* 일부 포함 된 패키지의 유형을 지정 하는 동안는 *경로* 파트 패키지 내에서 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-125">The *authority* specifies the type of package that a part is contained by, while the *path* specifies the location of a part within a package.</span></span>  
  
 <span data-ttu-id="3945f-126">다음 그림에서는 이 개념을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-126">This concept is illustrated by the following figure:</span></span>  
  
 <span data-ttu-id="3945f-127">![패키지, 인증 기관 및 경로의 관계](../../../../docs/framework/wpf/app-development/media/wpfpackurischemefigure2.PNG "WPFPackURISchemeFigure2")</span><span class="sxs-lookup"><span data-stu-id="3945f-127">![Relationship among package, authority, and path](../../../../docs/framework/wpf/app-development/media/wpfpackurischemefigure2.PNG "WPFPackURISchemeFigure2")</span></span>  
  
 <span data-ttu-id="3945f-128">패키지와 파트는 응용 프로그램 및 파일과 유사합니다. 즉, 응용 프로그램(패키지)은 다음을 비롯한 하나 이상의 파일(파트)을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-128">Packages and parts are analogous to applications and files, where an application (package) can include one or more files (parts), including:</span></span>  
  
-   <span data-ttu-id="3945f-129">로컬 어셈블리로 컴파일되는 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="3945f-129">Resource files that are compiled into the local assembly.</span></span>  
  
-   <span data-ttu-id="3945f-130">참조된 어셈블리로 컴파일되는 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="3945f-130">Resource files that are compiled into a referenced assembly.</span></span>  
  
-   <span data-ttu-id="3945f-131">참조하는 어셈블리로 컴파일되는 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="3945f-131">Resource files that are compiled into a referencing assembly.</span></span>  
  
-   <span data-ttu-id="3945f-132">콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="3945f-132">Content files.</span></span>  
  
-   <span data-ttu-id="3945f-133">원본 사이트 파일</span><span class="sxs-lookup"><span data-stu-id="3945f-133">Site of origin files.</span></span>  
  
 <span data-ttu-id="3945f-134">이러한 종류의 파일을 액세스 하려면 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 두 인증 기관과 지원: 응용 프로그램: / / / 및 siteoforigin: / / /입니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-134">To access these types of files, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] supports two authorities: application:/// and siteoforigin:///.</span></span> <span data-ttu-id="3945f-135">application:/// 인증 기관은 리소스 및 콘텐츠 파일을 비롯하여 컴파일 시 알려진 응용 프로그램 데이터 파일을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-135">The application:/// authority identifies application data files that are known at compile time, including resource and content files.</span></span> <span data-ttu-id="3945f-136">siteoforigin:/// 인증 기관은 원본 사이트 파일을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-136">The siteoforigin:/// authority identifies site of origin files.</span></span> <span data-ttu-id="3945f-137">다음 그림에서는 각 인증 기관의 범위를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-137">The scope of each authority is shown in the following figure.</span></span>  
  
 <span data-ttu-id="3945f-138">![Pack URI 다이어그램](../../../../docs/framework/wpf/app-development/media/wpfpackurischemefigure4.png "WPFPackURISchemeFigure4")</span><span class="sxs-lookup"><span data-stu-id="3945f-138">![Pack URI diagram](../../../../docs/framework/wpf/app-development/media/wpfpackurischemefigure4.png "WPFPackURISchemeFigure4")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3945f-139">팩의 인증 기관 구성 요소가 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 포함 된 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 패키지를 가리키는 하 고 RFC 2396 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-139">The authority component of a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] is an embedded [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that points to a package and must conform to RFC 2396.</span></span> <span data-ttu-id="3945f-140">또한 “/” 문자를 “,” 문자로 바꾸고 “%” 및 “?” 같은 예약 문자는 이스케이프해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-140">Additionally, the "/" character must be replaced with the "," character, and reserved characters such as "%" and "?" must be escaped.</span></span> <span data-ttu-id="3945f-141">자세한 내용은 OPC를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3945f-141">See the OPC for details.</span></span>  
  
 <span data-ttu-id="3945f-142">다음 섹션에서는 팩을 생성 하는 방법을 설명 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 리소스, 내용 및 원본 파일의 사이트 식별 하는 데 적절 한 경로와 함께에서이 두 인증 기관과 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-142">The following sections explain how to construct pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] using these two authorities in conjunction with the appropriate paths for identifying resource, content, and site of origin files.</span></span>  
  
<a name="Resource_File_Pack_URIs___Local_Assembly"></a>   
## <a name="resource-file-pack-uris"></a><span data-ttu-id="3945f-143">리소스 파일 Pack URI</span><span class="sxs-lookup"><span data-stu-id="3945f-143">Resource File Pack URIs</span></span>  
 <span data-ttu-id="3945f-144">리소스 파일으로 구성 된 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Resource` 항목 및 어셈블리에 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-144">Resource files are configured as [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`Resource` items and are compiled into assemblies.</span></span> [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]<span data-ttu-id="3945f-145"> 팩의 생성을 지원 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 로컬 어셈블리로 컴파일된 되거나 로컬 어셈블리에서 참조 되는 어셈블리로 컴파일된 리소스 파일을 식별 하는 데 사용 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-145"> supports the construction of pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that can be used to identify resource files that are either compiled into the local assembly or compiled into an assembly that is referenced from the local assembly.</span></span>  
  
<a name="Local_Assembly_Resource_File"></a>   
### <a name="local-assembly-resource-file"></a><span data-ttu-id="3945f-146">로컬 어셈블리 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="3945f-146">Local Assembly Resource File</span></span>  
 <span data-ttu-id="3945f-147">팩 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 리소스에 대 한 로컬 어셈블리로 컴파일된 파일 다음 기관과 경로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-147">The pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a resource file that is compiled into the local assembly uses the following authority and path:</span></span>  
  
-   <span data-ttu-id="3945f-148">**인증 기관**: application:///</span><span class="sxs-lookup"><span data-stu-id="3945f-148">**Authority**: application:///.</span></span>  
  
-   <span data-ttu-id="3945f-149">**경로**: 로컬 어셈블리 프로젝트 폴더 루트에 상대적인 경로를 포함한 리소스 파일의 이름</span><span class="sxs-lookup"><span data-stu-id="3945f-149">**Path**: The name of the resource file, including its path, relative to the local assembly project folder root.</span></span>  
  
 <span data-ttu-id="3945f-150">다음 예제에서는 팩 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 에 대 한는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 로컬 어셈블리의 프로젝트 폴더의 루트에 있는 리소스 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-150">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root of the local assembly's project folder.</span></span>  
  
 `pack://application:,,,/ResourceFile.xaml`  
  
 <span data-ttu-id="3945f-151">다음 예제에서는 팩 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 에 대 한는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 로컬 어셈블리의 프로젝트 폴더의 하위 폴더에 있는 리소스 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-151">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in a subfolder of the local assembly's project folder.</span></span>  
  
 `pack://application:,,,/Subfolder/ResourceFile.xaml`  
  
<a name="Resource_File_Pack_URIs___Referenced_Assembly"></a>   
### <a name="referenced-assembly-resource-file"></a><span data-ttu-id="3945f-152">참조된 어셈블리 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="3945f-152">Referenced Assembly Resource File</span></span>  
 <span data-ttu-id="3945f-153">팩 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 리소스에 대 한 파일 참조 어셈블리로 컴파일되는 다음 기관과 경로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-153">The pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a resource file that is compiled into a referenced assembly uses the following authority and path:</span></span>  
  
-   <span data-ttu-id="3945f-154">**인증 기관**: application:///</span><span class="sxs-lookup"><span data-stu-id="3945f-154">**Authority**: application:///.</span></span>  
  
-   <span data-ttu-id="3945f-155">**경로**: 참조된 어셈블리로 컴파일되는 리소스 파일의 이름.</span><span class="sxs-lookup"><span data-stu-id="3945f-155">**Path**: The name of a resource file that is compiled into a referenced assembly.</span></span> <span data-ttu-id="3945f-156">경로는 다음 형식을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-156">The path must conform to the following format:</span></span>  
  
     <span data-ttu-id="3945f-157">*AssemblyShortName*{*; 버전*] {*; PublicKey*]; component /*경로*</span><span class="sxs-lookup"><span data-stu-id="3945f-157">*AssemblyShortName*{*;Version*]{*;PublicKey*];component/*Path*</span></span>  
  
    -   <span data-ttu-id="3945f-158">**AssemblyShortName**: 참조된 어셈블리에 대한 약식 이름</span><span class="sxs-lookup"><span data-stu-id="3945f-158">**AssemblyShortName**: the short name for the referenced assembly.</span></span>  
  
    -   <span data-ttu-id="3945f-159">**;Version**[옵션]: 리소스 파일을 포함하는 참조된 어셈블리의 버전.</span><span class="sxs-lookup"><span data-stu-id="3945f-159">**;Version** [optional]: the version of the referenced assembly that contains the resource file.</span></span> <span data-ttu-id="3945f-160">동일한 약식 이름을 갖는 두 개 이상의 참조된 어셈블리가 로드된 경우 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-160">This is used when two or more referenced assemblies with the same short name are loaded.</span></span>  
  
    -   <span data-ttu-id="3945f-161">**;PublicKey**[옵션]: 참조된 어셈블리를 서명하는 데 사용된 공개 키.</span><span class="sxs-lookup"><span data-stu-id="3945f-161">**;PublicKey** [optional]: the public key that was used to sign the referenced assembly.</span></span> <span data-ttu-id="3945f-162">동일한 약식 이름을 갖는 두 개 이상의 참조된 어셈블리가 로드된 경우 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-162">This is used when two or more referenced assemblies with the same short name are loaded.</span></span>  
  
    -   <span data-ttu-id="3945f-163">**;component**: 참조되는 어셈블리가 로컬 어셈블리에서 참조된다는 것을 지정</span><span class="sxs-lookup"><span data-stu-id="3945f-163">**;component**: specifies that the assembly being referred to is referenced from the local assembly.</span></span>  
  
    -   <span data-ttu-id="3945f-164">**/Path**: 참조된 어셈블리 프로젝트 폴더의 루트에 상대적인 경로를 포함한 리소스 파일의 이름</span><span class="sxs-lookup"><span data-stu-id="3945f-164">**/Path**: the name of the resource file, including its path, relative to the root of the referenced assembly's project folder.</span></span>  
  
 <span data-ttu-id="3945f-165">다음 예제에서는 팩 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 에 대 한 한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 참조 된 어셈블리의 프로젝트 폴더의 루트에 있는 리소스 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-165">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root of the referenced assembly's project folder.</span></span>  
  
 `pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml`  
  
 <span data-ttu-id="3945f-166">다음 예제에서는 팩 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 에 대 한 한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 참조 된 어셈블리의 프로젝트 폴더의 하위 폴더에 있는 리소스 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-166">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in a subfolder of the referenced assembly's project folder.</span></span>  
  
 `pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml`  
  
 <span data-ttu-id="3945f-167">다음 예제에서는 팩 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 에 대 한 한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 참조 되는 버전 별로 어셈블리의 프로젝트 폴더의 루트 폴더에 있는 리소스 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-167">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root folder of a referenced, version-specific assembly's project folder.</span></span>  
  
 `pack://application:,,,/ReferencedAssembly;v1.0.0.1;component/ResourceFile.xaml`  
  
 <span data-ttu-id="3945f-168">pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 구문 참조 어셈블리 리소스 파일에 대 한 응용 프로그램 에서만 사용할 수 있습니다: / / / 기관입니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-168">Note that the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] syntax for referenced assembly resource files can be used only with the application:/// authority.</span></span> <span data-ttu-id="3945f-169">예를 들어 다음에서 지원 되지 않습니다 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-169">For example, the following is not supported in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span></span>  
  
 `pack://siteoforigin:,,,/SomeAssembly;component/ResourceFile.xaml`  
  
<a name="Content_File_Pack_URIs"></a>   
## <a name="content-file-pack-uris"></a><span data-ttu-id="3945f-170">콘텐츠 파일 Pack URI</span><span class="sxs-lookup"><span data-stu-id="3945f-170">Content File Pack URIs</span></span>  
 <span data-ttu-id="3945f-171">팩 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 콘텐츠 파일은 다음 인증 기관과 경로 사용 하 여:</span><span class="sxs-lookup"><span data-stu-id="3945f-171">The pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a content file uses the following authority and path:</span></span>  
  
-   <span data-ttu-id="3945f-172">**인증 기관**: application:///</span><span class="sxs-lookup"><span data-stu-id="3945f-172">**Authority**: application:///.</span></span>  
  
-   <span data-ttu-id="3945f-173">**경로**: 응용 프로그램의 주 실행 가능 어셈블리의 파일 시스템 위치에 상대적인 경로를 포함한 콘텐츠 파일의 이름</span><span class="sxs-lookup"><span data-stu-id="3945f-173">**Path**: The name of the content file, including its path relative to the file system location of the application's main executable assembly.</span></span>  
  
 <span data-ttu-id="3945f-174">다음 예제에서는 팩 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 에 대 한는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 실행 가능한 어셈블리와 같은 폴더에 있는 콘텐츠 파일을 합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-174">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] content file, located in the same folder as the executable assembly.</span></span>  
  
 `pack://application:,,,/ContentFile.xaml`  
  
 <span data-ttu-id="3945f-175">다음 예제에서는 팩 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 에 대 한는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 응용 프로그램의 실행 가능한 어셈블리에 상대적인 하위 폴더에 있는 콘텐츠 파일을 합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-175">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] content file, located in a subfolder that is relative to the application's executable assembly.</span></span>  
  
 `pack://application:,,,/Subfolder/ContentFile.xaml`  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)]<span data-ttu-id="3945f-176"> 콘텐츠 파일은 탐색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-176"> content files cannot be navigated to.</span></span> <span data-ttu-id="3945f-177">[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 구성표 탐색을 지원 [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] 있는 파일을 원본 사이트에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-177">The [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] scheme only supports navigation to [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] files that are located at the site of origin.</span></span>  
  
<a name="The_siteoforigin_____Authority"></a>   
## <a name="site-of-origin-pack-uris"></a><span data-ttu-id="3945f-178">원본 사이트 Pack URI</span><span class="sxs-lookup"><span data-stu-id="3945f-178">Site of Origin Pack URIs</span></span>  
 <span data-ttu-id="3945f-179">팩 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 원본 사이트에 대 한 파일 다음 기관과 경로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-179">The pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a site of origin file uses the following authority and path:</span></span>  
  
-   <span data-ttu-id="3945f-180">**인증 기관**: siteoforigin:///</span><span class="sxs-lookup"><span data-stu-id="3945f-180">**Authority**: siteoforigin:///.</span></span>  
  
-   <span data-ttu-id="3945f-181">**경로**: 실행 가능 어셈블리가 시작된 위치에 상대적인 경로를 포함한 원본 사이트 파일의 이름</span><span class="sxs-lookup"><span data-stu-id="3945f-181">**Path**: The name of the site of origin file, including its path relative to the location from which the executable assembly was launched.</span></span>  
  
 <span data-ttu-id="3945f-182">다음 예제에서는 팩 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 에 대 한는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 원본 사이트 파일을 실행 가능한 어셈블리가 시작 된 위치에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-182">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] site of origin file, stored in the location from which the executable assembly is launched.</span></span>  
  
 `pack://siteoforigin:,,,/SiteOfOriginFile.xaml`  
  
 <span data-ttu-id="3945f-183">다음 예제에서는 팩 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 에 대 한는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 원본 사이트 파일을 응용 프로그램의 실행 가능한 어셈블리 시작 위치에 상대적인 하위 폴더에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-183">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] site of origin file, stored in subfolder that is relative to the location from which the application's executable assembly is launched.</span></span>  
  
 `pack://siteoforigin:,,,/Subfolder/SiteOfOriginFile.xaml`  
  
<a name="Page_Files"></a>   
## <a name="page-files"></a><span data-ttu-id="3945f-184">페이지 파일</span><span class="sxs-lookup"><span data-stu-id="3945f-184">Page Files</span></span>  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]<span data-ttu-id="3945f-185"> 으로 구성 된 파일 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Page` 항목 리소스 파일과 마찬가지로 어셈블리로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-185"> files that are configured as [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`Page` items are compiled into assemblies in the same way as resource files.</span></span> <span data-ttu-id="3945f-186">따라서 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Page` 팩을 사용 하 여 항목을 식별할 수 있습니다 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 리소스 파일에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-186">Consequently, [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`Page` items can be identified using pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] for resource files.</span></span>  
  
 <span data-ttu-id="3945f-187">유형의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 가 일반적으로 구성 하는 파일 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Page` 항목은 해당 루트 요소에 따라 다음 중 하나:</span><span class="sxs-lookup"><span data-stu-id="3945f-187">The types of [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files that are commonly configured as [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`Page` items have one of the following as their root element:</span></span>  
  
-   <xref:System.Windows.Window?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Controls.Page?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Navigation.PageFunction%601?displayProperty=nameWithType>  
  
-   <xref:System.Windows.ResourceDictionary?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Documents.FlowDocument?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>  
  
<a name="Absolute_vs_Relative_Pack_URIs"></a>   
## <a name="absolute-vs-relative-pack-uris"></a><span data-ttu-id="3945f-188">절대 및 상대 Pack URI</span><span class="sxs-lookup"><span data-stu-id="3945f-188">Absolute vs. Relative Pack URIs</span></span>  
 <span data-ttu-id="3945f-189">정규화 된 팩 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 체계, 기관, 및 경로 포함 절대 팩 이라고 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-189">A fully qualified pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] includes the scheme, the authority, and the path, and it is considered an absolute pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span> <span data-ttu-id="3945f-190">개발자를 위한 단순화 된 버전으로 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 요소 일반적으로 설정할 수 있도록 적절 한 특성 상대 팩 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]만 경로 포함 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-190">As a simplification for developers, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elements typically allow you to set appropriate attributes with a relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], which includes only the path.</span></span>  
  
 <span data-ttu-id="3945f-191">예를 들어 다음과 같은 절대 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 로컬 어셈블리에 리소스 파일에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-191">For example, consider the following absolute pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a resource file in the local assembly.</span></span>  
  
 `pack://application:,,,/ResourceFile.xaml`  
  
 <span data-ttu-id="3945f-192">상대 팩 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 이 리소스를 참조 하는 파일에는 다음 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-192">The relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that refers to this resource file would be the following.</span></span>  
  
 `/ResourceFile.xaml`  
  
> [!NOTE]
>  <span data-ttu-id="3945f-193">원본 사이트 파일의 어셈블리와 연결 되어 있지 않으므로 있습니다만 참조할 수 절대 팩 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-193">Because site of origin files are not associated with assemblies, they can only be referred to with absolute pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)].</span></span>  
  
 <span data-ttu-id="3945f-194">기본적으로 상대 팩 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 태그 또는 참조를 포함 하는 코드의 위치에 상대적인 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-194">By default, a relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] is considered relative to the location of the markup or code that contains the reference.</span></span> <span data-ttu-id="3945f-195">그러나 앞에 백슬래시를 사용 하는 경우 상대 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 참조는 응용 프로그램의 루트를 기준으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-195">If a leading backslash is used, however, the relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] reference is then considered relative to the root of the application.</span></span> <span data-ttu-id="3945f-196">예를 들어 다음과 같은 프로젝트 구조를 가정해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-196">For example, consider the following project structure.</span></span>  
  
 `App.xaml`  
  
 `Page2.xaml`  
  
 `\SubFolder`  
  
 `+ Page1.xaml`  
  
 `+ Page2.xaml`  
  
 <span data-ttu-id="3945f-197">Page1.xaml 포함 되어 있는 경우는 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 참조 하는 *루트*\SubFolder\Page2.xaml, 참조가 다음 상대 팩을 사용할 수 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-197">If Page1.xaml contains a [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that references *Root*\SubFolder\Page2.xaml, the reference can use the following relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
 `Page2.xaml`  
  
 <span data-ttu-id="3945f-198">Page1.xaml 포함 되어 있는 경우는 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 참조 하는 *루트*\Page2.xaml, 참조가 다음 상대 팩을 사용할 수 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-198">If Page1.xaml contains a [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that references *Root*\Page2.xaml, the reference can use the following relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
 `/Page2.xaml`  
  
<a name="Pack_URI_Resolution"></a>   
## <a name="pack-uri-resolution"></a><span data-ttu-id="3945f-199">Pack URI 확인</span><span class="sxs-lookup"><span data-stu-id="3945f-199">Pack URI Resolution</span></span>  
 <span data-ttu-id="3945f-200">팩 형식을 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 팩용 수는 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 여러 가지 유형의 파일을 동일 하 게 보입니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-200">The format of pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] makes it is possible for pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] for different types of files to look the same.</span></span> <span data-ttu-id="3945f-201">예를 들어 다음과 같은 절대 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-201">For example, consider the following absolute pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
 `pack://application:,,,/ResourceOrContentFile.xaml`  
  
 <span data-ttu-id="3945f-202">이 절대 팩 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 로컬 어셈블리에 리소스 파일 또는 콘텐츠 파일을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-202">This absolute pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] could refer to either a resource file in the local assembly or a content file.</span></span> <span data-ttu-id="3945f-203">다음 상대에도 마찬가지입니다 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-203">The same is true for the following relative [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
 `/ResourceOrContentFile.xaml`  
  
 <span data-ttu-id="3945f-204">유형의 파일을 확인 하기 위해 한 팩 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 참조 하 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 해결 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 로컬 어셈블리 및 다음과 같은 추론을 사용 하 여 콘텐츠 파일에서 리소스 파일:</span><span class="sxs-lookup"><span data-stu-id="3945f-204">In order to determine the type of file that a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] refers to, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] resolves [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] for resource files in local assemblies and content files by using the following heuristics:</span></span>  
  
1.  <span data-ttu-id="3945f-205">어셈블리 메타 데이터에 대 한 프로브는 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> pack 일치 하는 특성 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-205">Probe the assembly metadata for an <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute that matches the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
2.  <span data-ttu-id="3945f-206">경우는 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> , 특성이 있으면 해당 팩의 경로 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 콘텐츠 파일을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-206">If the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute is found, the path of the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] refers to a content file.</span></span>  
  
3.  <span data-ttu-id="3945f-207">경우는 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 로컬 어셈블리로 컴파일되는 리소스 파일 집합을 검색, 특성을 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-207">If the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute is not found, probe the set resource files that are compiled into the local assembly.</span></span>  
  
4.  <span data-ttu-id="3945f-208">리소스 파일 팩의 경로 일치 하는 경우 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 발견 되 면 팩 경로 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 리소스 파일을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-208">If a resource file that matches the path of the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] is found, the path of the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] refers to a resource file.</span></span>  
  
5.  <span data-ttu-id="3945f-209">리소스가 없는 경우, 내부적으로 생성 <xref:System.Uri> 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-209">If the resource is not found, the internally created <xref:System.Uri> is invalid.</span></span>  
  
 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]<span data-ttu-id="3945f-210"> 해결 방법에 대 한 적용 되지 않습니다 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 하는 다음을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3945f-210"> resolution does not apply for [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that refer to the following:</span></span>  
  
-   <span data-ttu-id="3945f-211">참조 된 어셈블리의 콘텐츠 파일:이 파일 형식에서 지원 되지 않습니다 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-211">Content files in referenced assemblies: these file types are not supported by [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span></span>  
  
-   <span data-ttu-id="3945f-212">참조 된 어셈블리에 포함 된 파일: [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 을 식별 하는 참조 된 어셈블리의 이름을 둘 다 포함 되어 있으므로 고유 및 `;component` 접미사입니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-212">Embedded files in referenced assemblies: [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that identify them are unique because they include both the name of the referenced assembly and the `;component` suffix.</span></span>  
  
-   <span data-ttu-id="3945f-213">원본 사이트 파일: [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 식별 하는 팩으로 식별할 수 있는 파일만 되기 때문에 고유 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 는 siteoforigin를 포함 하는: / / / 기관입니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-213">Site of origin files: [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that identify them are unique because they are the only files that can be identified by pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that contain the siteoforigin:/// authority.</span></span>  
  
 <span data-ttu-id="3945f-214">압축 하는 한 가지 단순화 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 확인을 사용 하면 코드가 리소스 및 콘텐츠 파일의 위치와 다소 독립적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-214">One simplification that pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] resolution allows is for code to be somewhat independent of the locations of resource and content files.</span></span> <span data-ttu-id="3945f-215">예를 들어, 된 콘텐츠 파일에서 팩 다시 구성 되는 로컬 어셈블리에 리소스 파일의 경우 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 리소스 동일 하 게 유지, 마찬가지로 pack을 사용 하는 코드에 대 한 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-215">For example, if you have a resource file in the local assembly that is reconfigured to be a content file, the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for the resource remains the same, as does the code that uses the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
<a name="Programming_with_Pack_URIs"></a>   
## <a name="programming-with-pack-uris"></a><span data-ttu-id="3945f-216">Pack URI를 사용한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="3945f-216">Programming with Pack URIs</span></span>  
 <span data-ttu-id="3945f-217">많은 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 팩 설정 될 수 있는 속성을 구현 하는 클래스 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]를 포함 하 여:</span><span class="sxs-lookup"><span data-stu-id="3945f-217">Many [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] classes implement properties that can be set with pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], including:</span></span>  
  
-   <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Controls.Frame.Source%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Documents.Hyperlink.NavigateUri%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Window.Icon%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Controls.Image.Source%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="3945f-218">이러한 속성을 태그와 코드 모두에서 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-218">These properties can be set from both markup and code.</span></span> <span data-ttu-id="3945f-219">이 섹션에서는 두 경우에 대한 기본 구조를 설명한 다음 일반적인 시나리오 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-219">This section demonstrates the basic constructions for both and then shows examples of common scenarios.</span></span>  
  
<a name="Using_Pack_URIs_in_Markup"></a>   
### <a name="using-pack-uris-in-markup"></a><span data-ttu-id="3945f-220">태그에서 Pack URI 사용</span><span class="sxs-lookup"><span data-stu-id="3945f-220">Using Pack URIs in Markup</span></span>  
 <span data-ttu-id="3945f-221">팩 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 에서 팩을 사용 하 여 특성의 요소를 설정 하 여 태그에 지정 된 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-221">A pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] is specified in markup by setting the element of an attribute with the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span> <span data-ttu-id="3945f-222">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="3945f-222">For example:</span></span>  
  
 `<element attribute="pack://application:,,,/File.xaml" />`  
  
 <span data-ttu-id="3945f-223">표 1은 다양 한 절대 팩 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 태그에서 지정할 수 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-223">Table 1 illustrates the various absolute pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that you can specify in markup.</span></span>  
  
 <span data-ttu-id="3945f-224">표 1: 태그의 절대 Pack URI</span><span class="sxs-lookup"><span data-stu-id="3945f-224">Table 1: Absolute Pack URIs in Markup</span></span>  
  
|<span data-ttu-id="3945f-225">파일</span><span class="sxs-lookup"><span data-stu-id="3945f-225">File</span></span>|<span data-ttu-id="3945f-226">절대 팩 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3945f-226">Absolute pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span></span>|  
|----------|-------------------------------------------------------------------------------------------------------------------------|  
|<span data-ttu-id="3945f-227">리소스 파일 - 로컬 어셈블리</span><span class="sxs-lookup"><span data-stu-id="3945f-227">Resource file - local assembly</span></span>|`"pack://application:,,,/ResourceFile.xaml"`|  
|<span data-ttu-id="3945f-228">하위 폴더의 리소스 파일 - 로컬 어셈블리</span><span class="sxs-lookup"><span data-stu-id="3945f-228">Resource file in subfolder - local assembly</span></span>|`"pack://application:,,,/Subfolder/ResourceFile.xaml"`|  
|<span data-ttu-id="3945f-229">리소스 파일 - 참조된 어셈블리</span><span class="sxs-lookup"><span data-stu-id="3945f-229">Resource file - referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml"`|  
|<span data-ttu-id="3945f-230">참조된 어셈블리의 하위 폴더에 있는 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="3945f-230">Resource file in subfolder of referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|  
|<span data-ttu-id="3945f-231">버전이 있는 참조된 어셈블리의 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="3945f-231">Resource file in versioned referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml"`|  
|<span data-ttu-id="3945f-232">콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="3945f-232">Content file</span></span>|`"pack://application:,,,/ContentFile.xaml"`|  
|<span data-ttu-id="3945f-233">하위 폴더의 콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="3945f-233">Content file in subfolder</span></span>|`"pack://application:,,,/Subfolder/ContentFile.xaml"`|  
|<span data-ttu-id="3945f-234">원본 사이트 파일</span><span class="sxs-lookup"><span data-stu-id="3945f-234">Site of origin file</span></span>|`"pack://siteoforigin:,,,/SOOFile.xaml"`|  
|<span data-ttu-id="3945f-235">하위 폴더의 원본 사이트 파일</span><span class="sxs-lookup"><span data-stu-id="3945f-235">Site of origin file in subfolder</span></span>|`"pack://siteoforigin:,,,/Subfolder/SOOFile.xaml"`|  
  
 <span data-ttu-id="3945f-236">표 2에서는 다양 한 상대 pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 태그에서 지정할 수 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-236">Table 2 illustrates the various relative pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that you can specify in markup.</span></span>  
  
 <span data-ttu-id="3945f-237">표 2: 태그의 상대 Pack URI</span><span class="sxs-lookup"><span data-stu-id="3945f-237">Table 2: Relative Pack URIs in Markup</span></span>  
  
|<span data-ttu-id="3945f-238">파일</span><span class="sxs-lookup"><span data-stu-id="3945f-238">File</span></span>|<span data-ttu-id="3945f-239">상대 팩 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3945f-239">Relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span></span>|  
|----------|-------------------------------------------------------------------------------------------------------------------------|  
|<span data-ttu-id="3945f-240">로컬 어셈블리의 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="3945f-240">Resource file in local assembly</span></span>|`"/ResourceFile.xaml"`|  
|<span data-ttu-id="3945f-241">로컬 어셈블리의 하위 폴더에 있는 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="3945f-241">Resource file in subfolder of local assembly</span></span>|`"/Subfolder/ResourceFile.xaml"`|  
|<span data-ttu-id="3945f-242">참조된 어셈블리의 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="3945f-242">Resource file in referenced assembly</span></span>|`"/ReferencedAssembly;component/ResourceFile.xaml"`|  
|<span data-ttu-id="3945f-243">참조된 어셈블리의 하위 폴더에 있는 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="3945f-243">Resource file in subfolder of referenced assembly</span></span>|`"/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|  
|<span data-ttu-id="3945f-244">콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="3945f-244">Content file</span></span>|`"/ContentFile.xaml"`|  
|<span data-ttu-id="3945f-245">하위 폴더의 콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="3945f-245">Content file in subfolder</span></span>|`"/Subfolder/ContentFile.xaml"`|  
  
<a name="Using_Pack_URIs_in_Code"></a>   
### <a name="using-pack-uris-in-code"></a><span data-ttu-id="3945f-246">코드에서 Pack URI 사용</span><span class="sxs-lookup"><span data-stu-id="3945f-246">Using Pack URIs in Code</span></span>  
 <span data-ttu-id="3945f-247">팩을 지정 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 인스턴스화하여 코드에는 <xref:System.Uri> pack 전달과 클래스 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 생성자에 매개 변수로 합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-247">You specify a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] in code by instantiating the <xref:System.Uri> class and passing the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] as a parameter to the constructor.</span></span> <span data-ttu-id="3945f-248">다음 예제를 통해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-248">This is demonstrated in the following example.</span></span>  
  
```csharp  
Uri uri = new Uri("pack://application:,,,/File.xaml");  
```  
  
 <span data-ttu-id="3945f-249">기본적으로는 <xref:System.Uri> 클래스 고려 팩 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 절대적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-249">By default, the <xref:System.Uri> class considers pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] to be absolute.</span></span> <span data-ttu-id="3945f-250">인스턴스가 예외가 발생 하는 따라서는 <xref:System.Uri> 상대 팩 클래스를 만들 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-250">Consequently, an exception is raised when an instance of the <xref:System.Uri> class is created with a relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
```csharp  
Uri uri = new Uri("/File.xaml");  
```  
  
 <span data-ttu-id="3945f-251">다행히는 <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> 오버 로드는 <xref:System.Uri> 형식의 매개 변수를 허용 하는 클래스 생성자 <xref:System.UriKind> 지정할 수 있도록 여부는 팩 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 은 절대 또는 상대 합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-251">Fortunately, the <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> overload of the <xref:System.Uri> class constructor accepts a parameter of type <xref:System.UriKind> to allow you to specify whether a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] is either absolute or relative.</span></span>  
  
```csharp  
// Absolute URI (default)  
Uri absoluteUri = new Uri("pack://application:,,,/File.xaml", UriKind.Absolute);  
// Relative URI  
Uri relativeUri = new Uri("/File.xaml",   
                        UriKind.Relative);  
```  
  
 <span data-ttu-id="3945f-252">만 지정 해야 <xref:System.UriKind.Absolute> 또는 <xref:System.UriKind.Relative> 되었음을 확인 하 고 있는 경우 제공 된 팩 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 은 둘 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-252">You should specify only <xref:System.UriKind.Absolute> or <xref:System.UriKind.Relative> when you are certain that the provided pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] is one or the other.</span></span> <span data-ttu-id="3945f-253">팩 유형 알지 못하는 경우 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 사용 되는, 사용자가을 팩을 입력 하는 경우 같은 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 실행 시 사용 하 여 <xref:System.UriKind.RelativeOrAbsolute> 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-253">If you don't know the type of pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that is used, such as when a user enters a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] at run time, use <xref:System.UriKind.RelativeOrAbsolute> instead.</span></span>  
  
```csharp  
// Relative or Absolute URI provided by user via a text box  
TextBox userProvidedUriTextBox = new TextBox();  
Uri uri = new Uri(userProvidedUriTextBox.Text, UriKind.RelativeOrAbsolute);  
```  
  
 <span data-ttu-id="3945f-254">표 3에서는 다양 한 상대 pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 를 사용 하 여 코드에서 지정할 수 있는 <xref:System.Uri?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-254">Table 3 illustrates the various relative pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that you can specify in code by using <xref:System.Uri?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="3945f-255">표 3: 코드의 절대 Pack URI</span><span class="sxs-lookup"><span data-stu-id="3945f-255">Table 3: Absolute Pack URIs in Code</span></span>  
  
|<span data-ttu-id="3945f-256">파일</span><span class="sxs-lookup"><span data-stu-id="3945f-256">File</span></span>|<span data-ttu-id="3945f-257">절대 팩 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3945f-257">Absolute pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span></span>|  
|----------|-------------------------------------------------------------------------------------------------------------------------|  
|<span data-ttu-id="3945f-258">리소스 파일 - 로컬 어셈블리</span><span class="sxs-lookup"><span data-stu-id="3945f-258">Resource file - local assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ResourceFile.xaml", UriKind.Absolute);`|  
|<span data-ttu-id="3945f-259">하위 폴더의 리소스 파일 - 로컬 어셈블리</span><span class="sxs-lookup"><span data-stu-id="3945f-259">Resource file in subfolder - local assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|  
|<span data-ttu-id="3945f-260">리소스 파일 - 참조된 어셈블리</span><span class="sxs-lookup"><span data-stu-id="3945f-260">Resource file - referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Absolute);`|  
|<span data-ttu-id="3945f-261">참조된 어셈블리의 하위 폴더에 있는 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="3945f-261">Resource file in subfolder of referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|  
|<span data-ttu-id="3945f-262">버전이 있는 참조된 어셈블리의 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="3945f-262">Resource file in versioned referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml", UriKind.Absolute);`|  
|<span data-ttu-id="3945f-263">콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="3945f-263">Content file</span></span>|`Uri uri = new Uri("pack://application:,,,/ContentFile.xaml", UriKind.Absolute);`|  
|<span data-ttu-id="3945f-264">하위 폴더의 콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="3945f-264">Content file in subfolder</span></span>|`Uri uri = new Uri("pack://application:,,,/Subfolder/ContentFile.xaml", UriKind.Absolute);`|  
|<span data-ttu-id="3945f-265">원본 사이트 파일</span><span class="sxs-lookup"><span data-stu-id="3945f-265">Site of origin file</span></span>|`Uri uri = new Uri("pack://siteoforigin:,,,/SOOFile.xaml", UriKind.Absolute);`|  
|<span data-ttu-id="3945f-266">하위 폴더의 원본 사이트 파일</span><span class="sxs-lookup"><span data-stu-id="3945f-266">Site of origin file in subfolder</span></span>|`Uri uri = new Uri("pack://siteoforigin:,,,/Subfolder/SOOFile.xaml", UriKind.Absolute);`|  
  
 <span data-ttu-id="3945f-267">표 4에서는 다양 한 상대 pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 사용 하 여 코드에서 지정할 수 있는 <xref:System.Uri?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-267">Table 4 illustrates the various relative pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that you can specify in code using <xref:System.Uri?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="3945f-268">표 4: 코드의 상대 Pack URI</span><span class="sxs-lookup"><span data-stu-id="3945f-268">Table 4: Relative Pack URIs in Code</span></span>  
  
|<span data-ttu-id="3945f-269">파일</span><span class="sxs-lookup"><span data-stu-id="3945f-269">File</span></span>|<span data-ttu-id="3945f-270">상대 팩 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3945f-270">Relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span></span>|  
|----------|-------------------------------------------------------------------------------------------------------------------------|  
|<span data-ttu-id="3945f-271">리소스 파일 - 로컬 어셈블리</span><span class="sxs-lookup"><span data-stu-id="3945f-271">Resource file - local assembly</span></span>|`Uri uri = new Uri("/ResourceFile.xaml", UriKind.Relative);`|  
|<span data-ttu-id="3945f-272">하위 폴더의 리소스 파일 - 로컬 어셈블리</span><span class="sxs-lookup"><span data-stu-id="3945f-272">Resource file in subfolder - local assembly</span></span>|`Uri uri = new Uri("/Subfolder/ResourceFile.xaml", UriKind.Relative);`|  
|<span data-ttu-id="3945f-273">리소스 파일 - 참조된 어셈블리</span><span class="sxs-lookup"><span data-stu-id="3945f-273">Resource file - referenced assembly</span></span>|`Uri uri = new Uri("/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Relative);`|  
|<span data-ttu-id="3945f-274">하위 폴더의 리소스 파일 - 참조된 어셈블리</span><span class="sxs-lookup"><span data-stu-id="3945f-274">Resource file in subfolder - referenced assembly</span></span>|`Uri uri = new Uri("/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Relative);`|  
|<span data-ttu-id="3945f-275">콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="3945f-275">Content file</span></span>|`Uri uri = new Uri("/ContentFile.xaml", UriKind.Relative);`|  
|<span data-ttu-id="3945f-276">하위 폴더의 콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="3945f-276">Content file in subfolder</span></span>|`Uri uri = new Uri("/Subfolder/ContentFile.xaml", UriKind.Relative);`|  
  
<a name="Common_Pack_URI_Scenarios"></a>   
### <a name="common-pack-uri-scenarios"></a><span data-ttu-id="3945f-277">일반적인 Pack URI 시나리오</span><span class="sxs-lookup"><span data-stu-id="3945f-277">Common Pack URI Scenarios</span></span>  
 <span data-ttu-id="3945f-278">앞의 섹션에서는 팩을 생성 하는 방법을 살펴보았습니다 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 리소스, 내용 및 원본 사이트 파일을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-278">The preceding sections have discussed how to construct pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] to identify resource, content, and site of origin files.</span></span> <span data-ttu-id="3945f-279">[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], 이러한 구성은 다양 한 방식으로에 사용 되 고 다음 섹션에서는 몇 가지 일반적인 사용을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-279">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], these constructions are used in a variety of ways, and the following sections cover several common usages.</span></span>  
  
<a name="Specifying_the_UI_to_Show_when_an_Application_Starts"></a>   
#### <a name="specifying-the-ui-to-show-when-an-application-starts"></a><span data-ttu-id="3945f-280">응용 프로그램을 시작할 때 표시되는 UI 지정</span><span class="sxs-lookup"><span data-stu-id="3945f-280">Specifying the UI to Show When an Application Starts</span></span>  
 <span data-ttu-id="3945f-281"><xref:System.Windows.Application.StartupUri%2A> 첫 번째 지정 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 때 표시 되는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램이 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-281"><xref:System.Windows.Application.StartupUri%2A> specifies the first [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] to show when a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application is launched.</span></span> <span data-ttu-id="3945f-282">독립 실행형 응용 프로그램의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 다음 예제와 같이 창 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-282">For standalone applications, the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] can be a window, as shown in the following example.</span></span>  
  
 [!code-xaml[PackURIOverviewSnippets#StartupUriWindow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/Copy of App.xaml#startupuriwindow)]  
  
 <span data-ttu-id="3945f-283">독립 실행형 응용 프로그램 및 [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] 다음 예제와 같이 초기 UI로 페이지를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-283">Standalone applications and [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] can also specify a page as the initial UI, as shown in the following example.</span></span>  
  
 [!code-xaml[PackURIOverviewSnippets#StartupUriPage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/App.xaml#startupuripage)]  
  
 <span data-ttu-id="3945f-284">응용 프로그램은 독립 실행형 응용 프로그램 및 한 페이지를 지정 하는 경우 <xref:System.Windows.Application.StartupUri%2A>, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 열립니다는 <xref:System.Windows.Navigation.NavigationWindow> 페이지를 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-284">If the application is a standalone application and a page is specified with <xref:System.Windows.Application.StartupUri%2A>, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] opens a <xref:System.Windows.Navigation.NavigationWindow> to host the page.</span></span> <span data-ttu-id="3945f-285">에 대 한 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], 페이지 호스트 브라우저에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-285">For [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], the page is shown in the host browser.</span></span>  
  
<a name="Navigating_to_a_Page"></a>   
#### <a name="navigating-to-a-page"></a><span data-ttu-id="3945f-286">페이지 탐색</span><span class="sxs-lookup"><span data-stu-id="3945f-286">Navigating to a Page</span></span>  
 <span data-ttu-id="3945f-287">다음 예제에서는 페이지를 탐색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-287">The following example shows how to navigate to a page.</span></span>  
  
 [!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]  
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]  
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]  
  
 <span data-ttu-id="3945f-288">탐색 하는 다양 한 방법에 대 한 자세한 내용은 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], 참조 [탐색 개요](../../../../docs/framework/wpf/app-development/navigation-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-288">For more information on the various ways to navigate in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], see [Navigation Overview](../../../../docs/framework/wpf/app-development/navigation-overview.md).</span></span>  
  
<a name="Specifying_a_Window_Icon"></a>   
#### <a name="specifying-a-window-icon"></a><span data-ttu-id="3945f-289">창 아이콘 지정</span><span class="sxs-lookup"><span data-stu-id="3945f-289">Specifying a Window Icon</span></span>  
 <span data-ttu-id="3945f-290">다음 예제에서는 URI를 사용하여 창 아이콘을 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-290">The following example shows how to use a URI to specify a window's icon.</span></span>  
  
 [!code-xaml[WindowIconSnippets#WindowIconSetXAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/WindowIconSnippets/XAML/MainWindow.xaml#windowiconsetxaml)]  
  
 <span data-ttu-id="3945f-291">자세한 내용은 <xref:System.Windows.Window.Icon%2A>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3945f-291">For more information, see <xref:System.Windows.Window.Icon%2A>.</span></span>  
  
<a name="Loading_Image__Audio__and_Video_Files"></a>   
#### <a name="loading-image-audio-and-video-files"></a><span data-ttu-id="3945f-292">이미지, 오디오 및 비디오 파일 로드</span><span class="sxs-lookup"><span data-stu-id="3945f-292">Loading Image, Audio, and Video Files</span></span>  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]<span data-ttu-id="3945f-293"> 응용 프로그램을 다양 한 미디어 유형으로는 모두 식별 하 고 수와 사용 하는 데 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]다음 예제에 표시 된 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-293"> allows applications to use a wide variety of media types, all of which can be identified and loaded with pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], as shown in the following examples.</span></span>  
  
 [!code-xaml[MediaPlayerVideoSample#VideoPackURIAtSOO](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerVideoSample/CS/HomePage.xaml#videopackuriatsoo)]  
  
 [!code-xaml[MediaPlayerAudioSample#AudioPackURIAtSOO](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerAudioSample/CS/HomePage.xaml#audiopackuriatsoo)]  
  
 [!code-xaml[ImageSample#ImagePackURIContent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageSample/CS/HomePage.xaml#imagepackuricontent)]  
  
 <span data-ttu-id="3945f-294">미디어 콘텐츠를 사용한 작업에 대 한 자세한 내용은 참조 하십시오. [그래픽 및 멀티미디어](../../../../docs/framework/wpf/graphics-multimedia/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-294">For more information on working with media content, see [Graphics and Multimedia](../../../../docs/framework/wpf/graphics-multimedia/index.md).</span></span>  
  
<a name="Loading_a_Resource_Dictionary_from_the_Site_of_Origin"></a>   
#### <a name="loading-a-resource-dictionary-from-the-site-of-origin"></a><span data-ttu-id="3945f-295">원본 사이트에서 리소스 사전 로드</span><span class="sxs-lookup"><span data-stu-id="3945f-295">Loading a Resource Dictionary from the Site of Origin</span></span>  
 <span data-ttu-id="3945f-296">리소스 사전 (<xref:System.Windows.ResourceDictionary>) 응용 프로그램 테마를 지 원하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-296">Resource dictionaries (<xref:System.Windows.ResourceDictionary>) can be used to support application themes.</span></span> <span data-ttu-id="3945f-297">테마를 만들고 관리하는 한 가지 방법은 응용 프로그램의 원본 사이트에 위치한 리소스 사전으로 여러 개의 테마를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-297">One way to create and manage themes is to create multiple themes as resource dictionaries that are located at an application's site of origin.</span></span> <span data-ttu-id="3945f-298">이렇게 하면 응용 프로그램을 다시 컴파일하여 배포할 필요 없이 테마를 추가하고 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-298">This allows themes to be added and updated without recompiling and redeploying an application.</span></span> <span data-ttu-id="3945f-299">이러한 리소스 사전을 식별할 수 있고 팩을 사용 하 여 로드 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], 다음 예제에 나와 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-299">These resource dictionaries can be identified and loaded using pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], which is shown in the following example.</span></span>  
  
 [!code-xaml[ResourceDictionarySnippets#ResourceDictionaryPackURI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourceDictionarySnippets/CS/App.xaml#resourcedictionarypackuri)]  
  
 <span data-ttu-id="3945f-300">테마에 대 한 개요에 대 한 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], 참조 [스타일 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3945f-300">For an overview of themes in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], see [Styling and Templating](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3945f-301">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3945f-301">See Also</span></span>  
 [<span data-ttu-id="3945f-302">WPF 응용 프로그램 리소스, 콘텐츠 및 데이터 파일</span><span class="sxs-lookup"><span data-stu-id="3945f-302">WPF Application Resource, Content, and Data Files</span></span>](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)
