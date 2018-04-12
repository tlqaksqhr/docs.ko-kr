---
title: 클래스가 자동화를 지원하지 않거나 필요한 인터페이스를 지원하지 않습니다.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID430
ms.assetid: d985bb7e-e48e-443e-86f2-ddb86758757c
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6528ceabeb7fb7a1cdc0beff2fd362632a0a0c9a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="class-does-not-support-automation-or-does-not-support-expected-interface"></a><span data-ttu-id="76eb7-102">클래스가 자동화를 지원하지 않거나 필요한 인터페이스를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76eb7-102">Class does not support Automation or does not support expected interface</span></span>
<span data-ttu-id="76eb7-103">`GetObject` 또는 `CreateObject` 함수 호출에서 지정한 클래스가 프로그래밍 기능 인터페이스를 표시하지 않았거나 프로젝트를 .dll과 .exe 간에 변경했습니다.</span><span class="sxs-lookup"><span data-stu-id="76eb7-103">Either the class you specified in the `GetObject` or `CreateObject` function call has not exposed a programmability interface, or you changed a project from .dll to .exe, or vice versa.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="76eb7-104">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="76eb7-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="76eb7-105">개체를 만든 응용 프로그램 설명서를 참조하여 이 개체 클래스에서 자동화를 사용하는 경우의 제한을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="76eb7-105">Check the documentation of the application that created the object for limitations on the use of automation with this class of object.</span></span>  
  
2.  <span data-ttu-id="76eb7-106">프로젝트를 .dll과 .exe 간에 변경한 경우에는 이전 .dll 또는 .exe의 등록을 수동으로 취소해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76eb7-106">If you changed a project from .dll to .exe or vice versa, you must manually unregister the old .dll or .exe.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76eb7-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="76eb7-107">See Also</span></span>  
 [<span data-ttu-id="76eb7-108">오류 형식</span><span class="sxs-lookup"><span data-stu-id="76eb7-108">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [<span data-ttu-id="76eb7-109">의견 보내기</span><span class="sxs-lookup"><span data-stu-id="76eb7-109">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
