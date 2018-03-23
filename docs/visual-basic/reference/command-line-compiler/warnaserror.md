---
title: -warnaserror (Visual Basic)
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ae8ed68045529e626f2788f854d8e6a6933e7e2
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="-warnaserror-visual-basic"></a><span data-ttu-id="483de-102">-warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="483de-102">-warnaserror (Visual Basic)</span></span>
<span data-ttu-id="483de-103">컴파일러에서 맨 처음 발견 되는 경고를 오류로 처리 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="483de-103">Causes the compiler to treat the first occurrence of a warning as an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="483de-104">구문</span><span class="sxs-lookup"><span data-stu-id="483de-104">Syntax</span></span>  
  
```  
-warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="483de-105">인수</span><span class="sxs-lookup"><span data-stu-id="483de-105">Arguments</span></span>  
  
|<span data-ttu-id="483de-106">용어</span><span class="sxs-lookup"><span data-stu-id="483de-106">Term</span></span>|<span data-ttu-id="483de-107">정의</span><span class="sxs-lookup"><span data-stu-id="483de-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="483de-108">+ &#124; -</span><span class="sxs-lookup"><span data-stu-id="483de-108">+ &#124; -</span></span>|<span data-ttu-id="483de-109">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="483de-109">Optional.</span></span> <span data-ttu-id="483de-110">기본적으로 `-warnaserror-` 됩니다. 경고 되지 않더라도 컴파일러에서 출력 파일을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="483de-110">By default, `-warnaserror-` is in effect; warnings do not prevent the compiler from producing an output file.</span></span> <span data-ttu-id="483de-111">`-warnaserror` 동일한 옵션으로 `-warnaserror+`, 경고를 오류로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="483de-111">The `-warnaserror` option, which is the same as `-warnaserror+`, causes warnings to be treated as errors.</span></span>|  
|`numberList`|<span data-ttu-id="483de-112">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="483de-112">Optional.</span></span> <span data-ttu-id="483de-113">경고 ID의 쉼표로 구분 된 목록에 있는 번호는 `-warnaserror` 옵션은 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="483de-113">Comma-delimited list of the warning ID numbers to which the `-warnaserror` option applies.</span></span> <span data-ttu-id="483de-114">경고 ID를 지정 하는 경우는 `-warnaserror` 옵션은 모든 경고에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="483de-114">If no warning ID is specified, the `-warnaserror` option applies to all warnings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="483de-115">설명</span><span class="sxs-lookup"><span data-stu-id="483de-115">Remarks</span></span>  
 <span data-ttu-id="483de-116">`-warnaserror` 모든 경고를 오류로 처리 하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="483de-116">The `-warnaserror` option treats all warnings as errors.</span></span> <span data-ttu-id="483de-117">일반적으로 보고 되는 경고는 대신 오류로 보고 되는 모든 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="483de-117">Any messages that would ordinarily be reported as warnings are instead reported as errors.</span></span> <span data-ttu-id="483de-118">컴파일러 경고로 동일한 경고를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="483de-118">The compiler reports subsequent occurrences of the same warning as warnings.</span></span>  
  
 <span data-ttu-id="483de-119">기본적으로 `-warnaserror-` 이 적용 되는 정보 경고를 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="483de-119">By default, `-warnaserror-` is in effect, which causes the warnings to be informational only.</span></span> <span data-ttu-id="483de-120">`-warnaserror` 동일한 옵션으로 `-warnaserror+`, 경고를 오류로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="483de-120">The `-warnaserror` option, which is the same as `-warnaserror+`, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="483de-121">특정 경고만 경고가 오류로 처리 하려는 경우를 오류로 처리할 경고 번호를 쉼표로 구분 된 목록이 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="483de-121">If you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="483de-122">`-warnaserror` 옵션에 경고가 표시 되는 방식을 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="483de-122">The `-warnaserror` option does not control how warnings are displayed.</span></span> <span data-ttu-id="483de-123">사용 하 여는 [-nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) 경고를 사용 하지 않도록 설정 하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="483de-123">Use the [-nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) option to disable warnings.</span></span>  
  
|<span data-ttu-id="483de-124">-Warnaserror 모든 경고를 Visual Studio IDE에서 오류로 처리 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="483de-124">To set -warnaserror to treat all warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="483de-125">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="483de-125">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="483de-126">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="483de-126">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="483de-127">2.  **컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="483de-127">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="483de-128">3.  있는지 확인은 **모든 경고를 해제** 확인란이 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="483de-128">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="483de-129">4.  확인 된 **모든 경고를 오류로 처리** 확인란 합니다.</span><span class="sxs-lookup"><span data-stu-id="483de-129">4.  Check the **Treat all warnings as errors** check box.</span></span>|  
  
|<span data-ttu-id="483de-130">-Warnaserror 특정 경고 Visual Studio IDE에서 오류를 처리 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="483de-130">To set -warnaserror to treat specific warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="483de-131">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="483de-131">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="483de-132">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="483de-132">On the **Project** menu, click **Properties**.</span></span><br /><span data-ttu-id="483de-133">2.  **컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="483de-133">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="483de-134">3.  있는지 확인은 **모든 경고를 해제** 확인란이 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="483de-134">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="483de-135">4.  있는지 확인은 **모든 경고를 오류로 처리** 확인란이 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="483de-135">4.  Make sure the **Treat all warnings as errors** check box is unchecked.</span></span><br /><span data-ttu-id="483de-136">5.  선택 **오류** 에서 **알림** 열 옆에 경고를 오류로 처리할지를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="483de-136">5.  Select **Error** from the **Notification** column adjacent to the warning that should be treated as an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="483de-137">예제</span><span class="sxs-lookup"><span data-stu-id="483de-137">Example</span></span>  
 <span data-ttu-id="483de-138">다음 코드에서는 `In.vb` 경고가의 첫 번째 오류를 표시 하려면 컴파일러를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="483de-138">The following code compiles `In.vb` and directs the compiler to display an error for the first occurrence of every warning it finds.</span></span>  
  
```console
vbc -warnaserror in.vb  
```  
  
## <a name="example"></a><span data-ttu-id="483de-139">예제</span><span class="sxs-lookup"><span data-stu-id="483de-139">Example</span></span>  
 <span data-ttu-id="483de-140">다음 코드에서는 `T2.vb` 만 사용 하지 않는 지역 변수 (42024)에 대 한 경고를 오류로 취급 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="483de-140">The following code compiles `T2.vb` and treats only the warning for unused local variables (42024) as an error.</span></span>  
  
```console
vbc -warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="483de-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="483de-141">See Also</span></span>  
 [<span data-ttu-id="483de-142">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="483de-142">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="483de-143">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="483de-143">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="483de-144">Visual Basic에서 경고 구성</span><span class="sxs-lookup"><span data-stu-id="483de-144">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
