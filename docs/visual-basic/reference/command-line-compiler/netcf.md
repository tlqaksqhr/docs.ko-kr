---
title: -netcf
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /netcf
- -netcf
helpviewer_keywords:
- -netcf compiler option [Visual Basic]
- netcf compiler option [Visual Basic]
- /netcf compiler option [Visual Basic]
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82a0adc9e821df3a789cf19e798d4bad9e9a69e3
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="-netcf"></a><span data-ttu-id="1a1d7-102">-netcf</span><span class="sxs-lookup"><span data-stu-id="1a1d7-102">-netcf</span></span>
<span data-ttu-id="1a1d7-103">[!INCLUDE[Compact](~/includes/compact-md.md)]를 대상으로 하도록 컴파일러를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1d7-103">Sets the compiler to target the [!INCLUDE[Compact](~/includes/compact-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a1d7-104">구문</span><span class="sxs-lookup"><span data-stu-id="1a1d7-104">Syntax</span></span>  
  
```  
-netcf  
```  
  
## <a name="remarks"></a><span data-ttu-id="1a1d7-105">설명</span><span class="sxs-lookup"><span data-stu-id="1a1d7-105">Remarks</span></span>  
 <span data-ttu-id="1a1d7-106">`-netcf` 옵션을 사용 하면은 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 대상에 컴파일러는 [!INCLUDE[Compact](~/includes/compact-md.md)] 전체 대신 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1d7-106">The `-netcf` option causes the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler to target the [!INCLUDE[Compact](~/includes/compact-md.md)] rather than the full [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="1a1d7-107">전체에만 존재 하는 언어 기능이 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1a1d7-107">Language functionality that is present only in the full [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] is disabled.</span></span>  
  
 <span data-ttu-id="1a1d7-108">`-netcf` 옵션은 함께 사용할 [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1d7-108">The `-netcf` option is designed to be used with [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span></span> <span data-ttu-id="1a1d7-109">사용 하지 않도록 설정 하는 언어 기능은 `-netcf` 대상 파일에 없는 동일한 언어 기능과 `-sdkpath`합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1d7-109">The language features disabled by `-netcf` are the same language features not present in the files targeted with `-sdkpath`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1a1d7-110">`-netcf` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 명령줄에서 컴파일할 경우에 사용할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a1d7-110">The `-netcf` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="1a1d7-111">`-netcf` 옵션을 설정 하는 경우는 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 장치 프로젝트를 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1d7-111">The `-netcf` option is set when a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] device project is loaded.</span></span>  
  
 <span data-ttu-id="1a1d7-112">`-netcf` 다음과 같은 언어 기능을 변경 하는 옵션:</span><span class="sxs-lookup"><span data-stu-id="1a1d7-112">The `-netcf` option changes the following language features:</span></span>  
  
-   <span data-ttu-id="1a1d7-113">[끝 \<키워드 > 문을](../../../visual-basic/language-reference/statements/end-keyword-statement.md) 는 프로그램 실행을 종료 하는 키워드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1a1d7-113">The [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) keyword, which terminates execution of a program, is disabled.</span></span> <span data-ttu-id="1a1d7-114">다음 프로그램 없이 컴파일되고 실행 `-netcf` 컴파일 시 하지만 `-netcf`합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1d7-114">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>  
  
     [!code-vb[VbVbalrCompiler#34](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_1.vb)]  
  
-   <span data-ttu-id="1a1d7-115">모든 양식에서 런타임에 바인딩을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1a1d7-115">Late binding, in all forms, is disabled.</span></span> <span data-ttu-id="1a1d7-116">런타임에 바인딩 시나리오를 인식 된 발생 한 경우 컴파일 타임 오류가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a1d7-116">Compile-time errors are generated when recognized late-binding scenarios are encountered.</span></span> <span data-ttu-id="1a1d7-117">다음 프로그램 없이 컴파일되고 실행 `-netcf` 컴파일 시 하지만 `-netcf`합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1d7-117">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>  
  
     [!code-vb[VbVbalrCompiler#35](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_2.vb)]  
  
-   <span data-ttu-id="1a1d7-118">[자동](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), 및 [유니코드](../../../visual-basic/language-reference/modifiers/unicode.md) 한정자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1a1d7-118">The [Auto](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), and [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) modifiers are disabled.</span></span> <span data-ttu-id="1a1d7-119">구문은 [선언 문의](../../../visual-basic/language-reference/statements/declare-statement.md) 문을로 수정 됩니다 `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1d7-119">The syntax of the [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) statement is also modified to `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span></span> <span data-ttu-id="1a1d7-120">다음 코드의 결과 보여 줍니다. `-netcf` 는 컴파일에 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1d7-120">The following code shows the effect of `-netcf` on a compilation.</span></span>  
  
     [!code-vb[VbVbalrCompiler#36](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_3.vb)]  
  
-   <span data-ttu-id="1a1d7-121">제거 된 Visual Basic 6.0 키워드를 사용 하 여 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 다른 오류를 생성 때 `-netcf` 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a1d7-121">Using Visual Basic 6.0 keywords that were removed from [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] generates a different error when `-netcf` is used.</span></span> <span data-ttu-id="1a1d7-122">이 다음 키워드에 대 한 오류 메시지를 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1a1d7-122">This affects the error messages for the following keywords:</span></span>  
  
    -   `Open`  
  
    -   `Close`  
  
    -   `Put`  
  
    -   `Print`  
  
    -   `Write`  
  
    -   `Input`  
  
    -   `Lock`  
  
    -   `Unlock`  
  
    -   `Seek`  
  
    -   `Width`  
  
    -   `Name`  
  
    -   `FreeFile`  
  
    -   `EOF`  
  
    -   `Loc`  
  
    -   `LOF`  
  
    -   `Line`  
  
## <a name="example"></a><span data-ttu-id="1a1d7-123">예제</span><span class="sxs-lookup"><span data-stu-id="1a1d7-123">Example</span></span>  
 <span data-ttu-id="1a1d7-124">다음 코드에서는 `Myfile.vb` 와 [!INCLUDE[Compact](~/includes/compact-md.md)]의 기본 설치 디렉터리에 있는 mscorlib.dll 및 Microsoft.VisualBasic.dll의 버전을 사용 하는 [!INCLUDE[Compact](~/includes/compact-md.md)] C 드라이브에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a1d7-124">The following code compiles `Myfile.vb` with the [!INCLUDE[Compact](~/includes/compact-md.md)], using the versions of mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the [!INCLUDE[Compact](~/includes/compact-md.md)] on the C drive.</span></span> <span data-ttu-id="1a1d7-125">일반적으로 가장 최신 버전의 사용은 [!INCLUDE[Compact](~/includes/compact-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="1a1d7-125">Typically, you would use the most recent version of the [!INCLUDE[Compact](~/includes/compact-md.md)].</span></span>  
  
```console  
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="1a1d7-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1a1d7-126">See Also</span></span>  
 [<span data-ttu-id="1a1d7-127">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="1a1d7-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="1a1d7-128">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="1a1d7-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="1a1d7-129">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="1a1d7-129">-sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
