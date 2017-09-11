---
title: "/bugreport | Microsoft 문서"
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
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
caps.latest.revision: 22
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
ms.openlocfilehash: b959ef7958cffbbb31f3907eaf8749ca93ac538d
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="bugreport"></a><span data-ttu-id="01e7c-102">/bugreport</span><span class="sxs-lookup"><span data-stu-id="01e7c-102">/bugreport</span></span>
<span data-ttu-id="01e7c-103">버그 보고서를 파일로 작성할 때는 사용할 수 있는 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="01e7c-103">Creates a file that you can use when you file a bug report.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01e7c-104">구문</span><span class="sxs-lookup"><span data-stu-id="01e7c-104">Syntax</span></span>  
  
```  
/bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="01e7c-105">인수</span><span class="sxs-lookup"><span data-stu-id="01e7c-105">Arguments</span></span>  
  
|<span data-ttu-id="01e7c-106">용어</span><span class="sxs-lookup"><span data-stu-id="01e7c-106">Term</span></span>|<span data-ttu-id="01e7c-107">정의</span><span class="sxs-lookup"><span data-stu-id="01e7c-107">Definition</span></span>|  
|---|---|  
|`file`|<span data-ttu-id="01e7c-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="01e7c-108">Required.</span></span> <span data-ttu-id="01e7c-109">버그 보고서를 포함 하는 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="01e7c-109">The name of the file that will contain your bug report.</span></span> <span data-ttu-id="01e7c-110">파일 이름을 따옴표로 묶습니다 ("") 이름에 공백이 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="01e7c-110">Enclose the file name in quotation marks (" ") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01e7c-111">주의</span><span class="sxs-lookup"><span data-stu-id="01e7c-111">Remarks</span></span>  
 <span data-ttu-id="01e7c-112">다음 정보에 추가 됩니다 `file`:</span><span class="sxs-lookup"><span data-stu-id="01e7c-112">The following information is added to `file`:</span></span>  
  
-   <span data-ttu-id="01e7c-113">컴파일할 때 모든 소스 코드 파일의 복사본입니다.</span><span class="sxs-lookup"><span data-stu-id="01e7c-113">A copy of all source-code files in the compilation.</span></span>  
  
-   <span data-ttu-id="01e7c-114">컴파일에 사용 되는 컴파일러 옵션의 목록.</span><span class="sxs-lookup"><span data-stu-id="01e7c-114">A list of the compiler options used in the compilation.</span></span>  
  
-   <span data-ttu-id="01e7c-115">컴파일러, 공용 언어 런타임 및 운영 체제에 대 한 버전 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="01e7c-115">Version information about your compiler, common language runtime, and operating system.</span></span>  
  
-   <span data-ttu-id="01e7c-116">컴파일러 출력, 있는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="01e7c-116">Compiler output, if any.</span></span>  
  
-   <span data-ttu-id="01e7c-117">에 대 한 메시지가 표시 되는 문제에 대 한 설명</span><span class="sxs-lookup"><span data-stu-id="01e7c-117">A description of the problem, for which you are prompted.</span></span>  
  
-   <span data-ttu-id="01e7c-118">에 대 한 메시지가 표시 되는 문제를 생각 하는 방법에 대 한 설명을 수정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e7c-118">A description of how you think the problem should be fixed, for which you are prompted.</span></span>  
  
 <span data-ttu-id="01e7c-119">모든 소스 코드 파일의 복사본에 포함 되어 있으므로 `file`, 가능한 가장 짧은 프로그램의 코드 결함을 재현 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="01e7c-119">Because a copy of all source-code files is included in `file`, you may want to reproduce the (suspected) code defect in the shortest possible program.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="01e7c-120">`/bugreport` 옵션은 잠재적으로 중요 한 정보가 포함 된 파일을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e7c-120">The `/bugreport` option produces a file that contains potentially sensitive information.</span></span> <span data-ttu-id="01e7c-121">현재 시간, 컴파일러 버전 이때 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 버전, 운영 체제 버전, 사용자 이름, 명령줄 인수는 컴파일러를 실행 하면서 모든 소스 코드 및 참조 된 어셈블리의 모든 이진 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="01e7c-121">This includes current time, compiler version, [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] version, OS version, user name, the command-line arguments with which the compiler was run, all source code, and the binary form of any referenced assembly.</span></span> <span data-ttu-id="01e7c-122">이 옵션의 서버 쪽 컴파일에 대 한 Web.config 파일에서 명령줄 옵션을 지정 하 여 액세스할 수는 [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="01e7c-122">This option can be accessed by specifying command-line options in the Web.config file for a server-side compilation of an [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] application.</span></span> <span data-ttu-id="01e7c-123">이 방지 하려면 사용자가 서버에서 컴파일하지을 Machine.config 파일을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e7c-123">To prevent this, modify the Machine.config file to disallow users from compiling on the server.</span></span>  
  
 <span data-ttu-id="01e7c-124">이 옵션은 함께 사용할 경우 `/errorreport:prompt`, `/errorreport:queue`, 또는 `/errorreport:send`, 응용 프로그램의 정보를 내부 컴파일러 오류를 발견 한 `file` Microsoft Corporation로 보내집니다.</span><span class="sxs-lookup"><span data-stu-id="01e7c-124">If this option is used with `/errorreport:prompt`, `/errorreport:queue`, or `/errorreport:send`, and your application encounters an internal compiler error, the information in `file` is sent to Microsoft Corporation.</span></span> <span data-ttu-id="01e7c-125">정보는 Microsoft 엔지니어가 오류의 원인을 파악 하는 데 도움이 되며의 다음 릴리스를 개선 하는 데 도움이 될 수 있습니다 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="01e7c-125">That information will help Microsoft engineers identify the cause of the error and may help improve the next release of [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="01e7c-126">기본적으로 정보가 Microsoft에 보내집니다.</span><span class="sxs-lookup"><span data-stu-id="01e7c-126">By default, no information is sent to Microsoft.</span></span> <span data-ttu-id="01e7c-127">그러나 컴파일하는 경우 응용 프로그램 사용 하 여 `/errorreport:queue`, 기본적으로 활성화 되어, 응용 프로그램의 오류 보고서를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e7c-127">However, when you compile an application by using `/errorreport:queue`, which is enabled by default, the application collects its error reports.</span></span> <span data-ttu-id="01e7c-128">그런 다음 컴퓨터의 관리자가 로그인 할 때 오류 보고 시스템 관리자를 로그온 이후 발생 한 모든 오류 보고서를 Microsoft에 전달 하는 팝업 창을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e7c-128">Then, when the computer's administrator logs in, the error reporting system displays a pop-up window that enables the administrator to forward to Microsoft any error reports that occurred since the logon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="01e7c-129">`/bugreport` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 사용할 수는 명령줄에서 컴파일할 때만 합니다.</span><span class="sxs-lookup"><span data-stu-id="01e7c-129">The `/bugreport` option is not available from within the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01e7c-130">예제</span><span class="sxs-lookup"><span data-stu-id="01e7c-130">Example</span></span>  
 <span data-ttu-id="01e7c-131">다음 예제에서는 컴파일합니다 `T2.vb` 파일에 모든 버그 보고 정보를 저장 하 고 `Problem.txt`합니다.</span><span class="sxs-lookup"><span data-stu-id="01e7c-131">The following example compiles `T2.vb` and puts all bug-reporting information in the file `Problem.txt`.</span></span>  
  
```  
vbc /bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="01e7c-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="01e7c-132">See Also</span></span>  
 <span data-ttu-id="01e7c-133">[Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="01e7c-133">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="01e7c-134"> [/debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md) </span><span class="sxs-lookup"><span data-stu-id="01e7c-134"> [/debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md) </span></span>  
<span data-ttu-id="01e7c-135"> [/errorreport](../../../visual-basic/reference/command-line-compiler/errorreport.md) </span><span class="sxs-lookup"><span data-stu-id="01e7c-135"> [/errorreport](../../../visual-basic/reference/command-line-compiler/errorreport.md) </span></span>  
<span data-ttu-id="01e7c-136"> [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="01e7c-136"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="01e7c-137"> [securityPolicy (ASP.NET 설정 스키마)에 대 한 trustLevel 요소](http://msdn.microsoft.com/en-us/729ab04c-03da-4ee5-86b1-be9d08a09369)</span><span class="sxs-lookup"><span data-stu-id="01e7c-137"> [trustLevel Element for securityPolicy (ASP.NET Settings Schema)](http://msdn.microsoft.com/en-us/729ab04c-03da-4ee5-86b1-be9d08a09369)</span></span>
