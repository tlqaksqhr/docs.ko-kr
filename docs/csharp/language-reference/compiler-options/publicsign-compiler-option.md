---
title: -publicsign(C# 컴파일러 옵션)
ms.date: 05/15/2018
f1_keywords:
- /publicsign
helpviewer_keywords:
- -publicsign compiler option [C#]
- publicsign compiler option [C#]
- /publicsign compiler option [C#]
ms.openlocfilehash: ec25f9c1f2ef943db41bcfa20c8efd1d05866acd
ms.sourcegitcommit: 77d9a94dac4c05827ed0663d95e0f9ad35d6682e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2018
ms.locfileid: "34472826"
---
# <a name="-publicsign-c-compiler-options"></a><span data-ttu-id="9b49f-102">-publicsign(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="9b49f-102">-publicsign (C# Compiler Options)</span></span>

<span data-ttu-id="9b49f-103">이 옵션을 사용하면 컴파일러는 공개 키를 적용하지만 실제로 어셈블리에 서명하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b49f-103">This option causes the compiler to apply a public key but does not actually sign the assembly.</span></span> <span data-ttu-id="9b49f-104">또한 **-publicsign** 옵션은 파일이 실제로 서명되었음을 런타임에 알리는 비트를 어셈블리에 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9b49f-104">The **-publicsign** option also sets a bit in the assembly that tells the runtime that the file is actually signed.</span></span>

## <a name="syntax"></a><span data-ttu-id="9b49f-105">구문</span><span class="sxs-lookup"><span data-stu-id="9b49f-105">Syntax</span></span>

```console
-publicsign
```

## <a name="arguments"></a><span data-ttu-id="9b49f-106">인수</span><span class="sxs-lookup"><span data-stu-id="9b49f-106">Arguments</span></span>

<span data-ttu-id="9b49f-107">없음</span><span class="sxs-lookup"><span data-stu-id="9b49f-107">None.</span></span>

## <a name="remarks"></a><span data-ttu-id="9b49f-108">설명</span><span class="sxs-lookup"><span data-stu-id="9b49f-108">Remarks</span></span>

<span data-ttu-id="9b49f-109">**-publicsign** 옵션에는 [-keyfile](keyfile-compiler-option.md) 또는 [-keycontainer](keycontainer-compiler-option.md)를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b49f-109">The **-publicsign** option requires the use of the [-keyfile](keyfile-compiler-option.md) or [-keycontainer](keycontainer-compiler-option.md).</span></span> <span data-ttu-id="9b49f-110">**keyfile** 또는 **keycontainer** 옵션은 공개 키를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9b49f-110">The **keyfile** or **keycontainer** options specify the public key.</span></span>

<span data-ttu-id="9b49f-111">**-publicsign** 및 **-delaysign** 옵션은 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9b49f-111">The **-publicsign** and **-delaysign** options are mutually exclusive.</span></span>

<span data-ttu-id="9b49f-112">“모조 서명” 또는 “OSS 서명”이라고도 하는 공개 서명은 출력 어셈블리에 공개 키를 포함하고 “서명된” 플래그를 설정하지만 개인 키를 사용하여 어셈블리에 실제로 서명하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b49f-112">Sometimes called "fake sign" or "OSS sign", public signing includes the public key in an output assembly and sets the "signed" flag, but doesn't actually sign the assembly with a private key.</span></span> <span data-ttu-id="9b49f-113">이 서명은 릴리스된 “완전히 서명된” 어셈블리와 호환되지만 어셈블리 서명에 사용된 개인 키에는 액세스할 수 없는 어셈블리를 빌드하려는 오픈 소스 프로젝트에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="9b49f-113">This is useful for open source projects where people want to build assemblies which are compatible with the released "fully signed" assemblies, but don't have access to the private key used to sign the assemblies.</span></span> <span data-ttu-id="9b49f-114">어셈블리가 완전히 서명되었는지 실제로 확인해야 하는 소비자는 거의 없으므로 완전히 서명된 어셈블리가 사용되는 거의 모든 시나리오에서 이러한 공개적으로 빌드된 어셈블리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b49f-114">Since almost no consumers actually need to check if the assembly is fully signed, these publicly built assemblies are useable in almost every scenario where the fully signed one would be used.</span></span>

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="9b49f-115">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="9b49f-115">To set this compiler option in the Visual Studio development environment</span></span>

1. <span data-ttu-id="9b49f-116">프로젝트의 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9b49f-116">Open the **Properties** page for the project.</span></span>
1. <span data-ttu-id="9b49f-117">**서명만 연기** 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="9b49f-117">Modify the **Delay sign only** property.</span></span>

## <a name="see-also"></a><span data-ttu-id="9b49f-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9b49f-118">See Also</span></span>
 [<span data-ttu-id="9b49f-119">C# 컴파일러 -delaysign 옵션</span><span class="sxs-lookup"><span data-stu-id="9b49f-119">C# Compiler -delaysign option</span></span>](delaysign-compiler-option.md)  
 [<span data-ttu-id="9b49f-120">C# 컴파일러 -keyfile 옵션</span><span class="sxs-lookup"><span data-stu-id="9b49f-120">C# Compiler -keyfile option</span></span>](keyfile-compiler-option.md)  
 [<span data-ttu-id="9b49f-121">C# 컴파일러 -keycontainer 옵션</span><span class="sxs-lookup"><span data-stu-id="9b49f-121">C# Compiler -keycontainer option</span></span>](keycontainer-compiler-option.md)  
 [<span data-ttu-id="9b49f-122">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="9b49f-122">C# Compiler Options</span></span>](index.md)  
 [<span data-ttu-id="9b49f-123">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="9b49f-123">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
