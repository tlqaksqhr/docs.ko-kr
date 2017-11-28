---
title: "어셈블리 매니페스트"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assembly manifest
- dynamic assemblies, assembly manifest
- metadata, assembly manifest
- culture, assembly manifest
- assemblies [.NET Framework], metadata
ms.assetid: 8e40fab9-549d-4731-aec2-ffa47a382de0
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1df64129a0ae15b5bad387a62ca60bb4b1b92f7d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="assembly-manifest"></a><span data-ttu-id="c9e69-102">어셈블리 매니페스트</span><span class="sxs-lookup"><span data-stu-id="c9e69-102">Assembly Manifest</span></span>
<span data-ttu-id="c9e69-103">정적 또는 동적 어셈블리인지 여부에 상관 없이 모든 어셈블리는 어셈블리의 요소가 서로 어떻게 연관되는지를 설명하는 데이터 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e69-103">Every assembly, whether static or dynamic, contains a collection of data that describes how the elements in the assembly relate to each other.</span></span> <span data-ttu-id="c9e69-104">이러한 어셈블리 메타데이터는 어셈블리 매니페스트에 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e69-104">The assembly manifest contains this assembly metadata.</span></span> <span data-ttu-id="c9e69-105">어셈블리 매니페스트는 어셈블리의 버전 요구 사항과 보안 ID를 지정하는 데 필요한 모든 메타데이터와 어셈블리의 범위를 정의하고 리소스나 클래스에 대한 참조를 확인하는 데 필요한 모든 메타데이터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e69-105">An assembly manifest contains all the metadata needed to specify the assembly's version requirements and security identity, and all metadata needed to define the scope of the assembly and resolve references to resources and classes.</span></span> <span data-ttu-id="c9e69-106">어셈블리 매니페스트는 MSIL(Microsoft Intermediate Language)로 PE 파일(.exe 또는 .dll)에 저장되거나 어셈블리 매니페스트 정보만 포함하는 독립 실행형 PE 파일에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9e69-106">The assembly manifest can be stored in either a PE file (an .exe or .dll) with Microsoft intermediate language (MSIL) code or in a standalone PE file that contains only assembly manifest information.</span></span>  
  
 <span data-ttu-id="c9e69-107">다음 예제에서는 매니페스트를 저장하는 여러 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c9e69-107">The following illustration shows the different ways the manifest can be stored.</span></span>  
  
 <span data-ttu-id="c9e69-108">![단일 파일 어셈블리](../../../docs/framework/app-domains/media/assemblytypes.gif "assemblytypes")</span><span class="sxs-lookup"><span data-stu-id="c9e69-108">![A single&#45;file assembly](../../../docs/framework/app-domains/media/assemblytypes.gif "assemblytypes")</span></span>  
<span data-ttu-id="c9e69-109">어셈블리 종류</span><span class="sxs-lookup"><span data-stu-id="c9e69-109">Types of assemblies</span></span>  
  
 <span data-ttu-id="c9e69-110">하나의 연관 파일을 갖는 어셈블리의 경우, 매니페스트는 PE 파일에 포함되어 단일 파일 어셈블리를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e69-110">For an assembly with one associated file, the manifest is incorporated into the PE file to form a single-file assembly.</span></span> <span data-ttu-id="c9e69-111">독립 실행형 매니페스트 파일을 만들거나 어셈블리의 PE 파일 중 하나에 매니페스트를 포함시키면 다중 파일 어셈블리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e69-111">You can create a multifile assembly with a standalone manifest file or with the manifest incorporated into one of the PE files in the assembly.</span></span>  
  
 <span data-ttu-id="c9e69-112">각 어셈블리의 매니페스트는 다음 기능을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e69-112">Each assembly's manifest performs the following functions:</span></span>  
  
-   <span data-ttu-id="c9e69-113">어셈블리를 구성하고 있는 파일을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e69-113">Enumerates the files that make up the assembly.</span></span>  
  
-   <span data-ttu-id="c9e69-114">어셈블리의 형식 및 리소스로의 참조가 해당 선언 및 구현이 포함된 파일에 매핑되는 방법을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e69-114">Governs how references to the assembly's types and resources map to the files that contain their declarations and implementations.</span></span>  
  
-   <span data-ttu-id="c9e69-115">어셈블리가 종속된 다른 어셈블리를 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e69-115">Enumerates other assemblies on which the assembly depends.</span></span>  
  
-   <span data-ttu-id="c9e69-116">어셈블리 소비자와 어셈블리의 구현 정보 간의 간접 참조 수준을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e69-116">Provides a level of indirection between consumers of the assembly and the assembly's implementation details.</span></span>  
  
-   <span data-ttu-id="c9e69-117">어셈블리가 자체 설명되도록 렌더링합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e69-117">Renders the assembly self-describing.</span></span>  
  
## <a name="assembly-manifest-contents"></a><span data-ttu-id="c9e69-118">어셈블리 매니페스트 내용</span><span class="sxs-lookup"><span data-stu-id="c9e69-118">Assembly Manifest Contents</span></span>  
 <span data-ttu-id="c9e69-119">다음 표에서는 어셈블리 매니페스트에 포함되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c9e69-119">The following table shows the information contained in the assembly manifest.</span></span> <span data-ttu-id="c9e69-120">어셈블리의 ID는 처음 네 개 항목(어셈블리 이름, 버전 번호, 문화권 및 강력한 이름 정보)으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9e69-120">The first four items—the assembly name, version number, culture, and strong name information—make up the assembly's identity.</span></span>  
  
|<span data-ttu-id="c9e69-121">정보</span><span class="sxs-lookup"><span data-stu-id="c9e69-121">Information</span></span>|<span data-ttu-id="c9e69-122">설명</span><span class="sxs-lookup"><span data-stu-id="c9e69-122">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="c9e69-123">어셈블리 이름</span><span class="sxs-lookup"><span data-stu-id="c9e69-123">Assembly name</span></span>|<span data-ttu-id="c9e69-124">어셈블리의 이름을 나타내는 텍스트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c9e69-124">A text string specifying the assembly's name.</span></span>|  
|<span data-ttu-id="c9e69-125">버전 번호</span><span class="sxs-lookup"><span data-stu-id="c9e69-125">Version number</span></span>|<span data-ttu-id="c9e69-126">주 버전 번호와 부 버전 번호 및 수정 번호와 빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="c9e69-126">A major and minor version number, and a revision and build number.</span></span> <span data-ttu-id="c9e69-127">공용 언어 런타임은 이들 번호를 사용하여 버전 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e69-127">The common language runtime uses these numbers to enforce version policy.</span></span>|  
|<span data-ttu-id="c9e69-128">문화권</span><span class="sxs-lookup"><span data-stu-id="c9e69-128">Culture</span></span>|<span data-ttu-id="c9e69-129">어셈블리에서 지원하는 문화권 또는 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="c9e69-129">Information on the culture or language the assembly supports.</span></span> <span data-ttu-id="c9e69-130">이 정보는 특정 어셈블리를 문화권 또는 언어 관련 정보를 포함하는 위성 어셈블리로 지정할 때만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e69-130">This information should be used only to designate an assembly as a satellite assembly containing culture- or language-specific information.</span></span> <span data-ttu-id="c9e69-131">문화권 정보를 포함하는 어셈블리는 자동으로 위성 어셈블리로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9e69-131">(An assembly with culture information is automatically assumed to be a satellite assembly.)</span></span>|  
|<span data-ttu-id="c9e69-132">강력한 이름 정보</span><span class="sxs-lookup"><span data-stu-id="c9e69-132">Strong name information</span></span>|<span data-ttu-id="c9e69-133">어셈블리에 강력한 이름을 지정하는 경우 게시자의 공개 키.</span><span class="sxs-lookup"><span data-stu-id="c9e69-133">The public key from the publisher if the assembly has been given a strong name.</span></span>|  
|<span data-ttu-id="c9e69-134">어셈블리에 포함된 파일 목록</span><span class="sxs-lookup"><span data-stu-id="c9e69-134">List of all files in the assembly</span></span>|<span data-ttu-id="c9e69-135">어셈블리에 포함된 각 파일의 해시와 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c9e69-135">A hash of each file contained in the assembly and a file name.</span></span> <span data-ttu-id="c9e69-136">어셈블리를 구성하는 모든 파일은 어셈블리 매니페스트가 포함된 파일과 동일한 디렉터리에 위치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e69-136">Note that all files that make up the assembly must be in the same directory as the file containing the assembly manifest.</span></span>|  
|<span data-ttu-id="c9e69-137">형식 참조 정보</span><span class="sxs-lookup"><span data-stu-id="c9e69-137">Type reference information</span></span>|<span data-ttu-id="c9e69-138">이 정보는 형식 참조를 해당 선언 및 구현이 포함된 파일에 매핑하는 데 사용되며</span><span class="sxs-lookup"><span data-stu-id="c9e69-138">Information used by the runtime to map a type reference to the file that contains its declaration and implementation.</span></span> <span data-ttu-id="c9e69-139">어셈블리에서 내보내는 형식에 대해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9e69-139">This is used for types that are exported from the assembly.</span></span>|  
|<span data-ttu-id="c9e69-140">참조된 어셈블리에 대한 정보</span><span class="sxs-lookup"><span data-stu-id="c9e69-140">Information on referenced assemblies</span></span>|<span data-ttu-id="c9e69-141">어셈블리에서 정적으로 참조하는 다른 어셈블리의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="c9e69-141">A list of other assemblies that are statically referenced by the assembly.</span></span> <span data-ttu-id="c9e69-142">각 참조는 종속 어셈블리의 이름, 어셈블리 메타데이터(버전, 문화권, 운영 체제 등) 및 공개 키(강력한 이름의 어셈블리인 경우)를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e69-142">Each reference includes the dependent assembly's name, assembly metadata (version, culture, operating system, and so on), and public key, if the assembly is strong named.</span></span>|  
  
 <span data-ttu-id="c9e69-143">코드에서 어셈블리 특성을 사용하여 어셈블리 매니페스트에 있는 정보를 추가하거나 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e69-143">You can add or change some information in the assembly manifest by using assembly attributes in your code.</span></span> <span data-ttu-id="c9e69-144">버전 정보나 정보 특성(상표, 저작권, 제품, 회사, 정보 버전 등)을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e69-144">You can change version information and informational attributes, including Trademark, Copyright, Product, Company, and Informational Version.</span></span> <span data-ttu-id="c9e69-145">어셈블리 특성에 대한 전체 목록은 [어셈블리 특성 설정](../../../docs/framework/app-domains/set-assembly-attributes.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c9e69-145">For a complete list of assembly attributes, see [Setting Assembly Attributes](../../../docs/framework/app-domains/set-assembly-attributes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9e69-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c9e69-146">See Also</span></span>  
 [<span data-ttu-id="c9e69-147">어셈블리 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="c9e69-147">Assembly Contents</span></span>](../../../docs/framework/app-domains/assembly-contents.md)  
 [<span data-ttu-id="c9e69-148">어셈블리 버전 관리</span><span class="sxs-lookup"><span data-stu-id="c9e69-148">Assembly Versioning</span></span>](../../../docs/framework/app-domains/assembly-versioning.md)  
 [<span data-ttu-id="c9e69-149">위성 어셈블리 만들기</span><span class="sxs-lookup"><span data-stu-id="c9e69-149">Creating Satellite Assemblies</span></span>](../../../docs/framework/resources/creating-satellite-assemblies-for-desktop-apps.md)  
 [<span data-ttu-id="c9e69-150">강력한 이름의 어셈블리</span><span class="sxs-lookup"><span data-stu-id="c9e69-150">Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/strong-named-assemblies.md)
