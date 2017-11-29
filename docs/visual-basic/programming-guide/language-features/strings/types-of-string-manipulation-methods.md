---
title: "Visual Basic의 문자열 조작 메서드 유형"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b437be4a6f4a0cc9d5a4d21291a80c9cb8fffcd3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a><span data-ttu-id="7e055-102">Visual Basic의 문자열 조작 메서드 유형</span><span class="sxs-lookup"><span data-stu-id="7e055-102">Types of String Manipulation Methods in Visual Basic</span></span>
<span data-ttu-id="7e055-103">분석 및 나 문자열을 조작 하는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e055-103">There are several different ways to analyze and manipulate your strings.</span></span> <span data-ttu-id="7e055-104">에 포함 된 일부 메서드는 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 언어 및 다른 사용자에 내재 된는 `String` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="7e055-104">Some of the methods are a part of the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] language, and others are inherent in the `String` class.</span></span>  
  
## <a name="visual-basic-language-and-the-net-framework"></a><span data-ttu-id="7e055-105">Visual Basic 언어와.NET Framework</span><span class="sxs-lookup"><span data-stu-id="7e055-105">Visual Basic Language and the .NET Framework</span></span>  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="7e055-106">메서드는 언어의 기본 기능으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e055-106"> methods are used as inherent functions of the language.</span></span> <span data-ttu-id="7e055-107">코드에서 자격 증명 없이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e055-107">They may be used without qualification in your code.</span></span> <span data-ttu-id="7e055-108">다음 예제에서는의 일반적인 용도 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 문자열 조작 명령:</span><span class="sxs-lookup"><span data-stu-id="7e055-108">The following example shows typical use of a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] string-manipulation command:</span></span>  
  
 [!code-vb[VbVbalrStrings#44](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_1.vb)]  
  
 <span data-ttu-id="7e055-109">이 예제는 `Mid` 함수에서 직접 연산을 수행 `aString` 값을 할당 하 고 `bString`합니다.</span><span class="sxs-lookup"><span data-stu-id="7e055-109">In this example, the `Mid` function performs a direct operation on `aString` and assigns the value to `bString`.</span></span>  
  
 <span data-ttu-id="7e055-110">Visual Basic 문자열 조작 메서드 목록에 대 한 참조 [문자열 조작 요약](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7e055-110">For a list of Visual Basic string manipulation methods, see [String Manipulation Summary](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span></span>  
  
### <a name="shared-methods-and-instance-methods"></a><span data-ttu-id="7e055-111">공유 메서드와 인스턴스 메서드</span><span class="sxs-lookup"><span data-stu-id="7e055-111">Shared Methods and Instance Methods</span></span>  
 <span data-ttu-id="7e055-112">방법을 사용 하 여 문자열을 조작할 수도 있습니다는 `String` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="7e055-112">You can also manipulate strings with the methods of the `String` class.</span></span> <span data-ttu-id="7e055-113">메서드의 두 가지 `String`: *공유* 메서드 및 *인스턴스* 메서드.</span><span class="sxs-lookup"><span data-stu-id="7e055-113">There are two types of methods in `String`: *shared* methods and *instance* methods.</span></span>  
  
#### <a name="shared-methods"></a><span data-ttu-id="7e055-114">공유 메서드</span><span class="sxs-lookup"><span data-stu-id="7e055-114">Shared Methods</span></span>  
 <span data-ttu-id="7e055-115">발생 하는 방법은 공유 메서드는 `String` 클래스 자체와 작동 하도록 해당 클래스의 인스턴스를 필요로 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e055-115">A shared method is a method that stems from the `String` class itself and does not require an instance of that class to work.</span></span> <span data-ttu-id="7e055-116">이러한 메서드는 클래스의 이름으로 정규화 할 수 있습니다 (`String`)의 인스턴스 대신는 `String` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="7e055-116">These methods can be qualified with the name of the class (`String`) rather than with an instance of the `String` class.</span></span> <span data-ttu-id="7e055-117">예:</span><span class="sxs-lookup"><span data-stu-id="7e055-117">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#45](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_2.vb)]  
  
 <span data-ttu-id="7e055-118">앞의 예제에는 <xref:System.String.Copy%2A?displayProperty=nameWithType> 메서드는 정적 메서드는 식에 대해 동작 하는 것은 되며 결과 값을 할당 `bString`합니다.</span><span class="sxs-lookup"><span data-stu-id="7e055-118">In the preceding example, the <xref:System.String.Copy%2A?displayProperty=nameWithType> method is a static method, which acts upon an expression it is given and assigns the resulting value to `bString`.</span></span>  
  
#### <a name="instance-methods"></a><span data-ttu-id="7e055-119">인스턴스 메서드</span><span class="sxs-lookup"><span data-stu-id="7e055-119">Instance Methods</span></span>  
 <span data-ttu-id="7e055-120">인스턴스 메서드와 달리,의 특정 인스턴스에서 형태소 분석 `String` 및 인스턴스 이름으로 한정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e055-120">Instance methods, by contrast, stem from a particular instance of `String` and must be qualified with the instance name.</span></span> <span data-ttu-id="7e055-121">예:</span><span class="sxs-lookup"><span data-stu-id="7e055-121">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#46](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_3.vb)]  
  
 <span data-ttu-id="7e055-122">이 예제는 <xref:System.String.Substring%2A?displayProperty=nameWithType> 메서드는 인스턴스 메서드 `String` (즉, `aString`).</span><span class="sxs-lookup"><span data-stu-id="7e055-122">In this example, the <xref:System.String.Substring%2A?displayProperty=nameWithType> method is a method of the instance of `String` (that is, `aString`).</span></span> <span data-ttu-id="7e055-123">에 작업을 수행할 `aString` 해당 값을 할당 하 고 `bString`합니다.</span><span class="sxs-lookup"><span data-stu-id="7e055-123">It performs an operation on `aString` and assigns that value to `bString`.</span></span>  
  
 <span data-ttu-id="7e055-124">자세한 내용은 참조에 대 한 설명서는 <xref:System.String> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="7e055-124">For more information, see the documentation for the <xref:System.String> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e055-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7e055-125">See Also</span></span>  
 [<span data-ttu-id="7e055-126">Visual Basic의 문자열 소개</span><span class="sxs-lookup"><span data-stu-id="7e055-126">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
