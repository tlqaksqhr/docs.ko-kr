---
title: "외부 함수(F#)"
description: "네이티브 코드의 함수를 호출 하는 것에 대 한 F # 언어 지원에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c26b6124-ceaa-471c-9dc9-861b4dfa332a
ms.openlocfilehash: 69b73983a91bc6c7cc38fa34484a3c89fc01858f
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2017
---
# <a name="external-functions"></a><span data-ttu-id="7f51c-104">외부 함수</span><span class="sxs-lookup"><span data-stu-id="7f51c-104">External Functions</span></span>

<span data-ttu-id="7f51c-105">이 항목에서는 F # 언어 지원과 네이티브 코드의 함수를 호출 하는 것에 대 한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="7f51c-105">This topic describes F# language support for calling functions in native code.</span></span>

## <a name="syntax"></a><span data-ttu-id="7f51c-106">구문</span><span class="sxs-lookup"><span data-stu-id="7f51c-106">Syntax</span></span>

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a><span data-ttu-id="7f51c-107">설명</span><span class="sxs-lookup"><span data-stu-id="7f51c-107">Remarks</span></span>

<span data-ttu-id="7f51c-108">위 구문에서 *인수* 에 제공 되는 인수를 나타내는 `System.Runtime.InteropServices.DllImportAttribute` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="7f51c-108">In the previous syntax, *arguments* represents arguments that are supplied to the `System.Runtime.InteropServices.DllImportAttribute` attribute.</span></span> <span data-ttu-id="7f51c-109">첫 번째 인수는.dll 확장명을 제외한이 함수를 포함 하는 DLL의 이름을 나타내는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7f51c-109">The first argument is a string that represents the name of the DLL that contains this function, without the .dll extension.</span></span> <span data-ttu-id="7f51c-110">공용 속성에 대 한 추가 인수를 제공할 수 있습니다는 `System.Runtime.InteropServices.DllImportAttribute` 호출 규칙 같은 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="7f51c-110">Additional arguments can be supplied for any of the public properties of the `System.Runtime.InteropServices.DllImportAttribute` class, such as the calling convention.</span></span>

<span data-ttu-id="7f51c-111">다음과 같은 내보낸된 함수를 포함 하는 c + + DLL 네이티브 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f51c-111">Assume you have a native C++ DLL that contains the following exported function.</span></span>

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

<span data-ttu-id="7f51c-112">다음 코드를 사용 하 여 F #에서이 함수를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f51c-112">You can call this function from F# by using the following code.</span></span>

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

<span data-ttu-id="7f51c-113">네이티브 코드와의 상호 운용성 라고 *플랫폼 호출* 및 CLR의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="7f51c-113">Interoperability with native code is referred to as *platform invoke* and is a feature of the CLR.</span></span> <span data-ttu-id="7f51c-114">자세한 내용은 [비관리 코드 상호 운용](../../../../docs/framework/interop/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7f51c-114">For more information, see [Interoperating with Unmanaged Code](../../../../docs/framework/interop/index.md).</span></span> <span data-ttu-id="7f51c-115">해당 섹션의 정보는 F #에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f51c-115">The information in that section is applicable to F#.</span></span>


## <a name="see-also"></a><span data-ttu-id="7f51c-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7f51c-116">See Also</span></span>

[<span data-ttu-id="7f51c-117">함수</span><span class="sxs-lookup"><span data-stu-id="7f51c-117">Functions</span></span>](index.md)
