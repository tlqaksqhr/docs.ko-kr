---
title: -recurse(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /recurse
helpviewer_keywords:
- /recurse compiler option [C#]
- recurse compiler option [C#]
- -recurse compiler option [C#]
ms.assetid: 4e8212e5-04e3-45b1-8a42-41bc50e683b0
ms.openlocfilehash: 7d18fb2b1710e074653e054d003be762d947d1be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33214591"
---
# <a name="-recurse-c-compiler-options"></a><span data-ttu-id="26d03-102">-recurse(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="26d03-102">-recurse (C# Compiler Options)</span></span>
<span data-ttu-id="26d03-103">-recurse 옵션을 사용하면 지정된 디렉터리(dir) 또는 프로젝트 디렉터리의 모든 자식 디렉터리에 있는 소스 코드 파일을 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26d03-103">The -recurse option enables you to compile source code files in all child directories of either the specified directory (dir) or of the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26d03-104">구문</span><span class="sxs-lookup"><span data-stu-id="26d03-104">Syntax</span></span>  
  
```console  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="26d03-105">인수</span><span class="sxs-lookup"><span data-stu-id="26d03-105">Arguments</span></span>  
 <span data-ttu-id="26d03-106">`dir`(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="26d03-106">`dir` (optional)</span></span>  
 <span data-ttu-id="26d03-107">검색을 시작하려는 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="26d03-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="26d03-108">지정하지 않으면 프로젝트 디렉터리에서 검색이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="26d03-108">If this is not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="26d03-109">검색할 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="26d03-109">The file(s) to search for.</span></span> <span data-ttu-id="26d03-110">와일드카드 문자가 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="26d03-110">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26d03-111">설명</span><span class="sxs-lookup"><span data-stu-id="26d03-111">Remarks</span></span>  
 <span data-ttu-id="26d03-112">**-recurse** 옵션을 사용하면 지정된 디렉터리(`dir`) 또는 프로젝트 디렉터리의 모든 자식 디렉터리에 있는 소스 코드 파일을 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26d03-112">The **-recurse** option lets you compile source code files in all child directories of either the specified directory (`dir`) or of the project directory.</span></span>  
  
 <span data-ttu-id="26d03-113">파일 이름에 와일드카드를 사용하면 **-recurse**를 사용하지 않고 프로젝트 디렉터리에서 일치하는 모든 파일을 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26d03-113">You can use wildcards in a file name to compile all matching files in the project directory without using **-recurse**.</span></span>  
  
 <span data-ttu-id="26d03-114">이 컴파일러 옵션은 Visual Studio에서 사용할 수 없으며 프로그래밍 방식으로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="26d03-114">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26d03-115">예</span><span class="sxs-lookup"><span data-stu-id="26d03-115">Example</span></span>  
 <span data-ttu-id="26d03-116">현재 디렉터리의 모든 C# 파일을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="26d03-116">Compiles all C# files in the current directory:</span></span>  
  
```console  
csc *.cs  
```  
  
 <span data-ttu-id="26d03-117">dir1\dir2 디렉터리와 자식 디렉터리에 있는 모든 C# 파일을 컴파일하여 dir2.dll을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="26d03-117">Compiles all of the C# files in the dir1\dir2 directory and any directories below it and generates dir2.dll:</span></span>  
  
```console  
csc -target:library -out:dir2.dll -recurse:dir1\dir2\*.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="26d03-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="26d03-118">See Also</span></span>  
 [<span data-ttu-id="26d03-119">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="26d03-119">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="26d03-120">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="26d03-120">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
