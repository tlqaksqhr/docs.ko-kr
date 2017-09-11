---
title: "/nowarn | Microsoft 문서"
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
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
caps.latest.revision: 15
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
ms.openlocfilehash: 308bf24c2a397a75f36b97062dde7380b90c8994
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="nowarn"></a><span data-ttu-id="218a1-102">/nowarn</span><span class="sxs-lookup"><span data-stu-id="218a1-102">/nowarn</span></span>
<span data-ttu-id="218a1-103">컴파일러에서 경고를 생성하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="218a1-103">Suppresses the compiler's ability to generate warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="218a1-104">구문</span><span class="sxs-lookup"><span data-stu-id="218a1-104">Syntax</span></span>  
  
```  
/nowarn[:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="218a1-105">인수</span><span class="sxs-lookup"><span data-stu-id="218a1-105">Arguments</span></span>  
  
|<span data-ttu-id="218a1-106">용어</span><span class="sxs-lookup"><span data-stu-id="218a1-106">Term</span></span>|<span data-ttu-id="218a1-107">정의</span><span class="sxs-lookup"><span data-stu-id="218a1-107">Definition</span></span>|  
|---|---|  
|`numberList`|<span data-ttu-id="218a1-108">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="218a1-108">Optional.</span></span> <span data-ttu-id="218a1-109">쉼표로 구분 된 목록 컴파일러를 표시 하지 않아야 하는 경고 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="218a1-109">Comma-delimited list of the warning ID numbers that the compiler should suppress.</span></span> <span data-ttu-id="218a1-110">경고 Id를 지정 하지 않은 모든 경고가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="218a1-110">If the warning IDs are not specified, all warnings are suppressed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="218a1-111">주의</span><span class="sxs-lookup"><span data-stu-id="218a1-111">Remarks</span></span>  
 <span data-ttu-id="218a1-112">`/nowarn` 옵션을 사용 하면 경고가 생성 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="218a1-112">The `/nowarn` option causes the compiler to not generate warnings.</span></span> <span data-ttu-id="218a1-113">개별 경고를 표시 하지 않으려면 경고 ID를 제공 된 `/nowarn` 콜론 뒤 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="218a1-113">To suppress an individual warning, supply the warning ID to the `/nowarn` option following the colon.</span></span> <span data-ttu-id="218a1-114">여러 경고 번호를 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="218a1-114">Separate multiple warning numbers with commas.</span></span>  
  
 <span data-ttu-id="218a1-115">경고 식별자의 숫자 부분만 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="218a1-115">You need to specify only the numeric part of the warning identifier.</span></span> <span data-ttu-id="218a1-116">B c&42024;를 사용 하지 않는 지역 변수에 대 한 경고를 표시 하지 않으려는 경우 지정 하는 예를 들어 `/nowarn:42024`합니다.</span><span class="sxs-lookup"><span data-stu-id="218a1-116">For example, if you want to suppress BC42024, the warning for unused local variables, specify `/nowarn:42024`.</span></span>  
  
 <span data-ttu-id="218a1-117">경고 ID 번호에 대 한 자세한 내용은 참조 하십시오. [Visual Basic에서 경고 구성](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.</span><span class="sxs-lookup"><span data-stu-id="218a1-117">For more information on the warning ID numbers, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
|<span data-ttu-id="218a1-118">Visual Studio에서 /nowarn을 설정 하려면 통합 개발 환경</span><span class="sxs-lookup"><span data-stu-id="218a1-118">To set /nowarn in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="218a1-119">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="218a1-119">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="218a1-120">에 **프로젝트** 메뉴를 클릭 하 여 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="218a1-120">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="218a1-121">자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="218a1-121">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="218a1-122">2.  클릭 하 고 **컴파일** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="218a1-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="218a1-123">3.  선택은 **모든 경고를 해제** 확인란 모든 경고를 비활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="218a1-123">3.  Select the **Disable all warnings** check box to disable all warnings.</span></span><br />     <span data-ttu-id="218a1-124">또는</span><span class="sxs-lookup"><span data-stu-id="218a1-124">- or -</span></span><br />     <span data-ttu-id="218a1-125">특정 경고를 비활성화 하려면 클릭 **None** 경고 옆의 드롭다운 목록에서.</span><span class="sxs-lookup"><span data-stu-id="218a1-125">To disable a particular warning, click **None** from the drop-down list adjacent to the warning.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="218a1-126">예제</span><span class="sxs-lookup"><span data-stu-id="218a1-126">Example</span></span>  
 <span data-ttu-id="218a1-127">다음 코드에서는 `T2.vb` 모든 경고를 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="218a1-127">The following code compiles `T2.vb` and does not display any warnings.</span></span>  
  
```  
vbc /nowarn t2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="218a1-128">예제</span><span class="sxs-lookup"><span data-stu-id="218a1-128">Example</span></span>  
 <span data-ttu-id="218a1-129">다음 코드에서는 `T2.vb` 를 사용 하지 않는 지역 변수 (42024)에 대 한 경고를 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="218a1-129">The following code compiles `T2.vb` and does not display the warnings for unused local variables (42024).</span></span>  
  
```  
vbc /nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="218a1-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="218a1-130">See Also</span></span>  
 <span data-ttu-id="218a1-131">[Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="218a1-131">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="218a1-132"> [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="218a1-132"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="218a1-133"> [Visual Basic에서 경고 구성](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="218a1-133"> [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)</span></span>
