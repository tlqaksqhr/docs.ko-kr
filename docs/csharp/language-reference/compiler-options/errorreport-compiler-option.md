---
title: "-errorreport(C# 컴파일러 옵션)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /errorreport
helpviewer_keywords:
- -errorreport compiler option [C#]
- errorreport compiler option [C#]
- /errorreport compiler option [C#]
ms.assetid: bd0e7493-b79d-4369-9c3f-ba26ebdfbedf
caps.latest.revision: "35"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6d2fcb3f0bf4491de23b70c8beebf7ae495b2aa0
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="-errorreport-c-compiler-options"></a><span data-ttu-id="5d45d-102">-errorreport(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="5d45d-102">-errorreport (C# Compiler Options)</span></span>
<span data-ttu-id="5d45d-103">이 옵션은 C# 내부 컴파일러 오류를 Microsoft에 보고하는 편리한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5d45d-103">This option provides a convenient way to report a C# internal compiler error to Microsoft.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5d45d-104">Windows Vista 및 Windows Server 2008에서 Visual Studio에 대한 오류 보고 설정은 WER(Windows 오류 보고)을 통한 설정을 재정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d45d-104">On Windows Vista and Windows Server 2008, the error reporting settings that you make for Visual Studio do not override the settings made through Windows Error Reporting (WER).</span></span> <span data-ttu-id="5d45d-105">항상 WER 설정이 Visual Studio 오류 보고 설정보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="5d45d-105">WER settings always take precedence over Visual Studio error reporting settings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d45d-106">구문</span><span class="sxs-lookup"><span data-stu-id="5d45d-106">Syntax</span></span>  
  
```console  
-errorreport:{ none | prompt | queue | send }  
```  
  
## <a name="arguments"></a><span data-ttu-id="5d45d-107">인수</span><span class="sxs-lookup"><span data-stu-id="5d45d-107">Arguments</span></span>  
 <span data-ttu-id="5d45d-108">**none**</span><span class="sxs-lookup"><span data-stu-id="5d45d-108">**none**</span></span>  
 <span data-ttu-id="5d45d-109">내부 컴파일러 오류에 대한 보고서를 수집하거나 Microsoft로 보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d45d-109">Reports about internal compiler errors will not be collected or sent to Microsoft.</span></span>  
  
 <span data-ttu-id="5d45d-110">**prompt**</span><span class="sxs-lookup"><span data-stu-id="5d45d-110">**prompt**</span></span>  
 <span data-ttu-id="5d45d-111">내부 컴파일러 오류가 발생하면 보고서를 보낼지 묻는 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5d45d-111">Prompts you to send a report when you receive an internal compiler error.</span></span> <span data-ttu-id="5d45d-112">**prompt**는 개발 환경에서 응용 프로그램을 컴파일할 때 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="5d45d-112">**prompt** is the default when you compile an application in the development environment.</span></span>  
  
 <span data-ttu-id="5d45d-113">**queue**</span><span class="sxs-lookup"><span data-stu-id="5d45d-113">**queue**</span></span>  
 <span data-ttu-id="5d45d-114">오류 보고서를 큐에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="5d45d-114">Queues the error report.</span></span> <span data-ttu-id="5d45d-115">관리자 자격 증명으로 로그온하면 마지막으로 로그온한 시간 이후에 발생한 모든 오류를 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d45d-115">When you log on with administrative credentials, you can report any failures since the last time that you were logged on.</span></span> <span data-ttu-id="5d45d-116">3일에 두 번 이상 오류 보고서를 보내라는 메시지가 표시되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d45d-116">You will not be prompted to send reports for failures more than once every three days.</span></span> <span data-ttu-id="5d45d-117">**queue**는 명령줄에서 응용 프로그램을 컴파일할 때의 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="5d45d-117">**queue** is the default when you compile an application at the command line.</span></span>  
  
 <span data-ttu-id="5d45d-118">**send**</span><span class="sxs-lookup"><span data-stu-id="5d45d-118">**send**</span></span>  
 <span data-ttu-id="5d45d-119">내부 컴파일러 오류 보고서를 Microsoft에 자동으로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="5d45d-119">Automatically sends reports of internal compiler errors to Microsoft.</span></span> <span data-ttu-id="5d45d-120">이 옵션을 사용하려면 먼저 Microsoft 데이터 수집 정책에 동의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d45d-120">To enable this option, you must first agree to the Microsoft data collection policy.</span></span> <span data-ttu-id="5d45d-121">처음으로 컴퓨터에서 **-errorreport:send**를 지정하면 컴파일러 메시지에서 Microsoft 데이터 수집 정책이 포함된 Web 사이트를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="5d45d-121">The first time that you specify **-errorreport:send** on a computer, a compiler message will refer you to a Web site that contains the Microsoft data collection policy.</span></span>  
    
## <a name="remarks"></a><span data-ttu-id="5d45d-122">설명</span><span class="sxs-lookup"><span data-stu-id="5d45d-122">Remarks</span></span>  
 <span data-ttu-id="5d45d-123">내부 컴파일러 오류(ICE)는 컴파일러에서 소스 코드 파일을 처리할 수 없을 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="5d45d-123">An internal compiler error (ICE) results when the compiler cannot process a source code file.</span></span> <span data-ttu-id="5d45d-124">ICE가 발생하면 컴파일러에서 출력 파일 또는 코드를 수정하는 데 사용할 수 있는 유용한 진단을 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d45d-124">When an ICE occurs, the compiler does not produce an output file or any useful diagnostic that you can use to fix your code.</span></span>  
  
 <span data-ttu-id="5d45d-125">이전 릴리스에서는 ICE를 수신하는 경우 Microsoft 기술 지원 서비스에 문의하여 문제를 보고하도록 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5d45d-125">In previous releases, when you received an ICE, you were encouraged to contact Microsoft Product Support Services to report the problem.</span></span> <span data-ttu-id="5d45d-126">**-errorreport**를 사용하여 Visual C#팀에 ICE 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d45d-126">By using **-errorreport**, you can provide ICE information to the Visual C# team.</span></span> <span data-ttu-id="5d45d-127">오류 보고서는 향후 컴파일러 릴리스를 개선하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d45d-127">Your error reports can help improve future compiler releases.</span></span>  
  
 <span data-ttu-id="5d45d-128">사용자가 보고서를 보내는 능력은 컴퓨터 및 사용자 정책 권한에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="5d45d-128">A user's ability to send reports depends on computer and user policy permissions.</span></span>  
  
 <span data-ttu-id="5d45d-129">오류 디버거에 대한 자세한 내용은 [Windows용 Dr. Watson(Drwtsn32.exe) 도구에 대한 설명](https://support.microsoft.com/help/308538/description-of-the-dr--watson-for-windows-drwtsn32-exe-tool)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5d45d-129">For more information about error debugger, see [Description of the Dr. Watson for Windows (Drwtsn32.exe) Tool](https://support.microsoft.com/help/308538/description-of-the-dr--watson-for-windows-drwtsn32-exe-tool).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="5d45d-130">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="5d45d-130">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="5d45d-131">프로젝트 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5d45d-131">Open the project's **Properties** page.</span></span> <span data-ttu-id="5d45d-132">자세한 내용은 [프로젝트 디자이너, 빌드 페이지(C#)](/visualstudio/ide/reference/build-page-project-designer-csharp)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5d45d-132">For more information, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>  
  
2.  <span data-ttu-id="5d45d-133">**빌드** 속성 페이지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5d45d-133">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="5d45d-134">**고급** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5d45d-134">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="5d45d-135">**내부 컴파일러 오류 보고** 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="5d45d-135">Modify the **Internal Compiler Error Reporting** property.</span></span>  
  
 <span data-ttu-id="5d45d-136">이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.ErrorReport%2A>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5d45d-136">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.ErrorReport%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d45d-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5d45d-137">See Also</span></span>  
 [<span data-ttu-id="5d45d-138">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="5d45d-138">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
