---
title: -out(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /out
helpviewer_keywords:
- /out compiler option [C#]
- out compiler option [C#]
- -out compiler option [C#]
ms.assetid: 70d91d01-7bd2-4aea-ba8b-4e9807e9caa5
ms.openlocfilehash: 0f33f003f31a3a668342c517d1562e80b0410e00
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="-out-c-compiler-options"></a><span data-ttu-id="1879c-102">-out(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="1879c-102">-out (C# Compiler Options)</span></span>
<span data-ttu-id="1879c-103">**-out** 옵션은 출력 파일의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1879c-103">The **-out** option specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1879c-104">구문</span><span class="sxs-lookup"><span data-stu-id="1879c-104">Syntax</span></span>  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="1879c-105">인수</span><span class="sxs-lookup"><span data-stu-id="1879c-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="1879c-106">컴파일러에서 생성된 출력 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1879c-106">The name of the output file created by the compiler.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1879c-107">설명</span><span class="sxs-lookup"><span data-stu-id="1879c-107">Remarks</span></span>  
 <span data-ttu-id="1879c-108">명령줄에서 컴파일에 대해 여러 출력 파일을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1879c-108">On the command line, it is possible to specify multiple output files for your compilation.</span></span> <span data-ttu-id="1879c-109">컴파일러는 **-out** 옵션 뒤에 하나 이상의 소스 코드 파일이 있을 것으로 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="1879c-109">The compiler expects to find one or more source code files following the **-out** option.</span></span> <span data-ttu-id="1879c-110">그런 다음 **-out** 옵션으로 지정된 출력 파일에 모든 소스 코드 파일이 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="1879c-110">Then, all source code files will be compiled into the output file specified by that **-out** option.</span></span>  
  
 <span data-ttu-id="1879c-111">만들려는 파일의 전체 이름과 확장명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1879c-111">Specify the full name and extension of the file you want to create.</span></span>  
  
 <span data-ttu-id="1879c-112">출력 파일의 이름을 지정하지 않을 경우</span><span class="sxs-lookup"><span data-stu-id="1879c-112">If you do not specify the name of the output file:</span></span>  
  
-   <span data-ttu-id="1879c-113">.exe는 **Main** 메서드가 포함된 소스 코드 파일에서 해당 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1879c-113">An .exe will take its name from the source code file that contains the **Main** method.</span></span>  
  
-   <span data-ttu-id="1879c-114">.dll 또는 netmodule은 첫 번째 소스 코드 파일에서 해당 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1879c-114">A .dll or .netmodule will take its name from the first source code file.</span></span>  
  
 <span data-ttu-id="1879c-115">한 출력 파일을 컴파일하는 데 사용되는 소스 코드 파일을 동일한 컴파일에서 다른 출력 파일의 컴파일에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1879c-115">A source code file used to compile one output file cannot be used in the same compilation for the compilation of another output file.</span></span>  
  
 <span data-ttu-id="1879c-116">명령줄 컴파일에서 여러 출력 파일을 만들 때는 출력 파일 중 하나만 어셈블리가 될 수 있고, **-out**을 사용하여 명시적으로 또는 암시적으로 지정된 첫 번째 출력 파일만 어셈블리가 될 수 있다는 것에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="1879c-116">When producing multiple output files in a command-line compilation, keep in mind that only one of the output files can be an assembly and that only the first output file specified (implicitly or explicitly with **-out**) can be the assembly.</span></span>  
  
 <span data-ttu-id="1879c-117">컴파일의 일부로 생성된 모든 모듈은 컴파일할 때 함께 생성된 어셈블리와 연결된 파일이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1879c-117">Any modules produced as part of a compilation become files associated with any assembly also produced in the compilation.</span></span> <span data-ttu-id="1879c-118">연결된 파일을 보려면 [ildasm.exe](../../../framework/tools/ildasm-exe-il-disassembler.md)를 사용하여 어셈블리 매니페스트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1879c-118">Use [ildasm.exe](../../../framework/tools/ildasm-exe-il-disassembler.md) to view the assembly manifest to see the associated files.</span></span>  
  
 <span data-ttu-id="1879c-119">exe가 friend 어셈블리의 대상이 되려면 -out 컴파일러 옵션이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1879c-119">The -out compiler option is required in order for an exe to be the target of a friend assembly.</span></span> <span data-ttu-id="1879c-120">자세한 내용은 [Friend 어셈블리](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1879c-120">For more information see [Friend Assemblies](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="1879c-121">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="1879c-121">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="1879c-122">프로젝트 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1879c-122">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="1879c-123">**응용 프로그램** 속성 페이지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1879c-123">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="1879c-124">**어셈블리 이름** 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="1879c-124">Modify the **Assembly name** property.</span></span>  
  
     <span data-ttu-id="1879c-125">이 컴파일러 옵션을 프로그래밍 방식으로 설정하려면: <xref:VSLangProj80.ProjectProperties3.OutputFileName%2A>은 프로젝트 형식(exe, 라이브러리 등)과 어셈블리 이름의 조합으로 결정되는 읽기 전용 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="1879c-125">To set this compiler option programmatically: the <xref:VSLangProj80.ProjectProperties3.OutputFileName%2A> is a read-only property, which is determined by a combination of the project type (exe, library, and so forth) and the assembly name.</span></span> <span data-ttu-id="1879c-126">출력 파일 이름을 설정하려면 이러한 속성 중 하나 또는 둘 다를 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1879c-126">Modifying one or both of these properties will be necessary to set the output file name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1879c-127">예</span><span class="sxs-lookup"><span data-stu-id="1879c-127">Example</span></span>  
 <span data-ttu-id="1879c-128">`t.cs`를 컴파일하고 출력 파일 `t.exe`를 만들 뿐만 아니라 `t2.cs`를 작성하고 모듈 출력 파일 `mymodule.netmodule`을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1879c-128">Compile `t.cs` and create output file `t.exe`, as well as build `t2.cs` and create module output file `mymodule.netmodule`:</span></span>  
  
```console  
csc t.cs -out:mymodule.netmodule -target:module t2.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="1879c-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1879c-129">See Also</span></span>  
 [<span data-ttu-id="1879c-130">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="1879c-130">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="1879c-131">Friend 어셈블리</span><span class="sxs-lookup"><span data-stu-id="1879c-131">Friend Assemblies</span></span>](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)  
 [<span data-ttu-id="1879c-132">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="1879c-132">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
