---
title: /langversion(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cfe91588471cc8410b25addea8d66a0388c9c5be
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="langversion-visual-basic"></a><span data-ttu-id="5fba9-102">/langversion(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5fba9-102">/langversion (Visual Basic)</span></span>
<span data-ttu-id="5fba9-103">컴파일러가 지정된 된 Visual Basic 언어 버전에 포함 되어 있는 구문만 허용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fba9-103">Causes the compiler to accept only syntax that is included in the specified Visual Basic language version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fba9-104">구문</span><span class="sxs-lookup"><span data-stu-id="5fba9-104">Syntax</span></span>  
  
```  
/langversion:version  
```  
  
## <a name="arguments"></a><span data-ttu-id="5fba9-105">인수</span><span class="sxs-lookup"><span data-stu-id="5fba9-105">Arguments</span></span>  
 `version`  
 <span data-ttu-id="5fba9-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="5fba9-106">Required.</span></span> <span data-ttu-id="5fba9-107">컴파일 중에 사용할 언어 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="5fba9-107">The language version to be used during the compilation.</span></span> <span data-ttu-id="5fba9-108">사용 가능한 값은 `9`, `9.0`, `10`, 및 `10.0`합니다.</span><span class="sxs-lookup"><span data-stu-id="5fba9-108">Accepted values are `9`, `9.0`, `10`, and `10.0`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5fba9-109">설명</span><span class="sxs-lookup"><span data-stu-id="5fba9-109">Remarks</span></span>  
 <span data-ttu-id="5fba9-110">`/langversion` 옵션 컴파일러에서는 허용 되는 구문을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fba9-110">The `/langversion` option specifies what syntax the compiler accepts.</span></span> <span data-ttu-id="5fba9-111">예를 들어 언어 버전이 9.0에 인지를 지정 하면 컴파일러 버전 10.0에만 유효 하 고 이후 구문에 대 한 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fba9-111">For example, if you specify that the language version is 9.0, the compiler generates errors for syntax that is valid only in version 10.0 and later.</span></span>  
  
 <span data-ttu-id="5fba9-112">해당 대상 다른 버전의.NET Framework 응용 프로그램을 개발 하는 경우이 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fba9-112">You can use this option when you develop applications that target different versions of the .NET Framework.</span></span> <span data-ttu-id="5fba9-113">예를 들어.NET Framework 3.5를 대상으로 하는 경우 언어 버전 10.0에서에서 구문을 사용 하는지 확인 하려면이 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fba9-113">For example, if you are targeting .NET Framework 3.5, you could use this option to ensure that you do not use syntax from language version 10.0.</span></span>  
  
 <span data-ttu-id="5fba9-114">설정할 수 있습니다 `/langversion` 직접 명령줄을 사용 해야만 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fba9-114">You can set `/langversion` directly only by using the command line.</span></span> <span data-ttu-id="5fba9-115">자세한 내용은 [특정 대상 .NET Framework 버전 지정](/visualstudio/ide/targeting-a-specific-dotnet-framework-version)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5fba9-115">For more information, see [Targeting a Specific .NET Framework Version](/visualstudio/ide/targeting-a-specific-dotnet-framework-version).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5fba9-116">예제</span><span class="sxs-lookup"><span data-stu-id="5fba9-116">Example</span></span>  
 <span data-ttu-id="5fba9-117">다음 코드에서는 `sample.vb` Visual Basic 9.0에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fba9-117">The following code compiles `sample.vb` for Visual Basic 9.0.</span></span>  
  
```  
vbc /langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="5fba9-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5fba9-118">See Also</span></span>  
 [<span data-ttu-id="5fba9-119">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="5fba9-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="5fba9-120">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="5fba9-120">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="5fba9-121">특정 대상 .NET Framework 버전 지정</span><span class="sxs-lookup"><span data-stu-id="5fba9-121">Targeting a Specific .NET Framework Version</span></span>](/visualstudio/ide/targeting-a-specific-dotnet-framework-version)
