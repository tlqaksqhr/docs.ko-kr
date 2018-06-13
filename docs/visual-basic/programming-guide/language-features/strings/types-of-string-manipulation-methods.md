---
title: Visual Basic의 문자열 조작 메서드 유형
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
ms.openlocfilehash: 11903e067c064f129ecd2df80244edb6741c73be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648696"
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a><span data-ttu-id="fe0f2-102">Visual Basic의 문자열 조작 메서드 유형</span><span class="sxs-lookup"><span data-stu-id="fe0f2-102">Types of String Manipulation Methods in Visual Basic</span></span>
<span data-ttu-id="fe0f2-103">분석 및 나 문자열을 조작 하는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe0f2-103">There are several different ways to analyze and manipulate your strings.</span></span> <span data-ttu-id="fe0f2-104">일부 메서드는 Visual Basic 언어의 일부 이며 다른 사용자에 내재 된는 `String` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0f2-104">Some of the methods are a part of the Visual Basic language, and others are inherent in the `String` class.</span></span>  
  
## <a name="visual-basic-language-and-the-net-framework"></a><span data-ttu-id="fe0f2-105">Visual Basic 언어와.NET Framework</span><span class="sxs-lookup"><span data-stu-id="fe0f2-105">Visual Basic Language and the .NET Framework</span></span>  
 <span data-ttu-id="fe0f2-106">Visual Basic 메서드 언어의 기본 기능으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe0f2-106">Visual Basic methods are used as inherent functions of the language.</span></span> <span data-ttu-id="fe0f2-107">코드에서 자격 증명 없이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe0f2-107">They may be used without qualification in your code.</span></span> <span data-ttu-id="fe0f2-108">다음 예제에서는 Visual Basic 문자열 조작 명령의 일반적인 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fe0f2-108">The following example shows typical use of a Visual Basic string-manipulation command:</span></span>  
  
 [!code-vb[VbVbalrStrings#44](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_1.vb)]  
  
 <span data-ttu-id="fe0f2-109">이 예제는 `Mid` 함수에서 직접 연산을 수행 `aString` 값을 할당 하 고 `bString`합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0f2-109">In this example, the `Mid` function performs a direct operation on `aString` and assigns the value to `bString`.</span></span>  
  
 <span data-ttu-id="fe0f2-110">Visual Basic 문자열 조작 메서드 목록에 대 한 참조 [문자열 조작 요약](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0f2-110">For a list of Visual Basic string manipulation methods, see [String Manipulation Summary](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span></span>  
  
### <a name="shared-methods-and-instance-methods"></a><span data-ttu-id="fe0f2-111">공유 메서드와 인스턴스 메서드</span><span class="sxs-lookup"><span data-stu-id="fe0f2-111">Shared Methods and Instance Methods</span></span>  
 <span data-ttu-id="fe0f2-112">방법을 사용 하 여 문자열을 조작할 수도 있습니다는 `String` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0f2-112">You can also manipulate strings with the methods of the `String` class.</span></span> <span data-ttu-id="fe0f2-113">메서드의 두 가지 `String`: *공유* 메서드 및 *인스턴스* 메서드.</span><span class="sxs-lookup"><span data-stu-id="fe0f2-113">There are two types of methods in `String`: *shared* methods and *instance* methods.</span></span>  
  
#### <a name="shared-methods"></a><span data-ttu-id="fe0f2-114">공유 메서드</span><span class="sxs-lookup"><span data-stu-id="fe0f2-114">Shared Methods</span></span>  
 <span data-ttu-id="fe0f2-115">발생 하는 방법은 공유 메서드는 `String` 클래스 자체와 작동 하도록 해당 클래스의 인스턴스를 필요로 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe0f2-115">A shared method is a method that stems from the `String` class itself and does not require an instance of that class to work.</span></span> <span data-ttu-id="fe0f2-116">이러한 메서드는 클래스의 이름으로 정규화 할 수 있습니다 (`String`)의 인스턴스 대신는 `String` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0f2-116">These methods can be qualified with the name of the class (`String`) rather than with an instance of the `String` class.</span></span> <span data-ttu-id="fe0f2-117">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="fe0f2-117">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#45](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_2.vb)]  
  
 <span data-ttu-id="fe0f2-118">앞의 예제에는 <xref:System.String.Copy%2A?displayProperty=nameWithType> 메서드는 정적 메서드는 식에 대해 동작 하는 것은 되며 결과 값을 할당 `bString`합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0f2-118">In the preceding example, the <xref:System.String.Copy%2A?displayProperty=nameWithType> method is a static method, which acts upon an expression it is given and assigns the resulting value to `bString`.</span></span>  
  
#### <a name="instance-methods"></a><span data-ttu-id="fe0f2-119">인스턴스 메서드</span><span class="sxs-lookup"><span data-stu-id="fe0f2-119">Instance Methods</span></span>  
 <span data-ttu-id="fe0f2-120">인스턴스 메서드와 달리,의 특정 인스턴스에서 형태소 분석 `String` 및 인스턴스 이름으로 한정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0f2-120">Instance methods, by contrast, stem from a particular instance of `String` and must be qualified with the instance name.</span></span> <span data-ttu-id="fe0f2-121">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="fe0f2-121">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#46](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_3.vb)]  
  
 <span data-ttu-id="fe0f2-122">이 예제는 <xref:System.String.Substring%2A?displayProperty=nameWithType> 메서드는 인스턴스 메서드 `String` (즉, `aString`).</span><span class="sxs-lookup"><span data-stu-id="fe0f2-122">In this example, the <xref:System.String.Substring%2A?displayProperty=nameWithType> method is a method of the instance of `String` (that is, `aString`).</span></span> <span data-ttu-id="fe0f2-123">에 작업을 수행할 `aString` 해당 값을 할당 하 고 `bString`합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0f2-123">It performs an operation on `aString` and assigns that value to `bString`.</span></span>  
  
 <span data-ttu-id="fe0f2-124">자세한 내용은 참조에 대 한 설명서는 <xref:System.String> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="fe0f2-124">For more information, see the documentation for the <xref:System.String> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe0f2-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fe0f2-125">See Also</span></span>  
 [<span data-ttu-id="fe0f2-126">Visual Basic의 문자열 소개</span><span class="sxs-lookup"><span data-stu-id="fe0f2-126">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
