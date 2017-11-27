---
title: /utf8output(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 23c7c308865a6b6afb07443a42090fff3d9e2efb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="utf8output-visual-basic"></a><span data-ttu-id="d7005-102">/utf8output(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d7005-102">/utf8output (Visual Basic)</span></span>
<span data-ttu-id="d7005-103">UTF-8 인코딩을 사용하여 컴파일러 출력을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d7005-103">Displays compiler output using UTF-8 encoding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7005-104">구문</span><span class="sxs-lookup"><span data-stu-id="d7005-104">Syntax</span></span>  
  
```  
/utf8output[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="d7005-105">인수</span><span class="sxs-lookup"><span data-stu-id="d7005-105">Arguments</span></span>  
 <span data-ttu-id="d7005-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="d7005-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="d7005-107">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d7005-107">Optional.</span></span> <span data-ttu-id="d7005-108">이 옵션의 기본값은 `/utf8output-`, 즉, 컴파일러 출력에 utf-8 인코딩을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7005-108">The default for this option is `/utf8output-`, which means compiler output does not use UTF-8 encoding.</span></span> <span data-ttu-id="d7005-109">지정 `/utf8output` 지정 하는 것과 같습니다 `/utf8output+`합니다.</span><span class="sxs-lookup"><span data-stu-id="d7005-109">Specifying `/utf8output` is the same as specifying `/utf8output+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7005-110">설명</span><span class="sxs-lookup"><span data-stu-id="d7005-110">Remarks</span></span>  
 <span data-ttu-id="d7005-111">일부 국제 구성에서 컴파일러 출력을 콘솔에 올바르게 표시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7005-111">In some international configurations, compiler output cannot be displayed correctly in the console.</span></span> <span data-ttu-id="d7005-112">이러한 상황에서 사용 하 여 `/utf8output` 컴파일러 출력을 파일로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="d7005-112">In such situations, use `/utf8output` and redirect compiler output to a file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7005-113">`/utf8output` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 명령줄에서 컴파일할 경우에 사용할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7005-113">The `/utf8output` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7005-114">예제</span><span class="sxs-lookup"><span data-stu-id="d7005-114">Example</span></span>  
 <span data-ttu-id="d7005-115">다음 코드에서는 `In.vb` 표시 하도록 컴파일러에 지시 하 고 utf-8 인코딩을 사용 하 여 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7005-115">The following code compiles `In.vb` and directs the compiler to display output using UTF-8 encoding.</span></span>  
  
```  
vbc /utf8output in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7005-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d7005-116">See Also</span></span>  
 [<span data-ttu-id="d7005-117">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="d7005-117">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="d7005-118">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="d7005-118">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
