---
title: "변수 &quot;&lt;variablename&gt;&quot; 값이 할당 된 전에 사용 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42104
- BC42104
dev_langs:
- VB
helpviewer_keywords:
- BC42104
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
caps.latest.revision: 10
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
ms.openlocfilehash: dfc924ebbebb8b20654156b8871684dcfad6848a
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="variable-39ltvariablenamegt39-is-used-before-it-has-been-assigned-a-value"></a><span data-ttu-id="d6c64-102">변수 '&lt;variablename&gt;' 값이 할당 된 전에 사용 하는</span><span class="sxs-lookup"><span data-stu-id="d6c64-102">Variable &#39;&lt;variablename&gt;&#39; is used before it has been assigned a value</span></span>
<span data-ttu-id="d6c64-103">변수 '\<variablename > ' 값을 할당 되기 전에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6c64-103">Variable '\<variablename>' is used before it has been assigned a value.</span></span> <span data-ttu-id="d6c64-104">런타임에 null 참조 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6c64-104">A null reference exception could result at run time.</span></span>  
  
 <span data-ttu-id="d6c64-105">응용 프로그램에 어떤 값이 할당 되기 전에 변수를 읽고 해당 코드를 통해 하나 이상의 경로가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6c64-105">An application has at least one possible path through its code that reads a variable before any value is assigned to it.</span></span>  
  
 <span data-ttu-id="d6c64-106">변수에 값이 할당되지 않으면 해당 데이터 형식에 대한 기본값을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c64-106">If a variable has never been assigned a value, it holds the default value for its data type.</span></span> <span data-ttu-id="d6c64-107">참조 데이터 형식, 해당 기본값은 [Nothing](../../../visual-basic/language-reference/nothing.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c64-107">For a reference data type, that default value is [Nothing](../../../visual-basic/language-reference/nothing.md).</span></span> <span data-ttu-id="d6c64-108">값을 가진 참조 변수를 읽는 `Nothing` 발생할 수 있습니다는 <xref:System.NullReferenceException>에 따라서는.</xref:System.NullReferenceException></span><span class="sxs-lookup"><span data-stu-id="d6c64-108">Reading a reference variable that has a value of `Nothing` can cause a <xref:System.NullReferenceException> in some circumstances.</span></span>  
  
 <span data-ttu-id="d6c64-109">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="d6c64-109">By default, this message is a warning.</span></span> <span data-ttu-id="d6c64-110">경고를 숨기 거 나 경고를 오류로 처리에 대 한 자세한 내용은 참조 하십시오. [Visual Basic에서 경고 구성](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c64-110">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="d6c64-111">**오류 ID:** b c&42104;</span><span class="sxs-lookup"><span data-stu-id="d6c64-111">**Error ID:** BC42104</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d6c64-112">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="d6c64-112">To correct this error</span></span>  
  
-   <span data-ttu-id="d6c64-113">제어 흐름 논리를 확인 하 고 변수를 읽는 모든 문으로 제어가 전달 되기 전에 유효한 값에 있는지 확인 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d6c64-113">Check your control flow logic and make sure the variable has a valid value before control passes to any statement that reads it.</span></span>  
  
-   <span data-ttu-id="d6c64-114">변수에 올바른 값을 포함 하는 항상 유지 되도록 한 가지 방법은 선언의 일부로 초기화 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d6c64-114">One way to guarantee that the variable always has a valid value is to initialize it as part of its declaration.</span></span> <span data-ttu-id="d6c64-115">에 "초기화"를 참조 하십시오. [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c64-115">See "Initialization" in [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6c64-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d6c64-116">See Also</span></span>  
 <span data-ttu-id="d6c64-117">[Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md) </span><span class="sxs-lookup"><span data-stu-id="d6c64-117">[Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md) </span></span>  
<span data-ttu-id="d6c64-118"> [변수 선언](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="d6c64-118"> [Variable Declaration](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span></span>  
<span data-ttu-id="d6c64-119"> [변수 문제 해결](../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)</span><span class="sxs-lookup"><span data-stu-id="d6c64-119"> [Troubleshooting Variables](../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)</span></span>
