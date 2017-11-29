---
title: /rootnamespace
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- /rootnamespace
- rootnamespace
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6b5da8e5eacacde9de5bdc54ef2d5e4d7f0d2653
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="rootnamespace"></a><span data-ttu-id="9f27a-102">/rootnamespace</span><span class="sxs-lookup"><span data-stu-id="9f27a-102">/rootnamespace</span></span>
<span data-ttu-id="9f27a-103">모든 형식 선언에 대한 네임스페이스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f27a-103">Specifies a namespace for all type declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f27a-104">구문</span><span class="sxs-lookup"><span data-stu-id="9f27a-104">Syntax</span></span>  
  
```  
/rootnamespace:namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="9f27a-105">인수</span><span class="sxs-lookup"><span data-stu-id="9f27a-105">Arguments</span></span>  
  
|<span data-ttu-id="9f27a-106">용어</span><span class="sxs-lookup"><span data-stu-id="9f27a-106">Term</span></span>|<span data-ttu-id="9f27a-107">정의</span><span class="sxs-lookup"><span data-stu-id="9f27a-107">Definition</span></span>|  
|---|---|  
|`namespace`|<span data-ttu-id="9f27a-108">현재 프로젝트에 대 한 모든 형식 선언을 포함할를 네임 스페이스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9f27a-108">The name of the namespace in which to enclose all type declarations for the current project.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f27a-109">설명</span><span class="sxs-lookup"><span data-stu-id="9f27a-109">Remarks</span></span>  
 <span data-ttu-id="9f27a-110">사용 하 여 Visual Studio 통합된 개발 환경에서 만든 프로젝트를 컴파일하는 데 Visual Studio 실행 파일 (Devenv.exe)를 사용 하는 경우 `/rootnamespace` 의 값을 지정 하는 <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="9f27a-110">If you use the Visual Studio executable file (Devenv.exe) to compile a project created in the Visual Studio integrated development environment, use `/rootnamespace` to specify the value of the <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> property.</span></span> <span data-ttu-id="9f27a-111">참조 [Devenv 명령줄 스위치](/visualstudio/ide/reference/devenv-command-line-switches) 자세한 정보에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f27a-111">See [Devenv Command Line Switches](/visualstudio/ide/reference/devenv-command-line-switches) for more information.</span></span>  
  
 <span data-ttu-id="9f27a-112">공용 언어 런타임 MSIL 디스어셈블러를 사용 하 여 (`Ildasm.exe`) 출력 파일에 네임 스페이스 이름을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f27a-112">Use the common language runtime MSIL Disassembler (`Ildasm.exe`) to view the namespace names in your output file.</span></span>  
  
|<span data-ttu-id="9f27a-113">Visual Studio에서 /rootnamespace를 설정 하려면 통합 개발 환경</span><span class="sxs-lookup"><span data-stu-id="9f27a-113">To set /rootnamespace in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="9f27a-114">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9f27a-114">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="9f27a-115">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9f27a-115">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="9f27a-116">자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9f27a-116">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="9f27a-117">2.  **응용 프로그램** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9f27a-117">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="9f27a-118">3.  값을 수정 된 **루트 Namespace** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="9f27a-118">3.  Modify the value in the **Root Namespace** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9f27a-119">예제</span><span class="sxs-lookup"><span data-stu-id="9f27a-119">Example</span></span>  
 <span data-ttu-id="9f27a-120">다음 코드에서는 `In.vb` 네임 스페이스의 모든 형식 선언을 포함 하 고 `mynamespace`합니다.</span><span class="sxs-lookup"><span data-stu-id="9f27a-120">The following code compiles `In.vb` and encloses all type declarations in the namespace `mynamespace`.</span></span>  
  
```  
vbc /rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="9f27a-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9f27a-121">See Also</span></span>  
 [<span data-ttu-id="9f27a-122">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="9f27a-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="9f27a-123">Ildasm.exe(IL 디스어셈블러)</span><span class="sxs-lookup"><span data-stu-id="9f27a-123">Ildasm.exe (IL Disassembler)</span></span>](https://msdn.microsoft.com/library/f7dy01k1)  
 [<span data-ttu-id="9f27a-124">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="9f27a-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
