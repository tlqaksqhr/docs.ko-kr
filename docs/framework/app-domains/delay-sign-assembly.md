---
title: "어셈블리 서명 연기"
ms.date: 07/31/2017
ms.prod: .net-framework
ms.technology: dotnet-bcl
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- deferring assembly signing
- signing assemblies
- assemblies [.NET Framework], signing
- strong-named assemblies, delaying assembly signing
- partial assembly signing
ms.assetid: 9d300e17-5bf1-4360-97da-2aa55efd9070
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ce40f08b8b31ae3a4647e8919b4ea862fc03506f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="delay-signing-an-assembly"></a><span data-ttu-id="b3d54-102">어셈블리 서명 연기</span><span class="sxs-lookup"><span data-stu-id="b3d54-102">Delay Signing an Assembly</span></span>
<span data-ttu-id="b3d54-103">조직에 개발자가 일상적으로 액세스할 수 없는 엄격하게 보호된 키 쌍이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d54-103">An organization can have a closely guarded key pair that developers do not have access to on a daily basis.</span></span> <span data-ttu-id="b3d54-104">대부분이 경우 공개 키를 사용할 수 있지만 개인 키에 대한 액세스는 몇몇 개인만으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3d54-104">The public key is often available, but access to the private key is restricted to only a few individuals.</span></span> <span data-ttu-id="b3d54-105">강력한 이름을 사용하여 어셈블리를 개발할 경우 강력한 이름의 대상 어셈블리를 참조하는 각 어셈블리에는 대상 어셈블리에 강력한 이름을 지정하는 데 사용되는 공개 키의 토큰이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3d54-105">When developing assemblies with strong names, each assembly that references the strong-named target assembly contains the token of the public key used to give the target assembly a strong name.</span></span> <span data-ttu-id="b3d54-106">이를 위해 개발 프로세스 중에 공개 키를 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d54-106">This requires that the public key be available during the development process.</span></span>  
  
 <span data-ttu-id="b3d54-107">빌드 시간에 지연된 서명이나 부분 서명을 사용하여 PE(이식 가능한 실행 파일) 파일에서 강력한 이름 시그니처에 사용할 공간을 예약하지만, 약간 이후 단계까지(일반적으로 어셈블리를 제공하기 바로 전) 실제 서명을 연기할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d54-107">You can use delayed or partial signing at build time to reserve space in the portable executable (PE) file for the strong name signature, but defer the actual signing until some later stage (typically just before shipping the assembly).</span></span>  
  
 <span data-ttu-id="b3d54-108">다음 단계에서는 어셈블리 서명을 연기하는 프로세스를 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d54-108">The following steps outline the process to delay sign an assembly:</span></span>  
  
1.  <span data-ttu-id="b3d54-109">최종 서명을 수행할 조직에서 키 쌍의 공개 키 부분을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b3d54-109">Obtain the public key portion of the key pair from the organization that will do the eventual signing.</span></span> <span data-ttu-id="b3d54-110">일반적으로 이 키는 .snk 파일 형식으로, [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]에서 제공된 [강력한 이름 도구(Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md)를 사용하여 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d54-110">Typically this key is in the form of an .snk file, which can be created using the [Strong Name tool (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) provided by the [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span></span>  
  
2.  <span data-ttu-id="b3d54-111"><xref:System.Reflection>의 두 가지 사용자 지정 특성을 사용하여 어셈블리에 대한 소스 코드를 주석으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d54-111">Annotate the source code for the assembly with two custom attributes from <xref:System.Reflection>:</span></span>  
  
    -   <span data-ttu-id="b3d54-112"><xref:System.Reflection.AssemblyKeyFileAttribute> - 매개 변수로 공개 키가 포함된 파일의 이름을 생성자에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d54-112"><xref:System.Reflection.AssemblyKeyFileAttribute>, which passes the name of the file containing the public key as a parameter to its constructor.</span></span>  
  
    -   <span data-ttu-id="b3d54-113"><xref:System.Reflection.AssemblyDelaySignAttribute> - 매개 변수로 **true**를 생성자에 전달하여 서명 지연에 사용 중임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b3d54-113"><xref:System.Reflection.AssemblyDelaySignAttribute>, which indicates that delay signing is being used by passing **true** as a parameter to its constructor.</span></span> <span data-ttu-id="b3d54-114">예:</span><span class="sxs-lookup"><span data-stu-id="b3d54-114">For example:</span></span>  
  
         [!code-cpp[AssemblyDelaySignAttribute#4](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyDelaySignAttribute/cpp/source2.cpp#4)]
         [!code-csharp[AssemblyDelaySignAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyDelaySignAttribute/cs/source2.cs#4)]
         [!code-vb[AssemblyDelaySignAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyDelaySignAttribute/vb/source2.vb#4)]  
  
3.  <span data-ttu-id="b3d54-115">컴파일러는 공개 키를 어셈블리 매니페스트에 삽입하고 PE 파일에서 전체 강력한 이름 시그니처에 사용할 공간을 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d54-115">The compiler inserts the public key into the assembly manifest and reserves space in the PE file for the full strong name signature.</span></span> <span data-ttu-id="b3d54-116">실제 공개 키는 어셈블리가 빌드되는 동안 저장되어야 합니다. 그래야 이 어셈블리를 참조하는 다른 어셈블리가 자체적인 어셈블리 참조에 저장할 키를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d54-116">The real public key must be stored while the assembly is built so that other assemblies that reference this assembly can obtain the key to store in their own assembly reference.</span></span>  
  
4.  <span data-ttu-id="b3d54-117">어셈블리에 유효한 강력한 이름 시그니처가 없으므로 해당 시그니처의 확인이 해제되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d54-117">Because the assembly does not have a valid strong name signature, the verification of that signature must be turned off.</span></span> <span data-ttu-id="b3d54-118">강력한 이름 도구와 함께 **–Vr** 옵션을 사용하여 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d54-118">You can do this by using the **–Vr** option with the Strong Name tool.</span></span>  
  
     <span data-ttu-id="b3d54-119">다음 예제에서는 `myAssembly.dll`이라는 어셈블리에 대한 확인을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d54-119">The following example turns off verification for an assembly called `myAssembly.dll`.</span></span>  
  
    ```  
    sn –Vr myAssembly.dll  
    ```  
  
     <span data-ttu-id="b3d54-120">ARM(Advanced RISC Machine) 마이크로프로세서와 같은 강력한 이름 도구를 실행할 수 없는 플랫폼에서 확인을 해제하려면 **–Vk** 옵션을 사용하여 레지스트리 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b3d54-120">To turn off verification on platforms where you can’t run the Strong Name tool, such as Advanced RISC Machine (ARM) microprocessors, use the **–Vk** option to create a registry file.</span></span> <span data-ttu-id="b3d54-121">확인을 해제하려는 컴퓨터의 레지스트리에 레지스트리 파일을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b3d54-121">Import the registry file into the registry on the computer where you want to turn off verification.</span></span> <span data-ttu-id="b3d54-122">다음 예제에서는 `myAssembly.dll`에 대한 레지스트리 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b3d54-122">The following example creates a registry file for `myAssembly.dll`.</span></span>  
  
    ```  
    sn –Vk myRegFile.reg myAssembly.dll  
    ```  
  
     <span data-ttu-id="b3d54-123">**–Vr** 또는 **–Vk** 옵션을 사용하여 테스트 키 서명에 대해 .snk 파일을 선택적으로 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d54-123">With either the **–Vr** or **–Vk** option, you can optionally include an .snk file for test key signing.</span></span>  
  
    > [!WARNING]
    > <span data-ttu-id="b3d54-124">강력한 이름을 보안용으로 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="b3d54-124">Do not rely on strong names for security.</span></span> <span data-ttu-id="b3d54-125">강력한 이름은 고유한 ID를 제공할 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="b3d54-125">They provide a unique identity only.</span></span>
  
    > [!NOTE]
    >  <span data-ttu-id="b3d54-126">64비트 컴퓨터에서 Visual Studio를 통해 개발하는 동안 서명 연기를 사용하고 **모든 CPU**에 대한 어셈블리를 컴파일할 경우 **-Vr** 옵션을 두 번 적용해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d54-126">If you use delay signing during development with Visual Studio on a 64-bit computer, and you compile an assembly for **Any CPU**, you might have to apply the **-Vr** option twice.</span></span> <span data-ttu-id="b3d54-127">Visual Studio에서 **모든 CPU**는 **플랫폼 대상** 빌드 속성의 값이고 명령줄에서 컴파일할 경우 기본값입니다. 응용 프로그램을 명령줄 또는 파일 탐색기에서 실행하려면 [Sn.exe(강력한 이름 도구)](../../../docs/framework/tools/sn-exe-strong-name-tool.md)의 64비트 버전을 사용하여 **-Vr** 옵션을 어셈블리에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d54-127">(In Visual Studio, **Any CPU** is a value of the **Platform Target** build property; when you compile from the command line, it is the default.) To run your application from the command line or from File Explorer, use the 64-bit version of the [Sn.exe (Strong Name Tool)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) to apply the **-Vr** option to the assembly.</span></span> <span data-ttu-id="b3d54-128">디자인 타임에 어셈블리를 Visual Studio에 로드하려면(예: 어셈블리에 응용 프로그램의 다른 어셈블리에서 사용되는 구성 요소가 포함된 경우) 강력한 이름 도구의 32비트 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d54-128">To load the assembly into Visual Studio at design time (for example, if the assembly contains components that are used by other assemblies in your application), use the 32-bit version of the strong-name tool.</span></span> <span data-ttu-id="b3d54-129">그 이유는 JIT(Just-In-Time) 컴파일러가 명령줄에서 실행되는 어셈블리를 64비트 네이티브 코드로 컴파일하고, 디자인 타임 환경에 로드되는 어셈블리를 32비트 네이티브 코드로 컴파일하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="b3d54-129">This is because the just-in-time (JIT) compiler compiles the assembly to 64-bit native code when the assembly is run from the command line, and to 32-bit native code when the assembly is loaded into the design-time environment.</span></span>  
  
5.  <span data-ttu-id="b3d54-130">나중에, 일반적으로 제공하기 바로 전에 강력한 이름 도구와 함께 **–R** 옵션을 사용하여 실제 강력한 이름으로 서명하기 위해 조직의 서명 기관에 어셈블리를 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d54-130">Later, usually just before shipping, you submit the assembly to your organization's signing authority for the actual strong name signing using the **–R** option with the Strong Name tool.</span></span>  
  
     <span data-ttu-id="b3d54-131">다음 예제에서는 `myAssembly.dll` 키 쌍 파일을 사용하여 강력한 이름으로 `sgKey.snk` 어셈블리에 서명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d54-131">The following example signs an assembly called `myAssembly.dll` with a strong name using the `sgKey.snk` key pair.</span></span>  
  
    ```  
    sn -R myAssembly.dll sgKey.snk  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b3d54-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b3d54-132">See Also</span></span>  
 [<span data-ttu-id="b3d54-133">어셈블리 만들기</span><span class="sxs-lookup"><span data-stu-id="b3d54-133">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)  
 [<span data-ttu-id="b3d54-134">방법: 공개/개인 키 쌍 만들기</span><span class="sxs-lookup"><span data-stu-id="b3d54-134">How to: Create a Public-Private Key Pair</span></span>](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md)  
 [<span data-ttu-id="b3d54-135">Sn.exe(강력한 이름 도구)</span><span class="sxs-lookup"><span data-stu-id="b3d54-135">Sn.exe (Strong Name Tool)</span></span>](../../../docs/framework/tools/sn-exe-strong-name-tool.md)  
 [<span data-ttu-id="b3d54-136">어셈블리를 사용한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="b3d54-136">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
