---
title: "Visual Basic 제한 사항 | Microsoft 문서"
ms.custom: 
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
- limits
- limitations, Visual Basic
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
caps.latest.revision: 14
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
ms.openlocfilehash: a3bd551ade2f0c55cd943cfbd353b09dfede4063
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="visual-basic-limitations"></a><span data-ttu-id="1e21e-102">Visual Basic 제한 사항</span><span class="sxs-lookup"><span data-stu-id="1e21e-102">Visual Basic Limitations</span></span>
<span data-ttu-id="1e21e-103">이전 버전의 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 제한 사항이 있었습니다 변수 이름의 길이 등의 코드 모듈 및 모듈 크기에 허용 되는 변수의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1e21e-103">Earlier versions of [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] enforced boundaries in code, such as the length of variable names, the number of variables allowed in modules, and module size.</span></span> <span data-ttu-id="1e21e-104">[!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)], 이러한 제한이 완화 되었습니다, 작성 하 고 코드를 정렬 한 큰 자유를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e21e-104">In [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)], these restrictions have been relaxed, giving you greater freedom in writing and arranging your code.</span></span>  
  
 <span data-ttu-id="1e21e-105">실제 제한은 종속 더 보다 런타임에 메모리에서 컴파일 타임 고려 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1e21e-105">Physical limits are dependent more on run-time memory than on compile-time considerations.</span></span> <span data-ttu-id="1e21e-106">거의 발생할 가능성을 내부는 신중한 프로그래밍 관행을 사용 하 고 큰 응용 프로그램을 여러 클래스 및 모듈을 나누는 경우 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e21e-106">If you use prudent programming practices, and divide large applications into multiple classes and modules, then there is very little chance of encountering an internal [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] limitation.</span></span>  
  
 <span data-ttu-id="1e21e-107">다음은 극단적인 경우에 발생할 수 있는 몇 가지 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e21e-107">The following are some limitations that you might encounter in extreme cases:</span></span>  
  
-   <span data-ttu-id="1e21e-108">**이름 길이입니다.**</span><span class="sxs-lookup"><span data-stu-id="1e21e-108">**Name Length.**</span></span> <span data-ttu-id="1e21e-109">선언 된 모든 프로그래밍 요소 이름에 대 한 문자의 최대 수가입니다.</span><span class="sxs-lookup"><span data-stu-id="1e21e-109">There is a maximum number of characters for the name of every declared programming element.</span></span> <span data-ttu-id="1e21e-110">이 최대 요소 이름을 정규화 하는 경우 전체 정규화 문자열에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e21e-110">This maximum applies to an entire qualification string if the element name is qualified.</span></span> <span data-ttu-id="1e21e-111">참조 [선언 된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1e21e-111">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   <span data-ttu-id="1e21e-112">**줄 길이입니다.**</span><span class="sxs-lookup"><span data-stu-id="1e21e-112">**Line Length.**</span></span> <span data-ttu-id="1e21e-113">소스 코드의 실제 줄에서 65535 자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e21e-113">There is a maximum of 65535 characters in a physical line of source code.</span></span> <span data-ttu-id="1e21e-114">논리적 소스 코드 줄은 줄 연속 문자를 사용 하는 경우에 길어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e21e-114">The logical source code line can be longer if you use line continuation characters.</span></span> <span data-ttu-id="1e21e-115">참조 [하는 방법: 코드에서 문 분리 및 결합](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1e21e-115">See [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span></span>  
  
-   <span data-ttu-id="1e21e-116">**배열 차원입니다.**</span><span class="sxs-lookup"><span data-stu-id="1e21e-116">**Array Dimensions.**</span></span> <span data-ttu-id="1e21e-117">차원 배열에 선언할 수 있는 최대 수가입니다.</span><span class="sxs-lookup"><span data-stu-id="1e21e-117">There is a maximum number of dimensions you can declare for an array.</span></span> <span data-ttu-id="1e21e-118">배열 요소를 지정 하는 데 사용할 수는 인덱스 수를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e21e-118">This limits how many indexes you can use to specify an array element.</span></span> <span data-ttu-id="1e21e-119">참조 [Visual Basic의 차원 배열](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1e21e-119">See [Array Dimensions in Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).</span></span>  
  
-   <span data-ttu-id="1e21e-120">**문자열 길이입니다.**</span><span class="sxs-lookup"><span data-stu-id="1e21e-120">**String Length.**</span></span> <span data-ttu-id="1e21e-121">단일 문자열에 저장할 수는 유니코드 문자의 최대 수가입니다.</span><span class="sxs-lookup"><span data-stu-id="1e21e-121">There is a maximum number of Unicode characters you can store in a single string.</span></span> <span data-ttu-id="1e21e-122">참조 [문자열 데이터 형식](../../../visual-basic/language-reference/data-types/string-data-type.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1e21e-122">See [String Data Type](../../../visual-basic/language-reference/data-types/string-data-type.md).</span></span>  
  
-   <span data-ttu-id="1e21e-123">**환경 문자열 길이입니다.**</span><span class="sxs-lookup"><span data-stu-id="1e21e-123">**Environment String Length.**</span></span> <span data-ttu-id="1e21e-124">최대 명령줄 인수로 사용 되는 모든 환경 문자열에 대 한 32, 768 자의 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e21e-124">There is a maximum of 32768 characters for any environment string used as a command-line argument.</span></span> <span data-ttu-id="1e21e-125">이 모든 플랫폼에 대 한 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e21e-125">This is a limitation on all platforms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e21e-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1e21e-126">See Also</span></span>  
 <span data-ttu-id="1e21e-127">[프로그램 구조 및 코드 규칙](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="1e21e-127">[Program Structure and Code Conventions](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span></span>  
<span data-ttu-id="1e21e-128"> [Visual Basic 명명 규칙](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)</span><span class="sxs-lookup"><span data-stu-id="1e21e-128"> [Visual Basic Naming Conventions](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)</span></span>
