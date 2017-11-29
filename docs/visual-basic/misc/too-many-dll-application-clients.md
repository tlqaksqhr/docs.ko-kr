---
title: "DLL 응용 프로그램 클라이언트가 너무 많습니다."
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID47
ms.assetid: 4b87780b-67ad-4c96-9253-db954a751dad
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d4b9278134e937ac8bf4626237954432d727ac0d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="too-many-dll-application-clients"></a><span data-ttu-id="3906f-102">DLL 응용 프로그램 클라이언트가 너무 많습니다.</span><span class="sxs-lookup"><span data-stu-id="3906f-102">Too many DLL application clients</span></span>
<span data-ttu-id="3906f-103">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 에 대한 DLL(동적 연결 라이브러리)은 제한된 수의 호스트 응용 프로그램 액세스만 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3906f-103">The dynamic-link library (DLL) for [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] can only accommodate access by a limited number of host applications.</span></span> <span data-ttu-id="3906f-104">사용자 응용 프로그램 및 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 호스트인 다른 응용 프로그램(일부는 사용자 응용 프로그램에서 액세스할 수 있음)이 동시에 모두 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] DDL에 액세스하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3906f-104">Your application and other applications that are [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] hosts (some of which may be accessed by your application) are all attempting to access the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] DLL at the same time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3906f-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="3906f-105">To correct this error</span></span>  
  
-   <span data-ttu-id="3906f-106">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]에 액세스하는 열려 있는 응용 프로그램 수를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="3906f-106">Reduce the number of open applications accessing [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3906f-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3906f-107">See Also</span></span>  
 [<span data-ttu-id="3906f-108">오류 형식</span><span class="sxs-lookup"><span data-stu-id="3906f-108">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)
