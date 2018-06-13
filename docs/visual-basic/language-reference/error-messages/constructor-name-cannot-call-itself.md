---
title: 생성자 &#39; &lt;이름&gt; &#39; 자신을 호출할 수 없습니다
ms.date: 07/20/2015
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords:
- BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
ms.openlocfilehash: 069de813a0426230e19cddf14c3b83d40a602a41
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588998"
---
# <a name="constructor-39ltnamegt39-cannot-call-itself"></a><span data-ttu-id="78a41-102">생성자 &#39; &lt;이름&gt; &#39; 자신을 호출할 수 없습니다</span><span class="sxs-lookup"><span data-stu-id="78a41-102">Constructor &#39;&lt;name&gt;&#39; cannot call itself</span></span>
<span data-ttu-id="78a41-103">A `Sub New` 클래스 또는 구조체에는 프로시저가 자신을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a41-103">A `Sub New` procedure in a class or structure calls itself.</span></span>  
  
 <span data-ttu-id="78a41-104">클래스의 인스턴스를 초기화 하는 생성자의 목적은 또는 구조가 처음 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a41-104">The purpose of a constructor is to initialize an instance of a class or structure when it is first created.</span></span> <span data-ttu-id="78a41-105">클래스 또는 구조체는 다른 매개 변수 목록을 모두 있는 여러 생성자에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78a41-105">A class or structure can have several constructors, provided they all have different parameter lists.</span></span> <span data-ttu-id="78a41-106">생성자 자체 외에도 해당 기능을 수행 하려면 다른 생성자를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78a41-106">A constructor is permitted to call another constructor to perform its functionality in addition to its own.</span></span> <span data-ttu-id="78a41-107">자신을 호출 하는 생성자에 대 한 의미가 없습니다 있고 실제로 초래 무한 재귀가 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a41-107">But it is meaningless for a constructor to call itself, and in fact it would result in infinite recursion if permitted.</span></span>  
  
 <span data-ttu-id="78a41-108">**오류 ID:** BC30298</span><span class="sxs-lookup"><span data-stu-id="78a41-108">**Error ID:** BC30298</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="78a41-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="78a41-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="78a41-110">호출 중인 생성자의 매개 변수 목록을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a41-110">Check the parameter list of the constructor being called.</span></span> <span data-ttu-id="78a41-111">전화 통화를 걸기 생성자의 달라 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a41-111">It should be different from that of the constructor making the call.</span></span>  
  
2.  <span data-ttu-id="78a41-112">다른 생성자를 호출 하지 않을 경우 제거 된 `Sub New` 전적으로 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="78a41-112">If you do not intend to call a different constructor, remove the `Sub New` call entirely.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78a41-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="78a41-113">See Also</span></span>  
 [<span data-ttu-id="78a41-114">개체 수명: 개체가 만들어지고 제거되는 방법</span><span class="sxs-lookup"><span data-stu-id="78a41-114">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
