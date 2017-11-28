---
title: "방법: 어셈블리의 정규화된 이름 식별"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- names [.NET Framework], fully qualified type names
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
ms.assetid: 009dae23-e1f6-4a64-9a9a-32e4c34802b0
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6e3736a1fa16b51262169d4d3efec56a958cedf6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-an-assembly39s-fully-qualified-name"></a><span data-ttu-id="78bdb-102">방법: 어셈블리의 정규화된 이름 식별</span><span class="sxs-lookup"><span data-stu-id="78bdb-102">How to: Determine an Assembly&#39;s Fully Qualified Name</span></span>
<span data-ttu-id="78bdb-103">전역 어셈블리 캐시에서 어셈블리의 정규화된 이름을 찾으려면 전역 어셈블리 캐시 도구([Gacutil.exe](../../../docs/framework/tools/gacutil-exe-gac-tool.md))를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="78bdb-103">To discover the fully qualified name of an assembly in the global assembly cache, use the Global Assembly Cache Tool ([Gacutil.exe](../../../docs/framework/tools/gacutil-exe-gac-tool.md)).</span></span> <span data-ttu-id="78bdb-104">[방법: 전역 어셈블리 캐시의 내용 보기](../../../docs/framework/app-domains/how-to-view-the-contents-of-the-gac.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78bdb-104">See [How to: View the Contents of the Global Assembly Cache](../../../docs/framework/app-domains/how-to-view-the-contents-of-the-gac.md).</span></span>  
  
 <span data-ttu-id="78bdb-105">전역 어셈블리 캐시에 없는 어셈블리의 경우, 코드를 사용하여 콘솔이나 변수로 정보를 출력하거나 [Ildasm.exe(IL 디스어셈블러)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)를 사용하여 정규화된 이름이 포함된 어셈블리의 메타데이터를 검사하는 등 다양한 방법으로 정규화된 어셈블리 이름을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78bdb-105">For assemblies that are not in the global assembly cache, you can get the fully qualified assembly name in a number of ways: can use code to output the information to the console or to a variable, or you can use the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to examine the assembly's metadata, which contains the fully qualified name.</span></span>  
  
-   <span data-ttu-id="78bdb-106">응용 프로그램에서 어셈블리를 이미 로드한 경우 <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> 속성의 값을 검색하여 정규화된 이름을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78bdb-106">If the assembly is already loaded by the application, you can retrieve the value of the <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> property to get the fully qualified name.</span></span> <span data-ttu-id="78bdb-107">어셈블리가 GAC에 있는지 여부에 관계없이 이 접근 방식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78bdb-107">You can use this approach whether or not the assembly is in the GAC.</span></span> <span data-ttu-id="78bdb-108">예제에서는 그림을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="78bdb-108">The example provides an illustration.</span></span>  
  
-   <span data-ttu-id="78bdb-109">어셈블리의 파일 시스템 경로를 알고 있는 경우 static(Visual basic에서는 `Shared`) <xref:System.Reflection.AssemblyName.GetAssemblyName%2A?displayProperty=nameWithType> 메서드를 호출하여 정규화된 어셈블리 이름을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78bdb-109">If you know the assembly's file system path, you can call the static (`Shared` in Visual Basic) <xref:System.Reflection.AssemblyName.GetAssemblyName%2A?displayProperty=nameWithType> method to get the fully qualified assembly name.</span></span> <span data-ttu-id="78bdb-110">다음은 간단한 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="78bdb-110">The following is a simple example.</span></span>  
  
     [!code-csharp[System.Reflection.AssemblyName.GetAssemblyName#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.reflection.assemblyname.getassemblyname/cs/getassemblyname1.cs#1)]
     [!code-vb[System.Reflection.AssemblyName.GetAssemblyName#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.reflection.assemblyname.getassemblyname/vb/getassemblyname1.vb#1)]  
  
-   <span data-ttu-id="78bdb-111">[Ildasm.exe(IL 디스어셈블러)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)를 사용하여 정규화된 이름이 포함된 어셈블리의 메타데이터를 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78bdb-111">You can use the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to examine the assembly's metadata, which contains the fully qualified name.</span></span>  
  
 <span data-ttu-id="78bdb-112">버전, 문화권 및 어셈블리 이름과 같은 어셈블리 특성 설정에 대한 자세한 내용은 [어셈블리 특성 설정](../../../docs/framework/app-domains/set-assembly-attributes.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78bdb-112">For more information about setting assembly attributes such as version, culture, and assembly name, see [Setting Assembly Attributes](../../../docs/framework/app-domains/set-assembly-attributes.md).</span></span> <span data-ttu-id="78bdb-113">어셈블리에 강력한 이름을 지정하는 방법에 대한 자세한 내용은 [강력한 이름의 어셈블리 만들기 및 사용](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78bdb-113">For more information about giving an assembly a strong name, see [Creating and Using Strong-Named Assemblies](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="78bdb-114">예제</span><span class="sxs-lookup"><span data-stu-id="78bdb-114">Example</span></span>  
 <span data-ttu-id="78bdb-115">다음 코드 예제에서는 지정된 클래스를 포함하는 어셈블리의 정규화된 이름을 콘솔에 표시하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="78bdb-115">The following code example shows how to display the fully qualified name of an assembly containing a specified class to the console.</span></span> <span data-ttu-id="78bdb-116">앱에서 이미 로드한 어셈블리의 이름을 검색하므로 어셈블리가 GAC에 있는지 여부는 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="78bdb-116">Because it retrieves the name of an assembly that the app has already loaded, it does not matter whether the assembly is in the GAC.</span></span>  
  
 [!code-cpp[Assembly.Fullname#2](../../../samples/snippets/cpp/VS_Snippets_CLR/Assembly.FullName/CPP/example2.cpp#2)]
 [!code-csharp[Assembly.Fullname#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Assembly.FullName/CS/example2.cs#2)]
 [!code-vb[Assembly.Fullname#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Assembly.FullName/VB/example2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="78bdb-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="78bdb-117">See Also</span></span>  
 [<span data-ttu-id="78bdb-118">어셈블리 이름</span><span class="sxs-lookup"><span data-stu-id="78bdb-118">Assembly Names</span></span>](../../../docs/framework/app-domains/assembly-names.md)  
 [<span data-ttu-id="78bdb-119">어셈블리 만들기</span><span class="sxs-lookup"><span data-stu-id="78bdb-119">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)  
 [<span data-ttu-id="78bdb-120">강력한 이름의 어셈블리 만들기 및 사용</span><span class="sxs-lookup"><span data-stu-id="78bdb-120">Creating and Using Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)  
 [<span data-ttu-id="78bdb-121">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="78bdb-121">Global Assembly Cache</span></span>](../../../docs/framework/app-domains/gac.md)  
 [<span data-ttu-id="78bdb-122">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="78bdb-122">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="78bdb-123">어셈블리를 사용한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="78bdb-123">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
