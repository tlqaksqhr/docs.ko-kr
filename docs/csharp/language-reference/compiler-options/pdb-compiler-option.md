---
title: "-pdb(C# 컴파일러 옵션)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /pdb
dev_langs:
- CSharp
helpviewer_keywords:
- -pdb compiler option [C#]
- pdb compiler option [C#]
- /pdb compiler option [C#]
ms.assetid: e9d0f96a-5b75-45d6-9765-92538dd5f823
caps.latest.revision: 8
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
ms.openlocfilehash: 7c72c12347a9096aeed063b84310356cb07b49c3
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="pdb-c-compiler-options"></a><span data-ttu-id="91c9b-102">/pdb(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="91c9b-102">/pdb (C# Compiler Options)</span></span>
<span data-ttu-id="91c9b-103">**/pdb** 컴파일러 옵션은 디버그 기호 파일의 이름 및 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="91c9b-103">The **/pdb** compiler option specifies the name and location of the debug symbols file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91c9b-104">구문</span><span class="sxs-lookup"><span data-stu-id="91c9b-104">Syntax</span></span>  
  
```console  
/pdb:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="91c9b-105">인수</span><span class="sxs-lookup"><span data-stu-id="91c9b-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="91c9b-106">디버그 기호 파일의 이름 및 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="91c9b-106">The name and location of the debug symbols file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91c9b-107">설명</span><span class="sxs-lookup"><span data-stu-id="91c9b-107">Remarks</span></span>  
 <span data-ttu-id="91c9b-108">[/debug(C# 컴파일러 옵션)](../../../csharp/language-reference/compiler-options/debug-compiler-option.md)를 지정하는 경우 컴파일러는 출력 파일(.exe 또는 .dll)을 만들 디렉터리에 출력 파일의 이름과 동일한 파일 이름으로 .pdb 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="91c9b-108">When you specify [/debug (C# Compiler Options)](../../../csharp/language-reference/compiler-options/debug-compiler-option.md), the compiler will create a .pdb file in the same directory where the compiler will create the output file (.exe or .dll) with a file name that is the same as the name of the output file.</span></span>  
  
 <span data-ttu-id="91c9b-109">**/pdb**를 사용하면 .pdb 파일에 대해 기본값이 아닌 파일 이름과 위치를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91c9b-109">**/pdb** allows you to specify a non-default file name and location for the .pdb file.</span></span>  
  
 <span data-ttu-id="91c9b-110">Visual Studio 개발 환경에서는 이 컴파일러 옵션을 설정할 수 없으며 프로그래밍 방식으로 변경할 수도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="91c9b-110">This compiler option cannot be set in the Visual Studio development environment, nor can it be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91c9b-111">예제</span><span class="sxs-lookup"><span data-stu-id="91c9b-111">Example</span></span>  
 <span data-ttu-id="91c9b-112">`t.cs`를 컴파일하고 tt.pdb라는 .pdb 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="91c9b-112">Compile `t.cs` and create a .pdb file called tt.pdb:</span></span>  
  
```console  
csc /debug /pdb:tt t.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="91c9b-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="91c9b-113">See Also</span></span>  
 <span data-ttu-id="91c9b-114">[C# 컴파일러 옵션](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="91c9b-114">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="91c9b-115">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="91c9b-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

