---
title: "Visual Basic 명명 규칙"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- names [Visual Basic], Visual Basic rules
- naming conventions
- naming conventions [Visual Basic], Visual Basic
- Visual Basic code, naming conventions
- conventions [Visual Basic], Visual Basic coding
- names [Visual Basic], naming conventions
- naming conventions [Visual Basic], classes
ms.assetid: 164949a4-2a7c-4736-9d82-9c3078e2e56c
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a59139b57568810de80de764388eeffa5f8d7ac9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="visual-basic-naming-conventions"></a><span data-ttu-id="23600-102">Visual Basic 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="23600-102">Visual Basic Naming Conventions</span></span>
<span data-ttu-id="23600-103">Visual Basic 응용 프로그램의 요소 이름을 지정할 때 해당 이름의 첫 번째 문자는 영문자 또는 밑줄 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23600-103">When you name an element in your Visual Basic application, the first character of that name must be an alphabetic character or an underscore.</span></span> <span data-ttu-id="23600-104">단, 이름이 밑줄로 시작 준수 하지 않는 [언어 독립성 및 언어 독립적 구성 요소](https://msdn.microsoft.com/library/12a7a7h3) (CLS).</span><span class="sxs-lookup"><span data-stu-id="23600-104">Note, however, that names beginning with an underscore are not compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS).</span></span>  
  
 <span data-ttu-id="23600-105">다음 제안 사항을 명명에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23600-105">The following suggestions apply to naming.</span></span>  
  
-   <span data-ttu-id="23600-106">각 단어에는 대문자를 사용 하 여 이름 시작 `FindLastRecord` 및 `RedrawMyForm`합니다.</span><span class="sxs-lookup"><span data-stu-id="23600-106">Begin each separate word in a name with a capital letter, as in `FindLastRecord` and `RedrawMyForm`.</span></span>  
  
-   <span data-ttu-id="23600-107">와 같이 동사, 함수 및 메서드 이름은 시작 `InitNameArray` 또는 `CloseDialog`합니다.</span><span class="sxs-lookup"><span data-stu-id="23600-107">Begin function and method names with a verb, as in `InitNameArray` or `CloseDialog`.</span></span>  
  
-   <span data-ttu-id="23600-108">클래스, 구조체, 모듈 및 명사 속성 이름에서와 같이 시작 `EmployeeName` 또는 `CarAccessory`합니다.</span><span class="sxs-lookup"><span data-stu-id="23600-108">Begin class, structure, module, and property names with a noun, as in `EmployeeName` or `CarAccessory`.</span></span>  
  
-   <span data-ttu-id="23600-109">인터페이스 이름을 접두사로 시작 "I"는 명사 또는 명사구를 같은 뒤 `IComponent`, 또는 같은 인터페이스의 동작을 설명 하는 형용사와 `IPersistable`합니다.</span><span class="sxs-lookup"><span data-stu-id="23600-109">Begin interface names with the prefix "I", followed by a noun or a noun phrase, like `IComponent`, or with an adjective describing the interface's behavior, like `IPersistable`.</span></span> <span data-ttu-id="23600-110">약어 혼동 될 수 있기 때문 약어를 제한적으로 사용, 사용 및 밑줄을 사용 하지 않는 합니다.</span><span class="sxs-lookup"><span data-stu-id="23600-110">Do not use the underscore, and use abbreviations sparingly, because abbreviations can cause confusion.</span></span>  
  
-   <span data-ttu-id="23600-111">이벤트 처리기의 이름은 다음 이벤트의 유형을 설명 하는 명사로 시작는 "`EventHandler`"에서처럼: 접미사"`MouseEventHandler`"입니다.</span><span class="sxs-lookup"><span data-stu-id="23600-111">Begin event handler names with a noun describing the type of event followed by the "`EventHandler`" suffix, as in "`MouseEventHandler`".</span></span>  
  
-   <span data-ttu-id="23600-112">이벤트 인수 클래스의 이름에 포함 된 "`EventArgs`" 접미사입니다.</span><span class="sxs-lookup"><span data-stu-id="23600-112">In names of event argument classes, include the "`EventArgs`" suffix.</span></span>  
  
-   <span data-ttu-id="23600-113">이벤트 "before" 또는 "after"의 개념에, 하는 경우의 접미사를 사용 현재 또는 과거 시제에서와 같이 "`ControlAdd`"또는"`ControlAdded`"입니다.</span><span class="sxs-lookup"><span data-stu-id="23600-113">If an event has a concept of "before" or "after," use a suffix in present or past tense, as in "`ControlAdd`" or "`ControlAdded`".</span></span>  
  
-   <span data-ttu-id="23600-114">Long 또는 자주 사용 되는 용어에 대 한 예를 들어, "HTML", "Hypertext Markup Language" 하는 대신, 적절 한 이름 길이 유지 하려면 약어를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="23600-114">For long or frequently used terms, use abbreviations to keep name lengths reasonable, for example, "HTML", instead of "Hypertext Markup Language".</span></span> <span data-ttu-id="23600-115">일반적으로 변수 이름은 32 자 보다 큰 낮은 해상도로 설정 된 모니터에 대 한 읽기 하기 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="23600-115">In general, variable names greater than 32 characters are difficult to read on a monitor set to a low resolution.</span></span> <span data-ttu-id="23600-116">프로그램 약어는 전체 응용 프로그램 전체에서 일치 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="23600-116">Also, make sure your abbreviations are consistent throughout the entire application.</span></span> <span data-ttu-id="23600-117">임의로 전환 "HTML"과 "Hypertext Markup Language" 프로젝트에서 혼란이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23600-117">Randomly switching in a project between "HTML" and "Hypertext Markup Language" can lead to confusion.</span></span>  
  
-   <span data-ttu-id="23600-118">내부 범위에서 외부 범위에서 이름으로 동일한 이름을 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="23600-118">Avoid using names in an inner scope that are the same as names in an outer scope.</span></span> <span data-ttu-id="23600-119">잘못 된 변수에 액세스 하는 경우 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23600-119">Errors can result if the wrong variable is accessed.</span></span> <span data-ttu-id="23600-120">변수와 동일한 이름 가진 키워드 사이 충돌이 발생 하는 경우에 앞에 적절 한 형식 라이브러리 키워드를 식별 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23600-120">If a conflict occurs between a variable and the keyword of the same name, you must identify the keyword by preceding it with the appropriate type library.</span></span> <span data-ttu-id="23600-121">예를 들어, 라는 변수를 설정한 경우 `Date`, 내장 함수를 사용할 수 있습니다 `Date` 함수를 호출 하 여만 <xref:System.DateTime.Date%2A?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="23600-121">For example, if you have a variable called `Date`, you can use the intrinsic `Date` function only by calling <xref:System.DateTime.Date%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23600-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="23600-122">See Also</span></span>  
 [<span data-ttu-id="23600-123">코드에서 요소 이름으로 사용되는 키워드</span><span class="sxs-lookup"><span data-stu-id="23600-123">Keywords as Element Names in Code</span></span>](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)  
 [<span data-ttu-id="23600-124">Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="23600-124">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [<span data-ttu-id="23600-125">선언 요소 이름</span><span class="sxs-lookup"><span data-stu-id="23600-125">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="23600-126">프로그램 구조 및 코드 규칙</span><span class="sxs-lookup"><span data-stu-id="23600-126">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [<span data-ttu-id="23600-127">Visual Basic 언어 참조</span><span class="sxs-lookup"><span data-stu-id="23600-127">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)
