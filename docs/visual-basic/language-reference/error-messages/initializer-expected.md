---
title: "이니셜라이저가 필요합니다."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30996
- bc30996
helpviewer_keywords: BC30996
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 46ff91ec240212571f7ec9f26e82d9d128263545
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="initializer-expected"></a><span data-ttu-id="19ef6-102">이니셜라이저가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="19ef6-102">Initializer expected</span></span>
<span data-ttu-id="19ef6-103">초기화 목록의 비어 있는 경우 다음 예제와 같이 개체 이니셜라이저를 사용 하 여 클래스의 인스턴스를 선언 하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="19ef6-103">You have tried to declare an instance of a class by using an object initializer in which the initialization list is empty, as shown in the following example.</span></span>  
  
 `' Not valid.`  
  
 `' Dim aStudent As New Student With {}`  
  
 <span data-ttu-id="19ef6-104">다음 예제와 같이 이니셜라이저 목록에서 하나 이상의 필드 또는 속성 초기화 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19ef6-104">At least one field or property must be initialized in the initializer list, as shown in the following example.</span></span>  
  
 `Dim aStudent As New Student With {.year = "Senior"}`  
  
 <span data-ttu-id="19ef6-105">**오류 ID:** BC30996</span><span class="sxs-lookup"><span data-stu-id="19ef6-105">**Error ID:** BC30996</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="19ef6-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="19ef6-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="19ef6-107">하나 이상의 필드 또는 이니셜라이저의 속성을 초기화 하거나 개체 이니셜라이저를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="19ef6-107">Initialize at least one field or property in the initializer, or do not use an object initializer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19ef6-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="19ef6-108">See Also</span></span>  
 [<span data-ttu-id="19ef6-109">개체 이니셜라이저: 명명된 형식과 익명 형식</span><span class="sxs-lookup"><span data-stu-id="19ef6-109">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [<span data-ttu-id="19ef6-110">방법: 개체 이니셜라이저를 사용하여 개체 선언</span><span class="sxs-lookup"><span data-stu-id="19ef6-110">How to: Declare an Object by Using an Object Initializer</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
