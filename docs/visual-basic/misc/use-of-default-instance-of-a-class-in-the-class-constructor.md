---
title: "클래스 생성자에 클래스의 기본 인스턴스를 사용하면 무한 재귀 호출이 발생할 수 있습니다."
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: 9645b47f-7de5-46d0-bb45-d5fdaa8aaa2a
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6a0c54c6e62f9bdc7fe510500a486461d26636d8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="use-of-default-instance-of-a-class-in-the-class-constructor-could-lead-to-infinite-recursive-call"></a><span data-ttu-id="67974-102">클래스 생성자에 클래스의 기본 인스턴스를 사용하면 무한 재귀 호출이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67974-102">Use of Default Instance of a class in the class constructor could lead to infinite recursive call</span></span>
<span data-ttu-id="67974-103">클래스의 기본 인스턴스가 클래스의 생성자에서 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="67974-103">A default instance of a class has been used in the constructor of the class.</span></span> <span data-ttu-id="67974-104">이로 인해 무한 루프라고도 하는 무한 재귀 호출이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67974-104">This can lead to an infinite recursive call, also known as an infinite loop.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="67974-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="67974-105">To correct this error</span></span>  
  
-   <span data-ttu-id="67974-106">클래스 생성자에서 기본 인스턴스를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="67974-106">Remove the default instance from the class constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67974-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="67974-107">See Also</span></span>  
 [<span data-ttu-id="67974-108">생성자</span><span class="sxs-lookup"><span data-stu-id="67974-108">Constructors</span></span>](~/docs/visual-basic/programming-guide/concepts/object-oriented-programming.md#constructors)
