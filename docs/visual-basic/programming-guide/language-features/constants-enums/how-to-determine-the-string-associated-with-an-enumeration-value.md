---
title: "방법: 열거형 값과 연결된 문자열 확인(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- enumerations [Visual Basic]
- strings [Visual Basic], enumeration values
- values [Visual Basic], enumeration members
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 01e2b0cfa6b1e426b38198581c7d493c8907b79b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-the-string-associated-with-an-enumeration-value-visual-basic"></a><span data-ttu-id="6cf63-102">방법: 열거형 값과 연결된 문자열 확인(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6cf63-102">How to: Determine the String Associated with an Enumeration Value (Visual Basic)</span></span>
<span data-ttu-id="6cf63-103"><xref:System.Enum.GetValues%2A> 및 <xref:System.Enum.GetNames%2A> 메서드를 사용 하는 문자열 및 열거형 멤버와 관련 된 값을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cf63-103">The <xref:System.Enum.GetValues%2A> and <xref:System.Enum.GetNames%2A> methods allow you to determine the strings and values associated with enumeration members.</span></span>  
  
### <a name="to-determine-the-string-associated-with-an-enumeration"></a><span data-ttu-id="6cf63-104">열거형과 연결 된 문자열을 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="6cf63-104">To determine the string associated with an enumeration</span></span>  
  
-   <span data-ttu-id="6cf63-105">사용 된 <xref:System.Enum.GetNames%2A> 열거형 멤버와 연결 된 문자열을 검색 하는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="6cf63-105">Use the <xref:System.Enum.GetNames%2A> method to retrieve the strings associated with the enumeration members.</span></span> <span data-ttu-id="6cf63-106">이 예제에서는 열거형을 선언 `flavorEnum`를 사용 하 여는 <xref:System.Enum.GetNames%2A> 메서드 각 멤버와 연결 된 문자열을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cf63-106">This example declares an enumeration, `flavorEnum`, then uses the <xref:System.Enum.GetNames%2A> method to display the strings associated with each member.</span></span>  
  
     [!code-vb[VbEnumsTask#2](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-determine-the-string-associated-with-an-enumeration-value_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="6cf63-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6cf63-107">See Also</span></span>  
 <xref:System.Enum.GetValues%2A>  
 <xref:System.Enum.GetNames%2A>  
 <xref:System.Enum>  
 [<span data-ttu-id="6cf63-108">방법: 열거형 선언</span><span class="sxs-lookup"><span data-stu-id="6cf63-108">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [<span data-ttu-id="6cf63-109">방법: 열거형 멤버 참조</span><span class="sxs-lookup"><span data-stu-id="6cf63-109">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [<span data-ttu-id="6cf63-110">열거형 및 이름 한정</span><span class="sxs-lookup"><span data-stu-id="6cf63-110">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="6cf63-111">방법: Visual Basic에서 열거형 반복</span><span class="sxs-lookup"><span data-stu-id="6cf63-111">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [<span data-ttu-id="6cf63-112">열거형을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="6cf63-112">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [<span data-ttu-id="6cf63-113">Enum 문</span><span class="sxs-lookup"><span data-stu-id="6cf63-113">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
