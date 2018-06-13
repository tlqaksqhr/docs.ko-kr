---
title: -lib(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /lib
helpviewer_keywords:
- lib compiler option [C#]
- -lib compiler option [C#]
- /lib compiler option [C#]
ms.assetid: b0efcc88-e8aa-4df4-a00b-8bdef70b7673
ms.openlocfilehash: 7db975909f498a0b84e7405a12a8f8ec1e2dd34b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33216858"
---
# <a name="-lib-c-compiler-options"></a><span data-ttu-id="b838a-102">-lib(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="b838a-102">-lib (C# Compiler Options)</span></span>
<span data-ttu-id="b838a-103">**-lib** 옵션은 [-reference(C# 컴파일러 옵션)](../../../csharp/language-reference/compiler-options/reference-compiler-option.md) 옵션을 통해 참조되는 어셈블리의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b838a-103">The **-lib** option specifies the location of assemblies referenced by means of the [-reference (C# Compiler Options)](../../../csharp/language-reference/compiler-options/reference-compiler-option.md) option.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b838a-104">구문</span><span class="sxs-lookup"><span data-stu-id="b838a-104">Syntax</span></span>  
  
```console  
-lib:dir1[,dir2]  
```  
  
## <a name="arguments"></a><span data-ttu-id="b838a-105">인수</span><span class="sxs-lookup"><span data-stu-id="b838a-105">Arguments</span></span>  
 `dir1`  
 <span data-ttu-id="b838a-106">참조된 어셈블리를 현재 작업 디렉터리(컴파일러를 호출하는 디렉터리) 또는 공용 언어 런타임의 시스템 디렉터리에서 찾을 수 없는 경우 컴파일러에서 확인할 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="b838a-106">A directory for the compiler to look in if a referenced assembly is not found in the current working directory (the directory from which you are invoking the compiler) or in the common language runtime's system directory.</span></span>  
  
 `dir2`  
 <span data-ttu-id="b838a-107">어셈블리 참조를 검색할 하나 이상의 추가 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="b838a-107">One or more additional directories to search in for assembly references.</span></span> <span data-ttu-id="b838a-108">이름 사이에 공백 없이 추가 디렉터리 이름을 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="b838a-108">Separate additional directory names with a comma, and without white space between them.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b838a-109">설명</span><span class="sxs-lookup"><span data-stu-id="b838a-109">Remarks</span></span>  
 <span data-ttu-id="b838a-110">컴파일러는 정규화되지 않은 어셈블리 참조를 다음 순서대로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="b838a-110">The compiler searches for assembly references that are not fully qualified in the following order:</span></span>  
  
1.  <span data-ttu-id="b838a-111">현재 작업 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="b838a-111">Current working directory.</span></span> <span data-ttu-id="b838a-112">컴파일러가 호출되는 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="b838a-112">This is the directory from which the compiler is invoked.</span></span>  
  
2.  <span data-ttu-id="b838a-113">공용 언어 런타임 시스템 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="b838a-113">The common language runtime system directory.</span></span>  
  
3.  <span data-ttu-id="b838a-114">**-lib**로 지정된 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="b838a-114">Directories specified by **-lib**.</span></span>  
  
4.  <span data-ttu-id="b838a-115">LIB 환경 변수로 지정된 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="b838a-115">Directories specified by the LIB environment variable.</span></span>  
  
 <span data-ttu-id="b838a-116">어셈블리 참조를 지정하려면 **-reference**를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b838a-116">Use **-reference** to specify an assembly reference.</span></span>  
  
 <span data-ttu-id="b838a-117">**-lib**는 가감되므로 두 번 이상 지정하면 이전 값에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="b838a-117">**-lib** is additive; specifying it more than once appends to any prior values.</span></span>  
  
 <span data-ttu-id="b838a-118">**-lib**를 사용하는 대신 필요한 모든 어셈블리를 작업 디렉터리에 복사할 수도 있습니다. 이렇게 하면 단순히 어셈블리 이름을 **-reference**에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b838a-118">An alternative to using **-lib** is to copy into the working directory any required assemblies; this will allow you to simply pass the assembly name to **-reference**.</span></span> <span data-ttu-id="b838a-119">그런 다음 작업 디렉터리에서 어셈블리를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b838a-119">You can then delete the assemblies from the working directory.</span></span> <span data-ttu-id="b838a-120">종속 어셈블리의 경로는 어셈블리 매니페스트에 지정되지 않으므로 응용 프로그램이 대상 컴퓨터에서 시작될 수 있으며, 전역 어셈블리 캐시에서 어셈블리를 찾아 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b838a-120">Since the path to the dependent assembly is not specified in the assembly manifest, the application can be started on the target computer and will find and use the assembly in the global assembly cache.</span></span>  
  
 <span data-ttu-id="b838a-121">컴파일러가 어셈블리를 참조할 수 있다고 해서 공용 언어 런타임이 런타임에 어셈블리를 찾아 로드할 수 있다는 의미는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b838a-121">Because the compiler can reference the assembly does not imply the common language runtime will be able to find and load the assembly at runtime.</span></span> <span data-ttu-id="b838a-122">런타임에서 참조된 어셈블리를 검색하는 방법에 대한 자세한 내용은 [런타임에서 어셈블리를 찾는 방법](../../../framework/deployment/how-the-runtime-locates-assemblies.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b838a-122">See [How the Runtime Locates Assemblies](../../../framework/deployment/how-the-runtime-locates-assemblies.md) for details on how the runtime searches for referenced assemblies.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="b838a-123">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="b838a-123">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="b838a-124">프로젝트의 **속성 페이지** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b838a-124">Open the project's **Property Pages** dialog box.</span></span>  
  
2.  <span data-ttu-id="b838a-125">**참조 경로** 속성 페이지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b838a-125">Click the **References Path** property page.</span></span>  
  
3.  <span data-ttu-id="b838a-126">목록 상자 내용을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="b838a-126">Modify the contents of the list box.</span></span>  
  
 <span data-ttu-id="b838a-127">이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.ProjectProperties3.ReferencePath%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b838a-127">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.ReferencePath%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b838a-128">예</span><span class="sxs-lookup"><span data-stu-id="b838a-128">Example</span></span>  
 <span data-ttu-id="b838a-129">t2.cs를 컴파일하여 .exe 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b838a-129">Compile t2.cs to create an .exe file.</span></span> <span data-ttu-id="b838a-130">컴파일러는 작업 디렉터리 및 C 드라이브의 루트 디렉터리에서 어셈블리 참조를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b838a-130">The compiler will look in the working directory and in the root directory of the C drive for assembly references.</span></span>  
  
```console  
csc -lib:c:\ -reference:t2.dll t2.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="b838a-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b838a-131">See Also</span></span>  
 [<span data-ttu-id="b838a-132">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="b838a-132">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="b838a-133">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="b838a-133">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
