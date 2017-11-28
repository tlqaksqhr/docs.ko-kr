---
title: "-warnaserror(C# 컴파일러 옵션)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /warnaserror
helpviewer_keywords:
- /warnaserror compiler option [C#]
- -warnaserror compiler option [C#]
- warnaserror compiler option [C#]
ms.assetid: 04680ec3-08d6-4e2e-a274-38310e10e33c
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 28c2cdc26d32d98e617a0c4b8cd282d2fbc87f4d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="warnaserror-c-compiler-options"></a><span data-ttu-id="dc741-102">/warnaserror(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="dc741-102">/warnaserror (C# Compiler Options)</span></span>
<span data-ttu-id="dc741-103">**/warnaserror+** 옵션은 모든 경고를 오류로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="dc741-103">The **/warnaserror+** option treats all warnings as errors</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc741-104">구문</span><span class="sxs-lookup"><span data-stu-id="dc741-104">Syntax</span></span>  
  
```console  
/warnaserror[<U>+</U> | -][:warning-list]  
```  
  
## <a name="remarks"></a><span data-ttu-id="dc741-105">설명</span><span class="sxs-lookup"><span data-stu-id="dc741-105">Remarks</span></span>  
 <span data-ttu-id="dc741-106">일반적으로 경고로 보고되는 메시지가 대신 오류로 보고되며, 빌드 프로세스가 중지됩니다(출력 파일이 작성되지 않음).</span><span class="sxs-lookup"><span data-stu-id="dc741-106">Any messages that would ordinarily be reported as warnings are instead reported as errors, and the build process is halted (no output files are built).</span></span>  
  
 <span data-ttu-id="dc741-107">기본적으로 **/warnaserror-**가 적용되며, 경고가 발생해도 출력 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc741-107">By default, **/warnaserror-** is in effect, which causes warnings to not prevent the generation of an output file.</span></span> <span data-ttu-id="dc741-108">**/warnaserror+**와 동일한 **/warnaserror**는 경고가 오류로 처리되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc741-108">**/warnaserror**, which is the same as **/warnaserror+**, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="dc741-109">필요에 따라 몇 개의 특정 경고만 오류로 처리하려는 경우 오류로 처리할 경고 번호의 쉼표로 구분된 목록을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc741-109">Optionally, if you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span>  
  
 <span data-ttu-id="dc741-110">컴파일러에서 표시할 경고 수준을 지정하려면 [/warn](../../../csharp/language-reference/compiler-options/warn-compiler-option.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dc741-110">Use [/warn](../../../csharp/language-reference/compiler-options/warn-compiler-option.md) to specify the level of warnings that you want the compiler to display.</span></span> <span data-ttu-id="dc741-111">특정 경고를 사용하지 않으려면 [/nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dc741-111">Use [/nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md) to disable certain warnings.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="dc741-112">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="dc741-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="dc741-113">프로젝트 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="dc741-113">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="dc741-114">**빌드** 속성 페이지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dc741-114">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="dc741-115">**경고를 오류로 처리** 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="dc741-115">Modify the **Treat Warnings As Errors** property.</span></span>  
  
     <span data-ttu-id="dc741-116">프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc741-116">To set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc741-117">예제</span><span class="sxs-lookup"><span data-stu-id="dc741-117">Example</span></span>  
 <span data-ttu-id="dc741-118">`in.cs`를 컴파일하고 컴파일러에서 경고를 표시하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc741-118">Compile `in.cs` and have the compiler display no warnings:</span></span>  
  
```console  
csc /warnaserror in.cs  
csc /warnaserror:642,649,652 in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="dc741-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc741-119">See Also</span></span>  
 [<span data-ttu-id="dc741-120">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="dc741-120">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="dc741-121">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="dc741-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
