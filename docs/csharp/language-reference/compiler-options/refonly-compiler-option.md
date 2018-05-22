---
title: -refonly(C# 컴파일러 옵션)
ms.date: 07/08/2017
f1_keywords:
- /refonly
helpviewer_keywords:
- /refonly compiler option [C#]
- -refonly compiler option [C#]
- refonly compiler option [C#]
ms.openlocfilehash: c380df1cb473fcd187e56bb0a338a909dd3ac894
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="-refonly-c-compiler-options"></a><span data-ttu-id="860d5-102">-refonly(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="860d5-102">-refonly (C# Compiler Options)</span></span>

<span data-ttu-id="860d5-103">**-refonly** 옵션은 구현 어셈블리 대신 참조 어셈블리가 기본 출력으로 출력되어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="860d5-103">The **-refonly** option indicates that a reference assembly should be output instead of an implementation assembly, as the primary output.</span></span> <span data-ttu-id="860d5-104">`-refonly` 매개 변수는 참조 어셈블리가 실행될 수 없을 때 PDB 출력을 자동으로 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="860d5-104">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span>

## <a name="syntax"></a><span data-ttu-id="860d5-105">구문</span><span class="sxs-lookup"><span data-stu-id="860d5-105">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="860d5-106">설명</span><span class="sxs-lookup"><span data-stu-id="860d5-106">Remarks</span></span>

<span data-ttu-id="860d5-107">메타데이터 전용 어셈블리에는 단일 `throw null` 본문으로 대체되는 메서드 본문이 있지만 익명 형식을 제외한 모든 멤버가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="860d5-107">Metadata-only assemblies have their method bodies replaced with a single `throw null` body, but include all members except anonymous types.</span></span> <span data-ttu-id="860d5-108">본문이 없는 경우와 대조적으로 `throw null` 본문을 사용하는 이유는 PEVerify가 실행 및 전달될 수 있도록 하여 메타데이터의 완전성을 검증하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="860d5-108">The reason for using `throw null` bodies (as opposed to no bodies) is so that PEVerify could run and pass (thus validating the completeness of the metadata).</span></span>

<span data-ttu-id="860d5-109">참조 어셈블리에는 어셈블리 수준 `ReferenceAssembly` 특성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="860d5-109">Reference assemblies include an assembly-level `ReferenceAssembly` attribute.</span></span> <span data-ttu-id="860d5-110">이 특성을 소스에서 지정할 수 있습니다. 이렇게 하면 컴파일러가 특성을 합성할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="860d5-110">This attribute may be specified in source (then the compiler won't need to synthesize it).</span></span> <span data-ttu-id="860d5-111">이 특성으로 인해 런타임은 실행용 참조 어셈블리 로드를 거부합니다. 그러나 리플렉션 전용 모드에서 계속 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="860d5-111">Because of this attribute, runtimes will refuse to load reference assemblies for execution (but they can still be loaded in reflection-only mode).</span></span> <span data-ttu-id="860d5-112">어셈블리에 반영되는 도구는 참조 어셈블리를 리플렉션 전용으로 로드하는지, 아니면 런타임에서 typeload 오류가 발생하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="860d5-112">Tools that reflect on assemblies need to ensure they load reference assemblies as reflection-only, otherwise they will receive a typeload error from the runtime.</span></span>

<span data-ttu-id="860d5-113">참조 어셈블리는 메타데이터 전용 어셈블리에서 메타데이터(전용 멤버)를 추가로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="860d5-113">Reference assemblies further remove metadata (private members) from metadata-only assemblies:</span></span>

- <span data-ttu-id="860d5-114">참조 어셈블리에는 API 화면에 있어야 하는 항목에 대한 참조만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="860d5-114">A reference assembly only has references for what it needs in the API surface.</span></span> <span data-ttu-id="860d5-115">실제 어셈블리에는 특정 구현에 관련된 추가 참조가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="860d5-115">The real assembly may have additional references related to specific implementations.</span></span> <span data-ttu-id="860d5-116">예를 들어 `class C { private void M() { dynamic d = 1; ... } }`에 대한 참조 어셈블리는 `dynamic`에 필요한 형식을 참조하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="860d5-116">For instance, the reference assembly for `class C { private void M() { dynamic d = 1; ... } }` does not reference any types required for `dynamic`.</span></span>
- <span data-ttu-id="860d5-117">제거가 컴파일에 눈에 띄는 영향을 미치지 않을 경우 전용 함수-멤버(메서드, 속성 및 이벤트)가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="860d5-117">Private function-members (methods, properties, and events) are removed in cases where their removal doesn't observably impact compilation.</span></span> <span data-ttu-id="860d5-118">`InternalsVisibleTo` 특성이 없는 경우 내부 함수-멤버에 대해 동일한 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="860d5-118">If there are no `InternalsVisibleTo` attributes, do the same for internal function-members.</span></span>
- <span data-ttu-id="860d5-119">그러나 모든 형식(전용 또는 중첩 형식 포함)은 참조 어셈블리에서 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="860d5-119">But all types (including private or nested types) are kept in reference assemblies.</span></span> <span data-ttu-id="860d5-120">모든 특성이 유지됩니다(내부 특성인 경우에도).</span><span class="sxs-lookup"><span data-stu-id="860d5-120">All attributes are kept (even internal ones).</span></span>
- <span data-ttu-id="860d5-121">모든 가상 메서드가 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="860d5-121">All virtual methods are kept.</span></span> <span data-ttu-id="860d5-122">명시적 인터페이스 구현이 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="860d5-122">Explicit interface implementations are kept.</span></span> <span data-ttu-id="860d5-123">명시적으로 구현된 속성 및 이벤트가 유지됩니다. 해당 접근자가 가상이므로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="860d5-123">Explicitly implemented properties and events are kept, as their accessors are virtual (and are therefore kept).</span></span>
- <span data-ttu-id="860d5-124">구조체의 모든 필드가 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="860d5-124">All fields of a struct are kept.</span></span> <span data-ttu-id="860d5-125">이것은 post-C#-7.1 개선의 후보입니다.</span><span class="sxs-lookup"><span data-stu-id="860d5-125">(This is a candidate for post-C#-7.1 refinement)</span></span>

<span data-ttu-id="860d5-126">`-refonly` 및 [`-refout`](refout-compiler-option.md) 옵션은 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="860d5-126">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="860d5-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="860d5-127">See also</span></span>
 [<span data-ttu-id="860d5-128">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="860d5-128">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="860d5-129">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="860d5-129">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
