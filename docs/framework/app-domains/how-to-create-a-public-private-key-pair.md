---
title: "방법: 공개/개인 키 쌍 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- key pairs for strong-named assemblies
- signing assemblies
- assemblies [.NET Framework], signing
- cryptographic key pairs
- snk files (key pair files)
- public-private key pairs
- .snk files
- strong-named assemblies, key pairs
ms.assetid: 05026813-f3bd-4d7c-9e0b-fc588eb3d114
caps.latest.revision: 16
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 772bcae9c3467553e4ca90989a82798155ee034c
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-public-private-key-pair"></a><span data-ttu-id="87225-102">방법: 공개/개인 키 쌍 만들기</span><span class="sxs-lookup"><span data-stu-id="87225-102">How to: Create a Public-Private Key Pair</span></span>
<span data-ttu-id="87225-103">강력한 이름으로 어셈블리를 서명하려면 공개/개인 키 쌍이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87225-103">To sign an assembly with a strong name, you must have a public/private key pair.</span></span> <span data-ttu-id="87225-104">이 공개/개인 암호화 키 쌍은 컴파일 중에 강력한 이름의 어셈블리를 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="87225-104">This public and private cryptographic key pair is used during compilation to create a strong-named assembly.</span></span> <span data-ttu-id="87225-105">[Sn.exe(강력한 이름 도구)](../../../docs/framework/tools/sn-exe-strong-name-tool.md)를 사용하여 키 쌍을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87225-105">You can create a key pair using the [Strong Name tool (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md).</span></span> <span data-ttu-id="87225-106">대개 키 쌍 파일의 확장명은 .snk입니다.</span><span class="sxs-lookup"><span data-stu-id="87225-106">Key pair files usually have an .snk extension.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="87225-107">[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]의 C# 및 Visual Basic 프로젝트 속성 페이지에는 Sn.exe를 사용하지 않고 기존 키 파일을 선택하거나 새 키 파일을 생성할 수 있게 하는 **서명** 탭이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87225-107">In [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], the C# and Visual Basic project property pages include a **Signing** tab that enables you to select existing key files or to generate new key files without using Sn.exe.</span></span> <span data-ttu-id="87225-108">Visual C++에서는 **속성 페이지** 창의 **구성 속성** 섹션의 **링커** 섹션에 있는 **고급** 속성 페이지에서 기존 키 파일의 위치를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87225-108">In Visual C++, you can specify the location of an existing key file in the **Advanced** property page in the **Linker** section of the **Configuration Properties** section of the **Property Pages** window.</span></span> <span data-ttu-id="87225-109"><xref:System.Reflection.AssemblyKeyFileAttribute> 특성을 사용하여 키 파일 쌍을 식별하는 방법은 [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]부터 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87225-109">The use of the <xref:System.Reflection.AssemblyKeyFileAttribute> attribute to identify key file pairs has been made obsolete beginning with [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)].</span></span>  
  
### <a name="to-create-a-key-pair"></a><span data-ttu-id="87225-110">키 쌍을 만들려면</span><span class="sxs-lookup"><span data-stu-id="87225-110">To create a key pair</span></span>  
  
1.  <span data-ttu-id="87225-111">명령 프롬프트에 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="87225-111">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="87225-112">**sn –k** \<*file name*></span><span class="sxs-lookup"><span data-stu-id="87225-112">**sn –k** \<*file name*></span></span>  
  
     <span data-ttu-id="87225-113">이 명령에서 *file name*은 키 쌍이 포함된 출력 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="87225-113">In this command, *file name* is the name of the output file containing the key pair.</span></span>  
  
 <span data-ttu-id="87225-114">다음 예제에서는 `sgKey.snk`라는 키 쌍을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="87225-114">The following example creates a key pair called `sgKey.snk`.</span></span>  
  
```  
sn -k sgKey.snk  
```  
  
 <span data-ttu-id="87225-115">어셈블리 서명을 연기하고 전체 키 쌍을 제어하려는 경우(외부 테스트 시나리오가 아님), 다음 명령을 사용하여 키 쌍을 생성한 후 이 키 쌍에서 공개 키를 별도의 파일로 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87225-115">If you intend to delay sign an assembly and you control the whole key pair (which is unlikely outside test scenarios), you can use the following commands to generate a key pair and then extract the public key from it into a separate file.</span></span> <span data-ttu-id="87225-116">먼저 다음과 같이 키 쌍을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="87225-116">First, create the key pair:</span></span>  
  
```  
sn -k keypair.snk  
```  
  
 <span data-ttu-id="87225-117">그런 다음 이 키 쌍에서 공개 키를 추출하여 별도의 파일에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="87225-117">Next, extract the public key from the key pair and copy it to a separate file:</span></span>  
  
```  
sn -p keypair.snk public.snk  
```  
  
 <span data-ttu-id="87225-118">키 쌍을 만든 후에는 강력한 이름 서명 도구에서 찾을 수 있는 위치에 이 파일을 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87225-118">Once you create the key pair, you must put the file where the strong name signing tools can find it.</span></span>  
  
 <span data-ttu-id="87225-119">강력한 이름으로 어셈블리를 서명하는 경우 [Al.exe(어셈블리 링커)](../../../docs/framework/tools/al-exe-assembly-linker.md)는 현재 디렉터리 및 출력 디렉터리와 관련된 키 파일을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="87225-119">When signing an assembly with a strong name, the [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) looks for the key file relative to the current directory and to the output directory.</span></span> <span data-ttu-id="87225-120">명령줄 컴파일러를 사용하는 경우에는, 코드 모듈이 포함된 현재 디렉터리에 키를 복사하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87225-120">When using command-line compilers, you can simply copy the key to the current directory containing your code modules.</span></span>  
  
 <span data-ttu-id="87225-121">프로젝트 속성에 **서명** 탭이 없는 이전 버전의 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]를 사용하는 경우 키 파일의 위치를 다음과 같이 지정된 파일 특성(FileAttribute)을 가진 프로젝트 디렉터리로 지정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="87225-121">If you are using an earlier version of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] that does not have a **Signing** tab in the project properties, the recommended key file location is the project directory with the file attribute specified as follows:</span></span>  
  
 <span data-ttu-id="87225-122">[!code-cpp[AssemblyName_KeyPair#21](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyName_KeyPair/CPP/keyfileattrib.cpp#21)] [!code-csharp[AssemblyName_KeyPair#21](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyName_KeyPair/CS/keyfileattrib.cs#21)] [!code-vb[AssemblyName_KeyPair#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyName_KeyPair/VB/keyfileattrib.vb#21)]</span><span class="sxs-lookup"><span data-stu-id="87225-122">[!code-cpp[AssemblyName_KeyPair#21](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyName_KeyPair/CPP/keyfileattrib.cpp#21)] [!code-csharp[AssemblyName_KeyPair#21](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyName_KeyPair/CS/keyfileattrib.cs#21)] [!code-vb[AssemblyName_KeyPair#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyName_KeyPair/VB/keyfileattrib.vb#21)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87225-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87225-123">See Also</span></span>  
 [<span data-ttu-id="87225-124">강력한 이름의 어셈블리 만들기 및 사용</span><span class="sxs-lookup"><span data-stu-id="87225-124">Creating and Using Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)

