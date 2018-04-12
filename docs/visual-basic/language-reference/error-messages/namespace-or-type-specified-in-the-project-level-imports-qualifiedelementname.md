---
title: Namespace 또는 프로젝트 수준의 Imports &#39;에 지정 된 형식 &lt;qualifiedelementname&gt;&#39; 대상이 &#39; t public 멤버가 또는 형식을 찾을 수 없음
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40057
- bc40057
helpviewer_keywords:
- BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0d0a164562524af239b3b130f681dbc6eff23814
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="namespace-or-type-specified-in-the-project-level-imports-39ltqualifiedelementnamegt39-doesn39t-contain-any-public-member-or-cannot-be-found"></a><span data-ttu-id="1c7fb-102">Namespace 또는 프로젝트 수준의 Imports &#39;에 지정 된 형식 &lt;qualifiedelementname&gt;&#39; 대상이 &#39; t public 멤버가 또는 형식을 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="1c7fb-102">Namespace or type specified in the project-level Imports &#39;&lt;qualifiedelementname&gt;&#39; doesn&#39;t contain any public member or cannot be found</span></span>
<span data-ttu-id="1c7fb-103">프로젝트 수준의 Imports'에 지정 된 Namespace 또는 형식을\<qualifiedelementname >' public 멤버가 없거나 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7fb-103">Namespace or type specified in the project-level Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found.</span></span> <span data-ttu-id="1c7fb-104">해당 네임 스페이스 또는 형식 정의 되어 있고 하나 이상의 public 멤버를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7fb-104">Make sure the namespace or the type is defined and contains at least one public member.</span></span> <span data-ttu-id="1c7fb-105">별칭 이름에는 다른 별칭 포함 되어 있지 않은지 확인 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1c7fb-105">Make sure the alias name doesn't contain other aliases.</span></span>  
  
 <span data-ttu-id="1c7fb-106">프로젝트의 가져오기 속성 지정 하거나 찾을 수 없거나 정의 하지 않는 포함 하는 요소 `Public` 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="1c7fb-106">An import property of a project specifies a containing element that either cannot be found or does not define any `Public` members.</span></span>  
  
 <span data-ttu-id="1c7fb-107">A *요소가 포함 된* 네임 스페이스, 클래스, 구조체, 모듈, 인터페이스 또는 열거형 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7fb-107">A *containing element* can be a namespace, class, structure, module, interface, or enumeration.</span></span> <span data-ttu-id="1c7fb-108">포함 하는 요소, 변수, 프로시저 또는 다른 요소를 포함 하는 같은 멤버를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7fb-108">The containing element contains members, such as variables, procedures, or other containing elements.</span></span>  
  
 <span data-ttu-id="1c7fb-109">가져오기의 목적은 한정 하지 않고 코드 네임 스페이스 또는 형식 멤버에 액세스를 허용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7fb-109">The purpose of importing is to allow your code to access namespace or type members without having to qualify them.</span></span> <span data-ttu-id="1c7fb-110">프로젝트의 네임 스페이스 또는 형식에 대 한 참조를 추가 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7fb-110">Your project might also need to add a reference to the namespace or type.</span></span> <span data-ttu-id="1c7fb-111">자세한 내용은 "포함 된 요소 가져오기"를 참조 [선언 된 요소에 대 한 참조](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7fb-111">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="1c7fb-112">컴파일러에서 지정 된 포함 하는 요소를 찾을 수 없는 경우을 사용 하는 참조를 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7fb-112">If the compiler cannot find the specified containing element, then it cannot resolve references that use it.</span></span> <span data-ttu-id="1c7fb-113">요소를 찾습니다 있지만 요소는 노출 하지 않는 경우 `Public` 멤버 다음 참조가 없는 성공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7fb-113">If it finds the element but the element does not expose any `Public` members, then no reference can be successful.</span></span> <span data-ttu-id="1c7fb-114">두 경우 모두에서 요소를 가져오는 의미가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7fb-114">In either case it is meaningless to import the element.</span></span>  
  
 <span data-ttu-id="1c7fb-115">사용 된 **프로젝트 디자이너** 가져올 요소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7fb-115">You use the **Project Designer** to specify elements to import.</span></span> <span data-ttu-id="1c7fb-116">사용 하 여는 **가져온 네임 스페이스** 의 섹션은 **참조** 페이지.</span><span class="sxs-lookup"><span data-stu-id="1c7fb-116">Use the **Imported namespaces** section of the **References** page.</span></span> <span data-ttu-id="1c7fb-117">에 가져올 수 있습니다는 **프로젝트 디자이너** 두 번 클릭 하 여는 **My Project** 아이콘 **솔루션 탐색기**합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7fb-117">You can get to the **Project Designer** by double-clicking the **My Project** icon in **Solution Explorer**.</span></span>  
  
 <span data-ttu-id="1c7fb-118">**오류 ID:** BC40057</span><span class="sxs-lookup"><span data-stu-id="1c7fb-118">**Error ID:** BC40057</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1c7fb-119">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="1c7fb-119">To correct this error</span></span>  
  
1.  <span data-ttu-id="1c7fb-120">열기는 **프로젝트 디자이너** 로 전환 하 고는 **참조** 페이지.</span><span class="sxs-lookup"><span data-stu-id="1c7fb-120">Open the **Project Designer** and switch to the **Reference** page.</span></span>  
  
2.  <span data-ttu-id="1c7fb-121">에 **가져온 네임 스페이스** 섹션에서 요소가 포함 된 프로젝트에서 액세스할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7fb-121">In the **Imported namespaces** section, verify that the containing element is accessible from your project.</span></span>  
  
3.  <span data-ttu-id="1c7fb-122">포함 하는 요소가 하나 이상를 통해 노출 된 확인 `Public` 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="1c7fb-122">Verify that the containing element exposes at least one `Public` member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c7fb-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1c7fb-123">See Also</span></span>  
 [<span data-ttu-id="1c7fb-124">프로젝트 디자이너, 참조 페이지(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1c7fb-124">References Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/references-page-project-designer-visual-basic)  
 [<span data-ttu-id="1c7fb-125">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="1c7fb-125">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 [<span data-ttu-id="1c7fb-126">공용</span><span class="sxs-lookup"><span data-stu-id="1c7fb-126">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="1c7fb-127">Visual Basic의 네임 스페이스</span><span class="sxs-lookup"><span data-stu-id="1c7fb-127">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [<span data-ttu-id="1c7fb-128">선언된 요소 참조</span><span class="sxs-lookup"><span data-stu-id="1c7fb-128">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
