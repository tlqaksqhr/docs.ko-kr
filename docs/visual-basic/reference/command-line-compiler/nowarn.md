---
title: -nowarn
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d2f3f15ef12b24b8baedc9db59e772aa9eb073bc
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="-nowarn"></a><span data-ttu-id="1862a-102">-nowarn</span><span class="sxs-lookup"><span data-stu-id="1862a-102">-nowarn</span></span>
<span data-ttu-id="1862a-103">컴파일러에서 경고를 생성하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1862a-103">Suppresses the compiler's ability to generate warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1862a-104">구문</span><span class="sxs-lookup"><span data-stu-id="1862a-104">Syntax</span></span>  
  
```  
-nowarn[:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="1862a-105">인수</span><span class="sxs-lookup"><span data-stu-id="1862a-105">Arguments</span></span>  
  
|<span data-ttu-id="1862a-106">용어</span><span class="sxs-lookup"><span data-stu-id="1862a-106">Term</span></span>|<span data-ttu-id="1862a-107">정의</span><span class="sxs-lookup"><span data-stu-id="1862a-107">Definition</span></span>|  
|---|---|  
|`numberList`|<span data-ttu-id="1862a-108">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1862a-108">Optional.</span></span> <span data-ttu-id="1862a-109">쉼표로 구분 된 목록 컴파일러 표시 되지 않아야 하는 경고 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="1862a-109">Comma-delimited list of the warning ID numbers that the compiler should suppress.</span></span> <span data-ttu-id="1862a-110">경고 Id를 지정 하지 않은 모든 경고가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1862a-110">If the warning IDs are not specified, all warnings are suppressed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1862a-111">설명</span><span class="sxs-lookup"><span data-stu-id="1862a-111">Remarks</span></span>  
 <span data-ttu-id="1862a-112">`-nowarn` 옵션을 사용 하면 경고가 생성 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1862a-112">The `-nowarn` option causes the compiler to not generate warnings.</span></span> <span data-ttu-id="1862a-113">개별 경고를 표시 하지 않으려면 경고 ID를 제공는 `-nowarn` 콜론 뒤 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="1862a-113">To suppress an individual warning, supply the warning ID to the `-nowarn` option following the colon.</span></span> <span data-ttu-id="1862a-114">여러 경고 번호를 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="1862a-114">Separate multiple warning numbers with commas.</span></span>  
  
 <span data-ttu-id="1862a-115">경고 식별자의 숫자 부분만 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1862a-115">You need to specify only the numeric part of the warning identifier.</span></span> <span data-ttu-id="1862a-116">BC42024, 사용 하지 않는 지역 변수에 대 한 경고를 표시 하지 않으려는 경우 지정 하는 예를 들어 `-nowarn:42024`합니다.</span><span class="sxs-lookup"><span data-stu-id="1862a-116">For example, if you want to suppress BC42024, the warning for unused local variables, specify `-nowarn:42024`.</span></span>  
  
 <span data-ttu-id="1862a-117">경고 ID 번호에 대 한 자세한 내용은 참조 하십시오. [Visual Basic에서 경고 구성](/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.</span><span class="sxs-lookup"><span data-stu-id="1862a-117">For more information on the warning ID numbers, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
|<span data-ttu-id="1862a-118">-Nowarn Visual Studio 통합된 개발 환경에서 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="1862a-118">To set -nowarn in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="1862a-119">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1862a-119">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="1862a-120">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1862a-120">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="1862a-121">2.  **컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1862a-121">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="1862a-122">3.  선택 된 **모든 경고를 해제** 확인란 모든 경고를 비활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="1862a-122">3.  Select the **Disable all warnings** check box to disable all warnings.</span></span><br />     <span data-ttu-id="1862a-123">또는</span><span class="sxs-lookup"><span data-stu-id="1862a-123">- or -</span></span><br />     <span data-ttu-id="1862a-124">특정 경고를 사용 하지 않으려면 **None** 경고 옆의 드롭다운 목록에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="1862a-124">To disable a particular warning, click **None** from the drop-down list adjacent to the warning.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1862a-125">예제</span><span class="sxs-lookup"><span data-stu-id="1862a-125">Example</span></span>  
 <span data-ttu-id="1862a-126">다음 코드에서는 `T2.vb` 모든 경고를 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1862a-126">The following code compiles `T2.vb` and does not display any warnings.</span></span>  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="1862a-127">예제</span><span class="sxs-lookup"><span data-stu-id="1862a-127">Example</span></span>  
 <span data-ttu-id="1862a-128">다음 코드에서는 `T2.vb` 를 사용 하지 않는 지역 변수 (42024)에 대 한 경고를 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1862a-128">The following code compiles `T2.vb` and does not display the warnings for unused local variables (42024).</span></span>  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="1862a-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1862a-129">See Also</span></span>  
 [<span data-ttu-id="1862a-130">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="1862a-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="1862a-131">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="1862a-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="1862a-132">Visual Basic에서 경고 구성</span><span class="sxs-lookup"><span data-stu-id="1862a-132">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
