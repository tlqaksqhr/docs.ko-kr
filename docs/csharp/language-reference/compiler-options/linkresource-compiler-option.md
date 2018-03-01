---
title: "-linkresource(C# 컴파일러 옵션)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /linkresource
helpviewer_keywords:
- /linkresource compiler option [C#]
- linkres compiler option [C#]
- /linkres compiler option [C#]
- -linkres compiler option [C#]
- -linkresource compiler option [C#]
- linkresource compiler option [C#]
ms.assetid: 440c26c2-77c1-4811-a0a3-57cce3f5fc96
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7da5a55fa96c11d79f8c616cf0f1f4e0ed109bfa
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="-linkresource-c-compiler-options"></a><span data-ttu-id="7e239-102">-linkresource(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="7e239-102">-linkresource (C# Compiler Options)</span></span>
<span data-ttu-id="7e239-103">출력 파일에 .NET Framework 리소스에 대한 링크를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7e239-103">Creates a link to a .NET Framework resource in the output file.</span></span> <span data-ttu-id="7e239-104">리소스 파일은 출력 파일에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e239-104">The resource file is not added to the output file.</span></span> <span data-ttu-id="7e239-105">이 점에서 출력 파일에 리소스 파일을 포함하는 [-resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) 옵션과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="7e239-105">This differs from the [-resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) option which does embed a resource file in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e239-106">구문</span><span class="sxs-lookup"><span data-stu-id="7e239-106">Syntax</span></span>  
  
```console  
-linkresource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="7e239-107">인수</span><span class="sxs-lookup"><span data-stu-id="7e239-107">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="7e239-108">어셈블리에서 연결할 .NET Framework 리소스 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="7e239-108">The .NET Framework resource file to which you want to link from the assembly.</span></span>  
  
 <span data-ttu-id="7e239-109">`identifier`(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="7e239-109">`identifier` (optional)</span></span>  
 <span data-ttu-id="7e239-110">리소스의 논리적 이름으로, 리소스를 로드하는 데 사용되는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7e239-110">The logical name for the resource; the name that is used to load the resource.</span></span> <span data-ttu-id="7e239-111">기본값은 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7e239-111">The default is the name of the file.</span></span>  
  
 <span data-ttu-id="7e239-112">`accessibility-modifier`(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="7e239-112">`accessibility-modifier` (optional)</span></span>  
 <span data-ttu-id="7e239-113">리소스의 접근성으로, public 또는 private입니다.</span><span class="sxs-lookup"><span data-stu-id="7e239-113">The accessibility of the resource: public or private.</span></span> <span data-ttu-id="7e239-114">기본값은 public입니다.</span><span class="sxs-lookup"><span data-stu-id="7e239-114">The default is public.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e239-115">설명</span><span class="sxs-lookup"><span data-stu-id="7e239-115">Remarks</span></span>  
 <span data-ttu-id="7e239-116">기본적으로 연결된 리소스는 C# 컴파일러로 생성될 때 어셈블리에서 public입니다.</span><span class="sxs-lookup"><span data-stu-id="7e239-116">By default, linked resources are public in the assembly when they are created with the C# compiler.</span></span> <span data-ttu-id="7e239-117">리소스를 private로 만들려면 접근성 한정자로 `private`를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7e239-117">To make the resources private, specify `private` as the accessibility modifier.</span></span> <span data-ttu-id="7e239-118">`public` 또는 `private` 이외의 다른 한정자는 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e239-118">No other modifier other than `public` or `private` is allowed.</span></span>  
  
 <span data-ttu-id="7e239-119">**-linkresource**에는 **-target:module** 이외의 [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) 옵션 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7e239-119">**-linkresource** requires one of the [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) options other than **-target:module**.</span></span>  
  
 <span data-ttu-id="7e239-120">예를 들어 `filename`이 [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md)나 개발 환경에서 만들어진 .NET Framework 리소스 파일인 경우에는 <xref:System.Resources> 네임스페이스의 멤버를 사용하여 해당 파일에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e239-120">If `filename` is a .NET Framework resource file created, for example, by [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="7e239-121">자세한 내용은 <xref:System.Resources.ResourceManager?displayProperty=nameWithType>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7e239-121">For more information, see <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span></span> <span data-ttu-id="7e239-122">다른 모든 리소스의 경우에는 런타임에 `GetManifestResource` 클래스의 <xref:System.Reflection.Assembly> 메서드를 사용하여 리소스에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="7e239-122">For all other resources, use the `GetManifestResource` methods in the <xref:System.Reflection.Assembly> class to access the resource at run time.</span></span>  
  
 <span data-ttu-id="7e239-123">`filename`에 지정된 파일은 모든 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e239-123">The file specified in `filename` can be any format.</span></span> <span data-ttu-id="7e239-124">예를 들어 네이티브 DLL을 어셈블리의 일부로 설정하면 전역 어셈블리 캐시에 설치하고 어셈블리의 관리 코드에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e239-124">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span> <span data-ttu-id="7e239-125">다음 중 두 번째 예제에서 이 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7e239-125">The second of the following examples shows how to do this.</span></span> <span data-ttu-id="7e239-126">어셈블리 링커에서도 동일한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e239-126">You can do the same thing in the Assembly Linker.</span></span> <span data-ttu-id="7e239-127">다음 중 세 번째 예제에서 이 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7e239-127">The third of the following examples shows how to do this.</span></span> <span data-ttu-id="7e239-128">자세한 내용은 [Al.exe(어셈블리 링커)](../../../framework/tools/al-exe-assembly-linker.md) 및 [어셈블리 및 전역 어셈블리 캐시 사용](../../../framework/app-domains/working-with-assemblies-and-the-gac.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7e239-128">For more information, see [Al.exe (Assembly Linker)](../../../framework/tools/al-exe-assembly-linker.md) and [Working with Assemblies and the Global Assembly Cache](../../../framework/app-domains/working-with-assemblies-and-the-gac.md).</span></span>  
  
 <span data-ttu-id="7e239-129">**-linkres**는 **-linkresource**의 약식입니다.</span><span class="sxs-lookup"><span data-stu-id="7e239-129">**-linkres** is the short form of **-linkresource**.</span></span>  
  
 <span data-ttu-id="7e239-130">이 컴파일러 옵션은 Visual Studio에서 사용할 수 없으며 프로그래밍 방식으로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7e239-130">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e239-131">예</span><span class="sxs-lookup"><span data-stu-id="7e239-131">Example</span></span>  
 <span data-ttu-id="7e239-132">`in.cs`를 컴파일하고 리소스 파일 `rf.resource`에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="7e239-132">Compile `in.cs` and link to resource file `rf.resource`:</span></span>  
  
```console  
csc -linkresource:rf.resource in.cs  
```  
  
## <a name="example"></a><span data-ttu-id="7e239-133">예</span><span class="sxs-lookup"><span data-stu-id="7e239-133">Example</span></span>  
 <span data-ttu-id="7e239-134">`A.cs`를 DLL로 컴파일하고, 네이티브 DLL N.dll에 연결한 다음 출력을 GAC(전역 어셈블리 캐시)에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="7e239-134">Compile `A.cs` into a DLL, link to a native DLL N.dll, and put the output in the Global Assembly Cache (GAC).</span></span> <span data-ttu-id="7e239-135">이 예제에서는 A.dll과 N.dll이 둘 다 GAC에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e239-135">In this example, both A.dll and N.dll will reside in the GAC.</span></span>  
  
```console  
csc -linkresource:N.dll -t:library A.cs  
gacutil -i A.dll  
```  
  
## <a name="example"></a><span data-ttu-id="7e239-136">예</span><span class="sxs-lookup"><span data-stu-id="7e239-136">Example</span></span>  
 <span data-ttu-id="7e239-137">이 예제에서는 앞의 예제와 동일한 작업을 수행하지만 어셈블리 링커 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7e239-137">This example does the same thing as the previous one, but by using Assembly Linker options.</span></span>  
  
```console  
csc -t:module A.cs  
al -out:A.dll A.netmodule -link:N.dll   
gacutil -i A.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="7e239-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7e239-138">See Also</span></span>  
 [<span data-ttu-id="7e239-139">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="7e239-139">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="7e239-140">Al.exe(어셈블리 링커)</span><span class="sxs-lookup"><span data-stu-id="7e239-140">Al.exe (Assembly Linker)</span></span>](../../../framework/tools/al-exe-assembly-linker.md)  
 [<span data-ttu-id="7e239-141">어셈블리 및 전역 어셈블리 캐시 사용</span><span class="sxs-lookup"><span data-stu-id="7e239-141">Working with Assemblies and the Global Assembly Cache</span></span>](../../../framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [<span data-ttu-id="7e239-142">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="7e239-142">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
