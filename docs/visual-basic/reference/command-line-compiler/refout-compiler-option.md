---
title: -refout (Visual Basic)
ms.date: 03/16/2018
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d6075b92efd1eec9797fca248e97a325bd5df4bb
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2018
---
# <a name="-refout-visual-basic"></a><span data-ttu-id="21b7b-102">-refout (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="21b7b-102">-refout (Visual Basic)</span></span>

<span data-ttu-id="21b7b-103">**-refout** 옵션은 참조 어셈블리가 출력되어야 하는 파일 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="21b7b-103">The **-refout** option specifies a file path where the reference assembly should be output.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="21b7b-104">구문</span><span class="sxs-lookup"><span data-stu-id="21b7b-104">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="21b7b-105">인수</span><span class="sxs-lookup"><span data-stu-id="21b7b-105">Arguments</span></span>

 <span data-ttu-id="21b7b-106">`filepath` 경로 참조 어셈블리의 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="21b7b-106">`filepath` The path and filename of the reference assembly.</span></span> <span data-ttu-id="21b7b-107">일반적으로 주 어셈블리의 하위 폴더에는 것이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21b7b-107">It should generally be in a sub-folder of the primary assembly.</span></span> <span data-ttu-id="21b7b-108">권장되는 규칙(MSBuild에서 사용됨)은 주 어셈블리에 상대적으로 “ref/” sub-폴더에 참조 어셈블리를 배치하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="21b7b-108">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span> <span data-ttu-id="21b7b-109">모든 폴더 `filepath` 있어야; 컴파일러에서 만들 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="21b7b-109">All folders in `filepath` must exist; the compiler does not create them.</span></span> 

## <a name="remarks"></a><span data-ttu-id="21b7b-110">설명</span><span class="sxs-lookup"><span data-stu-id="21b7b-110">Remarks</span></span>

<span data-ttu-id="21b7b-111">Visual Basic에서는 `-refout` 버전부터 15.3 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="21b7b-111">Visual Basic supports the `-refout` switch starting with version 15.3.</span></span>

<span data-ttu-id="21b7b-112">참조 어셈블리는 메타 데이터는 있지만 구현 코드가 없는 포함 하는 메타 데이터 전용 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="21b7b-112">Reference assemblies are metadata-only assemblies that contain metadata but no implementation code.</span></span> <span data-ttu-id="21b7b-113">익명 형식을 제외한 모든 항목에 대 한 형식 및 멤버 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21b7b-113">They include type and member information for everything except anonymous types.</span></span> <span data-ttu-id="21b7b-114">단일 메서드 본문 바뀝니다 `throw null` 문.</span><span class="sxs-lookup"><span data-stu-id="21b7b-114">Their method bodies are replaced with a single `throw null` statement.</span></span> <span data-ttu-id="21b7b-115">사용 하기 위한 이유 `throw null` (본문이 없습니다) 대비 메서드 본문은 PEVerify 실행 하 고 (따라서 메타 데이터의 완전성 유효성 검사)를 전달할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="21b7b-115">The reason for using `throw null` method bodies (as opposed to no bodies) is so that PEVerify can run and pass (thus validating the completeness of the metadata).</span></span>

<span data-ttu-id="21b7b-116">참조 어셈블리는 어셈블리 수준 포함 [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="21b7b-116">Reference assemblies include an assembly-level [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) attribute.</span></span> <span data-ttu-id="21b7b-117">이 특성을 소스에서 지정할 수 있습니다. 이렇게 하면 컴파일러가 특성을 합성할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="21b7b-117">This attribute may be specified in source (then the compiler won't need to synthesize it).</span></span> <span data-ttu-id="21b7b-118">이 특성으로 인해 런타임 실행에 대 한 참조 어셈블리를 로드 하지 않습니다 (그러나 여전히 있을 수 있습니다는 리플렉션 전용 컨텍스트에 로드).</span><span class="sxs-lookup"><span data-stu-id="21b7b-118">Because of this attribute, runtimes refuse to load reference assemblies for execution (but they can still be loaded in a reflection-only context).</span></span> <span data-ttu-id="21b7b-119">어셈블리를 반영 하는 도구를 참조 어셈블리를 리플렉션 전용으로 로드를 확인 해야 합니다. 그렇지 않으면 런타임에서 throw 된 <xref:System.BadImageFormatException>합니다.</span><span class="sxs-lookup"><span data-stu-id="21b7b-119">Tools that reflect on assemblies need to ensure they load reference assemblies as reflection-only; otherwise, the runtime throws a <xref:System.BadImageFormatException>.</span></span>

<span data-ttu-id="21b7b-120">`-refout` 및 [`-refonly`](refonly-compiler-option.md) 옵션은 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="21b7b-120">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="21b7b-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="21b7b-121">See Also</span></span>
<span data-ttu-id="21b7b-122">[-refonly](refonly-compiler-option.md) </span><span class="sxs-lookup"><span data-stu-id="21b7b-122">[-refonly](refonly-compiler-option.md) </span></span>  
[<span data-ttu-id="21b7b-123">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="21b7b-123">Visual Basic Command-Line Compiler</span></span>](index.md)  
[<span data-ttu-id="21b7b-124">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="21b7b-124">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)  

