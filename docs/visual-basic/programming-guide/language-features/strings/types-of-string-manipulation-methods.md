---
title: "Visual Basic의 문자열 조작 메서드 유형 | Microsoft 문서"
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
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
caps.latest.revision: 12
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
ms.openlocfilehash: 9c63ad0931ae2f3760576a792795b9fe0ab6a409
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a><span data-ttu-id="97961-102">Visual Basic의 문자열 조작 메서드 유형</span><span class="sxs-lookup"><span data-stu-id="97961-102">Types of String Manipulation Methods in Visual Basic</span></span>
<span data-ttu-id="97961-103">분석 및 문자열을 조작 하는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97961-103">There are several different ways to analyze and manipulate your strings.</span></span> <span data-ttu-id="97961-104">일부인 일부 메서드는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 에 내재 된 언어 및 다른 사용자는 `String` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="97961-104">Some of the methods are a part of the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] language, and others are inherent in the `String` class.</span></span>  
  
## <a name="visual-basic-language-and-the-net-framework"></a><span data-ttu-id="97961-105">Visual Basic 언어와.NET Framework</span><span class="sxs-lookup"><span data-stu-id="97961-105">Visual Basic Language and the .NET Framework</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="97961-106">메서드는 언어의 기본 기능으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97961-106"> methods are used as inherent functions of the language.</span></span> <span data-ttu-id="97961-107">코드에서 자격 증명 없이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97961-107">They may be used without qualification in your code.</span></span> <span data-ttu-id="97961-108">다음 예제에서는 일반적인 사용을 보여 줍니다.는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 문자열 조작 명령:</span><span class="sxs-lookup"><span data-stu-id="97961-108">The following example shows typical use of a [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] string-manipulation command:</span></span>  
  
 <span data-ttu-id="97961-109">[!code-vb[VbVbalrStrings #&44;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="97961-109">[!code-vb[VbVbalrStrings#44](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_1.vb)]</span></span>  
  
 <span data-ttu-id="97961-110">이 예제는 `Mid` 에서 직접 작업을 수행 하는 함수 `aString` 값을 할당 하 고 `bString`합니다.</span><span class="sxs-lookup"><span data-stu-id="97961-110">In this example, the `Mid` function performs a direct operation on `aString` and assigns the value to `bString`.</span></span>  
  
 <span data-ttu-id="97961-111">Visual Basic 문자열 조작 메서드 목록이 참조 [문자열 조작 요약](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="97961-111">For a list of Visual Basic string manipulation methods, see [String Manipulation Summary](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span></span>  
  
### <a name="shared-methods-and-instance-methods"></a><span data-ttu-id="97961-112">공유 메서드와 인스턴스 메서드</span><span class="sxs-lookup"><span data-stu-id="97961-112">Shared Methods and Instance Methods</span></span>  
 <span data-ttu-id="97961-113">메서드로 문자열을 조작할 수도 `String` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="97961-113">You can also manipulate strings with the methods of the `String` class.</span></span> <span data-ttu-id="97961-114">메서드는 두 가지 `String`: *공유* 메서드 및 *인스턴스* 메서드.</span><span class="sxs-lookup"><span data-stu-id="97961-114">There are two types of methods in `String`: *shared* methods and *instance* methods.</span></span>  
  
#### <a name="shared-methods"></a><span data-ttu-id="97961-115">공유 메서드</span><span class="sxs-lookup"><span data-stu-id="97961-115">Shared Methods</span></span>  
 <span data-ttu-id="97961-116">발생 하는 방법은 공유 메서드는 `String` 클래스 자체와 작동 하도록 해당 클래스의 인스턴스를 필요로 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97961-116">A shared method is a method that stems from the `String` class itself and does not require an instance of that class to work.</span></span> <span data-ttu-id="97961-117">이러한 메서드는 클래스의 이름으로 정규화 할 수 있습니다 (`String`)의 인스턴스 대신는 `String` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="97961-117">These methods can be qualified with the name of the class (`String`) rather than with an instance of the `String` class.</span></span> <span data-ttu-id="97961-118">예:</span><span class="sxs-lookup"><span data-stu-id="97961-118">For example:</span></span>  
  
 <span data-ttu-id="97961-119">[!code-vb[VbVbalrStrings #&45;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="97961-119">[!code-vb[VbVbalrStrings#45](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_2.vb)]</span></span>  
  
 <span data-ttu-id="97961-120">앞의 예제에는 <xref:System.String.Copy%2A?displayProperty=fullName>메서드는 정적 메서드를 작동 하는 식에 대해 지정 하 고 결과 값을 할당 `bString`.</xref:System.String.Copy%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="97961-120">In the preceding example, the <xref:System.String.Copy%2A?displayProperty=fullName> method is a static method, which acts upon an expression it is given and assigns the resulting value to `bString`.</span></span>  
  
#### <a name="instance-methods"></a><span data-ttu-id="97961-121">인스턴스 메서드</span><span class="sxs-lookup"><span data-stu-id="97961-121">Instance Methods</span></span>  
 <span data-ttu-id="97961-122">인스턴스 메서드는 반면,의 특정 인스턴스에서 생기고 `String` 및 인스턴스 이름으로 한정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97961-122">Instance methods, by contrast, stem from a particular instance of `String` and must be qualified with the instance name.</span></span> <span data-ttu-id="97961-123">예:</span><span class="sxs-lookup"><span data-stu-id="97961-123">For example:</span></span>  
  
 <span data-ttu-id="97961-124">[!code-vb[VbVbalrStrings #&46;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="97961-124">[!code-vb[VbVbalrStrings#46](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_3.vb)]</span></span>  
  
 <span data-ttu-id="97961-125">이 예제는 <xref:System.String.Substring%2A?displayProperty=fullName>메서드가 인스턴스 메서드가 `String` (즉, `aString`).</xref:System.String.Substring%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="97961-125">In this example, the <xref:System.String.Substring%2A?displayProperty=fullName> method is a method of the instance of `String` (that is, `aString`).</span></span> <span data-ttu-id="97961-126">에 작업을 수행 `aString` 해당 값을 할당 하 고 `bString`합니다.</span><span class="sxs-lookup"><span data-stu-id="97961-126">It performs an operation on `aString` and assigns that value to `bString`.</span></span>  
  
 <span data-ttu-id="97961-127">자세한 내용은 <xref:System.String>클래스</xref:System.String> 에 대 한 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="97961-127">For more information, see the documentation for the <xref:System.String> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97961-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="97961-128">See Also</span></span>  
 [<span data-ttu-id="97961-129">Visual Basic의 문자열 소개</span><span class="sxs-lookup"><span data-stu-id="97961-129">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
