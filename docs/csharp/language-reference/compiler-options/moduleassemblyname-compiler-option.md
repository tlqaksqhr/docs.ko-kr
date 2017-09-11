---
title: "-moduleassemblyname(C# 컴파일러 옵션)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /moduleassemblyname
dev_langs:
- CSharp
helpviewer_keywords:
- moduleassemblyname compiler option [C#]
- /moduleassemblyname compiler option [C#]
- .moduleassemblyname compiler option [C#]
ms.assetid: d464d9b9-f18d-423b-95e9-66c7878fd53a
caps.latest.revision: 10
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
ms.openlocfilehash: 2522609aa41ad944b37a8882c1cc56cd5967b330
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="moduleassemblyname-c-compiler-option"></a><span data-ttu-id="f977e-102">/moduleassemblyname(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="f977e-102">/moduleassemblyname (C# Compiler Option)</span></span>
<span data-ttu-id="f977e-103">.netmodule에서 public이 아닌 형식에 액세스할 수 있는 어셈블리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f977e-103">Specifies an assembly whose non-public types a .netmodule can access.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f977e-104">구문</span><span class="sxs-lookup"><span data-stu-id="f977e-104">Syntax</span></span>  
  
```console  
/moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="f977e-105">인수</span><span class="sxs-lookup"><span data-stu-id="f977e-105">Arguments</span></span>  
 `assembly_name`  
 <span data-ttu-id="f977e-106">.netmodule에서 public이 아닌 형식에 액세스할 수 있는 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f977e-106">The name of the assembly whose non-public types the .netmodule can access.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f977e-107">설명</span><span class="sxs-lookup"><span data-stu-id="f977e-107">Remarks</span></span>  
 <span data-ttu-id="f977e-108">**/moduleassemblyname**은 .netmodule을 빌드할 때와 다음 조건이 충족되는 경우 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f977e-108">**/moduleassemblyname** should be used when building a .netmodule, and where the following conditions are true:</span></span>  
  
-   <span data-ttu-id="f977e-109">.netmodule은 기존 어셈블리의 public이 아닌 형식에 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f977e-109">The .netmodule needs access to non-public types in an existing assembly.</span></span>  
  
-   <span data-ttu-id="f977e-110">.netmodule을 빌드할 어셈블리의 이름을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f977e-110">You know the name of the assembly into which the .netmodule will be built.</span></span>  
  
-   <span data-ttu-id="f977e-111">기존 어셈블리는 friend 어셈블리(friend assembly)에 .netmodule을 빌드할 어셈블리에 대한 액세스를 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="f977e-111">The existing assembly has granted friend assembly access to the assembly into which the .netmodule will be built.</span></span>  
  
 <span data-ttu-id="f977e-112">.netmodule 빌드 방법에 대한 자세한 내용은 [/target:module(C# 컴파일러 옵션)](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f977e-112">For more information on building a .netmodule, see [/target:module (C# Compiler Options)](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md).</span></span>  
  
 <span data-ttu-id="f977e-113">friend 어셈블리에 대한 자세한 내용은 [Friend 어셈블리](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f977e-113">For more information on friend assemblies, see [Friend Assemblies](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).</span></span>  
  
 <span data-ttu-id="f977e-114">개발 환경 내에서는 이 옵션을 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f977e-114">This option is not available from within the development environment; it is only available when compiling from the command line.</span></span>  
  
 <span data-ttu-id="f977e-115">이 컴파일러 옵션은 Visual Studio에서 사용할 수 없으며 프로그래밍 방식으로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f977e-115">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f977e-116">예제</span><span class="sxs-lookup"><span data-stu-id="f977e-116">Example</span></span>  
 <span data-ttu-id="f977e-117">이 샘플에서는 private 형식을 사용하여 어셈블리를 빌드하므로 friend 어셈블리가 csman_an_assembly라는 어셈블리에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f977e-117">This sample builds an assembly with a private type, and that gives friend assembly access to an assembly called csman_an_assembly.</span></span>  
  
```csharp  
// moduleassemblyname_1.cs  
// compile with: /target:library  
using System;  
using System.Runtime.CompilerServices;  
  
[assembly:InternalsVisibleTo ("csman_an_assembly")]  
  
class An_Internal_Class   
{  
    public void Test()   
    {   
        Console.WriteLine("An_Internal_Class.Test called");   
    }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="f977e-118">예제</span><span class="sxs-lookup"><span data-stu-id="f977e-118">Example</span></span>  
 <span data-ttu-id="f977e-119">이 샘플은 어셈블리 moduleassemblyname_1.dll에 public이 아닌 형식에 액세스하는 .netmodule을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="f977e-119">This sample builds a .netmodule that accesses a non-public type in the assembly moduleassemblyname_1.dll.</span></span> <span data-ttu-id="f977e-120">이 .netmodule이 csman_an_assembly라는 어셈블리에 빌드될 것임을 알기 때문에 **/moduleassemblyname**을 지정하여 .netmodule이 friend 어셈블리(friend assembly)에 csman_an_assembly에 대한 액세스를 부여한 어셈블리의 public이 아닌 형식에 액세스하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f977e-120">By knowing that this .netmodule will be built into an assembly called csman_an_assembly, we can specify **/moduleassemblyname**, allowing the .netmodule to access non-public types in an assembly that has granted friend assembly access to csman_an_assembly.</span></span>  
  
```csharp  
// moduleassemblyname_2.cs  
// compile with: /moduleassemblyname:csman_an_assembly /target:module /reference:moduleassemblyname_1.dll  
class B {  
    public void Test() {  
        An_Internal_Class x = new An_Internal_Class();  
        x.Test();  
    }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="f977e-121">예제</span><span class="sxs-lookup"><span data-stu-id="f977e-121">Example</span></span>  
 <span data-ttu-id="f977e-122">이 코드 샘플에서는 이전에 빌드한 어셈블리와 .netmodule을 참조하여 csman_an_assembly 어셈블리를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="f977e-122">This code sample builds the assembly csman_an_assembly, referencing the previously-built assembly and .netmodule.</span></span>  
  
```csharp  
// csman_an_assembly.cs  
// compile with: /addmodule:moduleassemblyname_2.netmodule /reference:moduleassemblyname_1.dll  
class A {  
    public static void Main() {  
        B bb = new B();  
        bb.Test();  
    }  
}  
```  
  
 <span data-ttu-id="f977e-123">**An_Internal_Class.Test 호출됨**</span><span class="sxs-lookup"><span data-stu-id="f977e-123">**An_Internal_Class.Test called**</span></span>   
## <a name="see-also"></a><span data-ttu-id="f977e-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f977e-124">See Also</span></span>  
 <span data-ttu-id="f977e-125">[C# 컴파일러 옵션](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="f977e-125">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="f977e-126">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="f977e-126">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

