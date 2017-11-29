---
title: "방법: Visual Basic에서 열거형 반복"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arrays [Visual Basic], iterating
- enumerations [Visual Basic], iterating
- ListBox control [Windows Forms], populating from an enumeration
ms.assetid: e5aa10eb-cfcd-4a3b-8e76-f06b8f2002be
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 439e6eae7d475316625a2cc1d3a70a9e7181f68a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-iterate-through-an-enumeration-in-visual-basic"></a><span data-ttu-id="4b14d-102">방법: Visual Basic에서 열거형 반복</span><span class="sxs-lookup"><span data-stu-id="4b14d-102">How to: Iterate Through An Enumeration in Visual Basic</span></span>
<span data-ttu-id="4b14d-103">열거형은 관련된 상수 집합으로 작업하고 이름과 상수 값을 연결하는 편리한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4b14d-103">Enumerations provide a convenient way to work with sets of related constants, and to associate constant values with names.</span></span> <span data-ttu-id="4b14d-104">열거를 반복 하려면 이동할 수 있습니다 사용 하 여 배열에는 <xref:System.Enum.GetValues%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="4b14d-104">To iterate through an enumeration, you can move it into an array using the <xref:System.Enum.GetValues%2A> method.</span></span> <span data-ttu-id="4b14d-105">사용 하는 열거형 반복할 수도 있습니다는 `For...Each` 문을 사용 하는 <xref:System.Enum.GetNames%2A> 또는 <xref:System.Enum.GetValues%2A> 문자열이 나 숫자 값을 추출 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="4b14d-105">You could also iterate through an enumeration using a `For...Each` statement, using the <xref:System.Enum.GetNames%2A> or <xref:System.Enum.GetValues%2A> method to extract the string or numeric value.</span></span>  
  
### <a name="to-iterate-through-an-enumeration"></a><span data-ttu-id="4b14d-106">열거형 반복 하려면</span><span class="sxs-lookup"><span data-stu-id="4b14d-106">To iterate through an enumeration</span></span>  
  
-   <span data-ttu-id="4b14d-107">배열을 선언 하 여 열거를 사용 하 여 변환할는 <xref:System.Enum.GetValues%2A> 때 배열을 전달 하기 전에 메서드는 다른 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="4b14d-107">Declare an array and convert the enumeration to it with the <xref:System.Enum.GetValues%2A> method before passing the array as you would any other variable.</span></span> <span data-ttu-id="4b14d-108">다음 예제에서는 표시 된 열거형의 각 구성원 <xref:Microsoft.VisualBasic.FirstDayOfWeek> 대로 반복 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="4b14d-108">The following example displays each member of the enumeration <xref:Microsoft.VisualBasic.FirstDayOfWeek> as it iterates through the enumeration.</span></span>  
  
     [!code-vb[VbEnumsTask#7](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-iterate-through-an-enumeration_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="4b14d-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b14d-109">See Also</span></span>  
 [<span data-ttu-id="4b14d-110">열거형 개요</span><span class="sxs-lookup"><span data-stu-id="4b14d-110">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [<span data-ttu-id="4b14d-111">방법: 열거형 선언</span><span class="sxs-lookup"><span data-stu-id="4b14d-111">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [<span data-ttu-id="4b14d-112">열거형을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="4b14d-112">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [<span data-ttu-id="4b14d-113">방법: 열거형 값과 연결된 문자열 확인</span><span class="sxs-lookup"><span data-stu-id="4b14d-113">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [<span data-ttu-id="4b14d-114">방법: 열거형 멤버 참조</span><span class="sxs-lookup"><span data-stu-id="4b14d-114">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [<span data-ttu-id="4b14d-115">열거형 및 이름 한정</span><span class="sxs-lookup"><span data-stu-id="4b14d-115">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="4b14d-116">배열</span><span class="sxs-lookup"><span data-stu-id="4b14d-116">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
