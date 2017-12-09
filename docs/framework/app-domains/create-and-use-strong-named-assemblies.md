---
title: "강력한 이름의 어셈블리 만들기 및 사용"
ms.date: 08/01/2017
ms.prod: .net-framework
ms.technology: dotnet-bcl
ms.topic: article
helpviewer_keywords:
- strong-name bypass feature
- strong-named assemblies, about strong-named assemblies
- strong-named assemblies
- signing assemblies
- assemblies [.NET Framework], signing
- strong-named assemblies, scenarios
- assemblies [.NET Framework], strong-named
- strong-named assemblies, loading into trusted application domains
- assembly binding, strong-named
ms.assetid: ffbf6d9e-4a88-4a8a-9645-4ce0ee1ee5f9
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 39fbd38549a791a761c633dca90dbdeeeefce10b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="creating-and-using-strong-named-assemblies"></a><span data-ttu-id="7aa7b-102">강력한 이름의 어셈블리 만들기 및 사용</span><span class="sxs-lookup"><span data-stu-id="7aa7b-102">Creating and Using Strong-Named Assemblies</span></span>
<a name="top"></a> <span data-ttu-id="7aa7b-103">강력한 이름은 간단한 텍스트 이름, 버전 번호 및 문화권 정보(제공되는 경우)를 포함하는 어셈블리 ID와 공개 키 및 디지털 서명으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-103">A strong name consists of the assembly's identity—its simple text name, version number, and culture information (if provided)—plus a public key and a digital signature.</span></span> <span data-ttu-id="7aa7b-104">디지털 서명은 해당 개인 키를 사용하여 어셈블리 파일에서 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-104">It is generated from an assembly file using the corresponding private key.</span></span> <span data-ttu-id="7aa7b-105">어셈블리 파일은 어셈블리를 구성하는 모든 파일의 이름과 해시가 들어 있는 어셈블리 매니페스트를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-105">(The assembly file contains the assembly manifest, which contains the names and hashes of all the files that make up the assembly.)</span></span>  
  
 <span data-ttu-id="7aa7b-106">강력한 이름의 어셈블리는 다른 강력한 이름의 어셈블리에서 형식만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-106">A strong-named assembly can only use types from other strong-named assemblies.</span></span> <span data-ttu-id="7aa7b-107">그러지 않으면 강력한 이름의 어셈블리 무결성이 손상됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-107">Otherwise, the integrity of the strong-named assembly would be compromised.</span></span>  
  
 <span data-ttu-id="7aa7b-108">이 개요는 다음과 같은 단원으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-108">This overview contains the following sections:</span></span>  
  
-   [<span data-ttu-id="7aa7b-109">강력한 이름 시나리오</span><span class="sxs-lookup"><span data-stu-id="7aa7b-109">Strong Name Scenario</span></span>](#strong_name_scenario)  
  
-   [<span data-ttu-id="7aa7b-110">신뢰할 수 있는 어셈블리의 서명 확인 건너뛰기</span><span class="sxs-lookup"><span data-stu-id="7aa7b-110">Bypassing Signature Verification of Trusted Assemblies</span></span>](#bypassing_signature_verification)  
  
-   [<span data-ttu-id="7aa7b-111">관련 항목</span><span class="sxs-lookup"><span data-stu-id="7aa7b-111">Related Topics</span></span>](#related_topics)  
  
<a name="strong_name_scenario"></a>   
## <a name="strong-name-scenario"></a><span data-ttu-id="7aa7b-112">강력한 이름 시나리오</span><span class="sxs-lookup"><span data-stu-id="7aa7b-112">Strong Name Scenario</span></span>  
 <span data-ttu-id="7aa7b-113">다음 시나리오에서는 강력한 이름이 있는 어셈블리에 서명하고 나중에 이 이름을 사용하여 해당 어셈블리를 참조하는 과정에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-113">The following scenario outlines the process of signing an assembly with a strong name and later referencing it by that name.</span></span>  
  
1.  <span data-ttu-id="7aa7b-114">다음 방법 중 하나를 사용하여 강력한 이름의 어셈블리 A를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-114">Assembly A is created with a strong name using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="7aa7b-115">강력한 이름 만들기를 지원하는 개발 환경(예: [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)])을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-115">Using a development environment that supports creating strong names, such as [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)].</span></span>  
  
    -   <span data-ttu-id="7aa7b-116">[Sn.exe(강력한 이름 도구)](../../../docs/framework/tools/sn-exe-strong-name-tool.md)를 사용하여 암호화 키 쌍을 만들고 명령줄 컴파일러 또는 [Al.exe(어셈블리 링커)](../../../docs/framework/tools/al-exe-assembly-linker.md)를 사용하여 해당 키 쌍을 어셈블리에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-116">Creating a cryptographic key pair using the [Strong Name tool (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) and assigning that key pair to the assembly using either a command-line compiler or the [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md).</span></span> <span data-ttu-id="7aa7b-117">Windows SDK(소프트웨어 개발 키트)는 Sn.exe와 Al.exe를 모두 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-117">The Windows Software Development Kit (SDK) provides both Sn.exe and Al.exe.</span></span>  
  
2.  <span data-ttu-id="7aa7b-118">개발 환경 또는 도구에서는 개발자 개인 키를 사용하여 어셈블리 매니페스트가 포함된 파일의 해시에 서명합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-118">The development environment or tool signs the hash of the file containing the assembly's manifest with the developer's private key.</span></span> <span data-ttu-id="7aa7b-119">이 디지털 서명은 어셈블리 A의 매니페스트가 포함된 PE(이식 가능한 실행) 파일에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-119">This digital signature is stored in the portable executable (PE) file that contains Assembly A's manifest.</span></span>  
  
3.  <span data-ttu-id="7aa7b-120">어셈블리 B는 어셈블리 A의 소비자입니다. 어셈블리 B의 매니페스트에 있는 참조 섹션에는 어셈블리 A의 공개 키를 나타내는 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-120">Assembly B is a consumer of Assembly A. The reference section of Assembly B's manifest includes a token that represents Assembly A's public key.</span></span> <span data-ttu-id="7aa7b-121">토큰은 전체 공개 키의 일부이며, 공간을 절약하기 위해 키 자체 대신 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-121">A token is a portion of the full public key and is used rather than the key itself to save space.</span></span>  
  
4.  <span data-ttu-id="7aa7b-122">어셈블리가 전역 어셈블리 캐시에 있는 경우 공용 언어 런타임은 강력한 이름 서명을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-122">The common language runtime verifies the strong name signature when the assembly is placed in the global assembly cache.</span></span> <span data-ttu-id="7aa7b-123">런타임에 강력한 이름으로 바인딩할 때 공용 언어 런타임은 어셈블리 B의 매니페스트에 저장된 키와 어셈블리 A의 강력한 이름을 생성하는 데 사용된 키를 비교합니다. .NET Framework 보안 검사를 통과하고 바인딩에 성공하면, 어셈블리 B에서 어셈블리 A의 비트가 변조되지 않았고 실제로 어셈블리 A의 개발자가 이러한 비트를 전달했음을 보증합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-123">When binding by strong name at run time, the common language runtime compares the key stored in Assembly B's manifest with the key used to generate the strong name for Assembly A. If the .NET Framework security checks pass and the bind succeeds, Assembly B has a guarantee that Assembly A's bits have not been tampered with and that these bits actually come from the developers of Assembly A.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7aa7b-124">이 시나리오에서는 신뢰 문제를 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-124">This scenario doesn't address trust issues.</span></span> <span data-ttu-id="7aa7b-125">어셈블리에는 강력한 이름 외에도 전체 Microsoft Authenticode 서명이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-125">Assemblies can carry full Microsoft Authenticode signatures in addition to a strong name.</span></span> <span data-ttu-id="7aa7b-126">Authenticode 서명에는 신뢰 관계를 설정하는 인증서가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-126">Authenticode signatures include a certificate that establishes trust.</span></span> <span data-ttu-id="7aa7b-127">강력한 이름에는 이런 방식으로 코드에 서명하지 않아도 된다는 점에 유의하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-127">It's important to note that strong names don't require code to be signed in this way.</span></span> <span data-ttu-id="7aa7b-128">강력한 이름은 고유한 ID를 제공할 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-128">Strong names only provide a unique identity.</span></span>  
  
 [<span data-ttu-id="7aa7b-129">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="7aa7b-129">Back to top</span></span>](#top)  
  
<a name="bypassing_signature_verification"></a>   
## <a name="bypassing-signature-verification-of-trusted-assemblies"></a><span data-ttu-id="7aa7b-130">신뢰할 수 있는 어셈블리의 서명 확인 건너뛰기</span><span class="sxs-lookup"><span data-stu-id="7aa7b-130">Bypassing Signature Verification of Trusted Assemblies</span></span>  
 <span data-ttu-id="7aa7b-131">[!INCLUDE[net_v35SP1_long](../../../includes/net-v35sp1-long-md.md)]부터는 어셈블리가 완전 신뢰 응용 프로그램 도메인(예: `MyComputer` 영역의 기본 응용 프로그램 도메인)에 로드될 때 강력한 이름 서명의 유효성을 검사하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-131">Starting with the [!INCLUDE[net_v35SP1_long](../../../includes/net-v35sp1-long-md.md)], strong-name signatures are not validated when an assembly is loaded into a full-trust application domain, such as the default application domain for the `MyComputer` zone.</span></span> <span data-ttu-id="7aa7b-132">이를 강력한 이름 건너뛰기 기능이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-132">This is referred to as the strong-name bypass feature.</span></span> <span data-ttu-id="7aa7b-133">완전 신뢰 환경에서는 <xref:System.Security.Permissions.StrongNameIdentityPermission>에 대한 요청이 해당 서명과 관계없이 서명된 완전 신뢰 어셈블리에 대해 항상 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-133">In a full-trust environment, demands for <xref:System.Security.Permissions.StrongNameIdentityPermission> always succeed for signed, full-trust assemblies, regardless of their signature.</span></span> <span data-ttu-id="7aa7b-134">강력한 이름 건너뛰기 기능을 사용하면 이러한 상황에서 완전 신뢰 어셈블리의 강력한 이름 서명을 확인하는 데 따르는 불필요한 오버헤드가 발생하지 않으므로 어셈블리가 더 빠르게 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-134">The strong-name bypass feature avoids the unnecessary overhead of strong-name signature verification of full-trust assemblies in this situation, allowing the assemblies to load faster.</span></span>  
  
 <span data-ttu-id="7aa7b-135">건너뛰기 기능은 강력한 이름으로 서명되었으며 다음과 같은 특징이 있는 모든 어셈블리에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-135">The bypass feature applies to any assembly that is signed with a strong name and that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="7aa7b-136"><xref:System.Security.Policy.StrongName> 증명 정보 없이 완전 신뢰 가능(예: `MyComputer` 영역 증명 정보 보유)</span><span class="sxs-lookup"><span data-stu-id="7aa7b-136">Fully trusted without <xref:System.Security.Policy.StrongName> evidence (for example, has `MyComputer` zone evidence).</span></span>  
  
-   <span data-ttu-id="7aa7b-137">완전히 신뢰할 수 있는 <xref:System.AppDomain>에 로드됨</span><span class="sxs-lookup"><span data-stu-id="7aa7b-137">Loaded into a fully trusted <xref:System.AppDomain>.</span></span>  
  
-   <span data-ttu-id="7aa7b-138">해당 <xref:System.AppDomain>의 <xref:System.AppDomainSetup.ApplicationBase%2A> 속성 아래에 있는 위치에서 로드됨</span><span class="sxs-lookup"><span data-stu-id="7aa7b-138">Loaded from a location under the <xref:System.AppDomainSetup.ApplicationBase%2A> property of that <xref:System.AppDomain>.</span></span>  
  
-   <span data-ttu-id="7aa7b-139">서명이 연기되지 않음</span><span class="sxs-lookup"><span data-stu-id="7aa7b-139">Not delay-signed.</span></span>  
  
 <span data-ttu-id="7aa7b-140">개별 응용 프로그램 또는 컴퓨터에 대해 이 기능을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-140">This feature can be disabled for individual applications or for a computer.</span></span> <span data-ttu-id="7aa7b-141">[방법: 강력한 이름 건너뛰기 기능 비활성화](../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-141">See [How to: Disable the Strong-Name Bypass Feature](../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md).</span></span>  
  
 [<span data-ttu-id="7aa7b-142">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="7aa7b-142">Back to top</span></span>](#top)  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a><span data-ttu-id="7aa7b-143">관련 항목</span><span class="sxs-lookup"><span data-stu-id="7aa7b-143">Related Topics</span></span>  
  
|<span data-ttu-id="7aa7b-144">제목</span><span class="sxs-lookup"><span data-stu-id="7aa7b-144">Title</span></span>|<span data-ttu-id="7aa7b-145">설명</span><span class="sxs-lookup"><span data-stu-id="7aa7b-145">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="7aa7b-146">방법: 공개/개인 키 쌍 만들기</span><span class="sxs-lookup"><span data-stu-id="7aa7b-146">How to: Create a Public-Private Key Pair</span></span>](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md)|<span data-ttu-id="7aa7b-147">어셈블리 서명을 위해 암호화 키 쌍을 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-147">Describes how to create a cryptographic key pair for signing an assembly.</span></span>|  
|[<span data-ttu-id="7aa7b-148">방법: 강력한 이름으로 어셈블리 서명</span><span class="sxs-lookup"><span data-stu-id="7aa7b-148">How to: Sign an Assembly with a Strong Name</span></span>](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)|<span data-ttu-id="7aa7b-149">강력한 이름의 어셈블리를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-149">Describes how to create a strong-named assembly.</span></span>|  
|[<span data-ttu-id="7aa7b-150">향상된 강력한 이름 지정</span><span class="sxs-lookup"><span data-stu-id="7aa7b-150">Enhanced Strong Naming</span></span>](../../../docs/framework/app-domains/enhanced-strong-naming.md)|<span data-ttu-id="7aa7b-151">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에서 강력한 이름에 대해 향상된 기능을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-151">Describes enhancements to strong-names in the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span>|  
|[<span data-ttu-id="7aa7b-152">방법: 강력한 이름의 어셈블리 참조</span><span class="sxs-lookup"><span data-stu-id="7aa7b-152">How to: Reference a Strong-Named Assembly</span></span>](../../../docs/framework/app-domains/how-to-reference-a-strong-named-assembly.md)|<span data-ttu-id="7aa7b-153">컴파일 타임 또는 런타임에 강력한 이름의 어셈블리에 있는 형식 또는 리소스를 참조하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-153">Describes how to reference types or resources in a strong-named assembly at compile time or run time.</span></span>|  
|[<span data-ttu-id="7aa7b-154">방법: 강력한 이름 건너뛰기 기능 비활성화</span><span class="sxs-lookup"><span data-stu-id="7aa7b-154">How to: Disable the Strong-Name Bypass Feature</span></span>](../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md)|<span data-ttu-id="7aa7b-155">강력한 이름 서명의 유효성 검사를 건너뛰는 기능을 비활성화하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-155">Describes how to disable the feature that bypasses the validation of strong-name signatures.</span></span> <span data-ttu-id="7aa7b-156">이 기능은 모든 응용 프로그램 또는 특정 응용 프로그램에 대해 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-156">This feature can be disabled for all or for specific applications.</span></span>|  
|[<span data-ttu-id="7aa7b-157">어셈블리 만들기</span><span class="sxs-lookup"><span data-stu-id="7aa7b-157">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)|<span data-ttu-id="7aa7b-158">단일 파일 어셈블리와 다중 파일 어셈블리에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-158">Provides an overview of single-file and multifile assemblies.</span></span>|  
|[<span data-ttu-id="7aa7b-159">Visual Studio에서 어셈블리 서명을 연기하는 방법</span><span class="sxs-lookup"><span data-stu-id="7aa7b-159">How to Delay Sign an Assembly in Visual Studio</span></span>](/visualstudio/ide/managing-assembly-and-manifest-signing#how-to-sign-an-assembly-in-visual-studio)|<span data-ttu-id="7aa7b-160">어셈블리를 만든 후 강력한 이름의 어셈블리에 서명하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-160">Explains how to sign an assembly with a strong name after the assembly has been created.</span></span>|  
|[<span data-ttu-id="7aa7b-161">Sn.exe(강력한 이름 도구)</span><span class="sxs-lookup"><span data-stu-id="7aa7b-161">Sn.exe (Strong Name Tool)</span></span>](../../../docs/framework/tools/sn-exe-strong-name-tool.md)|<span data-ttu-id="7aa7b-162">강력한 이름의 어셈블리를 만들 수 있도록 지원하는 .NET Framework에 포함된 도구에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-162">Describes the tool included in the .NET Framework that helps create assemblies with strong names.</span></span> <span data-ttu-id="7aa7b-163">이 도구는 키 관리, 서명 생성 및 서명 확인을 위한 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-163">This tool provides options for key management, signature generation, and signature verification.</span></span>|  
|[<span data-ttu-id="7aa7b-164">Al.exe(어셈블리 링커)</span><span class="sxs-lookup"><span data-stu-id="7aa7b-164">Al.exe (Assembly Linker)</span></span>](../../../docs/framework/tools/al-exe-assembly-linker.md)|<span data-ttu-id="7aa7b-165">모듈 또는 리소스 파일에서 어셈블리 매니페스트가 있는 파일을 생성하는 .NET Framework에 포함된 도구에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-165">Describes the tool included in the .NET Framework that generates a file that has an assembly manifest from modules or resource files.</span></span>|
