---
title: "&#39; 모듈 &#39; 문은은 파일이 나 네임 스페이스 수준 에서만 사용할 수 있습니다."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords: BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 61fe12fbd7d20e6cd2b6bc464e7fc3293150213b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="39module39-statements-can-occur-only-at-file-or-namespace-level"></a><span data-ttu-id="86c3d-102">&#39; 모듈 &#39; 문은은 파일이 나 네임 스페이스 수준 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86c3d-102">&#39;Module&#39; statements can occur only at file or namespace level</span></span>
<span data-ttu-id="86c3d-103">`Module`문이 소스 파일의 맨 위쪽에 표시 해야 직후 `Option` 및 `Imports` 문, 전역 특성 및 네임 스페이스 선언을 다른 모든 선언 앞입니다.</span><span class="sxs-lookup"><span data-stu-id="86c3d-103">`Module` statements must appear at the top of your source file immediately after `Option` and `Imports` statements, global attributes, and namespace declarations, but before all other declarations.</span></span>  
  
 <span data-ttu-id="86c3d-104">**오류 ID:** BC30617</span><span class="sxs-lookup"><span data-stu-id="86c3d-104">**Error ID:** BC30617</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="86c3d-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="86c3d-105">To correct this error</span></span>  
  
-   <span data-ttu-id="86c3d-106">이동 된 `Module` 문을 네임 스페이스 선언 또는 소스 파일의 맨 위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86c3d-106">Move the `Module` statement to the top of your namespace declaration or source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86c3d-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="86c3d-107">See Also</span></span>  
 [<span data-ttu-id="86c3d-108">Module 문</span><span class="sxs-lookup"><span data-stu-id="86c3d-108">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
