---
title: "&#39; &lt;키워드&gt;&#39; 하 여 인스턴스 메서드 내 에서만 유효"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords: BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a61314c036cec0fd1412a9c844a610fbd1401add
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="39ltkeywordgt39-is-valid-only-within-an-instance-method"></a><span data-ttu-id="1424b-102">&#39; &lt;키워드&gt;&#39; 하 여 인스턴스 메서드 내 에서만 유효</span><span class="sxs-lookup"><span data-stu-id="1424b-102">&#39;&lt;keyword&gt;&#39; is valid only within an instance method</span></span>
<span data-ttu-id="1424b-103">`Me`, `MyClass`, 및 `MyBase` 키워드 특정 클래스 인스턴스를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="1424b-103">The `Me`, `MyClass`, and `MyBase` keywords refer to specific class instances.</span></span> <span data-ttu-id="1424b-104">공유 안에 사용할 수 없습니다 `Function` 또는 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="1424b-104">You cannot use them inside a shared `Function` or `Sub` procedure.</span></span>  
  
 <span data-ttu-id="1424b-105">**오류 ID:** BC30043</span><span class="sxs-lookup"><span data-stu-id="1424b-105">**Error ID:** BC30043</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1424b-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="1424b-106">To correct this error</span></span>  
  
-   <span data-ttu-id="1424b-107">프로시저에서 키워드를 제거 하거나 제거는 `Shared` 프로시저 선언에서 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="1424b-107">Remove the keyword from the procedure, or remove the `Shared` keyword from the procedure declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1424b-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1424b-108">See Also</span></span>  
 [<span data-ttu-id="1424b-109">개체 변수 할당</span><span class="sxs-lookup"><span data-stu-id="1424b-109">Object Variable Assignment</span></span>](../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [<span data-ttu-id="1424b-110">Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="1424b-110">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [<span data-ttu-id="1424b-111">상속 기본 사항</span><span class="sxs-lookup"><span data-stu-id="1424b-111">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
