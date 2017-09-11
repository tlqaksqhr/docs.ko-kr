---
title: "/warnaserror (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 8ed72415a75860b34e37c2bf4fc686cdae37f69e
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="warnaserror-visual-basic"></a><span data-ttu-id="2b572-102">/warnaserror(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2b572-102">/warnaserror (Visual Basic)</span></span>
<span data-ttu-id="2b572-103">컴파일러에서 맨 처음 발견 되는 경고를 오류로 처리 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b572-103">Causes the compiler to treat the first occurrence of a warning as an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b572-104">구문</span><span class="sxs-lookup"><span data-stu-id="2b572-104">Syntax</span></span>  
  
```  
/warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="2b572-105">인수</span><span class="sxs-lookup"><span data-stu-id="2b572-105">Arguments</span></span>  
  
|<span data-ttu-id="2b572-106">용어</span><span class="sxs-lookup"><span data-stu-id="2b572-106">Term</span></span>|<span data-ttu-id="2b572-107">정의</span><span class="sxs-lookup"><span data-stu-id="2b572-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="2b572-108">+ &#124; -</span><span class="sxs-lookup"><span data-stu-id="2b572-108">+ &#124; -</span></span>|<span data-ttu-id="2b572-109">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="2b572-109">Optional.</span></span> <span data-ttu-id="2b572-110">기본적으로 `/warnaserror-` 는 사실; 경고 되지 않더라도 컴파일러에서 출력 파일을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b572-110">By default, `/warnaserror-` is in effect; warnings do not prevent the compiler from producing an output file.</span></span> <span data-ttu-id="2b572-111">`/warnaserror` 동일한 옵션으로 `/warnaserror+`, 경고가 오류로 처리 되도록 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b572-111">The `/warnaserror` option, which is the same as `/warnaserror+`, causes warnings to be treated as errors.</span></span>|  
|`numberList`|<span data-ttu-id="2b572-112">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="2b572-112">Optional.</span></span> <span data-ttu-id="2b572-113">경고 ID의 쉼표로 구분 된 목록에 있는 번호는 `/warnaserror` 옵션은 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b572-113">Comma-delimited list of the warning ID numbers to which the `/warnaserror` option applies.</span></span> <span data-ttu-id="2b572-114">경고 ID를 지정 하는 경우는 `/warnaserror` 옵션은 모든 경고에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b572-114">If no warning ID is specified, the `/warnaserror` option applies to all warnings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b572-115">설명</span><span class="sxs-lookup"><span data-stu-id="2b572-115">Remarks</span></span>  
 <span data-ttu-id="2b572-116">`/warnaserror` 옵션 모든 경고를 오류로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b572-116">The `/warnaserror` option treats all warnings as errors.</span></span> <span data-ttu-id="2b572-117">일반적으로 보고 되는 대로 경고 대신 오류로 보고 되는 모든 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="2b572-117">Any messages that would ordinarily be reported as warnings are instead reported as errors.</span></span> <span data-ttu-id="2b572-118">컴파일러는 이후에 나오는 동일한 경고를 경고로 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="2b572-118">The compiler reports subsequent occurrences of the same warning as warnings.</span></span>  
  
 <span data-ttu-id="2b572-119">기본적으로 `/warnaserror-` 만 정보 제공 용으로 경고를 일으키는 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b572-119">By default, `/warnaserror-` is in effect, which causes the warnings to be informational only.</span></span> <span data-ttu-id="2b572-120">`/warnaserror` 동일한 옵션으로 `/warnaserror+`, 경고가 오류로 처리 되도록 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b572-120">The `/warnaserror` option, which is the same as `/warnaserror+`, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="2b572-121">특정 경고만 오류로 처리를 하려는 경우 오류로 처리할 경고 번호의 쉼표로 구분 된 목록을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b572-121">If you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2b572-122">`/warnaserror` 옵션에 경고가 표시 되는 방식을 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b572-122">The `/warnaserror` option does not control how warnings are displayed.</span></span> <span data-ttu-id="2b572-123">사용 된 [/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) 경고를 비활성화 하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="2b572-123">Use the [/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) option to disable warnings.</span></span>  
  
|<span data-ttu-id="2b572-124">/Warnaserror 모든 경고를 Visual Studio IDE에서 오류로 처리 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="2b572-124">To set /warnaserror to treat all warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="2b572-125">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b572-125">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="2b572-126">에 **프로젝트** 메뉴를 클릭 하 여 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="2b572-126">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="2b572-127">자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b572-127">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="2b572-128">2.  클릭 하 고 **컴파일** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b572-128">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="2b572-129">3.  있는지는 **모든 경고를 해제** 확인란이 선택 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b572-129">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="2b572-130">4.  확인 된 **모든 경고를 오류로 처리** 확인란입니다.</span><span class="sxs-lookup"><span data-stu-id="2b572-130">4.  Check the **Treat all warnings as errors** check box.</span></span>|  
  
|<span data-ttu-id="2b572-131">/Warnaserror 특정 경고 Visual Studio IDE에서 오류를 처리 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="2b572-131">To set /warnaserror to treat specific warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="2b572-132">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b572-132">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="2b572-133">에 **프로젝트** 메뉴를 클릭 하 여 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="2b572-133">On the **Project** menu, click **Properties**.</span></span><br /><span data-ttu-id="2b572-134">2.  클릭 하 고 **컴파일** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b572-134">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="2b572-135">3.  있는지는 **모든 경고를 해제** 확인란이 선택 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b572-135">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="2b572-136">4.  있는지는 **모든 경고를 오류로 처리** 확인란이 선택 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b572-136">4.  Make sure the **Treat all warnings as errors** check box is unchecked.</span></span><br /><span data-ttu-id="2b572-137">5.  선택 **오류** 에서 **알림** 옆에 경고를 오류로 처리 해야 하는 열입니다.</span><span class="sxs-lookup"><span data-stu-id="2b572-137">5.  Select **Error** from the **Notification** column adjacent to the warning that should be treated as an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2b572-138">예제</span><span class="sxs-lookup"><span data-stu-id="2b572-138">Example</span></span>  
 <span data-ttu-id="2b572-139">다음 코드에서는 `In.vb` 를 처음 발견 된 모든 경고에 대 한 오류를 표시 하도록 컴파일러에 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b572-139">The following code compiles `In.vb` and directs the compiler to display an error for the first occurrence of every warning it finds.</span></span>  
  
```  
vbc /warnaserror in.vb  
```  
  
## <a name="example"></a><span data-ttu-id="2b572-140">예제</span><span class="sxs-lookup"><span data-stu-id="2b572-140">Example</span></span>  
 <span data-ttu-id="2b572-141">다음 코드에서는 `T2.vb` 만 사용 하지 않는 지역 변수 (42024)에 대 한 경고를 오류로 취급 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b572-141">The following code compiles `T2.vb` and treats only the warning for unused local variables (42024) as an error.</span></span>  
  
```  
vbc /warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="2b572-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2b572-142">See Also</span></span>  
 <span data-ttu-id="2b572-143">[Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="2b572-143">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="2b572-144"> [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="2b572-144"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="2b572-145"> [Visual Basic에서 경고 구성](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="2b572-145"> [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)</span></span>
