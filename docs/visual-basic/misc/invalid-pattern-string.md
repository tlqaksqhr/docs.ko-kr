---
title: 잘못된 패턴 문자열
ms.date: 07/20/2015
ms.assetid: ec1aecdb-5339-4a93-be71-eec56b1d7438
ms.openlocfilehash: 4905f74683989d8e1a2b041a8af4af4d7432ffab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33635647"
---
# <a name="invalid-pattern-string"></a><span data-ttu-id="b9155-102">잘못된 패턴 문자열</span><span class="sxs-lookup"><span data-stu-id="b9155-102">Invalid pattern string</span></span>
<span data-ttu-id="b9155-103">검색의 `Like` 작업에서 지정된 패턴 문자열이 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b9155-103">The pattern string specified in the `Like` operation of a search is invalid.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b9155-104">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="b9155-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="b9155-105">목록 식에 유효한 문자를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="b9155-105">Review the valid characters for list expressions.</span></span>  
  
2.  <span data-ttu-id="b9155-106">패턴 범위에서 `[a-z]`처럼 범위 시작 문자가 범위 끝 문자보다 작은지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b9155-106">In the pattern range, ensure that the start range character is less than the end range character, as in `[a-z]`.</span></span>  
  
3.  <span data-ttu-id="b9155-107">패턴 범위에서 `[a--z]`처럼 여러 하이픈이 서로 인접하지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b9155-107">In the pattern range, ensure that there are not multiple hyphens next to each other, as in `[a--z]`.</span></span>  
  
4.  <span data-ttu-id="b9155-108">닫는 대괄호를 사용하여 패턴 범위를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="b9155-108">End pattern ranges with a closing bracket.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9155-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b9155-109">See Also</span></span>  
 [<span data-ttu-id="b9155-110">Like 연산자</span><span class="sxs-lookup"><span data-stu-id="b9155-110">Like Operator</span></span>](../../visual-basic/language-reference/operators/like-operator.md)
