---
title: "-reference(C# 컴파일러 옵션)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /reference
dev_langs:
- CSharp
helpviewer_keywords:
- /r compiler option [C#]
- reference compiler option [C#]
- r compiler option [C#]
- /reference compiler option [C#]
- -r compiler option [C#]
- metadata import [C#]
- public type information [C#]
- -reference compiler option [C#]
ms.assetid: 8d13e5b0-abf6-4c46-bf71-2daf2cd0a6c4
caps.latest.revision: 28
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
ms.openlocfilehash: f057da85202dc5b677af7b9106468b3bc1af6d3f
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="reference-c-compiler-options"></a><span data-ttu-id="81252-102">/reference(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="81252-102">/reference (C# Compiler Options)</span></span>
<span data-ttu-id="81252-103">**/reference** 옵션을 사용하면 컴파일러가 지정된 파일의 [public](../../../csharp/language-reference/keywords/public.md) 형식 정보를 현재 프로젝트로 가져오므로 지정된 어셈블리 파일의 메타데이터를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81252-103">The **/reference** option causes the compiler to import [public](../../../csharp/language-reference/keywords/public.md) type information in the specified file into the current project, thus enabling you to reference metadata from the specified assembly files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81252-104">구문</span><span class="sxs-lookup"><span data-stu-id="81252-104">Syntax</span></span>  
  
```console  
/reference:[alias=]filename  
/reference:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="81252-105">인수</span><span class="sxs-lookup"><span data-stu-id="81252-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="81252-106">어셈블리 매니페스트가 들어 있는 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="81252-106">The name of a file that contains an assembly manifest.</span></span> <span data-ttu-id="81252-107">둘 이상의 파일을 가져오려면 각 파일에 대해 별도 **/reference** 옵션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="81252-107">To import more than one file, include a separate **/reference** option for each file.</span></span>  
  
 `alias`  
 <span data-ttu-id="81252-108">어셈블리에 있는 모든 네임스페이스를 포함하는 루트 네임스페이스를 나타내는 유효한 C# 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="81252-108">A valid C# identifier that will represent a root namespace that will contain all namespaces in the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81252-109">설명</span><span class="sxs-lookup"><span data-stu-id="81252-109">Remarks</span></span>  
 <span data-ttu-id="81252-110">둘 이상의 파일에서 가져오려면 각 파일에 대해 **/reference** 옵션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="81252-110">To import from more than one file, include a **/reference** option for each file.</span></span>  
  
 <span data-ttu-id="81252-111">가져오는 파일에 매니페스트가 포함되어 있어야 합니다. 출력 파일이 [/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) 이외의 [/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) 옵션 중 하나로 컴파일된 상태여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81252-111">The files you import must contain a manifest; the output file must have been compiled with one of the [/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) options other than [/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md).</span></span>  
  
 <span data-ttu-id="81252-112">**/r**은 **/reference**의 약식입니다.</span><span class="sxs-lookup"><span data-stu-id="81252-112">**/r** is the short form of **/reference**.</span></span>  
  
 <span data-ttu-id="81252-113">[/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md)을 사용하여 어셈블리 매니페스트를 포함하지 않는 출력 파일에서 메타데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="81252-113">Use [/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md) to import metadata from an output file that does not contain an assembly manifest.</span></span>  
  
 <span data-ttu-id="81252-114">다른 어셈블리(어셈블리 B)를 참조하는 어셈블리(어셈블리 A)를 참조하면 다음과 같은 경우 어셈블리 B를 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81252-114">If you reference an assembly (Assembly A) that references another assembly (Assembly B), you will need to reference Assembly B if:</span></span>  
  
-   <span data-ttu-id="81252-115">어셈블리 A에서 사용하는 형식이 형식에서 상속되거나 어셈블리 B의 인터페이스를 구현하는 경우</span><span class="sxs-lookup"><span data-stu-id="81252-115">A type you use from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
-   <span data-ttu-id="81252-116">어셈블리 B의 반환 형식이나 매개 변수 형식을 사용하는 필드, 속성, 이벤트 또는 메서드를 호출하는 경우</span><span class="sxs-lookup"><span data-stu-id="81252-116">You invoke a field, property, event, or method that has a return type or parameter type from Assembly B.</span></span>  
  
 <span data-ttu-id="81252-117">[/lib](../../../csharp/language-reference/compiler-options/lib-compiler-option.md)를 사용하여 어셈블리 참조 중 하나 이상이 있는 디렉터리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="81252-117">Use [/lib](../../../csharp/language-reference/compiler-options/lib-compiler-option.md) to specify the directory in which one or more of your assembly references is located.</span></span> <span data-ttu-id="81252-118">**/lib** 항목에서는 컴파일러가 어셈블리를 검색하는 디렉터리에 대해서도 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="81252-118">The **/lib** topic also discusses the directories in which the compiler searches for assemblies.</span></span>  
  
 <span data-ttu-id="81252-119">컴파일러가 모듈이 아니라 어셈블리의 형식을 인식하려면 강제로 형식을 확인하도록 해야 하며, 이 작업을 위해 형식의 인스턴스를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81252-119">In order for the compiler to recognize a type in an assembly, and not in a module, it needs to be forced to resolve the type, which you can do by defining an instance of the type.</span></span> <span data-ttu-id="81252-120">컴파일러를 위해 어셈블리의 형식 이름을 확인하는 다른 방법이 있습니다. 예를 들어 어셈블리의 형식에서 상속하는 경우 컴파일러가 형식 이름을 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="81252-120">There are other ways to resolve type names in an assembly for the compiler: for example, if you inherit from a type in an assembly, the type name will then be recognized by the compiler.</span></span>  
  
 <span data-ttu-id="81252-121">때로는 하나의 어셈블리 내에서 동일한 구성 요소의 두 가지 버전을 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81252-121">Sometimes it is necessary to reference two different versions of the same component from within one assembly.</span></span> <span data-ttu-id="81252-122">이렇게 하려면 각 파일에 대한 **/reference** 스위치의 별칭 하위 옵션을 사용하여 두 파일을 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="81252-122">To do this, use the alias suboption on the **/reference** switch for each file to distinguish between the two files.</span></span> <span data-ttu-id="81252-123">이 별칭은 구성 요소 이름에 대한 한정자로 사용되며, 파일 중 하나의 구성 요소로 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="81252-123">This alias will be used as a qualifier for the component name, and will resolve to the component in one of the files.</span></span>  
  
 <span data-ttu-id="81252-124">자주 사용되는 .NET Framework 어셈블리를 참조하는 csc 지시 파일(.rsp)이 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="81252-124">The csc response (.rsp) file, which references commonly used .NET Framework assemblies, is used by default.</span></span> <span data-ttu-id="81252-125">컴파일러에서 csc.rsp를 사용하지 않도록 하려면 [/noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="81252-125">Use [/noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md) if you do not want the compiler to use csc.rsp.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="81252-126">Visual Studio에서 **참조 추가** 대화 상자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="81252-126">In Visual Studio, use the **Add Reference** dialog box.</span></span> <span data-ttu-id="81252-127">자세한 내용은 [방법: 참조 관리자를 사용하여 참조 추가 또는 제거](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81252-127">For more information, see [How to: Add or Remove References By Using the Reference Manager](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager).</span></span> <span data-ttu-id="81252-128">`/reference`를 사용한 참조 추가와 **참조 추가** 대화 상자를 사용한 참조 추가의 동작이 같도록 하려면 추가하는 어셈블리에 대한 **Interop 형식 포함** 속성을 **False**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="81252-128">To ensure equivalent behavior between adding references by using `/reference` and adding references by using the **Add Reference** dialog box, set the **Embed Interop Types** property to **False** for the assembly that you're adding.</span></span> <span data-ttu-id="81252-129">이 속성의 기본값은 **True**입니다.</span><span class="sxs-lookup"><span data-stu-id="81252-129">**True** is the default value for the property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81252-130">예제</span><span class="sxs-lookup"><span data-stu-id="81252-130">Example</span></span>  
 <span data-ttu-id="81252-131">이 예제에서는 [extern 별칭](../../../csharp/language-reference/keywords/extern-alias.md) 기능을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="81252-131">This example shows how to use the [extern alias](../../../csharp/language-reference/keywords/extern-alias.md) feature.</span></span>  
  
 <span data-ttu-id="81252-132">소스 파일을 컴파일하고, 이전에 컴파일된 `grid.dll` 및 `grid20.dll`에서 메타데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="81252-132">You compile the source file and import metadata from `grid.dll` and `grid20.dll`,which have been compiled previously.</span></span> <span data-ttu-id="81252-133">두 DLL에는 동일한 구성 요소의 서로 다른 버전이 포함되어 있으며, 두 **/reference**를 별칭 옵션과 함께 사용하여 소스 파일을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="81252-133">The two DLLs contain separate versions of the same component, and you use two **/reference** with alias options to compile the source file.</span></span> <span data-ttu-id="81252-134">옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="81252-134">The options look like this:</span></span>  
  
 <span data-ttu-id="81252-135">/reference:GridV1=grid.dll 및 /reference:GridV2=grid20.dll</span><span class="sxs-lookup"><span data-stu-id="81252-135">/reference:GridV1=grid.dll and /reference:GridV2=grid20.dll</span></span>  
  
 <span data-ttu-id="81252-136">이렇게 하면 외부 별칭 "GridV1" 및 "GridV2"가 설정되며, 프로그램에서 extern 문을 통해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="81252-136">This sets up the external aliases "GridV1" and "GridV2," which you use in your program by means of an extern statement:</span></span>  
  
```csharp  
extern alias GridV1;  
extern alias GridV2;  
// Using statements go here.  
```  
  
 <span data-ttu-id="81252-137">이 작업이 완료되면 다음과 같이 컨트롤 이름 앞에 GridV1을 추가하여 grid.dll에서 그리드 컨트롤을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81252-137">Once this is done, you can refer to the grid control from grid.dll by prefixing the control name with GridV1, like this:</span></span>  
  
```csharp  
GridV1::Grid  
```  
  
 <span data-ttu-id="81252-138">또한 다음과 같이 컨트롤 이름 앞에 GridV2를 추가하여 grid20.dll에서 그리드 컨트롤을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81252-138">In addition, you can refer to the grid control from grid20.dll by prefixing the control name with GridV2 like this:</span></span>  
  
```csharp  
GridV2::Grid   
```  
  
## <a name="see-also"></a><span data-ttu-id="81252-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="81252-139">See Also</span></span>  
 <span data-ttu-id="81252-140">[C# 컴파일러 옵션](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="81252-140">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="81252-141">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="81252-141">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

