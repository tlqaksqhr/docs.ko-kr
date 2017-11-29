---
title: "진입점(F#)"
description: "F # 프로그램 실행 정식으로 시작, 실행 파일로 컴파일로 진입점을 설정 하는 방법에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 91455443-ff9d-4510-a7e9-1560bdcd0bb0
ms.openlocfilehash: 685fd4da67119aa5fcaaffd142a0a17c8f5dc7f6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="entry-point"></a><span data-ttu-id="a6800-104">진입점</span><span class="sxs-lookup"><span data-stu-id="a6800-104">Entry Point</span></span>

<span data-ttu-id="a6800-105">이 항목에서는 F # 프로그램에 진입점을 설정 하려면 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6800-105">This topic describes the method that you use to set the entry point to an F# program.</span></span>


## <a name="syntax"></a><span data-ttu-id="a6800-106">구문</span><span class="sxs-lookup"><span data-stu-id="a6800-106">Syntax</span></span>

```fsharp
[<EntryPoint>]
let-function-binding
```

## <a name="remarks"></a><span data-ttu-id="a6800-107">설명</span><span class="sxs-lookup"><span data-stu-id="a6800-107">Remarks</span></span>
<span data-ttu-id="a6800-108">위 구문에서 *let 함수 바인딩에* 는 함수에 대 한 정의 `let` 바인딩.</span><span class="sxs-lookup"><span data-stu-id="a6800-108">In the previous syntax, *let-function-binding* is the definition of a function in a `let` binding.</span></span>

<span data-ttu-id="a6800-109">실행 파일로 실행 정식으로 시작은 컴파일된 프로그램 진입점입니다.</span><span class="sxs-lookup"><span data-stu-id="a6800-109">The entry point to a program that is compiled as an executable file is where execution formally starts.</span></span> <span data-ttu-id="a6800-110">적용 하 여 F # 응용 프로그램에 대 한 진입점을 지정 된 `EntryPoint` 프로그램의 특성 `main` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="a6800-110">You specify the entry point to an F# application by applying the `EntryPoint` attribute to the program's `main` function.</span></span> <span data-ttu-id="a6800-111">이 함수 (사용 하 여 만든는 `let` 바인딩) 마지막으로 컴파일된 파일에 마지막 함수 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6800-111">This function (created by using a `let` binding) must be the last function in the last compiled file.</span></span> <span data-ttu-id="a6800-112">마지막 컴파일된 파일은 프로젝트의 마지막 파일 또는 명령줄에 전달 되는 마지막 파일.</span><span class="sxs-lookup"><span data-stu-id="a6800-112">The last compiled file is the last file in the project or the last file that is passed to the command line.</span></span>

<span data-ttu-id="a6800-113">진입점 함수 형식이 `string array -> int`합니다.</span><span class="sxs-lookup"><span data-stu-id="a6800-113">The entry point function has type `string array -> int`.</span></span> <span data-ttu-id="a6800-114">명령줄에 제공 된 인수에 전달 되는 `main` 함수에 문자열의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="a6800-114">The arguments provided on the command line are passed to the `main` function in the array of strings.</span></span> <span data-ttu-id="a6800-115">배열의 첫 번째 요소는 첫 번째 인수입니다. 실행 파일의 이름 일부 다른 언어에서는 있는 그대로 배열에 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a6800-115">The first element of the array is the first argument; the name of the executable file is not included in the array, as it is in some other languages.</span></span> <span data-ttu-id="a6800-116">반환 값은 프로세스에 대 한 종료 코드로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6800-116">The return value is used as the exit code for the process.</span></span> <span data-ttu-id="a6800-117">0에는 일반적으로 성공을 나타냅니다. 0이 아닌 값에 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6800-117">Zero usually indicates success; nonzero values indicate an error.</span></span> <span data-ttu-id="a6800-118">규칙은 없습니다 반환 코드 0이 아닌;의 특정 의미에 대 한 반환 코드의 의미는 응용 프로그램 마다 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a6800-118">There is no convention for the specific meaning of nonzero return codes; the meanings of the return codes are application-specific.</span></span>

<span data-ttu-id="a6800-119">다음 예제에서는 간단한 `main` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="a6800-119">The following example illustrates a simple `main` function.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/entry-point/snippet501.fs)]

<span data-ttu-id="a6800-120">이 코드 명령줄으로 실행 되 면 `EntryPoint.exe 1 2 3`, 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a6800-120">When this code is executed with the command line `EntryPoint.exe 1 2 3`, the output is as follows.</span></span>

```console
Arguments passed to function : [|"1"; "2"; "3"|]
```

## <a name="implicit-entry-point"></a><span data-ttu-id="a6800-121">암시적 진입점</span><span class="sxs-lookup"><span data-stu-id="a6800-121">Implicit Entry Point</span></span>
<span data-ttu-id="a6800-122">프로그램에 아니요 **EntryPoint** 진입점으로 컴파일할 마지막 파일의 최상위 수준 바인딩이 명시적으로 나타내는 특성의 진입점으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6800-122">When a program has no **EntryPoint** attribute that explicitly indicates the entry point, the top level bindings in the last file to be compiled are used as the entry point.</span></span>


## <a name="see-also"></a><span data-ttu-id="a6800-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a6800-123">See Also</span></span>
[<span data-ttu-id="a6800-124">함수</span><span class="sxs-lookup"><span data-stu-id="a6800-124">Functions</span></span>](index.md)

[<span data-ttu-id="a6800-125">let 바인딩</span><span class="sxs-lookup"><span data-stu-id="a6800-125">let Bindings</span></span>](let-bindings.md)
