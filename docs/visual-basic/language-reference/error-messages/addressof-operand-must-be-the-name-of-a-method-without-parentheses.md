---
title: '&#39; AddressOf &#39; 피연산자의 괄호 없이 메서드 이름 이어야 합니다.'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 02c996f1c94250526982e35395288b07db619db7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="39addressof39-operand-must-be-the-name-of-a-method-without-parentheses"></a><span data-ttu-id="df436-102">&#39; AddressOf &#39; 피연산자의 괄호 없이 메서드 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df436-102">&#39;AddressOf&#39; operand must be the name of a method (without parentheses)</span></span>
<span data-ttu-id="df436-103">`AddressOf` 연산자는 특정 프로시저를 참조하는 프로시저 대리자 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="df436-103">The `AddressOf` operator creates a procedure delegate instance that references a specific procedure.</span></span> <span data-ttu-id="df436-104">구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="df436-104">The syntax is as follows.</span></span>  
  
 <span data-ttu-id="df436-105">`AddressOf` `procedurename`</span><span class="sxs-lookup"><span data-stu-id="df436-105">`AddressOf` `procedurename`</span></span>  
  
 <span data-ttu-id="df436-106">괄호 뒤의 인수를 삽입 `AddressOf`에 불필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="df436-106">You inserted parentheses around the argument following `AddressOf`, where none are needed.</span></span>  
  
 <span data-ttu-id="df436-107">**오류 ID:** BC30577</span><span class="sxs-lookup"><span data-stu-id="df436-107">**Error ID:** BC30577</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="df436-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="df436-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="df436-109">뒤의 인수 주위에 괄호를 제거 `AddressOf`합니다.</span><span class="sxs-lookup"><span data-stu-id="df436-109">Remove the parentheses around the argument following `AddressOf`.</span></span>  
  
2.  <span data-ttu-id="df436-110">인수는 메서드 이름 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="df436-110">Make sure the argument is a method name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df436-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="df436-111">See Also</span></span>  
 [<span data-ttu-id="df436-112">AddressOf 연산자</span><span class="sxs-lookup"><span data-stu-id="df436-112">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="df436-113">대리자</span><span class="sxs-lookup"><span data-stu-id="df436-113">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
