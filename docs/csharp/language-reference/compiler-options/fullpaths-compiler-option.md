---
title: "-fullpaths(C# 컴파일러 옵션)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /fullpaths
helpviewer_keywords:
- /fullpaths compiler option [C#]
- absolute paths [C#]
- fullpaths compiler option [C#]
- full paths [C#]
- -fullpaths compiler option [C#]
ms.assetid: d2a5f857-cbb2-430b-879c-d648aaf0b8c4
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b5cc48337c9c85bf5adfaf8fc24a414e6db4ba26
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="-fullpaths-c-compiler-options"></a><span data-ttu-id="d202b-102">-fullpaths(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="d202b-102">-fullpaths (C# Compiler Options)</span></span>
<span data-ttu-id="d202b-103">**-fullpaths** 옵션을 사용하면 컴파일러에서는 컴파일 오류 및 경고 목록을 만들때 파일의 전체 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d202b-103">The **-fullpaths** option causes the compiler to specify the full path to the file when listing compilation errors and warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d202b-104">구문</span><span class="sxs-lookup"><span data-stu-id="d202b-104">Syntax</span></span>  
  
```console  
-fullpaths  
```  
  
## <a name="remarks"></a><span data-ttu-id="d202b-105">설명</span><span class="sxs-lookup"><span data-stu-id="d202b-105">Remarks</span></span>  
 <span data-ttu-id="d202b-106">기본적으로 컴파일 도중 발생하는 오류와 경고에서는 오류가 발견된 파일의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d202b-106">By default, errors and warnings that result from compilation specify the name of the file in which an error was found.</span></span> <span data-ttu-id="d202b-107">**-fullpaths** 옵션을 사용하면 컴파일러에서는 파일의 전체 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d202b-107">The **-fullpaths** option causes the compiler to specify the full path to the file.</span></span>  
  
 <span data-ttu-id="d202b-108">이 컴파일러 옵션은 Visual Studio에서 사용할 수 없으며 프로그래밍 방식으로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d202b-108">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d202b-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d202b-109">See Also</span></span>  
 [<span data-ttu-id="d202b-110">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="d202b-110">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
