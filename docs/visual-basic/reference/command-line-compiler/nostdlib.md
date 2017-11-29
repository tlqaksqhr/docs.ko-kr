---
title: /nostdlib(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a9d76563a5b3d439495899e07ce2df59c0acd75e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="nostdlib-visual-basic"></a><span data-ttu-id="b98bd-102">/nostdlib(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b98bd-102">/nostdlib (Visual Basic)</span></span>
<span data-ttu-id="b98bd-103">컴파일러가를 자동으로 표준 라이브러리를 참조 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b98bd-103">Causes the compiler not to automatically reference the standard libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b98bd-104">구문</span><span class="sxs-lookup"><span data-stu-id="b98bd-104">Syntax</span></span>  
  
```  
/nostdlib  
```  
  
## <a name="remarks"></a><span data-ttu-id="b98bd-105">설명</span><span class="sxs-lookup"><span data-stu-id="b98bd-105">Remarks</span></span>  
 <span data-ttu-id="b98bd-106">`/nostdlib` 옵션 System.dll 어셈블리에 대 한 자동 참조를 제거 하 고 컴파일러가 Vbc.rsp 파일을 읽는 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b98bd-106">The `/nostdlib` option removes the automatic reference to the System.dll assembly and prevents the compiler from reading the Vbc.rsp file.</span></span> <span data-ttu-id="b98bd-107">Vbc.rsp 파일-Vbc.exe 파일과 동일한 디렉터리에 있는-자주 사용 되는 참조 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 어셈블리 및 가져오기는 `System` 및 `Microsoft.VisualBasic` 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="b98bd-107">The Vbc.rsp file—which is located in the same directory as the Vbc.exe file—references the commonly used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b98bd-108">Mscorlib.dll 및 Microsoft.VisualBasic.dll 어셈블리는 항상 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="b98bd-108">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b98bd-109">`/nostdlib` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 명령줄에서 컴파일할 경우에 사용할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b98bd-109">The `/nostdlib` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b98bd-110">예제</span><span class="sxs-lookup"><span data-stu-id="b98bd-110">Example</span></span>  
 <span data-ttu-id="b98bd-111">다음 코드에서는 `T2.vb` 표준 라이브러리를 참조 하지 않고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b98bd-111">The following code compiles `T2.vb` without referencing the standard libraries.</span></span> <span data-ttu-id="b98bd-112">설정 해야 합니다는 `_MYTYPE` 조건부 컴파일 상수를 문자열 제거 하려면 "Empty"는 `My` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="b98bd-112">You must set the `_MYTYPE` conditional-compilation constant to the string "Empty" to remove the `My` object.</span></span>  
  
```  
vbc /nostdlib /define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="b98bd-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b98bd-113">See Also</span></span>  
 [<span data-ttu-id="b98bd-114">/noconfig</span><span class="sxs-lookup"><span data-stu-id="b98bd-114">/noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [<span data-ttu-id="b98bd-115">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="b98bd-115">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="b98bd-116">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="b98bd-116">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="b98bd-117">My에 사용할 수 있는 개체 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="b98bd-117">Customizing Which Objects are Available in My</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
