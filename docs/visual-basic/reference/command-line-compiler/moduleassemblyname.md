---
title: "/moduleassemblyname | Microsoft 문서"
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
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
caps.latest.revision: 16
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
ms.openlocfilehash: 6852b8a0d9874fd65e93cdd9507fe9b7119ce5b3
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="moduleassemblyname"></a><span data-ttu-id="49961-102">/target</span><span class="sxs-lookup"><span data-stu-id="49961-102">/moduleassemblyname</span></span>
<span data-ttu-id="49961-103">이 모듈이 속할 어셈블리의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="49961-103">Specifies the name of the assembly that this module will be a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49961-104">구문</span><span class="sxs-lookup"><span data-stu-id="49961-104">Syntax</span></span>  
  
```  
/moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="49961-105">인수</span><span class="sxs-lookup"><span data-stu-id="49961-105">Arguments</span></span>  
  
|<span data-ttu-id="49961-106">용어</span><span class="sxs-lookup"><span data-stu-id="49961-106">Term</span></span>|<span data-ttu-id="49961-107">정의</span><span class="sxs-lookup"><span data-stu-id="49961-107">Definition</span></span>|  
|---|---|  
|`assembly_name`|<span data-ttu-id="49961-108">이 모듈의 일부가 될 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="49961-108">The name of the assembly that this module will be a part of.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49961-109">설명</span><span class="sxs-lookup"><span data-stu-id="49961-109">Remarks</span></span>  
 <span data-ttu-id="49961-110">컴파일러 프로세스는 `/moduleassemblyname` 경우에만 옵션은 `/target:module` 옵션이 지정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="49961-110">The compiler processes the `/moduleassemblyname` option only if the `/target:module` option has been specified.</span></span> <span data-ttu-id="49961-111">이 컴파일러에서 모듈을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="49961-111">This causes the compiler to create a module.</span></span> <span data-ttu-id="49961-112">컴파일러에서 생성 된 모듈은 지정 된 어셈블리에만 유효는 `/moduleassemblyname` 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="49961-112">The module created by the compiler is valid only for the assembly specified with the `/moduleassemblyname` option.</span></span> <span data-ttu-id="49961-113">다른 어셈블리에 모듈을 배치 하는 경우 런타임 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="49961-113">If you place the module in a different assembly, run-time errors will occur.</span></span>  
  
 <span data-ttu-id="49961-114">`/moduleassemblyname` 옵션은 다음 경우에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="49961-114">The `/moduleassemblyname` option is needed only when the following are true:</span></span>  
  
-   <span data-ttu-id="49961-115">모듈의 데이터 형식에 액세스 해야 하는 `Friend` 는 참조 된 어셈블리의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="49961-115">A data type in the module needs access to a `Friend` type in a referenced assembly.</span></span>  
  
-   <span data-ttu-id="49961-116">참조 된 어셈블리에 friend 어셈블리 액세스 되는 모듈을 빌드할 어셈블리에 부여.</span><span class="sxs-lookup"><span data-stu-id="49961-116">The referenced assembly has granted friend assembly access to the assembly into which the module will be built.</span></span>  
  
 <span data-ttu-id="49961-117">모듈을 만드는 방법에 대 한 자세한 내용은 참조 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="49961-117">For more information about creating a module, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span> <span data-ttu-id="49961-118">Friend 어셈블리에 대 한 자세한 내용은 참조 [Friend 어셈블리](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)합니다.</span><span class="sxs-lookup"><span data-stu-id="49961-118">For more information about friend assemblies, see [Friend Assemblies](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="49961-119">`/moduleassemblyname` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 사용할 수만 컴파일하는 경우 명령 프롬프트에서.</span><span class="sxs-lookup"><span data-stu-id="49961-119">The `/moduleassemblyname` option is not available from within the Visual Studio development environment; it is available only when you compile from a command prompt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49961-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="49961-120">See Also</span></span>  
 <span data-ttu-id="49961-121">[방법: 다중 파일 어셈블리 빌드](http://msdn.microsoft.com/library/261c5583-8a76-412d-bda7-9b8ee3b131e5) </span><span class="sxs-lookup"><span data-stu-id="49961-121">[How to: Build a Multifile Assembly](http://msdn.microsoft.com/library/261c5583-8a76-412d-bda7-9b8ee3b131e5) </span></span>  
<span data-ttu-id="49961-122"> [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="49961-122"> [Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="49961-123"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span><span class="sxs-lookup"><span data-stu-id="49961-123"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span></span>  
<span data-ttu-id="49961-124"> [주 /](../../../visual-basic/reference/command-line-compiler/main.md) </span><span class="sxs-lookup"><span data-stu-id="49961-124"> [/main](../../../visual-basic/reference/command-line-compiler/main.md) </span></span>  
<span data-ttu-id="49961-125"> [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) </span><span class="sxs-lookup"><span data-stu-id="49961-125"> [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) </span></span>  
<span data-ttu-id="49961-126"> [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) </span><span class="sxs-lookup"><span data-stu-id="49961-126"> [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) </span></span>  
<span data-ttu-id="49961-127"> [어셈블리 및 전역 어셈블리 캐시](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="49961-127"> [Assemblies and the Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="49961-128"> [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="49961-128"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="49961-129"> [Friend 어셈블리](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)</span><span class="sxs-lookup"><span data-stu-id="49961-129"> [Friend Assemblies](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)</span></span>
