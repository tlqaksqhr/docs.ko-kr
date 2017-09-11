---
title: "자동화 오류입니다. | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID440
dev_langs:
- VB
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
caps.latest.revision: 9
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
ms.openlocfilehash: b48ada07663889db633a43fabb577d5129c5cbb3
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="automation-error"></a><span data-ttu-id="58855-102">자동화 오류</span><span class="sxs-lookup"><span data-stu-id="58855-102">Automation error</span></span>
<span data-ttu-id="58855-103">메서드를 실행하는 동안 또는 개체 변수의 속성을 가져오거나 설정하는 동안 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="58855-103">An error occurred while executing a method or getting or setting a property of an object variable.</span></span> <span data-ttu-id="58855-104">이 오류는 개체를 만든 응용 프로그램에서 보고했습니다.</span><span class="sxs-lookup"><span data-stu-id="58855-104">The error was reported by the application that created the object.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="58855-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="58855-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="58855-106">`Err` 개체의 속성을 점검해 오류의 원인과 특성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="58855-106">Check the properties of the `Err` object to determine the source and nature of the error.</span></span>  
  
2.  <span data-ttu-id="58855-107">액세스하는 문 바로 전에 `On Error Resume Next` 문을 사용하고, 액세스하는 문 바로 후에 오류가 발생하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="58855-107">Use the `On Error Resume Next` statement immediately before the accessing statement, and then check for errors immediately after the accessing statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58855-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="58855-108">See Also</span></span>  
 <span data-ttu-id="58855-109">[오류 형식](../../../visual-basic/programming-guide/language-features/error-types.md) </span><span class="sxs-lookup"><span data-stu-id="58855-109">[Error Types](../../../visual-basic/programming-guide/language-features/error-types.md) </span></span>  
<span data-ttu-id="58855-110"> [의견 보내기](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span><span class="sxs-lookup"><span data-stu-id="58855-110"> [Talk to Us](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span></span>
