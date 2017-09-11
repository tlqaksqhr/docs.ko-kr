---
title: "-fullpaths(C# 컴파일러 옵션)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /fullpaths
dev_langs:
- CSharp
helpviewer_keywords:
- /fullpaths compiler option [C#]
- absolute paths [C#]
- fullpaths compiler option [C#]
- full paths [C#]
- -fullpaths compiler option [C#]
ms.assetid: d2a5f857-cbb2-430b-879c-d648aaf0b8c4
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
ms.openlocfilehash: abd78253c44ae1c90241b2ff2bd236513a846384
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="fullpaths-c-compiler-options"></a><span data-ttu-id="af846-102">/fullpaths(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="af846-102">/fullpaths (C# Compiler Options)</span></span>
<span data-ttu-id="af846-103">**/fullpaths** 옵션을 사용하면 컴파일러에서는 컴파일 오류 및 경고 목록을 만들 때 파일의 전체 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="af846-103">The **/fullpaths** option causes the compiler to specify the full path to the file when listing compilation errors and warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af846-104">구문</span><span class="sxs-lookup"><span data-stu-id="af846-104">Syntax</span></span>  
  
```console  
/fullpaths  
```  
  
## <a name="remarks"></a><span data-ttu-id="af846-105">설명</span><span class="sxs-lookup"><span data-stu-id="af846-105">Remarks</span></span>  
 <span data-ttu-id="af846-106">기본적으로 컴파일 도중 발생하는 오류와 경고에서는 오류가 발견된 파일의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="af846-106">By default, errors and warnings that result from compilation specify the name of the file in which an error was found.</span></span> <span data-ttu-id="af846-107">**/fullpaths** 옵션을 사용하면 컴파일러에서는 파일의 전체 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="af846-107">The **/fullpaths** option causes the compiler to specify the full path to the file.</span></span>  
  
 <span data-ttu-id="af846-108">이 컴파일러 옵션은 Visual Studio에서 사용할 수 없으며 프로그래밍 방식으로 변경할 수도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af846-108">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af846-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af846-109">See Also</span></span>  
 [<span data-ttu-id="af846-110">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="af846-110">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)

