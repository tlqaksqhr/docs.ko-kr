---
title: /quiet
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- /quiet
- quiet
helpviewer_keywords:
- -quiet compiler option [Visual Basic]
- /quiet compiler option [Visual Basic]
- quiet compiler option [Visual Basic]
ms.assetid: 5d77fa23-4c50-4708-8535-649912b098e8
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3b816cadb9d805d57a14e9b5df553654dd8167af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="quiet"></a><span data-ttu-id="17064-102">/quiet</span><span class="sxs-lookup"><span data-stu-id="17064-102">/quiet</span></span>
<span data-ttu-id="17064-103">컴파일러에서 구문 관련 오류 및 경고에 대한 코드를 표시하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="17064-103">Prevents the compiler from displaying code for syntax-related errors and warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17064-104">구문</span><span class="sxs-lookup"><span data-stu-id="17064-104">Syntax</span></span>  
  
```  
/quiet  
```  
  
## <a name="remarks"></a><span data-ttu-id="17064-105">설명</span><span class="sxs-lookup"><span data-stu-id="17064-105">Remarks</span></span>  
 <span data-ttu-id="17064-106">기본적으로 `/quiet`은 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="17064-106">By default, `/quiet` is not in effect.</span></span> <span data-ttu-id="17064-107">컴파일러에서 구문 관련 오류 또는 경고를 보고 하는 경우 또한 소스 코드에서 줄을 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="17064-107">When the compiler reports a syntax-related error or warning, it also outputs the line from source code.</span></span> <span data-ttu-id="17064-108">컴파일러 출력을 구문 분석 하는 응용 프로그램을 더 간편 하 게 진단 텍스트만 출력 하도록 컴파일러에 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17064-108">For applications that parse compiler output, it may be more convenient for the compiler to output only the text of the diagnostic.</span></span>  
  
 <span data-ttu-id="17064-109">다음 예에서 `Module1` 없이 컴파일한 경우 소스 코드를 포함 하는 오류 출력 `/quiet`합니다.</span><span class="sxs-lookup"><span data-stu-id="17064-109">In the following example, `Module1` outputs an error that includes source code when compiled without `/quiet`.</span></span>  
  
```  
Module Module1  
    Sub Main()  
        x()  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="17064-110">출력:</span><span class="sxs-lookup"><span data-stu-id="17064-110">Output:</span></span>  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
 `x`  
  
 `~`  
  
 <span data-ttu-id="17064-111">으로 컴파일된 `/quiet`, 컴파일러는 다음에만 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="17064-111">Compiled with `/quiet`, the compiler outputs only the following:</span></span>  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
> [!NOTE]
>  <span data-ttu-id="17064-112">`/quiet` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 명령줄에서 컴파일할 경우에 사용할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17064-112">The `/quiet` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17064-113">예제</span><span class="sxs-lookup"><span data-stu-id="17064-113">Example</span></span>  
 <span data-ttu-id="17064-114">다음 코드에서는 `T2.vb` 컴파일러 구문 관련 진단에 대 한 코드를 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="17064-114">The following code compiles `T2.vb` and does not display code for syntax-related compiler diagnostics:</span></span>  
  
```  
vbc /quiet t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="17064-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="17064-115">See Also</span></span>  
 [<span data-ttu-id="17064-116">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="17064-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="17064-117">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="17064-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
