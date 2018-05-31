---
title: -keycontainer(C# 컴파일러 옵션)
ms.date: 05/16/2018
f1_keywords:
- /keycontainer
helpviewer_keywords:
- /keycontainer compiler option [C#]
- keycontainer compiler option [C#]
- -keycontainer compiler option [C#]
ms.assetid: b3982b6d-2382-4f7e-bebd-ce98eaa30763
ms.openlocfilehash: 5a7b378cad7a1df9249fcbefa28bb9aa9a6a3da4
ms.sourcegitcommit: 77d9a94dac4c05827ed0663d95e0f9ad35d6682e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2018
ms.locfileid: "34472570"
---
# <a name="-keycontainer-c-compiler-options"></a><span data-ttu-id="7929a-102">-keycontainer(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="7929a-102">-keycontainer (C# Compiler Options)</span></span>
<span data-ttu-id="7929a-103">암호화 키 컨테이너의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7929a-103">Specifies the name of the cryptographic key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7929a-104">구문</span><span class="sxs-lookup"><span data-stu-id="7929a-104">Syntax</span></span>  
  
```console  
-keycontainer:string  
```  
  
## <a name="arguments"></a><span data-ttu-id="7929a-105">인수</span><span class="sxs-lookup"><span data-stu-id="7929a-105">Arguments</span></span>  
 `string`  
 <span data-ttu-id="7929a-106">강력한 이름 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7929a-106">The name of the strong name key container.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7929a-107">설명</span><span class="sxs-lookup"><span data-stu-id="7929a-107">Remarks</span></span>  
 <span data-ttu-id="7929a-108">**-keycontainer** 옵션을 사용하면 컴파일러는 공유 가능한 구성 요소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7929a-108">When the **-keycontainer** option is used, the compiler creates a sharable component.</span></span> <span data-ttu-id="7929a-109">컴파일러는 지정된 컨테이너의 공개 키를 어셈블리 매니페스트에 삽입하고 개인 키를 사용하여 최종 어셈블리에 서명합니다.</span><span class="sxs-lookup"><span data-stu-id="7929a-109">The compiler inserts a public key from the specified container into the assembly manifest and signs the final assembly with the private key.</span></span> <span data-ttu-id="7929a-110">키 파일을 생성하려면 명령줄에 `sn -k file`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7929a-110">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="7929a-111">`sn -i`는 컨테이너에 키 쌍을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="7929a-111">`sn -i` installs the key pair into a container.</span></span> <span data-ttu-id="7929a-112">CoreCLR에서 컴파일러를 실행하면 이 옵션이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7929a-112">This option is not supported when the compiler runs on CoreCLR.</span></span> <span data-ttu-id="7929a-113">CoreCLR에서 빌드할 때 어셈블리에 서명하려면 [-keyfile](keyfile-compiler-option.md) 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7929a-113">To sign an assembly when building on CoreCLR, use the [-keyfile](keyfile-compiler-option.md) option.</span></span>
  
 <span data-ttu-id="7929a-114">[-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md)로 컴파일하는 경우 키 파일의 이름이 모듈에 저장되고, [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md)을 사용하여 이 모듈을 어셈블리로 컴파일할 때 어셈블리에 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="7929a-114">If you compile with [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), the name of the key file is held in the module and incorporated into the assembly when you compile this module into an assembly with [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="7929a-115">MSIL(Microsoft Intermediate Language) 모듈의 소스 코드에서 이 옵션을 사용자 지정 특성(<xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=nameWithType>)으로 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7929a-115">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=nameWithType>) in the source code for any Microsoft intermediate language (MSIL) module.</span></span>  
  
 <span data-ttu-id="7929a-116">[-keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md)을 사용하여 암호화 정보를 컴파일러에 전달할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7929a-116">You can also pass your encryption information to the compiler with [-keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md).</span></span> <span data-ttu-id="7929a-117">공개 키를 어셈블리 매니페스트에 추가하고자 하지만 테스트가 완료될 때까지 어셈블리 서명을 지연하려면 [-delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7929a-117">Use [-delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md) if you want the public key added to the assembly manifest but want to delay signing the assembly until it has been tested.</span></span>  
  
 <span data-ttu-id="7929a-118">자세한 내용은 [강력한 이름의 어셈블리 만들기 및 사용](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) 및 [어셈블리 서명 지연](../../../framework/app-domains/delay-sign-assembly.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7929a-118">For more information, see [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) and [Delay Signing an Assembly](../../../framework/app-domains/delay-sign-assembly.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="7929a-119">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="7929a-119">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="7929a-120">이 컴파일러 옵션은 Visual Studio 개발 환경에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7929a-120">This compiler option is not available in the Visual Studio development environment.</span></span>  
  
 <span data-ttu-id="7929a-121">프로그래밍 방식으로 <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A>을 사용하여 이 컴파일러 옵션에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7929a-121">You can programmatically access this compiler option with <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7929a-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7929a-122">See Also</span></span>  
 <span data-ttu-id="7929a-123">[C# 컴파일러 -keyfile 옵션](keyfile-compiler-option.md) [C# 컴파일러 옵션](index.md)</span><span class="sxs-lookup"><span data-stu-id="7929a-123">[C# Compiler -keyfile option](keyfile-compiler-option.md) [C# Compiler Options](index.md)</span></span>  
 [<span data-ttu-id="7929a-124">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="7929a-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
