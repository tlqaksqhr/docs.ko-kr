---
title: "&quot;AddressOf&quot; 피연산자에 괄호 없이 사용 되는 메서드의 이름 이어야 합니다. | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30577
- bc30577
dev_langs:
- VB
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
caps.latest.revision: 10
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
ms.openlocfilehash: c4ee57896b70d8af1a7bc245bdb45521c2442fea
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="39addressof39-operand-must-be-the-name-of-a-method-without-parentheses"></a><span data-ttu-id="4ab40-102">'AddressOf' 피연산자에 괄호 없이 사용 되는 메서드의 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ab40-102">&#39;AddressOf&#39; operand must be the name of a method (without parentheses)</span></span>
<span data-ttu-id="4ab40-103">`AddressOf` 연산자는 특정 프로시저를 참조하는 프로시저 대리자 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4ab40-103">The `AddressOf` operator creates a procedure delegate instance that references a specific procedure.</span></span> <span data-ttu-id="4ab40-104">구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4ab40-104">The syntax is as follows.</span></span>  
  
 <span data-ttu-id="4ab40-105">`AddressOf` `procedurename`</span><span class="sxs-lookup"><span data-stu-id="4ab40-105">`AddressOf` `procedurename`</span></span>  
  
 <span data-ttu-id="4ab40-106">괄호 뒤의 인수를 삽입 `AddressOf`에 불필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ab40-106">You inserted parentheses around the argument following `AddressOf`, where none are needed.</span></span>  
  
 <span data-ttu-id="4ab40-107">**오류 ID:** BC30577</span><span class="sxs-lookup"><span data-stu-id="4ab40-107">**Error ID:** BC30577</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4ab40-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="4ab40-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="4ab40-109">뒤의 인수를 괄호로 제거 `AddressOf`합니다.</span><span class="sxs-lookup"><span data-stu-id="4ab40-109">Remove the parentheses around the argument following `AddressOf`.</span></span>  
  
2.  <span data-ttu-id="4ab40-110">인수는 메서드 이름 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ab40-110">Make sure the argument is a method name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ab40-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4ab40-111">See Also</span></span>  
 <span data-ttu-id="4ab40-112">[AddressOf 연산자](../../../visual-basic/language-reference/operators/addressof-operator.md) </span><span class="sxs-lookup"><span data-stu-id="4ab40-112">[AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md) </span></span>  
<span data-ttu-id="4ab40-113"> [대리자](../../../visual-basic/programming-guide/language-features/delegates/index.md)</span><span class="sxs-lookup"><span data-stu-id="4ab40-113"> [Delegates](../../../visual-basic/programming-guide/language-features/delegates/index.md)</span></span>
