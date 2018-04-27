---
title: '방법: 명령줄 컴파일러 호출(Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line [Visual Basic], arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
caps.latest.revision: 28
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f1ccf08ba58fa6af60bd8ffd7cba79b205dc0f3d
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a><span data-ttu-id="9d8b8-102">방법: 명령줄 컴파일러 호출(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9d8b8-102">How to: Invoke the Command-Line Compiler (Visual Basic)</span></span>
<span data-ttu-id="9d8b8-103">MS-DOS 프롬프트 라고도 하는 명령줄에 실행 파일의 이름을 입력 하 여 명령줄 컴파일러를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d8b8-103">You can invoke the command-line compiler by typing the name of its executable file into the command line, also known as the MS-DOS prompt.</span></span> <span data-ttu-id="9d8b8-104">기본 Windows 명령 프롬프트에서에서 컴파일하는 경우에 실행 파일의 정규화 된 경로 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d8b8-104">If you compile from the default Windows Command Prompt, you must type the fully qualified path to the executable file.</span></span> <span data-ttu-id="9d8b8-105">이 기본 동작을 재정의 하려면 사용할 수 있습니다는 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] 명령 프롬프트 또는 PATH 환경 변수를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d8b8-105">To override this default behavior, you can either use the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Command Prompt, or modify the PATH environment variable.</span></span> <span data-ttu-id="9d8b8-106">둘 다 컴파일러 이름을 입력 하 여 원하는 디렉터리에서 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d8b8-106">Both allow you to compile from any directory by simply typing the compiler name.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-invoke-the-compiler-using-the-visual-studio-command-prompt"></a><span data-ttu-id="9d8b8-107">Visual Studio 명령 프롬프트를 사용 하 여 컴파일러를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="9d8b8-107">To invoke the compiler using the Visual Studio Command Prompt</span></span>  
  
1.  <span data-ttu-id="9d8b8-108">Microsoft Visual Studio 프로그램 그룹 내에서 Visual Studio Tools 프로그램 폴더를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9d8b8-108">Open the Visual Studio Tools program folder within the Microsoft Visual Studio program group.</span></span>  
  
2.  <span data-ttu-id="9d8b8-109">사용할 수는 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Visual Studio가 설치 되어 컴퓨터에 모든 디렉터리에서 컴파일러에 액세스 하려면 명령 프롬프트입니다.</span><span class="sxs-lookup"><span data-stu-id="9d8b8-109">You can use the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Command Prompt to access the compiler from any directory on your machine, if Visual Studio is installed.</span></span>  
  
3.  <span data-ttu-id="9d8b8-110">호출 된 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] 명령 프롬프트입니다.</span><span class="sxs-lookup"><span data-stu-id="9d8b8-110">Invoke the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Command Prompt.</span></span>  
  
4.  <span data-ttu-id="9d8b8-111">명령줄에서 입력 `vbc.exe` *sourceFileName* 한 다음 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="9d8b8-111">At the command line, type `vbc.exe` *sourceFileName* and then press ENTER.</span></span>  
  
     <span data-ttu-id="9d8b8-112">예를 들어 라는 디렉터리에 소스 코드를 저장 하는 경우 `SourceFiles`, 종류와 명령 프롬프트를 열 때 `cd SourceFiles` 해당 디렉터리로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d8b8-112">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="9d8b8-113">디렉터리 라는 소스 파일을 포함 하는 경우 `Source.vb`를 입력 하 여 컴파일할 수 `vbc.exe Source.vb`합니다.</span><span class="sxs-lookup"><span data-stu-id="9d8b8-113">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>  
  
### <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a><span data-ttu-id="9d8b8-114">Windows 명령 프롬프트에 대 한 컴파일러를 PATH 환경 변수를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="9d8b8-114">To set the PATH environment variable to the compiler for the Windows Command Prompt</span></span>  
  
1.  <span data-ttu-id="9d8b8-115">로컬 디스크에 Vbc.exe를 찾으려고 Windows 검색 기능을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d8b8-115">Use the Windows Search feature to find Vbc.exe on your local disk.</span></span>  
  
     <span data-ttu-id="9d8b8-116">컴파일러 있는 디렉터리의 정확한 이름을 Windows 디렉터리의 위치는 "" 설치 된.NET Framework의 버전에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="9d8b8-116">The exact name of the directory where the compiler is located depends on the location of the Windows directory and the version of the ".NET Framework" installed.</span></span> <span data-ttu-id="9d8b8-117">".NET Framework" 설치 된 버전이 둘 이상 있는 경우 (일반적으로 최신 버전)를 사용 하는 버전을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d8b8-117">If you have more than one version of the ".NET Framework" installed, you must determine which version to use (typically the latest version).</span></span>  
  
2.  <span data-ttu-id="9d8b8-118">사용자 **시작** 메뉴를 마우스 오른쪽 단추로 클릭 **내 컴퓨터**, 클릭 하 고 **속성** 바로 가기 메뉴에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d8b8-118">From your **Start** Menu, right-click **My Computer**, and then click **Properties** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="9d8b8-119">클릭는 **고급** 탭을 클릭 한 다음 **환경 변수**합니다.</span><span class="sxs-lookup"><span data-stu-id="9d8b8-119">Click the **Advanced** tab, and then click **Environment Variables**.</span></span>  
  
4.  <span data-ttu-id="9d8b8-120">에 **시스템** 변수 창 **경로** 클릭 확인 하 고 목록에서 **편집**합니다.</span><span class="sxs-lookup"><span data-stu-id="9d8b8-120">In the **System** variables pane, select **Path** from the list and click **Edit**.</span></span>  
  
5.  <span data-ttu-id="9d8b8-121">에 **편집 시스템** 변수 대화 상자에서 문자열의 끝에 삽입 포인터를 이동는 **변수 값** 필드 세미콜론 (;)을 입력 하 고 1 단계에는 전체 디렉터리 이름이 차례로 나옵니다.</span><span class="sxs-lookup"><span data-stu-id="9d8b8-121">In the **Edit System** Variable dialog box, move the insertion point to the end of the string in the **Variable Value** field and type a semicolon (;) followed by the full directory name found in Step 1.</span></span>  
  
6.  <span data-ttu-id="9d8b8-122">클릭 **확인** 편집 내용을 확인 하는 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="9d8b8-122">Click **OK** to confirm your edits and close the dialog boxes.</span></span>  
  
     <span data-ttu-id="9d8b8-123">PATH 환경 변수를 변경한 후 실행할 수 있습니다 Visual Basic 컴파일러 Windows 명령 프롬프트에서 디렉터리에서 컴퓨터에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d8b8-123">After you change the PATH environment variable, you can run the Visual Basic compiler at the Windows Command Prompt from any directory on the computer.</span></span>  
  
### <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a><span data-ttu-id="9d8b8-124">Windows 명령 프롬프트를 사용 하 여 컴파일러를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="9d8b8-124">To invoke the compiler using the Windows Command Prompt</span></span>  
  
1.  <span data-ttu-id="9d8b8-125">**시작** 메뉴를 클릭 하 고 **Accessories** 폴더를 연 후는 **Windows 명령 프롬프트**합니다.</span><span class="sxs-lookup"><span data-stu-id="9d8b8-125">From the **Start** menu, click on the **Accessories** folder, and then open the **Windows Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="9d8b8-126">명령줄에서 입력 `vbc.exe` *sourceFileName* 한 다음 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="9d8b8-126">At the command line, type `vbc.exe`*sourceFileName* and then press ENTER.</span></span>  
  
     <span data-ttu-id="9d8b8-127">예를 들어 라는 디렉터리에 소스 코드를 저장 하는 경우 `SourceFiles`, 종류와 명령 프롬프트를 열 때 `cd SourceFiles` 해당 디렉터리로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d8b8-127">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="9d8b8-128">디렉터리 라는 소스 파일을 포함 하는 경우 `Source.vb`를 입력 하 여 컴파일할 수 `vbc.exe Source.vb`합니다.</span><span class="sxs-lookup"><span data-stu-id="9d8b8-128">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d8b8-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9d8b8-129">See Also</span></span>  
 [<span data-ttu-id="9d8b8-130">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="9d8b8-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="9d8b8-131">조건부 컴파일</span><span class="sxs-lookup"><span data-stu-id="9d8b8-131">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
