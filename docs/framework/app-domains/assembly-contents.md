---
title: 어셈블리 콘텐츠
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- assemblies [.NET Framework], single-file
- single-file assemblies
- multifile assemblies
ms.assetid: 28116714-da77-45f7-826d-fa035d121948
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38c0081e5677ca65e8c730c7199ebac5d4c86261
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="assembly-contents"></a><span data-ttu-id="32cb6-102">어셈블리 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="32cb6-102">Assembly Contents</span></span>
<span data-ttu-id="32cb6-103">일반적으로 정적 어셈블리는 네 가지 요소로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="32cb6-103">In general, a static assembly can consist of four elements:</span></span>  
  
-   <span data-ttu-id="32cb6-104">어셈블리 메타데이터를 포함하는 [어셈블리 매니페스트](../../../docs/framework/app-domains/assembly-manifest.md)</span><span class="sxs-lookup"><span data-stu-id="32cb6-104">The [assembly manifest](../../../docs/framework/app-domains/assembly-manifest.md), which contains assembly metadata.</span></span>  
  
-   <span data-ttu-id="32cb6-105">형식 메타데이터</span><span class="sxs-lookup"><span data-stu-id="32cb6-105">Type metadata.</span></span>  
  
-   <span data-ttu-id="32cb6-106">형식을 구현하는 MSIL(Microsoft Intermediate Language) 코드</span><span class="sxs-lookup"><span data-stu-id="32cb6-106">Microsoft intermediate language (MSIL) code that implements the types.</span></span>  
  
-   <span data-ttu-id="32cb6-107">리소스 집합</span><span class="sxs-lookup"><span data-stu-id="32cb6-107">A set of resources.</span></span>  
  
 <span data-ttu-id="32cb6-108">어셈블리 매니페스트만 있으면 되지만, 어셈블리에 의미 있는 기능을 부여하려면 형식 또는 리소스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="32cb6-108">Only the assembly manifest is required, but either types or resources are needed to give the assembly any meaningful functionality.</span></span>  
  
 <span data-ttu-id="32cb6-109">어셈블리의 요소를 그룹화하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32cb6-109">There are several ways to group these elements in an assembly.</span></span> <span data-ttu-id="32cb6-110">다음 예제에서와 같이 모든 요소를 하나의 실제 파일에 그룹화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32cb6-110">You can group all elements in a single physical file, which is shown in the following illustration.</span></span>  
  
 <span data-ttu-id="32cb6-111">![MyAssembly.dll](../../../docs/framework/app-domains/media/assemblyover1.gif "assemblyover1")</span><span class="sxs-lookup"><span data-stu-id="32cb6-111">![MyAssembly.dll](../../../docs/framework/app-domains/media/assemblyover1.gif "assemblyover1")</span></span>  
<span data-ttu-id="32cb6-112">단일 파일 어셈블리</span><span class="sxs-lookup"><span data-stu-id="32cb6-112">Single-file assembly</span></span>  
  
 <span data-ttu-id="32cb6-113">어셈블리의 요소를 여러 파일에 그룹화할 수도 있는데</span><span class="sxs-lookup"><span data-stu-id="32cb6-113">Alternatively, the elements of an assembly can be contained in several files.</span></span> <span data-ttu-id="32cb6-114">이러한 파일에는 컴파일된 코드의 모듈(.netmodule), 리소스(.bmp 또는 .jpg 파일), 응용 프로그램에 필요한 기타 파일 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32cb6-114">These files can be modules of compiled code (.netmodule), resources (such as .bmp or .jpg files), or other files required by the application.</span></span> <span data-ttu-id="32cb6-115">다중 파일 어셈블리는, 서로 다른 언어로 작성된 모듈을 결합하거나 응용 프로그램 다운로드 작업을 최적화할 수 있도록 필요할 때만 다운로드하는 모듈 안에 자주 사용하지 않는 형식을 그룹화할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="32cb6-115">Create a multifile assembly when you want to combine modules written in different languages and to optimize downloading an application by putting seldom used types in a module that is downloaded only when needed.</span></span>  
  
 <span data-ttu-id="32cb6-116">다음 그림에서는 가상의 응용 프로그램에 대해 일부 유틸리티 코드를 다른 모듈로 분리하고 원래 파일에 큰 리소스 파일(이 경우에는 .bmp 이미지)을 두었습니다.</span><span class="sxs-lookup"><span data-stu-id="32cb6-116">In the following illustration, the developer of a hypothetical application has chosen to separate some utility code into a different module and to keep a large resource file (in this case a .bmp image) in its original file.</span></span> <span data-ttu-id="32cb6-117">.NET Framework에서는 파일이 참조될 때만 파일을 다운로드합니다. 이와 같이 자주 참조되지 않는 코드를 응용 프로그램과 분리된 다른 파일에 보관함으로써 코드 다운로드를 최적화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32cb6-117">The .NET Framework downloads a file only when it is referenced; keeping infrequently referenced code in a separate file from the application optimizes code download.</span></span>  
  
 <span data-ttu-id="32cb6-118">![MyAssembly.dll](../../../docs/framework/app-domains/media/assemblyover2.gif "assemblyover2")</span><span class="sxs-lookup"><span data-stu-id="32cb6-118">![MyAssembly.dll](../../../docs/framework/app-domains/media/assemblyover2.gif "assemblyover2")</span></span>  
<span data-ttu-id="32cb6-119">다중 파일 어셈블리</span><span class="sxs-lookup"><span data-stu-id="32cb6-119">Multifile assembly</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="32cb6-120">파일 시스템은 다중 파일 어셈블리를 구성하는 파일을 실제로 연결하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="32cb6-120">The files that make up a multifile assembly are not physically linked by the file system.</span></span> <span data-ttu-id="32cb6-121">이들 파일은 어셈블리 매니페스트를 통해 연결되며, 공용 언어 런타임은 이들 파일을 하나의 단위로 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="32cb6-121">Rather, they are linked through the assembly manifest and the common language runtime manages them as a unit.</span></span>  
  
 <span data-ttu-id="32cb6-122">이 그림에서는 MyAssembly.dll에 포함된 어셈블리 매니페스트에 설명된 대로, 세 개 파일 모두 어셈블리에 속하지만</span><span class="sxs-lookup"><span data-stu-id="32cb6-122">In this illustration, all three files belong to an assembly, as described in the assembly manifest contained in MyAssembly.dll.</span></span> <span data-ttu-id="32cb6-123">파일 시스템에서는 이들 파일을 세 개의 별도 파일로 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="32cb6-123">To the file system, they are three separate files.</span></span> <span data-ttu-id="32cb6-124">Util.netmodule 파일은 아무런 어셈블리 정보를 포함하지 않기 때문에 모듈로 컴파일되었습니다.</span><span class="sxs-lookup"><span data-stu-id="32cb6-124">Note that the file Util.netmodule was compiled as a module because it contains no assembly information.</span></span> <span data-ttu-id="32cb6-125">어셈블리가 만들어질 때 MyAssembly.dll과 Util.netmodule 및 Graphic.bmp와의 관계를 나타내도록 어셈블리 매니페스트가 MyAssembly.dll에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="32cb6-125">When the assembly was created, the assembly manifest was added to MyAssembly.dll, indicating its relationship with Util.netmodule and Graphic.bmp.</span></span>  
  
 <span data-ttu-id="32cb6-126">소스 코드를 디자인하는 경우 응용 프로그램의 기능을 하나 이상의 파일로 분리하는 방법에 대해 명시적으로 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32cb6-126">As you currently design your source code, you make explicit decisions about how to partition the functionality of your application into one or more files.</span></span> <span data-ttu-id="32cb6-127">또한 .NET Framework 코드를 디자인하는 경우에도 해당 기능을 하나 이상의 어셈블리로 분리하는 방법에 대해 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32cb6-127">When designing .NET Framework code, you will make similar decisions about how to partition the functionality into one or more assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32cb6-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="32cb6-128">See Also</span></span>  
 [<span data-ttu-id="32cb6-129">공용 언어 런타임의 어셈블리</span><span class="sxs-lookup"><span data-stu-id="32cb6-129">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 [<span data-ttu-id="32cb6-130">어셈블리 매니페스트</span><span class="sxs-lookup"><span data-stu-id="32cb6-130">Assembly Manifest</span></span>](../../../docs/framework/app-domains/assembly-manifest.md)  
 [<span data-ttu-id="32cb6-131">어셈블리 보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="32cb6-131">Assembly Security Considerations</span></span>](../../../docs/framework/app-domains/assembly-security-considerations.md)
