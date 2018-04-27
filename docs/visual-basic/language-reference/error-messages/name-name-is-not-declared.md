---
title: 이름 &#39; &lt;이름&gt; &#39; 선언 되지 않았습니다
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30451
- vbc30451
helpviewer_keywords:
- BC30451
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 26245952a2dc5341dedba6c497c47773b882b49b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="name-39ltnamegt39-is-not-declared"></a><span data-ttu-id="a3f11-102">이름 &#39; &lt;이름&gt; &#39; 선언 되지 않았습니다</span><span class="sxs-lookup"><span data-stu-id="a3f11-102">Name &#39;&lt;name&gt;&#39; is not declared</span></span>
<span data-ttu-id="a3f11-103">문에서 프로그래밍 요소를 참조 하지만 컴파일러에서 정확한 해당 이름 가진 요소를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a3f11-103">A statement refers to a programming element, but the compiler cannot find an element with that exact name.</span></span>  
  
 <span data-ttu-id="a3f11-104">**오류 ID:** BC30451</span><span class="sxs-lookup"><span data-stu-id="a3f11-104">**Error ID:** BC30451</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a3f11-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="a3f11-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="a3f11-106">참조하는 문에서 이름의 철자를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="a3f11-106">Check the spelling of the name in the referring statement.</span></span> <span data-ttu-id="a3f11-107">Visual Basic은 대/소문자를 구분 하지만 맞춤법 다르면 전혀 다른 이름으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3f11-107">Visual Basic is case-insensitive, but any other variation in the spelling is regarded as a completely different name.</span></span> <span data-ttu-id="a3f11-108">밑줄(`_`)은 이름의 일부이므로 철자의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="a3f11-108">Note that the underscore (`_`) is part of the name and therefore part of the spelling.</span></span>  
  
2.  <span data-ttu-id="a3f11-109">멤버 액세스 연산자 있는지 확인 (`.`) 개체와 해당 멤버 사이입니다.</span><span class="sxs-lookup"><span data-stu-id="a3f11-109">Check that you have the member access operator (`.`) between an object and its member.</span></span> <span data-ttu-id="a3f11-110">예를 들어 <xref:System.Windows.Forms.TextBox> 이라는 `TextBox1`컨트롤이 있는 경우 해당 <xref:System.Windows.Forms.TextBoxBase.Text%2A> 속성에 액세스하려면 `TextBox1.Text`를 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3f11-110">For example, if you have a <xref:System.Windows.Forms.TextBox> control named `TextBox1`, to access its <xref:System.Windows.Forms.TextBoxBase.Text%2A> property you should type `TextBox1.Text`.</span></span> <span data-ttu-id="a3f11-111">`TextBox1Text`를 대신 입력하면 다른 이름이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="a3f11-111">If instead you type `TextBox1Text`, you have created a different name.</span></span>  
  
3.  <span data-ttu-id="a3f11-112">맞춤법이 올바른지 개체 멤버 액세스의 구문이 올바른지 요소가 선언 된 확인.</span><span class="sxs-lookup"><span data-stu-id="a3f11-112">If the spelling is correct and the syntax of any object member access is correct, verify that the element has been declared.</span></span> <span data-ttu-id="a3f11-113">자세한 내용은 참조 [요소 선언](../../../visual-basic/programming-guide/language-features/declared-elements/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a3f11-113">For more information, see [Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/index.md).</span></span>  
  
4.  <span data-ttu-id="a3f11-114">프로그래밍 요소가 선언 된 경우 범위에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3f11-114">If the programming element has been declared, check that it is in scope.</span></span> <span data-ttu-id="a3f11-115">참조 하는 문이 프로그래밍 요소를 선언 하는 영역 바깥에 있는 경우 요소 이름을 정규화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3f11-115">If the referring statement is outside the region declaring the programming element, you might need to qualify the element name.</span></span> <span data-ttu-id="a3f11-116">자세한 내용은 참조 [Visual Basic의 범위](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a3f11-116">For more information, see [Scope in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3f11-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a3f11-117">See Also</span></span>  
 [<span data-ttu-id="a3f11-118">선언 및 상수 요약</span><span class="sxs-lookup"><span data-stu-id="a3f11-118">Declarations and Constants Summary</span></span>](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md)  
 [<span data-ttu-id="a3f11-119">Visual Basic 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="a3f11-119">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [<span data-ttu-id="a3f11-120">선언 요소 이름</span><span class="sxs-lookup"><span data-stu-id="a3f11-120">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="a3f11-121">선언된 요소 참조</span><span class="sxs-lookup"><span data-stu-id="a3f11-121">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
