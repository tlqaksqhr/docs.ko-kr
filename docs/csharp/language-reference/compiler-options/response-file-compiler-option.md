---
title: "@(C# 컴파일러 옵션)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '@'
helpviewer_keywords:
- response files, specifying for compilation [C#]
- '@ compiler option'
ms.assetid: dda4fa9f-a02c-400f-8b6a-d58834e13d7f
caps.latest.revision: "9"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d4dc8c81a9afd60add4c2a62be6804a0f6446124
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="-c-compiler-options"></a><span data-ttu-id="49da2-102">@(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="49da2-102">@ (C# Compiler Options)</span></span>
<span data-ttu-id="49da2-103">@ 옵션을 사용하면 컴파일러 옵션과 컴파일할 소스 코드 파일이 포함된 파일을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49da2-103">The @ option lets you specify a file that contains compiler options and source code files to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49da2-104">구문</span><span class="sxs-lookup"><span data-stu-id="49da2-104">Syntax</span></span>  
  
```  
@response_file  
```  
  
## <a name="arguments"></a><span data-ttu-id="49da2-105">인수</span><span class="sxs-lookup"><span data-stu-id="49da2-105">Arguments</span></span>  
 `response_file`  
 <span data-ttu-id="49da2-106">컴파일러 옵션이나 컴파일할 소스 코드 파일이 나열된 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="49da2-106">A file that lists compiler options or source code files to compile.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49da2-107">설명</span><span class="sxs-lookup"><span data-stu-id="49da2-107">Remarks</span></span>  
 <span data-ttu-id="49da2-108">컴파일러 옵션 및 소스 코드 파일은 명령줄에 지정된 것처럼 컴파일러에서 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="49da2-108">The compiler options and source code files will be processed by the compiler just as if they had been specified on the command line.</span></span>  
  
 <span data-ttu-id="49da2-109">컴파일에 지시 파일을 둘 이상 지정하려면 여러 지시 파일 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="49da2-109">To specify more than one response file in a compilation, specify multiple response file options.</span></span> <span data-ttu-id="49da2-110">예:</span><span class="sxs-lookup"><span data-stu-id="49da2-110">For example:</span></span>  
  
```  
@file1.rsp @file2.rsp  
```  
  
 <span data-ttu-id="49da2-111">지시 파일에서 여러 컴파일러 옵션과 소스 코드 파일이 한 줄에 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49da2-111">In a response file, multiple compiler options and source code files can appear on one line.</span></span> <span data-ttu-id="49da2-112">단일 컴파일러 옵션 사양은 한 줄에 표시되어야 합니다(여러 줄에 걸쳐 있을 수 없음).</span><span class="sxs-lookup"><span data-stu-id="49da2-112">A single compiler option specification must appear on one line (cannot span multiple lines).</span></span> <span data-ttu-id="49da2-113">지시 파일은 # 기호로 시작하는 주석을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49da2-113">Response files can have comments that begin with the # symbol.</span></span>  
  
 <span data-ttu-id="49da2-114">지시 파일 내에서 컴파일러 옵션을 지정하는 것은 명령줄에서 해당 명령을 실행하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="49da2-114">Specifying compiler options from within a response file is just like issuing those commands on the command line.</span></span> <span data-ttu-id="49da2-115">자세한 내용은 [명령줄에서 빌드](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="49da2-115">See [Building from the Command Line](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md) for more information.</span></span>  
  
 <span data-ttu-id="49da2-116">명령 옵션이 발견되면 컴파일러에서 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="49da2-116">The compiler processes the command options as they are encountered.</span></span> <span data-ttu-id="49da2-117">따라서, 명령줄 인수는 지시 파일에서 이전에 나열된 옵션을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49da2-117">Therefore, command line arguments can override previously listed options in response files.</span></span> <span data-ttu-id="49da2-118">반대로 지시 파일의 옵션은 명령줄 또는 다른 지시 파일에서 이전에 나열된 옵션을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="49da2-118">Conversely, options in a response file will override options listed previously on the command line or in other response files.</span></span>  
  
 <span data-ttu-id="49da2-119">C#에서는 csc.exe 파일과 동일한 디렉터리에 있는 csc.rsp 파일을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="49da2-119">C# provides the csc.rsp file, which is located in the same directory as the csc.exe file.</span></span> <span data-ttu-id="49da2-120">csc.rsp에 대한 자세한 내용은 [/noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="49da2-120">See [/noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md) for more information on csc.rsp.</span></span>  
  
 <span data-ttu-id="49da2-121">Visual Studio 개발 환경에서는 이 컴파일러 옵션을 설정할 수 없으며 프로그래밍 방식으로 변경할 수도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="49da2-121">This compiler option cannot be set in the Visual Studio development environment, nor can it be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49da2-122">예제</span><span class="sxs-lookup"><span data-stu-id="49da2-122">Example</span></span>  
 <span data-ttu-id="49da2-123">다음은 샘플 지시 파일의 몇 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="49da2-123">The following are a few lines from a sample response file:</span></span>  
  
```console  
# build the first output file  
/target:exe /out:MyExe.exe source1.cs source2.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="49da2-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="49da2-124">See Also</span></span>  
 [<span data-ttu-id="49da2-125">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="49da2-125">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
