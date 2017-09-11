---
title: "/verbose | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 62285a727217aa897a83a9e746588c80a2c519c0
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="verbose"></a><span data-ttu-id="bc849-102">/verbose</span><span class="sxs-lookup"><span data-stu-id="bc849-102">/verbose</span></span>
<span data-ttu-id="bc849-103">상태 및 오류에 대 한 자세한 정보 메시지를 생성 하는 컴파일러가 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc849-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc849-104">구문</span><span class="sxs-lookup"><span data-stu-id="bc849-104">Syntax</span></span>  
  
```  
/verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="bc849-105">인수</span><span class="sxs-lookup"><span data-stu-id="bc849-105">Arguments</span></span>  
 <span data-ttu-id="bc849-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="bc849-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="bc849-107">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="bc849-107">Optional.</span></span> <span data-ttu-id="bc849-108">지정 `/verbose` 지정 하는 것과 같습니다 `/verbose+`, 자세한 정보 메시지를 내보낼 컴파일러가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc849-108">Specifying `/verbose` is the same as specifying `/verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="bc849-109">이 옵션의 기본값은 `/verbose-`합니다.</span><span class="sxs-lookup"><span data-stu-id="bc849-109">The default for this option is `/verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc849-110">주의</span><span class="sxs-lookup"><span data-stu-id="bc849-110">Remarks</span></span>  
 <span data-ttu-id="bc849-111">`/verbose` 옵션은 컴파일러에서 생성 한 오류의 총 수에 대 한 정보를 표시 합니다. 모듈에 의해 로드 되 고 있는 어셈블리를 보고 하 고 현재 컴파일 중인 파일을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc849-111">The `/verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc849-112">`/verbose` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 명령줄에서 컴파일할 때에 사용할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc849-112">The `/verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc849-113">예제</span><span class="sxs-lookup"><span data-stu-id="bc849-113">Example</span></span>  
 <span data-ttu-id="bc849-114">다음 코드에서는 `In.vb` 를 자세한 상태 정보를 표시 하도록 컴파일러에 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc849-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```  
vbc /verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="bc849-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bc849-115">See Also</span></span>  
 <span data-ttu-id="bc849-116">[Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="bc849-116">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="bc849-117"> [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="bc849-117"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
