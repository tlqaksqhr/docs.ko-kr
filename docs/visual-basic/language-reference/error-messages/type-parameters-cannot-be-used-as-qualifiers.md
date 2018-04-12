---
title: 형식 매개 변수는 한정자로 사용할 수 없습니다.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords:
- BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 58be51e0c05750ee044f0287cde8db037718b4aa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="type-parameters-cannot-be-used-as-qualifiers"></a><span data-ttu-id="40836-102">형식 매개 변수는 한정자로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="40836-102">Type parameters cannot be used as qualifiers</span></span>
<span data-ttu-id="40836-103">프로그래밍 요소가 형식 매개 변수를 포함 하는 한정 문자열 한정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40836-103">A programming element is qualified with a qualification string that includes a type parameter.</span></span>  
  
 <span data-ttu-id="40836-104">형식 매개 변수는 제네릭 형식 생성 될 때 제공 해야 하는 형식에 대 한 요구 사항을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="40836-104">A type parameter represents a requirement for a type that is to be supplied when the generic type is constructed.</span></span> <span data-ttu-id="40836-105">정의 된 특정 형식을 나타내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40836-105">It does not represent a specific defined type.</span></span> <span data-ttu-id="40836-106">정규화 문자열에는 컴파일 타임에 정의 된 요소에만 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40836-106">A qualification string must include only elements that are defined at compile time.</span></span>  
  
 <span data-ttu-id="40836-107">다음 문은 이 오류를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40836-107">The following statements can generate this error.</span></span>  
  
```  
Public Function checkText(Of c As System.Windows.Forms.Control)(  
    ByVal badText As String) As Boolean  
  
    Dim saveText As c.Text  
    ' Insert code to look for badText within saveText.  
End Function  
```  
  
 <span data-ttu-id="40836-108">**오류 ID:** BC32098</span><span class="sxs-lookup"><span data-stu-id="40836-108">**Error ID:** BC32098</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="40836-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="40836-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="40836-110">한정 문자열에서 형식 매개 변수를 제거 하거나 정의 된 형식으로 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="40836-110">Remove the type parameter from the qualification string, or replace it with a defined type.</span></span>  
  
2.  <span data-ttu-id="40836-111">생성된 된 형식을 자격이 부여 되는 프로그래밍 요소를 찾는 데 필요한 경우 프로그램 논리를 추가로 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40836-111">If you need to use a constructed type to locate the programming element being qualified, you must use additional program logic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40836-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="40836-112">See Also</span></span>  
 [<span data-ttu-id="40836-113">선언된 요소 참조</span><span class="sxs-lookup"><span data-stu-id="40836-113">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="40836-114">Visual Basic의 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="40836-114">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="40836-115">형식 목록</span><span class="sxs-lookup"><span data-stu-id="40836-115">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
