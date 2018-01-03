---
title: ".NET Framework 도구"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- command line, .NET Framework tools
- .NET Framework, tools
- tools [.NET Framework]
- running .NET Framework tools
ms.assetid: a2ca532d-91f7-426a-9303-417c2ee1247c
caps.latest.revision: "65"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2615c7b8c75f7736bbf8334512790d0a5c43c8d1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="net-framework-tools"></a><span data-ttu-id="013c8-102">.NET Framework 도구</span><span class="sxs-lookup"><span data-stu-id="013c8-102">.NET Framework Tools</span></span>
<span data-ttu-id="013c8-103">.NET Framework 도구를 사용하면 .NET Framework를 대상으로 하는 응용 프로그램 및 구성 요소를 보다 쉽게 만들고 배포하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-103">The .NET Framework tools make it easier for you to create, deploy, and manage applications and components that target the .NET Framework.</span></span>  
  
 <span data-ttu-id="013c8-104">이 단원에서 설명하는 대부분의 .NET Framework 도구는 Visual Studio와 함께 자동으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-104">Most of the .NET Framework tools described in this section are automatically installed with Visual Studio.</span></span> <span data-ttu-id="013c8-105">설치에 대한 자세한 내용은 [Visual Studio 다운로드](http://go.microsoft.com/fwlink/?LinkID=325532)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="013c8-105">(For installation information , see the [Visual Studio Downloads](http://go.microsoft.com/fwlink/?LinkID=325532).)</span></span>  
  
 <span data-ttu-id="013c8-106">어셈블리 캐시 뷰어(Shfusion.dll)를 제외한 모든 도구는 명령줄에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-106">You can run all the tools from the command line with the exception of the Assembly Cache Viewer (Shfusion.dll).</span></span> <span data-ttu-id="013c8-107">Shfusion.dll에 액세스하려면 파일 탐색기를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-107">You must access Shfusion.dll from File Explorer.</span></span>  
  
 <span data-ttu-id="013c8-108">명령줄 도구를 실행하는 가장 좋은 방법은 Visual Studio의 개발자 명령 프롬프트를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-108">The best way to run the command-line tools is by using the Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="013c8-109">이러한 유틸리티를 사용하면 설치 폴더로 이동하지 않아도 도구를 쉽게 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-109">These utilities enable you to run the tools easily, without navigating to the installation folder.</span></span> <span data-ttu-id="013c8-110">자세한 내용은 [명령 프롬프트](../../../docs/framework/tools/developer-command-prompt-for-vs.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="013c8-110">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="013c8-111">일부 도구는 32비트 컴퓨터 또는 64비트 컴퓨터 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-111">Some tools are specific to either 32-bit computers or 64-bit computers.</span></span> <span data-ttu-id="013c8-112">컴퓨터에 적절한 버전의 도구를 실행하세요.</span><span class="sxs-lookup"><span data-stu-id="013c8-112">Be sure to run the appropriate version of the tool for your computer.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="013c8-113">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="013c8-113">In This Section</span></span>  
 [<span data-ttu-id="013c8-114">Al.exe(어셈블리 링커)</span><span class="sxs-lookup"><span data-stu-id="013c8-114">Al.exe (Assembly Linker)</span></span>](../../../docs/framework/tools/al-exe-assembly-linker.md)  
 <span data-ttu-id="013c8-115">모듈 또는 리소스 파일로부터 어셈블리 매니페스트가 있는 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-115">Generates a file that has an assembly manifest from modules or resource files.</span></span>  
  
 [<span data-ttu-id="013c8-116">Aximp.exe(Windows Forms ActiveX 컨트롤 가져오기)</span><span class="sxs-lookup"><span data-stu-id="013c8-116">Aximp.exe (Windows Forms ActiveX Control Importer)</span></span>](../../../docs/framework/tools/aximp-exe-windows-forms-activex-control-importer.md)  
 <span data-ttu-id="013c8-117">ActiveX 컨트롤용 COM 형식 라이브러리의 형식 정의를 Windows Forms 컨트롤로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-117">Converts type definitions in a COM type library for an ActiveX control into a Windows Forms control.</span></span>  
  
 [<span data-ttu-id="013c8-118">Caspol.exe(코드 액세스 보안 정책 도구)</span><span class="sxs-lookup"><span data-stu-id="013c8-118">Caspol.exe (Code Access Security Policy Tool)</span></span>](../../../docs/framework/tools/caspol-exe-code-access-security-policy-tool.md)  
 <span data-ttu-id="013c8-119">컴퓨터 정책 수준, 사용자 정책 수준 및 엔터프라이즈 정책 수준의 보안 정책을 보고 구성할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-119">Enables you to view and configure security policy for the machine policy level, the user policy level, and the enterprise policy level.</span></span> <span data-ttu-id="013c8-120">[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 이상 버전에서 [\<legacyCasPolicy> 요소](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md)를 `true`로 설정하지 않으면 이 도구는 CAS(코드 액세스 보안) 정책에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-120">In the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] and later, this tool does not affect code access security (CAS) policy unless the [\<legacyCasPolicy> element](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) is set to `true`.</span></span> <span data-ttu-id="013c8-121">자세한 내용은 [보안 변경 내용](../../../docs/framework/security/security-changes.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="013c8-121">For more information, see [Security Changes](../../../docs/framework/security/security-changes.md).</span></span>  
  
 [<span data-ttu-id="013c8-122">Cert2spc.exe(SPC 테스트 도구)</span><span class="sxs-lookup"><span data-stu-id="013c8-122">Cert2spc.exe (Software Publisher Certificate Test Tool)</span></span>](../../../docs/framework/tools/cert2spc-exe-software-publisher-certificate-test-tool.md)  
 <span data-ttu-id="013c8-123">하나 이상의 X.509 인증서에서 SPC(소프트웨어 게시 인증서)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-123">Creates a Software Publisher's Certificate (SPC) from one or more X.509 certificates.</span></span> <span data-ttu-id="013c8-124">이 도구는 테스트 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-124">This tool is for testing purposes only.</span></span>  
  
 [<span data-ttu-id="013c8-125">Certmgr.exe(인증서 관리자 도구)</span><span class="sxs-lookup"><span data-stu-id="013c8-125">Certmgr.exe (Certificate Manager Tool)</span></span>](../../../docs/framework/tools/certmgr-exe-certificate-manager-tool.md)  
 <span data-ttu-id="013c8-126">인증서, CTL(인증서 신뢰 목록) 및 CRL(인증서 해지 목록)을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-126">Manages certificates, certificate trust lists (CTLs), and certificate revocation lists (CRLs).</span></span>  
  
 [<span data-ttu-id="013c8-127">Clrver.exe(CLR 버전 도구)</span><span class="sxs-lookup"><span data-stu-id="013c8-127">Clrver.exe (CLR Version Tool)</span></span>](../../../docs/framework/tools/clrver-exe-clr-version-tool.md)  
 <span data-ttu-id="013c8-128">컴퓨터에서 CLR(공용 언어 런타임)의 모든 설치 버전을 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-128">reports all the installed versions of the common language runtime (CLR) on the computer.</span></span>  
  
 [<span data-ttu-id="013c8-129">CorFlags.exe(CorFlags 변환 도구)</span><span class="sxs-lookup"><span data-stu-id="013c8-129">CorFlags.exe (CorFlags Conversion Tool)</span></span>](../../../docs/framework/tools/corflags-exe-corflags-conversion-tool.md)  
 <span data-ttu-id="013c8-130">PE(이식 가능한 실행) 이미지 헤더의 CorFlags 섹션을 구성할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-130">Lets you configure the CorFlags section of the header of a portable executable (PE) image.</span></span>  
  
 [<span data-ttu-id="013c8-131">Fuslogvw.exe(어셈블리 바인딩 로그 뷰어)</span><span class="sxs-lookup"><span data-stu-id="013c8-131">Fuslogvw.exe (Assembly Binding Log Viewer)</span></span>](../../../docs/framework/tools/fuslogvw-exe-assembly-binding-log-viewer.md)  
 <span data-ttu-id="013c8-132">.NET Framework에서 런타임에 어셈블리를 찾지 못하는 이유를 진단하는 데 도움이 되는 어셈블리 바인딩에 대한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-132">Displays information about assembly binds to help you diagnose why the .NET Framework cannot locate an assembly at run time.</span></span>  
  
 [<span data-ttu-id="013c8-133">Gacutil.exe(전역 어셈블리 캐시 도구)</span><span class="sxs-lookup"><span data-stu-id="013c8-133">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../../../docs/framework/tools/gacutil-exe-gac-tool.md)  
 <span data-ttu-id="013c8-134">전역 어셈블리 캐시와 다운로드 캐시의 내용을 보거나 조작할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-134">Lets you view and manipulate the contents of the global assembly cache and download cache.</span></span>  
  
 [<span data-ttu-id="013c8-135">Ilasm.exe(IL 어셈블러)</span><span class="sxs-lookup"><span data-stu-id="013c8-135">Ilasm.exe (IL Assembler)</span></span>](../../../docs/framework/tools/ilasm-exe-il-assembler.md)  
 <span data-ttu-id="013c8-136">IL(Intermediate Language)로 PE(이식 가능한 실행) 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-136">Generates a portable executable (PE) file from intermediate language (IL).</span></span> <span data-ttu-id="013c8-137">이렇게 생성된 실행 파일을 실행하여 IL이 예상대로 실행되는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-137">You can run the resulting executable to determine whether the IL performs as expected.</span></span>  
  
 [<span data-ttu-id="013c8-138">Ildasm.exe(IL 디스어셈블러)</span><span class="sxs-lookup"><span data-stu-id="013c8-138">Ildasm.exe (IL Disassembler)</span></span>](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)  
 <span data-ttu-id="013c8-139">IL(Intermediate Language) 코드가 들어 있는 PE(이식 가능한 실행) 파일을 사용하여 IL 어셈블러(Ilasm.exe)에 입력할 수 있는 텍스트 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-139">Takes a portable executable (PE) file that contains intermediate language (IL) code and creates a text file that can be input to the IL Assembler (Ilasm.exe).</span></span>  
  
 [<span data-ttu-id="013c8-140">Installutil.exe(설치 관리자 도구)</span><span class="sxs-lookup"><span data-stu-id="013c8-140">Installutil.exe (Installer Tool)</span></span>](../../../docs/framework/tools/installutil-exe-installer-tool.md)  
 <span data-ttu-id="013c8-141">특정 어셈블리에서 설치 관리자 구성 요소를 실행하는 방법으로 서버 리소스를 설치하고 제거할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-141">Enables you to install and uninstall server resources by executing the installer components in a specified assembly.</span></span> <span data-ttu-id="013c8-142"><xref:System.Configuration.Install> 네임스페이스의 클래스에서 작동합니다. 특정 어셈블리에서 설치 관리자 구성 요소를 실행하는 방법으로 서버 리소스를 설치하고 제거할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-142">(Works with classes in the <xref:System.Configuration.Install> namespace.) Enables you to install and uninstall server resources by executing the installer components in a specified assembly.</span></span> <span data-ttu-id="013c8-143"><xref:System.Configuration.Install> 네임스페이스의 클래스에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-143">(Works with classes in the <xref:System.Configuration.Install> namespace.)</span></span>  
  
 [<span data-ttu-id="013c8-144">Lc.exe(라이선스 컴파일러)</span><span class="sxs-lookup"><span data-stu-id="013c8-144">Lc.exe (License Compiler)</span></span>](../../../docs/framework/tools/lc-exe-license-compiler.md)  
 <span data-ttu-id="013c8-145">라이선스 정보가 들어 있는 텍스트 파일을 읽고, 공용 언어 런타임 실행 파일에 리소스로 포함할 수 있는 .licenses 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-145">Reads text files that contain licensing information and produces a .licenses file that can be embedded in a common language runtime executable as a resource.</span></span> <span data-ttu-id="013c8-146">라이선스 정보가 들어 있는 텍스트 파일을 읽고, 공용 언어 런타임 실행 파일에 리소스로 포함할 수 있는 .licenses 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-146">Reads text files that contain licensing information and produces a .licenses file that can be embedded in a common language runtime executable as a resource.</span></span>  
  
 [<span data-ttu-id="013c8-147">Mage.exe(매니페스트 생성 및 편집 도구)</span><span class="sxs-lookup"><span data-stu-id="013c8-147">Mage.exe (Manifest Generation and Editing Tool)</span></span>](../../../docs/framework/tools/mage-exe-manifest-generation-and-editing-tool.md)  
 <span data-ttu-id="013c8-148">응용 프로그램 및 배포 매니페스트를 만들고, 편집하고, 서명할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-148">Lets you create, edit, and sign application and deployment manifests.</span></span> <span data-ttu-id="013c8-149">Mage.exe는 명령줄 도구로서 일괄 처리 스크립트뿐 아니라 ASP.NET 응용 프로그램을 비롯한 Windows 기반 응용 프로그램에서도 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-149">As a command-line tool, Mage.exe can be run from both batch scripts and other Windows-based applications, including ASP.NET applications.</span></span>  
  
 [<span data-ttu-id="013c8-150">MageUI.exe(매니페스트 생성 및 편집 도구, 그래픽 클라이언트)</span><span class="sxs-lookup"><span data-stu-id="013c8-150">MageUI.exe (Manifest Generation and Editing Tool, Graphical Client)</span></span>](../../../docs/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client.md)  
 <span data-ttu-id="013c8-151">명령줄 도구인 Mage.exe와 동일한 기능을 지원하지만 Windows 기반 UI(사용자 인터페이스)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-151">Supports the same functionality as the command-line tool Mage.exe, but uses a Windows-based user interface (UI).</span></span> <span data-ttu-id="013c8-152">명령줄 도구인 Mage.exe와 동일한 기능을 지원하지만 Windows 기반 UI(사용자 인터페이스)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-152">Supports the same functionality as the command-line tool Mage.exe, but uses a Windows-based user interface (UI).</span></span>  
  
 [<span data-ttu-id="013c8-153">MDbg.exe(.NET Framework 명령줄 디버거)</span><span class="sxs-lookup"><span data-stu-id="013c8-153">MDbg.exe (.NET Framework Command-Line Debugger)</span></span>](../../../docs/framework/tools/mdbg-exe.md)  
 <span data-ttu-id="013c8-154">도구 공급업체 및 응용 프로그램 개발자가 .NET Framework 공용 언어 런타임을 대상으로 하는 프로그램에서 버그를 쉽게 찾아서 수정할 수 있도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-154">Helps tools vendors and application developers find and fix bugs in programs that target the .NET Framework common language runtime.</span></span> <span data-ttu-id="013c8-155">이 도구에는 디버깅 서비스를 제공하기 위해 런타임 디버깅 API가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-155">This tool uses the runtime debugging API to provide debugging services.</span></span>  
  
 [<span data-ttu-id="013c8-156">Mgmtclassgen.exe(강력하게 형식화된 관리 클래스 생성기)</span><span class="sxs-lookup"><span data-stu-id="013c8-156">Mgmtclassgen.exe (Management Strongly Typed Class Generator)</span></span>](../../../docs/framework/tools/mgmtclassgen-exe.md)  
 <span data-ttu-id="013c8-157">지정된 WMI(Windows Management Instrumentation) 클래스에 대한 초기 바인딩 관리되는 클래스를 생성할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-157">Enables you to generate an early-bound managed class for a specified Windows Management Instrumentation (WMI) class.</span></span>  
  
 [<span data-ttu-id="013c8-158">Mpgo.exe(관리되는 프로필 기반 최적화 도구)</span><span class="sxs-lookup"><span data-stu-id="013c8-158">Mpgo.exe (Managed Profile Guided Optimization Tool)</span></span>](../../../docs/framework/tools/mpgo-exe-managed-profile-guided-optimization-tool.md)  
 <span data-ttu-id="013c8-159">일반 최종 사용자 시나리오를 사용하여 네이티브 이미지 어셈블리를 조정하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-159">Enables you to tune native image assemblies using common end-user scenarios.</span></span> <span data-ttu-id="013c8-160">Mpgo.exe는 응용 프로그램 개발자가 선택한 교육 시나리오를 사용하여 네이티브 이미지 응용 프로그램 어셈블리(.NET Framework 어셈블리는 아님)에 대한 프로필 데이터를 생성하고 사용할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-160">Mpgo.exe allows the generation and consumption of profile data for native image application assemblies (not the .NET Framework assemblies) using training scenarios selected by the application developer.</span></span>  
  
 [<span data-ttu-id="013c8-161">Ngen.exe(네이티브 이미지 생성기)</span><span class="sxs-lookup"><span data-stu-id="013c8-161">Ngen.exe (Native Image Generator)</span></span>](../../../docs/framework/tools/ngen-exe-native-image-generator.md)  
 <span data-ttu-id="013c8-162">컴파일된 프로세서별 컴퓨터 코드가 포함된 파일인 네이티브 이미지를 사용하여 관리되는 응용 프로그램의 성능을 향상시킵니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-162">Improves the performance of managed applications through the use of native images (files containing compiled processor-specific machine code).</span></span> <span data-ttu-id="013c8-163">런타임은 JIT(Just-In-Time) 컴파일러를 사용하지 않고 캐시의 네이티브 이미지를 사용하여 원본 어셈블리를 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-163">The runtime can use native images from the cache instead of using the just-in-time (JIT) compiler to compile the original assembly.</span></span>  
  
 [<span data-ttu-id="013c8-164">Peverify.exe(PEVerify 도구)</span><span class="sxs-lookup"><span data-stu-id="013c8-164">Peverify.exe (PEVerify Tool)</span></span>](../../../docs/framework/tools/peverify-exe-peverify-tool.md)  
 <span data-ttu-id="013c8-165">MSIL(Microsoft Intermediate Language) 코드 및 관련 메타데이터가 형식 안전성 요구 사항을 충족하는지 여부를 쉽게 확인할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-165">Helps you verify whether your Microsoft intermediate language (MSIL) code and associated metadata meet type safety requirements.</span></span> <span data-ttu-id="013c8-166">MSIL(Microsoft Intermediate Language) 코드 및 관련 메타데이터가 형식 안전성 요구 사항을 충족하는지 여부를 쉽게 확인할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-166">Helps you verify whether your Microsoft intermediate language (MSIL) code and associated metadata meet type safety requirements.</span></span>  
  
 [<span data-ttu-id="013c8-167">Regasm.exe(어셈블리 등록 도구)</span><span class="sxs-lookup"><span data-stu-id="013c8-167">Regasm.exe (Assembly Registration Tool)</span></span>](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md)  
 <span data-ttu-id="013c8-168">어셈블리 내의 메타데이터를 읽고 레지스트리에 필요한 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-168">Reads the metadata within an assembly and adds the necessary entries to the registry.</span></span> <span data-ttu-id="013c8-169">이렇게 하면 COM 클라이언트를 .NET Framework 클래스로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-169">This enables COM clients to appear as .NET Framework classes.</span></span>  
  
 [<span data-ttu-id="013c8-170">Regsvcs.exe(.NET 서비스 설치 도구)</span><span class="sxs-lookup"><span data-stu-id="013c8-170">Regsvcs.exe (.NET Services Installation Tool)</span></span>](../../../docs/framework/tools/regsvcs-exe-net-services-installation-tool.md)  
 <span data-ttu-id="013c8-171">어셈블리를 로드 및 등록하고, 형식 라이브러리를 생성하여 지정된 COM+ 버전 1.0 응용 프로그램에 설치하며, 프로그래밍 방식으로 클래스에 추가한 서비스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-171">Loads and registers an assembly, generates and installs a type library into a specified COM+ version 1.0 application, and configures services that you have added programmatically to a class.</span></span>  
  
 [<span data-ttu-id="013c8-172">Resgen.exe(리소스 파일 생성기)</span><span class="sxs-lookup"><span data-stu-id="013c8-172">Resgen.exe (Resource File Generator)</span></span>](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)  
 <span data-ttu-id="013c8-173">텍스트 파일(.txt 또는 .restext)과 XML 기반 리소스 형식 파일(.resx)을 런타임 이진 실행 파일에 포함시키거나 위성 어셈블리로 컴파일할 수 있는 공용 언어 런타임 이진 파일(.resources)로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-173">Converts text (.txt or .restext) files and XML-based resource format (.resx) files to common language runtime binary (.resources) files that can be embedded in a runtime binary executable or compiled into satellite assemblies.</span></span>  
  
 [<span data-ttu-id="013c8-174">SecAnnotate.exe(.NET Security Annotator 도구)</span><span class="sxs-lookup"><span data-stu-id="013c8-174">SecAnnotate.exe (.NET Security Annotator Tool)</span></span>](../../../docs/framework/tools/secannotate-exe-net-security-annotator-tool.md)  
 <span data-ttu-id="013c8-175">어셈블리의 SecurityCritical 및 SecuritySafeCritical 부분을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-175">Identifies the SecurityCritical and SecuritySafeCritical portions of an assembly.</span></span> <span data-ttu-id="013c8-176">어셈블리의 `SecurityCritical` 및 `SecuritySafeCritical` 부분을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-176">Identifies the `SecurityCritical` and `SecuritySafeCritical` portions of an assembly.</span></span>  
  
 [<span data-ttu-id="013c8-177">SignTool.exe(서명 도구)</span><span class="sxs-lookup"><span data-stu-id="013c8-177">SignTool.exe (Sign Tool)</span></span>](../../../docs/framework/tools/signtool-exe.md)  
 <span data-ttu-id="013c8-178">파일에 디지털 서명을 하고, 파일의 서명을 확인하고, 파일에 타임스탬프를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-178">Digitally signs files, verifies signatures in files, and time-stamps files.</span></span>  
  
 [<span data-ttu-id="013c8-179">Sn.exe(강력한 이름 도구)</span><span class="sxs-lookup"><span data-stu-id="013c8-179">Sn.exe (Strong Name Tool)</span></span>](../../../docs/framework/tools/sn-exe-strong-name-tool.md)  
 <span data-ttu-id="013c8-180">강력한 이름을 사용하여 어셈블리를 만들 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-180">Helps create assemblies with strong names.</span></span> <span data-ttu-id="013c8-181">이 도구는 키 관리, 서명 생성 및 서명 확인을 위한 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-181">This tool provides options for key management, signature generation, and signature verification.</span></span>  
  
 [<span data-ttu-id="013c8-182">SOS.dll(SOS 디버깅 확장)</span><span class="sxs-lookup"><span data-stu-id="013c8-182">SOS.dll (SOS Debugging Extension)</span></span>](../../../docs/framework/tools/sos-dll-sos-debugging-extension.md)  
 <span data-ttu-id="013c8-183">내부 공용 언어 런타임 환경에 대한 정보를 제공하여 관리되는 프로그램을 WinDbg.exe 디버거와 Visual Studio에서 쉽게 디버깅할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-183">Helps you debug managed programs in the WinDbg.exe debugger and in Visual Studio by providing information about the internal common language runtime environment.</span></span>  
  
 [<span data-ttu-id="013c8-184">SqlMetal.exe(코드 생성 도구)</span><span class="sxs-lookup"><span data-stu-id="013c8-184">SqlMetal.exe (Code Generation Tool)</span></span>](../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)  
 <span data-ttu-id="013c8-185">.NET Framework의 LINQ to SQL 구성 요소에 대한 코드와 매핑을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-185">Generates code and mapping for the LINQ to SQL component of the .NET Framework.</span></span>  
  
 [<span data-ttu-id="013c8-186">Storeadm.exe(격리된 저장소 도구)</span><span class="sxs-lookup"><span data-stu-id="013c8-186">Storeadm.exe (Isolated Storage Tool)</span></span>](../../../docs/framework/tools/storeadm-exe-isolated-storage-tool.md)  
 <span data-ttu-id="013c8-187">사용자의 저장소를 나열하고 삭제할 수 있는 옵션을 제공함으로써 격리된 저장소를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-187">Manages isolated storage; provides options for listing the user's stores and deleting them.</span></span>  
  
 [<span data-ttu-id="013c8-188">Tlbexp.exe(형식 라이브러리 내보내기)</span><span class="sxs-lookup"><span data-stu-id="013c8-188">Tlbexp.exe (Type Library Exporter)</span></span>](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)  
 <span data-ttu-id="013c8-189">공용 언어 런타임 어셈블리에 정의된 형식을 설명하는 형식 라이브러리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-189">Generates a type library that describes the types that are defined in a common language runtime assembly.</span></span>  
  
 [<span data-ttu-id="013c8-190">Tlbimp.exe(형식 라이브러리 가져오기)</span><span class="sxs-lookup"><span data-stu-id="013c8-190">Tlbimp.exe (Type Library Importer)</span></span>](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)  
 <span data-ttu-id="013c8-191">COM 형식 라이브러리에 있는 형식 정의를 공용 언어 런타임 어셈블리에 있는 동일한 기능의 정의로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-191">Converts the type definitions found in a COM type library into equivalent definitions in a common language runtime assembly.</span></span>  
  
 [<span data-ttu-id="013c8-192">Winmdexp.exe(Windows 런타임 메타데이터 내보내기 도구)</span><span class="sxs-lookup"><span data-stu-id="013c8-192">Winmdexp.exe (Windows Runtime Metadata Export Tool)</span></span>](../../../docs/framework/tools/winmdexp-exe-windows-runtime-metadata-export-tool.md)  
 <span data-ttu-id="013c8-193">.winmdobj 파일로 컴파일된 .NET Framework 어셈블리를 Windows 런타임 메타데이터 및 구현 정보가 둘 다 포함된 .winmd 파일로 패키지된 Windows 런타임 구성 요소에 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-193">Exports a .NET Framework assembly that is compiled as a .winmdobj file into a Windows Runtime component, which is packaged as a .winmd file that contains both Windows Runtime metadata and implementation information.</span></span>  
  
 [<span data-ttu-id="013c8-194">Winres.exe(Windows Forms 리소스 편집기)</span><span class="sxs-lookup"><span data-stu-id="013c8-194">Winres.exe (Windows Forms Resource Editor)</span></span>](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md)  
 <span data-ttu-id="013c8-195">Windows Forms에 사용되는 UI(사용자 인터페이스) 리소스(.resx 또는 .resources 파일)를 쉽게 지역화할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-195">Helps you localize user interface (UI) resources (.resx or .resources files) that are used by Windows Forms.</span></span> <span data-ttu-id="013c8-196">문자열을 번역한 다음 지역화(번역)된 문자열에 적합하도록 컨트롤의 크기를 조정하거나 컨트롤을 이동하고 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-196">You can translate strings, and then size, move, and hide controls to accommodate the localized strings.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="013c8-197">관련 단원</span><span class="sxs-lookup"><span data-stu-id="013c8-197">Related Sections</span></span>  
 [<span data-ttu-id="013c8-198">도구</span><span class="sxs-lookup"><span data-stu-id="013c8-198">Tools</span></span>](http://msdn.microsoft.com/library/f533241c-317c-445e-88ca-c80c8d078fca)  
 <span data-ttu-id="013c8-199">isXPS 규칙 도구(isXPS.exe) 및 성능 프로파일링 도구와 같은 도구가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-199">Includes tools such as the isXPS Conformance tool (isXPS.exe) and performance profiling tools.</span></span>  
  
 [<span data-ttu-id="013c8-200">Windows Communication Foundation 도구</span><span class="sxs-lookup"><span data-stu-id="013c8-200">Windows Communication Foundation Tools</span></span>](../../../docs/framework/wcf/tools.md)  
 <span data-ttu-id="013c8-201">WCF(Windows Communication Foundation) 응용 프로그램을 보다 쉽게 만들고 배포하고 관리할 수 있도록 지원하는 도구가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="013c8-201">Includes tools that make it easier for you to create, deploy, and manage Windows Communication Foundation (WCF) applications.</span></span>
