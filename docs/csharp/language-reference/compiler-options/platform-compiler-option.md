---
title: -platform(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /platform
helpviewer_keywords:
- platform compiler option [C#]
- -platform compiler option [C#]
- /platform compiler option [C#]
ms.assetid: c290ff5e-47f4-4a85-9bb3-9c2525b0be04
ms.openlocfilehash: d4cb4e219189deb6048692822c9245c5a03c5675
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="-platform-c-compiler-options"></a><span data-ttu-id="903dd-102">-platform(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="903dd-102">-platform (C# Compiler Options)</span></span>
<span data-ttu-id="903dd-103">어셈블리를 실행할 수 있는 CLR(공용 언어 런타임) 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="903dd-103">Specifies which version of the Common Language Runtime (CLR) can run the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="903dd-104">구문</span><span class="sxs-lookup"><span data-stu-id="903dd-104">Syntax</span></span>  
  
```console  
-platform:string  
```  
  
#### <a name="parameters"></a><span data-ttu-id="903dd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="903dd-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="903dd-106">anycpu(기본값), anycpu32bitpreferred, ARM, x64, x86 또는 Itanium입니다.</span><span class="sxs-lookup"><span data-stu-id="903dd-106">anycpu (default), anycpu32bitpreferred, ARM, x64, x86, or Itanium.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="903dd-107">설명</span><span class="sxs-lookup"><span data-stu-id="903dd-107">Remarks</span></span>  
  
-   <span data-ttu-id="903dd-108">**anycpu**(기본값)는 어셈블리를 모든 플랫폼에서 실행되도록 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="903dd-108">**anycpu** (default) compiles your assembly to run on any platform.</span></span> <span data-ttu-id="903dd-109">응용 프로그램은 가능할 때마다 64비트로 실행되고 해당 모드를 사용할 수 있을 때만 32비트로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="903dd-109">Your application runs as a 64-bit process whenever possible and falls back to 32-bit when only that mode is available.</span></span>  
  
-   <span data-ttu-id="903dd-110">**anycpu32bitpreferred**는 어셈블리를 모든 플랫폼에서 실행되도록 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="903dd-110">**anycpu32bitpreferred** compiles your assembly to run on any platform.</span></span> <span data-ttu-id="903dd-111">응용 프로그램은 64비트와 32비트 응용 프로그램을 모두 지원하는 시스템에서 32비트로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="903dd-111">Your application runs in 32-bit mode on systems that support both 64-bit and 32-bit applications.</span></span> <span data-ttu-id="903dd-112">.NET Framework 4.5를 대상으로 하는 프로젝트에 대해서만 이 옵션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="903dd-112">You can specify this option only for projects that target the .NET Framework 4.5.</span></span>  
  
-   <span data-ttu-id="903dd-113">**ARM**은 ARM(고급 RISC 컴퓨터) 프로세서가 있는 컴퓨터에서 실행할 어셈블리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="903dd-113">**ARM** compiles your assembly to run on a computer that has an Advanced RISC Machine (ARM) processor.</span></span>  
  
-   <span data-ttu-id="903dd-114">**x64**는 AMD64 또는 EM64T 명령 집합을 지원하는 컴퓨터에서 64비트 CLR에 의해 실행되도록 어셈블리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="903dd-114">**x64** compiles your assembly to be run by the 64-bit CLR on a computer that supports the AMD64 or EM64T instruction set.</span></span>  
  
-   <span data-ttu-id="903dd-115">**x86**은 32비트, x86 호환 CLR에 의해 실행되도록 어셈블리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="903dd-115">**x86** compiles your assembly to be run by the 32-bit, x86-compatible CLR.</span></span>  
  
-   <span data-ttu-id="903dd-116">**Itanium**은 Itanium 프로세서 탑재 컴퓨터에서 64비트 CLR에 의해 실행되도록 어셈블리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="903dd-116">**Itanium** compiles your assembly to be run by the 64-bit CLR on a computer with an Itanium processor.</span></span>  
  
 <span data-ttu-id="903dd-117">64비트 Windows 운영 체제:</span><span class="sxs-lookup"><span data-stu-id="903dd-117">On a 64-bit Windows operating system:</span></span>  
  
-   <span data-ttu-id="903dd-118">**-platform:x86**으로 컴파일된 어셈블리는 WOW64에서 실행되는 32비트 CLR에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="903dd-118">Assemblies compiled with **-platform:x86** execute on the 32-bit CLR running under WOW64.</span></span>  
  
-   <span data-ttu-id="903dd-119">**-platform:anycpu**로 컴파일된 DLL은 이 DLL이 로드된 프로세스와 동일한 CLR에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="903dd-119">A DLL compiled with the **-platform:anycpu** executes on the same CLR as the process into which it is loaded.</span></span>  
  
-   <span data-ttu-id="903dd-120">**-platform:anycpu**로 컴파일된 실행 파일은 64비트 CLR에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="903dd-120">Executables that are compiled with the **-platform:anycpu** execute on the 64-bit CLR.</span></span>  
  
-   <span data-ttu-id="903dd-121">**-platform:anycpu32bitpreferred**로 컴파일된 실행 파일은 32비트 CLR에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="903dd-121">Executables compiled with **-platform:anycpu32bitpreferred** execute on the 32-bit CLR.</span></span>  
  
 <span data-ttu-id="903dd-122">**anycpu32bitpreferred** 설정은 실행 파일(.EXE)에 대해서만 유효하고 .NET Framework 4.5를 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="903dd-122">The **anycpu32bitpreferred** setting is valid only for executable (.EXE) files, and it requires the .NET Framework 4.5.</span></span>  
  
 <span data-ttu-id="903dd-123">Windows 64비트 운영 체제에서 실행할 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [64비트 응용 프로그램](../../../framework/64-bit-apps.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="903dd-123">For more information about developing an application to run on a Windows 64-bit operating system, see [64-bit Applications](../../../framework/64-bit-apps.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="903dd-124">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="903dd-124">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="903dd-125">프로젝트의 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="903dd-125">Open the **Properties** page for the project.</span></span>  
  
2.  <span data-ttu-id="903dd-126">**빌드** 속성 페이지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="903dd-126">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="903dd-127">.NET Framework 4.5를 대상으로 하는 프로젝트에 대해 **플랫폼 대상** 속성을 수정하고 **32비트 선호** 확인란을 선택하거나 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="903dd-127">Modify the **Platform target** property and, for projects that target the .NET Framework 4.5, select or clear the **Prefer 32-bit** check box.</span></span>  
  
 <span data-ttu-id="903dd-128">**-platform**은 Visual C# Express의 개발 환경에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="903dd-128">**Note -platform** is not available in the development environment in Visual C# Express.</span></span>  
  
 <span data-ttu-id="903dd-129">이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.PlatformTarget%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="903dd-129">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.PlatformTarget%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="903dd-130">예</span><span class="sxs-lookup"><span data-stu-id="903dd-130">Example</span></span>  
 <span data-ttu-id="903dd-131">다음 예제에서는 **-platform** 옵션을 사용하여 응용 프로그램이 64비트 Windows 운영 체제의 64비트 CLR에서만 실행되도록 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="903dd-131">The following example shows how to use the **-platform** option to specify that the application should be run by the 64-bit CLR on a 64-bit Windows operating system.</span></span>  
  
```console  
csc -platform:anycpu filename.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="903dd-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="903dd-132">See Also</span></span>  
 [<span data-ttu-id="903dd-133">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="903dd-133">C# Compiler Options</span></span>](index.md)  
 [<span data-ttu-id="903dd-134">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="903dd-134">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
