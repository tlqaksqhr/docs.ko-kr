---
title: 소스 줄, 파일 및 경로 식별자(F#)
description: '기본 제공 F # 식별자 값을 사용 하면 소스 줄 번호, 디렉터리 및 파일 이름을 코드에서 액세스할 수를 사용 하는 방법에 알아봅니다.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 18a26f0aa0a0c1f9c0b448ec46eaebd540391324
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="source-line-file-and-path-identifiers"></a><span data-ttu-id="04e1e-103">소스 줄, 파일 및 경로 식별자</span><span class="sxs-lookup"><span data-stu-id="04e1e-103">Source Line, File, and Path Identifiers</span></span>

<span data-ttu-id="04e1e-104">식별자 `__LINE__`, `__SOURCE_DIRECTORY__` 및 `__SOURCE_FILE__` 코드의 소스 줄 번호, 디렉터리 및 파일 이름에 액세스할 수 있도록 하는 기본 제공 값입니다.</span><span class="sxs-lookup"><span data-stu-id="04e1e-104">The identifiers `__LINE__`, `__SOURCE_DIRECTORY__` and `__SOURCE_FILE__` are built-in values that enable you to access the source line number, directory and file name in your code.</span></span>


## <a name="syntax"></a><span data-ttu-id="04e1e-105">구문</span><span class="sxs-lookup"><span data-stu-id="04e1e-105">Syntax</span></span>

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a><span data-ttu-id="04e1e-106">설명</span><span class="sxs-lookup"><span data-stu-id="04e1e-106">Remarks</span></span>
<span data-ttu-id="04e1e-107">이러한 각 값의 형식이 `string`합니다.</span><span class="sxs-lookup"><span data-stu-id="04e1e-107">Each of these values has type `string`.</span></span>

<span data-ttu-id="04e1e-108">다음 표에서 소스 줄, 파일 및 경로 식별자 F #에서 사용할 수 있는 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04e1e-108">The following table summarizes the source line, file, and path identifiers that are available in F#.</span></span> <span data-ttu-id="04e1e-109">이러한 식별자는 전처리기 매크로; 하지 컴파일러에서 인식 되는 기본 제공 값 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="04e1e-109">These identifiers are not preprocessor macros; they are built-in values that are recognized by the compiler.</span></span>

|<span data-ttu-id="04e1e-110">미리 정의 된 식별자</span><span class="sxs-lookup"><span data-stu-id="04e1e-110">Predefined identifier</span></span>|<span data-ttu-id="04e1e-111">설명</span><span class="sxs-lookup"><span data-stu-id="04e1e-111">Description</span></span>|
|---------------------|-----------|
|`__LINE__`|<span data-ttu-id="04e1e-112">현재 줄 번호를 고려 `#line` 지시문입니다.</span><span class="sxs-lookup"><span data-stu-id="04e1e-112">Evaluates to the current line number, considering `#line` directives.</span></span>|
|`__SOURCE_DIRECTORY__`|<span data-ttu-id="04e1e-113">현재 원본 디렉터리의 전체 경로를 계산 고려 `#line` 지시문입니다.</span><span class="sxs-lookup"><span data-stu-id="04e1e-113">Evaluates to the current full path of the source directory, considering `#line` directives.</span></span>|
|`__SOURCE_FILE__`|<span data-ttu-id="04e1e-114">현재 소스 파일 이름과 경로 계산 고려 `#line` 지시문입니다.</span><span class="sxs-lookup"><span data-stu-id="04e1e-114">Evaluates to the current source file name and its path, considering `#line` directives.</span></span>|
<span data-ttu-id="04e1e-115">에 대 한 자세한 내용은 `#line` 지시문 참조 [컴파일러 지시문](compiler-directives.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="04e1e-115">For more information about the `#line` directive, see [Compiler Directives](compiler-directives.md).</span></span>

## <a name="example"></a><span data-ttu-id="04e1e-116">예제</span><span class="sxs-lookup"><span data-stu-id="04e1e-116">Example</span></span>

<span data-ttu-id="04e1e-117">다음 코드 예제에서는 이러한 값을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="04e1e-117">The following code example demonstrates the use of these values.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

<span data-ttu-id="04e1e-118">출력:</span><span class="sxs-lookup"><span data-stu-id="04e1e-118">Output:</span></span>

```
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo\Program.fs
```

## <a name="see-also"></a><span data-ttu-id="04e1e-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04e1e-119">See Also</span></span>
[<span data-ttu-id="04e1e-120">컴파일러 지시문</span><span class="sxs-lookup"><span data-stu-id="04e1e-120">Compiler Directives</span></span>](compiler-directives.md)

[<span data-ttu-id="04e1e-121">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="04e1e-121">F# Language Reference</span></span>](index.md)
