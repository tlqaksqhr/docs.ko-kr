---
title: "/nostdlib (Visual Basic) | Microsoft 문서"
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
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
caps.latest.revision: 18
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
ms.openlocfilehash: 046e2b845324ed1c2f8c15bbb029fe84f7693f6e
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="nostdlib-visual-basic"></a><span data-ttu-id="c9619-102">/nostdlib(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c9619-102">/nostdlib (Visual Basic)</span></span>
<span data-ttu-id="c9619-103">컴파일러가를 자동으로 표준 라이브러리를 참조 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9619-103">Causes the compiler not to automatically reference the standard libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9619-104">구문</span><span class="sxs-lookup"><span data-stu-id="c9619-104">Syntax</span></span>  
  
```  
/nostdlib  
```  
  
## <a name="remarks"></a><span data-ttu-id="c9619-105">주의</span><span class="sxs-lookup"><span data-stu-id="c9619-105">Remarks</span></span>  
 <span data-ttu-id="c9619-106">`/nostdlib` 옵션 System.dll 어셈블리에 대 한 자동 참조를 제거 하 고는 컴파일러가 Vbc.rsp 파일을 읽을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9619-106">The `/nostdlib` option removes the automatic reference to the System.dll assembly and prevents the compiler from reading the Vbc.rsp file.</span></span> <span data-ttu-id="c9619-107">Vbc.rsp 파일-Vbc.exe 파일과 동일한 디렉터리에 있는-자주 사용 되는 참조 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 어셈블리 및 가져오기는 `System` 및 `Microsoft.VisualBasic` 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c9619-107">The Vbc.rsp file—which is located in the same directory as the Vbc.exe file—references the commonly used [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9619-108">Mscorlib.dll 및 Microsoft.VisualBasic.dll 어셈블리는 항상 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9619-108">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9619-109">`/nostdlib` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 명령줄에서 컴파일할 때에 사용할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9619-109">The `/nostdlib` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9619-110">예제</span><span class="sxs-lookup"><span data-stu-id="c9619-110">Example</span></span>  
 <span data-ttu-id="c9619-111">다음 코드에서는 `T2.vb` 표준 라이브러리를 참조 하지 않고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9619-111">The following code compiles `T2.vb` without referencing the standard libraries.</span></span> <span data-ttu-id="c9619-112">설정 해야는 `_MYTYPE` 조건부 컴파일 상수를 문자열 "Empty"를 제거 하는 `My` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c9619-112">You must set the `_MYTYPE` conditional-compilation constant to the string "Empty" to remove the `My` object.</span></span>  
  
```  
vbc /nostdlib /define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="c9619-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c9619-113">See Also</span></span>  
 <span data-ttu-id="c9619-114">[/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span><span class="sxs-lookup"><span data-stu-id="c9619-114">[/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span></span>  
<span data-ttu-id="c9619-115"> [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="c9619-115"> [Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="c9619-116"> [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="c9619-116"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="c9619-117"> [My에 사용할 수 있는 개체 사용자 지정](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)</span><span class="sxs-lookup"><span data-stu-id="c9619-117"> [Customizing Which Objects are Available in My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)</span></span>
