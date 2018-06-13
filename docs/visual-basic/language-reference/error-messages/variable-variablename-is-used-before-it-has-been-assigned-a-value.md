---
title: 변수 &#39; &lt;variablename&gt; &#39; 값이 할당 되기 전에 사용 되었습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc42104
- BC42104
helpviewer_keywords:
- BC42104
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
ms.openlocfilehash: d314f952bd6e11adaac642ba63ed292f48cda805
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33596921"
---
# <a name="variable-39ltvariablenamegt39-is-used-before-it-has-been-assigned-a-value"></a><span data-ttu-id="5df8a-102">변수 &#39; &lt;variablename&gt; &#39; 값이 할당 되기 전에 사용 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5df8a-102">Variable &#39;&lt;variablename&gt;&#39; is used before it has been assigned a value</span></span>
<span data-ttu-id="5df8a-103">변수 '\<variablename >' 값이 할당 되기 전에 사용 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5df8a-103">Variable '\<variablename>' is used before it has been assigned a value.</span></span> <span data-ttu-id="5df8a-104">런타임에 null 참조 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5df8a-104">A null reference exception could result at run time.</span></span>  
  
 <span data-ttu-id="5df8a-105">응용 프로그램에 코드 값을 할당 하기 전에 변수를 읽는 통해 하나 이상의 경로가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5df8a-105">An application has at least one possible path through its code that reads a variable before any value is assigned to it.</span></span>  
  
 <span data-ttu-id="5df8a-106">변수에 값이 할당되지 않으면 해당 데이터 형식에 대한 기본값을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="5df8a-106">If a variable has never been assigned a value, it holds the default value for its data type.</span></span> <span data-ttu-id="5df8a-107">참조 데이터 형식에 대 한 해당 기본값은 [Nothing](../../../visual-basic/language-reference/nothing.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5df8a-107">For a reference data type, that default value is [Nothing](../../../visual-basic/language-reference/nothing.md).</span></span> <span data-ttu-id="5df8a-108">값이 `Nothing` 인 참조 변수를 읽으면 일부 환경에서 <xref:System.NullReferenceException> 이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5df8a-108">Reading a reference variable that has a value of `Nothing` can cause a <xref:System.NullReferenceException> in some circumstances.</span></span>  
  
 <span data-ttu-id="5df8a-109">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="5df8a-109">By default, this message is a warning.</span></span> <span data-ttu-id="5df8a-110">경고를 숨기 거 나 경고를 오류로 처리 하는 방법에 대 한 자세한 내용은 참조 하십시오. [Visual Basic에서 경고 구성](/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.</span><span class="sxs-lookup"><span data-stu-id="5df8a-110">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="5df8a-111">**오류 ID:** b c 42104</span><span class="sxs-lookup"><span data-stu-id="5df8a-111">**Error ID:** BC42104</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5df8a-112">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="5df8a-112">To correct this error</span></span>  
  
-   <span data-ttu-id="5df8a-113">제어 흐름 논리를 읽어온 문에 컨트롤이 전달 되기 전에 변수가 유효한 값이 있는지 확인 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5df8a-113">Check your control flow logic and make sure the variable has a valid value before control passes to any statement that reads it.</span></span>  
  
-   <span data-ttu-id="5df8a-114">변수 값이 올바른 값을 항상에 있는지를 보장 하기 위해 한 가지 방법은 해당 선언의 일부로 초기화 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5df8a-114">One way to guarantee that the variable always has a valid value is to initialize it as part of its declaration.</span></span> <span data-ttu-id="5df8a-115">"초기화"를 참조 하십시오. [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5df8a-115">See "Initialization" in [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5df8a-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5df8a-116">See Also</span></span>  
 [<span data-ttu-id="5df8a-117">Dim 문</span><span class="sxs-lookup"><span data-stu-id="5df8a-117">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="5df8a-118">변수 선언</span><span class="sxs-lookup"><span data-stu-id="5df8a-118">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="5df8a-119">변수 문제 해결</span><span class="sxs-lookup"><span data-stu-id="5df8a-119">Troubleshooting Variables</span></span>](../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)
