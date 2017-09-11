---
title: "-addmodule(C# 컴파일러 옵션)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /addmodule
dev_langs:
- CSharp
helpviewer_keywords:
- /addmodule compiler option [C#]
- -addmodule compiler option [C#]
- addmodule compiler option [C#]
ms.assetid: ed604546-0dc2-4bd4-9a3e-610a8d973e58
caps.latest.revision: 13
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 79fdad111b1f059e6a3b00e393ea2474f71db947
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="addmodule-c-compiler-options"></a><span data-ttu-id="88a0d-102">/addmodule(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="88a0d-102">/addmodule (C# Compiler Options)</span></span>
<span data-ttu-id="88a0d-103">이 옵션은 target:module 스위치로 만들어진 모듈을 현재 컴파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="88a0d-103">This option adds a module that was created with the target:module switch to the current compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88a0d-104">구문</span><span class="sxs-lookup"><span data-stu-id="88a0d-104">Syntax</span></span>  
  
```console  
/addmodule:file[;file2]  
```  
  
## <a name="arguments"></a><span data-ttu-id="88a0d-105">인수</span><span class="sxs-lookup"><span data-stu-id="88a0d-105">Arguments</span></span>  
 <span data-ttu-id="88a0d-106">`file`, `file2`</span><span class="sxs-lookup"><span data-stu-id="88a0d-106">`file`, `file2`</span></span>  
 <span data-ttu-id="88a0d-107">메타데이터를 포함하는 출력 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="88a0d-107">An output file that contains metadata.</span></span> <span data-ttu-id="88a0d-108">파일에 어셈블리 매니페스트를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88a0d-108">The file cannot contain an assembly manifest.</span></span> <span data-ttu-id="88a0d-109">둘 이상의 파일을 가져오려면 파일 이름을 쉼표 또는 세미콜론으로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="88a0d-109">To import more than one file, separate file names with either a comma or a semicolon.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="88a0d-110">설명</span><span class="sxs-lookup"><span data-stu-id="88a0d-110">Remarks</span></span>  
 <span data-ttu-id="88a0d-111">**/addmodule**을 사용하여 추가된 모든 모듈은 런타임에 출력 파일과 동일한 디렉터리에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88a0d-111">All modules added with **/addmodule** must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="88a0d-112">즉, 컴파일 시간에 임의 디렉터리에 있는 모듈을 지정할 수 있지만 런타임에 모듈이 응용 프로그램 디렉터리에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88a0d-112">That is, you can specify a module in any directory at compile time but the module must be in the application directory at run time.</span></span> <span data-ttu-id="88a0d-113">런타임에 모듈이 응용 프로그램 디렉터리에 없는 경우 <xref:System.TypeLoadException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="88a0d-113">If the module is not in the application directory at run time, you will get a <xref:System.TypeLoadException>.</span></span>  
  
 <span data-ttu-id="88a0d-114">`file`에 어셈블리를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88a0d-114">`file` cannot contain an assembly.</span></span> <span data-ttu-id="88a0d-115">예를 들어 [/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md)을 사용하여 출력 파일이 만들어진 경우 **/addmodule**을 사용하여 해당 메타데이터를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88a0d-115">For example, if the output file was created with [/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), its metadata can be imported with **/addmodule**.</span></span>  
  
 <span data-ttu-id="88a0d-116">출력 파일이 **/target:module** 이외의 **/target** 옵션으로 만들어진 경우 **/addmodule**을 사용하여 해당 메타데이터를 가져올 수 없지만 [/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)를 사용하여 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88a0d-116">If the output file was created with a **/target** option other than **/target:module**, its metadata cannot be imported with **/addmodule** but can be imported with [/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md).</span></span>  
  
 <span data-ttu-id="88a0d-117">이 컴파일러 옵션은 Visual Studio에서 사용할 수 없습니다. 프로젝트에서 모듈을 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88a0d-117">This compiler option is unavailable in Visual Studio; a project cannot reference a module.</span></span> <span data-ttu-id="88a0d-118">또한 이 컴파일러 옵션은 프로그래밍 방식으로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88a0d-118">In addition, this compiler option cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88a0d-119">예제</span><span class="sxs-lookup"><span data-stu-id="88a0d-119">Example</span></span>  
 <span data-ttu-id="88a0d-120">소스 파일 `input.cs`를 컴파일하고 `metad1.netmodule` 및 `metad2.netmodule`의 메타데이터를 추가하여 `out.exe`를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="88a0d-120">Compile source file `input.cs` and add metadata from `metad1.netmodule` and `metad2.netmodule` to produce `out.exe`:</span></span>  
  
```console  
csc /addmodule:metad1.netmodule;metad2.netmodule /out:out.exe input.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="88a0d-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="88a0d-121">See Also</span></span>  
 <span data-ttu-id="88a0d-122">[C# 컴파일러 옵션](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="88a0d-122">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 <span data-ttu-id="88a0d-123">[프로젝트 및 솔루션 속성 관리](/visualstudio/ide/managing-project-and-solution-properties) </span><span class="sxs-lookup"><span data-stu-id="88a0d-123">[Managing Project and Solution Properties](/visualstudio/ide/managing-project-and-solution-properties) </span></span>  
 <span data-ttu-id="88a0d-124">[다중 파일 어셈블리](../../../framework/app-domains/multifile-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="88a0d-124">[Multifile Assemblies](../../../framework/app-domains/multifile-assemblies.md) </span></span>  
 [<span data-ttu-id="88a0d-125">방법: 다중 파일 어셈블리 빌드</span><span class="sxs-lookup"><span data-stu-id="88a0d-125">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)

