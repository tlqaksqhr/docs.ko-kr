---
title: -noconfig(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /noconfig
helpviewer_keywords:
- /noconfig compiler option [C#]
- csc.rsp
- -noconfig compiler option [C#]
- noconfig compiler option [C#]
ms.assetid: cd26967e-e494-4c8c-b5c9-af13b2f78b2e
ms.openlocfilehash: 96321de5982a79cb073b658a84e0e580dd466539
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="-noconfig-c-compiler-options"></a><span data-ttu-id="72485-102">-noconfig(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="72485-102">-noconfig (C# Compiler Options)</span></span>
<span data-ttu-id="72485-103">**-noconfig** 옵션은 csc.exe 파일과 동일한 디렉터리에 있고 여기서 로드되는 csc.rsp 파일로 컴파일하지 않도록 컴파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="72485-103">The **-noconfig** option tells the compiler not to compile with the csc.rsp file, which is located in and loaded from the same directory as the csc.exe file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72485-104">구문</span><span class="sxs-lookup"><span data-stu-id="72485-104">Syntax</span></span>  
  
```console  
-noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="72485-105">설명</span><span class="sxs-lookup"><span data-stu-id="72485-105">Remarks</span></span>  
 <span data-ttu-id="72485-106">csc.rsp 파일은 .NET Framework와 함께 제공되는 모든 어셈블리를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="72485-106">The csc.rsp file references all the assemblies shipped with the .NET Framework.</span></span> <span data-ttu-id="72485-107">Visual Studio .NET 개발 환경에 포함된 실제 참조는 프로젝트 형식에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="72485-107">The actual references that the Visual Studio .NET development environment includes depend on the project type.</span></span>  
  
 <span data-ttu-id="72485-108">csc.rsp 파일을 수정하여 **-noconfig** 옵션을 제외하고 csc.exe를 사용하여 명령줄에서 컴파일할 때마다 포함되어야 하는 추가 컴파일러 옵션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72485-108">You can modify the csc.rsp file and specify additional compiler options that should be included in every compilation from the command line with csc.exe (except the **-noconfig** option).</span></span>  
  
 <span data-ttu-id="72485-109">컴파일러는 **csc** 명령에 마지막으로 전달된 옵션을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="72485-109">The compiler processes the options passed to the **csc** command last.</span></span> <span data-ttu-id="72485-110">따라서 명령줄의 모든 옵션은 csc.rsp 파일에 있는 동일한 옵션의 설정을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="72485-110">Therefore, any option on the command line overrides the setting of the same option in the csc.rsp file.</span></span>  
  
 <span data-ttu-id="72485-111">컴파일러가 csc.rsp 파일의 설정을 찾아서 사용하지 않도록 하려면 **-noconfig**를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="72485-111">If you do not want the compiler to look for and use the settings in the csc.rsp file, specify **-noconfig**.</span></span>  
  
 <span data-ttu-id="72485-112">이 컴파일러 옵션은 Visual Studio에서 사용할 수 없으며 프로그래밍 방식으로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="72485-112">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72485-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="72485-113">See Also</span></span>  
 [<span data-ttu-id="72485-114">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="72485-114">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="72485-115">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="72485-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
