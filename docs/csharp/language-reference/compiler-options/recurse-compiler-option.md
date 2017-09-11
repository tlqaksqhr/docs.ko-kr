---
title: "-recurse(C# 컴파일러 옵션)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /recurse
dev_langs:
- CSharp
helpviewer_keywords:
- /recurse compiler option [C#]
- recurse compiler option [C#]
- -recurse compiler option [C#]
ms.assetid: 4e8212e5-04e3-45b1-8a42-41bc50e683b0
caps.latest.revision: 12
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
ms.openlocfilehash: 99664f8b32f5f9e5bf491c5bfde2c1649de42dd9
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="recurse-c-compiler-options"></a><span data-ttu-id="3cbaa-102">/recurse(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="3cbaa-102">/recurse (C# Compiler Options)</span></span>
<span data-ttu-id="3cbaa-103">/recurse 옵션을 사용하면 지정된 디렉터리(dir) 또는 프로젝트 디렉터리의 모든 자식 디렉터리에 있는 소스 코드 파일을 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-103">The /recurse option enables you to compile source code files in all child directories of either the specified directory (dir) or of the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cbaa-104">구문</span><span class="sxs-lookup"><span data-stu-id="3cbaa-104">Syntax</span></span>  
  
```console  
/recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="3cbaa-105">인수</span><span class="sxs-lookup"><span data-stu-id="3cbaa-105">Arguments</span></span>  
 <span data-ttu-id="3cbaa-106">`dir`(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="3cbaa-106">`dir` (optional)</span></span>  
 <span data-ttu-id="3cbaa-107">검색을 시작하려는 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="3cbaa-108">지정하지 않으면 프로젝트 디렉터리에서 검색이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-108">If this is not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="3cbaa-109">검색할 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-109">The file(s) to search for.</span></span> <span data-ttu-id="3cbaa-110">와일드카드 문자가 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-110">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3cbaa-111">설명</span><span class="sxs-lookup"><span data-stu-id="3cbaa-111">Remarks</span></span>  
 <span data-ttu-id="3cbaa-112">**/recurse** 옵션을 사용하면 지정된 디렉터리(`dir`) 또는 프로젝트 디렉터리의 모든 자식 디렉터리에 있는 소스 코드 파일을 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-112">The **/recurse** option lets you compile source code files in all child directories of either the specified directory (`dir`) or of the project directory.</span></span>  
  
 <span data-ttu-id="3cbaa-113">파일 이름에 와일드카드를 사용하면 **/recurse**를 사용하지 않고 프로젝트 디렉터리에서 일치하는 모든 파일을 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-113">You can use wildcards in a file name to compile all matching files in the project directory without using **/recurse**.</span></span>  
  
 <span data-ttu-id="3cbaa-114">이 컴파일러 옵션은 Visual Studio에서 사용할 수 없으며 프로그래밍 방식으로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-114">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cbaa-115">예제</span><span class="sxs-lookup"><span data-stu-id="3cbaa-115">Example</span></span>  
 <span data-ttu-id="3cbaa-116">현재 디렉터리의 모든 C# 파일을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-116">Compiles all C# files in the current directory:</span></span>  
  
```console  
csc *.cs  
```  
  
 <span data-ttu-id="3cbaa-117">dir1\dir2 디렉터리와 자식 디렉터리에 있는 모든 C# 파일을 컴파일하여 dir2.dll을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbaa-117">Compiles all of the C# files in the dir1\dir2 directory and any directories below it and generates dir2.dll:</span></span>  
  
```console  
csc /target:library /out:dir2.dll /recurse:dir1\dir2\*.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="3cbaa-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3cbaa-118">See Also</span></span>  
 <span data-ttu-id="3cbaa-119">[C# 컴파일러 옵션](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="3cbaa-119">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="3cbaa-120">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="3cbaa-120">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

