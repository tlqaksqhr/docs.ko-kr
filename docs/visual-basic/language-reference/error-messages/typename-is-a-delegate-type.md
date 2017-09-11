---
title: "&quot;&lt;typename&gt;&quot; 대리자 형식입니다. | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32008
- vbc32008
dev_langs:
- VB
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
caps.latest.revision: 11
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
ms.openlocfilehash: 55532e269a7d6756157d324a2db14320df5d3f55
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="39lttypenamegt39-is-a-delegate-type"></a><span data-ttu-id="dc1d5-102">'&lt;typename&gt;' 대리자 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="dc1d5-102">&#39;&lt;typename&gt;&#39; is a delegate type</span></span>
<span data-ttu-id="dc1d5-103">'\<유형 이름 > ' 대리자 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="dc1d5-103">'\<typename>' is a delegate type.</span></span> <span data-ttu-id="dc1d5-104">대리자 구문에는 인수 목록으로 단일 AddressOf 식만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="dc1d5-104">Delegate construction permits only a single AddressOf expression as an argument list.</span></span> <span data-ttu-id="dc1d5-105">종종 AddressOf 식은 대리자 구문 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc1d5-105">Often an AddressOf expression can be used instead of a delegate construction.</span></span>  
  
 <span data-ttu-id="dc1d5-106">A `New` 절 대리자 클래스의 인스턴스를 만들고 대리자 생성자는 잘못 된 인수 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc1d5-106">A `New` clause creating an instance of a delegate class supplies an invalid argument list to the delegate constructor.</span></span>  
  
 <span data-ttu-id="dc1d5-107">하나만 제공할 수 있습니다 `AddressOf` 새 대리자 인스턴스를 만들 때 식입니다.</span><span class="sxs-lookup"><span data-stu-id="dc1d5-107">You can supply only a single `AddressOf` expression when creating a new delegate instance.</span></span>  
  
 <span data-ttu-id="dc1d5-108">전달 하지 않으면 모든 인수는 대리자 생성자에 둘 이상의 인수를 전달 하거나 단일 인수를 전달 하는 경우는 유효 하지 않은 경우이 오류가 발생할 수 있습니다 `AddressOf` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="dc1d5-108">This error can result if you do not pass any arguments to the delegate constructor, if you pass more than one argument, or if you pass a single argument that is not a valid `AddressOf` expression.</span></span>  
  
 <span data-ttu-id="dc1d5-109">**오류 ID:** BC32008</span><span class="sxs-lookup"><span data-stu-id="dc1d5-109">**Error ID:** BC32008</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="dc1d5-110">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="dc1d5-110">To correct this error</span></span>  
  
-   <span data-ttu-id="dc1d5-111">단일을 사용 하 여 `AddressOf` 대리자 클래스에 대 한 인수 목록에서 식의 `New` 절.</span><span class="sxs-lookup"><span data-stu-id="dc1d5-111">Use a single `AddressOf` expression in the argument list for the delegate class in the `New` clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc1d5-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc1d5-112">See Also</span></span>  
 <span data-ttu-id="dc1d5-113">[New 연산자](../../../visual-basic/language-reference/operators/new-operator.md) </span><span class="sxs-lookup"><span data-stu-id="dc1d5-113">[New Operator](../../../visual-basic/language-reference/operators/new-operator.md) </span></span>  
<span data-ttu-id="dc1d5-114"> [AddressOf 연산자](../../../visual-basic/language-reference/operators/addressof-operator.md) </span><span class="sxs-lookup"><span data-stu-id="dc1d5-114"> [AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md) </span></span>  
<span data-ttu-id="dc1d5-115"> [대리자](../../../visual-basic/programming-guide/language-features/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="dc1d5-115"> [Delegates](../../../visual-basic/programming-guide/language-features/delegates/index.md) </span></span>  
<span data-ttu-id="dc1d5-116"> [방법: 대리자 메서드 호출](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)</span><span class="sxs-lookup"><span data-stu-id="dc1d5-116"> [How to: Invoke a Delegate Method](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)</span></span>
