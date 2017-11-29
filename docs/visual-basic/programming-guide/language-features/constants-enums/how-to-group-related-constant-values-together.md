---
title: "방법: 관련 상수 값 그룹화(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: be57b56047654d6eb3536bb0b8f63eca27decdb7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a><span data-ttu-id="04764-102">방법: 관련 상수 값 그룹화(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="04764-102">How to: Group Related Constant Values Together (Visual Basic)</span></span>
<span data-ttu-id="04764-103">열거형은 서로 관련된 있는 상수를 함께 그룹화 하는 가장 좋은 방법은입니다.</span><span class="sxs-lookup"><span data-stu-id="04764-103">An enumeration is the best way to group related constants together.</span></span> <span data-ttu-id="04764-104">구성 된 열거형을 만들면는 `Enum` 선언 섹션에는 클래스 또는 모듈의 문을 합니다.</span><span class="sxs-lookup"><span data-stu-id="04764-104">You create an enumeration with the `Enum` statement in the declarations section of a class or a module.</span></span> <span data-ttu-id="04764-105">자세한 내용은 참조 [하는 방법: 열거형 선언](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="04764-105">For more information, see [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span></span>  
  
### <a name="to-group-related-constant-values"></a><span data-ttu-id="04764-106">그룹에 관련 상수 값</span><span class="sxs-lookup"><span data-stu-id="04764-106">To group related constant values</span></span>  
  
1.  <span data-ttu-id="04764-107">코드 액세스 수준을 포함 하는 선언을 작성는 `Enum` 키워드 및 유효한 이름이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04764-107">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name.</span></span> <span data-ttu-id="04764-108">이 예제에서는 만듭니다는 `Private` 열거형 `temperatureValues`합니다.</span><span class="sxs-lookup"><span data-stu-id="04764-108">This example creates the `Private` enumeration, `temperatureValues`.</span></span>  
  
     [!code-vb[VbEnumsTask#21](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-group-related-constant-values-together_1.vb)]  
  
2.  <span data-ttu-id="04764-109">열거형에서 상수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="04764-109">Define the constants in the enumeration.</span></span> <span data-ttu-id="04764-110">이 예제에서는 만듭니다는 `Public` 열거형 `temperatureValues` 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="04764-110">This example creates the `Public` enumeration `temperatureValues` and assigns its values.</span></span>  
  
     [!code-vb[VbEnumsTask#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-group-related-constant-values-together_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="04764-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04764-111">See Also</span></span>  
 [<span data-ttu-id="04764-112">열거형 및 이름 한정</span><span class="sxs-lookup"><span data-stu-id="04764-112">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="04764-113">방법: 열거형 멤버 참조</span><span class="sxs-lookup"><span data-stu-id="04764-113">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [<span data-ttu-id="04764-114">열거형을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="04764-114">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [<span data-ttu-id="04764-115">상수 개요</span><span class="sxs-lookup"><span data-stu-id="04764-115">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [<span data-ttu-id="04764-116">상수 및 리터럴 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="04764-116">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [<span data-ttu-id="04764-117">상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="04764-117">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
