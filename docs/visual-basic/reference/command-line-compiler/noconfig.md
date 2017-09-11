---
title: "/noconfig | Microsoft 문서"
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
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
caps.latest.revision: 15
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
ms.openlocfilehash: fe3271e4a119e0c40370a7351bb39188f4d1c8ef
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="noconfig"></a><span data-ttu-id="d84ac-102">/noconfig</span><span class="sxs-lookup"><span data-stu-id="d84ac-102">/noconfig</span></span>
<span data-ttu-id="d84ac-103">지정 하는 컴파일러 참조 하지 않아야 자동으로 자주 사용 되는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 어셈블리 또는 가져오기는 `System` 및 `Microsoft.VisualBasic` 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="d84ac-103">Specifies that the compiler should not automatically reference the commonly used [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] assemblies or import the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d84ac-104">구문</span><span class="sxs-lookup"><span data-stu-id="d84ac-104">Syntax</span></span>  
  
```  
/noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="d84ac-105">설명</span><span class="sxs-lookup"><span data-stu-id="d84ac-105">Remarks</span></span>  
 <span data-ttu-id="d84ac-106">`/noconfig` 옵션 Vbc.exe 파일과 동일한 디렉터리에 있는 Vbc.rsp 파일을 사용 하 여 컴파일하면 하지 않도록 컴파일러에 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d84ac-106">The `/noconfig` option tells the compiler not to compile with the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="d84ac-107">Vbc.rsp 파일은 일반적으로 사용 되는 참조 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 어셈블리 및 가져오기는 `System` 및 `Microsoft.VisualBasic` 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="d84ac-107">The Vbc.rsp file references the commonly used [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span> <span data-ttu-id="d84ac-108">컴파일러는 암시적으로 System.dll 어셈블리를 참조 하지 않는 한는 `/nostdlib` 옵션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d84ac-108">The compiler implicitly references the System.dll assembly unless the `/nostdlib` option is specified.</span></span> <span data-ttu-id="d84ac-109">`/nostdlib` 옵션 Vbc.rsp 컴파일하거나 System.dll 어셈블리를 자동으로 참조 하지 않도록 컴파일러에 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d84ac-109">The `/nostdlib` option tells the compiler not to compile with Vbc.rsp or automatically reference the System.dll assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d84ac-110">Mscorlib.dll 및 Microsoft.VisualBasic.dll 어셈블리는 항상 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="d84ac-110">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
 <span data-ttu-id="d84ac-111">모든 Vbc.exe 컴파일에 포함 되어야 하는 추가 컴파일러 옵션을 지정 하려면 Vbc.rsp 파일을 수정할 수 있습니다 (지정 하는 경우를 제외 하 고는 `/noconfig` 옵션).</span><span class="sxs-lookup"><span data-stu-id="d84ac-111">You can modify the Vbc.rsp file to specify additional compiler options that should be included in every Vbc.exe compilation (except when specifying the `/noconfig` option).</span></span> <span data-ttu-id="d84ac-112">자세한 내용은 [@ (지시 파일 지정)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d84ac-112">For more information, see [@ (Specify Response File)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span></span>  
  
 <span data-ttu-id="d84ac-113">컴파일러에 전달 된 옵션으로 처리 된 `vbc` 마지막 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="d84ac-113">The compiler processes the options passed to the `vbc` command last.</span></span> <span data-ttu-id="d84ac-114">따라서 명령줄에서 모든 옵션은 Vbc.rsp 파일에 동일한 옵션의 설정을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d84ac-114">Therefore, any option on the command line overrides the setting of the same option in the Vbc.rsp file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d84ac-115">`/noconfig` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 명령줄에서 컴파일할 때에 사용할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d84ac-115">The `/noconfig` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d84ac-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d84ac-116">See Also</span></span>  
 <span data-ttu-id="d84ac-117">[/nostdlib (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nostdlib.md) </span><span class="sxs-lookup"><span data-stu-id="d84ac-117">[/nostdlib (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nostdlib.md) </span></span>  
<span data-ttu-id="d84ac-118"> [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="d84ac-118"> [Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="d84ac-119"> [@ (지시 파일 지정)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md) </span><span class="sxs-lookup"><span data-stu-id="d84ac-119"> [@ (Specify Response File)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md) </span></span>  
<span data-ttu-id="d84ac-120"> [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)</span><span class="sxs-lookup"><span data-stu-id="d84ac-120"> [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)</span></span>
