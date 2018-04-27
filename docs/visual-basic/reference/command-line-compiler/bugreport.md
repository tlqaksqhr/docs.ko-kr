---
title: -bugreport
ms.date: 03/08/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 097435a3d8acda6325b27abaf3ca0fd2839d344e
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="-bugreport"></a><span data-ttu-id="37762-102">-bugreport</span><span class="sxs-lookup"><span data-stu-id="37762-102">-bugreport</span></span>
<span data-ttu-id="37762-103">버그 보고서를 파일로 작성할 때는 사용할 수 있는 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="37762-103">Creates a file that you can use when you file a bug report.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37762-104">구문</span><span class="sxs-lookup"><span data-stu-id="37762-104">Syntax</span></span>  
  
```  
-bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="37762-105">인수</span><span class="sxs-lookup"><span data-stu-id="37762-105">Arguments</span></span>  
  
|<span data-ttu-id="37762-106">용어</span><span class="sxs-lookup"><span data-stu-id="37762-106">Term</span></span>|<span data-ttu-id="37762-107">정의</span><span class="sxs-lookup"><span data-stu-id="37762-107">Definition</span></span>|  
|---|---|  
|`file`|<span data-ttu-id="37762-108">필수.</span><span class="sxs-lookup"><span data-stu-id="37762-108">Required.</span></span> <span data-ttu-id="37762-109">버그 보고서를 포함 하는 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="37762-109">The name of the file that will contain your bug report.</span></span> <span data-ttu-id="37762-110">파일 이름을 따옴표로 묶습니다 ("")는 이름에 공백이 포함 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="37762-110">Enclose the file name in quotation marks (" ") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37762-111">설명</span><span class="sxs-lookup"><span data-stu-id="37762-111">Remarks</span></span>  
 <span data-ttu-id="37762-112">다음 정보에 추가 됩니다 `file`:</span><span class="sxs-lookup"><span data-stu-id="37762-112">The following information is added to `file`:</span></span>  
  
-   <span data-ttu-id="37762-113">컴파일할 때 모든 소스 코드 파일의 복사본입니다.</span><span class="sxs-lookup"><span data-stu-id="37762-113">A copy of all source-code files in the compilation.</span></span>  
  
-   <span data-ttu-id="37762-114">컴파일에 사용 된 컴파일러 옵션의 목록.</span><span class="sxs-lookup"><span data-stu-id="37762-114">A list of the compiler options used in the compilation.</span></span>  
  
-   <span data-ttu-id="37762-115">컴파일러, 공용 언어 런타임 및 운영 체제에 대 한 버전 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="37762-115">Version information about your compiler, common language runtime, and operating system.</span></span>  
  
-   <span data-ttu-id="37762-116">컴파일러 출력입니다(있는 경우).</span><span class="sxs-lookup"><span data-stu-id="37762-116">Compiler output, if any.</span></span>  
  
-   <span data-ttu-id="37762-117">에 대 한 메시지가 표시 되는 문제에 대 한 설명</span><span class="sxs-lookup"><span data-stu-id="37762-117">A description of the problem, for which you are prompted.</span></span>  
  
-   <span data-ttu-id="37762-118">문제를 생각 하는 방법에 대 한 설명을 수정 되어야는 대 한 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37762-118">A description of how you think the problem should be fixed, for which you are prompted.</span></span>  
  
 <span data-ttu-id="37762-119">모든 소스 코드 파일의 복사본에 포함 되어 있으므로 `file`, 가능한 한 짧은 프로그램의 코드 결함을 재현 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="37762-119">Because a copy of all source-code files is included in `file`, you may want to reproduce the (suspected) code defect in the shortest possible program.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="37762-120">`-bugreport` 옵션은 잠재적으로 중요 한 정보가 포함 된 파일을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="37762-120">The `-bugreport` option produces a file that contains potentially sensitive information.</span></span> <span data-ttu-id="37762-121">현재 시간, 컴파일러 버전 여기에 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 버전, 운영 체제 버전, 사용자 이름, 명령줄 인수는 컴파일러를 실행 하면서 모든 소스 코드 및 참조 된 어셈블리의 모든 이진 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="37762-121">This includes current time, compiler version, [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] version, OS version, user name, the command-line arguments with which the compiler was run, all source code, and the binary form of any referenced assembly.</span></span> <span data-ttu-id="37762-122">이 옵션의 서버 쪽 컴파일에 대 한 Web.config 파일에서 명령줄 옵션을 지정 하 여 액세스할 수는 [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="37762-122">This option can be accessed by specifying command-line options in the Web.config file for a server-side compilation of an [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] application.</span></span> <span data-ttu-id="37762-123">이 방지 하려면 사용자가 서버에서 컴파일하지을 Machine.config 파일을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="37762-123">To prevent this, modify the Machine.config file to disallow users from compiling on the server.</span></span>  
  
 <span data-ttu-id="37762-124">이 옵션은 함께 사용할 경우 `-errorreport:prompt`, `-errorreport:queue`, 또는 `-errorreport:send`, 응용 프로그램의 정보는 내부 컴파일러 오류를 발견 한 `file` Microsoft Corporation에 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37762-124">If this option is used with `-errorreport:prompt`, `-errorreport:queue`, or `-errorreport:send`, and your application encounters an internal compiler error, the information in `file` is sent to Microsoft Corporation.</span></span> <span data-ttu-id="37762-125">이 정보는 Microsoft 엔지니어가 오류의 원인을 파악 하는 데 도움이 되며 Visual Basic의 다음 릴리스에서 성능을 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37762-125">That information will help Microsoft engineers identify the cause of the error and may help improve the next release of Visual Basic.</span></span> <span data-ttu-id="37762-126">기본적으로 Microsoft로 정보가 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37762-126">By default, no information is sent to Microsoft.</span></span> <span data-ttu-id="37762-127">그러나 컴파일하는 경우 응용 프로그램 사용 하 여 `-errorreport:queue`, 기본적으로 활성화 되어, 응용 프로그램의 오류 보고서를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="37762-127">However, when you compile an application by using `-errorreport:queue`, which is enabled by default, the application collects its error reports.</span></span> <span data-ttu-id="37762-128">그런 다음 컴퓨터의 관리자가 로그인 할 때 오류 보고 시스템 관리자 로그온 이후 발생 한 모든 오류 보고서를 Microsoft로 전달할 수 있도록 하는 팝업 창을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="37762-128">Then, when the computer's administrator logs in, the error reporting system displays a pop-up window that enables the administrator to forward to Microsoft any error reports that occurred since the logon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="37762-129">`/bugreport` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 가능 하다는 명령줄에서 컴파일할 때만 합니다.</span><span class="sxs-lookup"><span data-stu-id="37762-129">The `/bugreport` option is not available from within the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37762-130">예제</span><span class="sxs-lookup"><span data-stu-id="37762-130">Example</span></span>  
 <span data-ttu-id="37762-131">다음 예제에서는 컴파일합니다 `T2.vb` 파일에 모든 버그 보고 정보를 저장 하 고 `Problem.txt`합니다.</span><span class="sxs-lookup"><span data-stu-id="37762-131">The following example compiles `T2.vb` and puts all bug-reporting information in the file `Problem.txt`.</span></span>  
  
```  
vbc -bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="37762-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="37762-132">See Also</span></span>  
 [<span data-ttu-id="37762-133">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="37762-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="37762-134">-디버그 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37762-134">-debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)  
 [<span data-ttu-id="37762-135">-errorreport</span><span class="sxs-lookup"><span data-stu-id="37762-135">-errorreport</span></span>](../../../visual-basic/reference/command-line-compiler/errorreport.md)  
 [<span data-ttu-id="37762-136">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="37762-136">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="37762-137">securityPolicy (ASP.NET 설정 스키마)에 대 한 trustLevel 요소</span><span class="sxs-lookup"><span data-stu-id="37762-137">trustLevel Element for securityPolicy (ASP.NET Settings Schema)</span></span>](http://msdn.microsoft.com/library/729ab04c-03da-4ee5-86b1-be9d08a09369)
