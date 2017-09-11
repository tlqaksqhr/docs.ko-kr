---
title: "너무 많은 클라이언트에서 DLL 응용 프로그램 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID47
ms.assetid: 4b87780b-67ad-4c96-9253-db954a751dad
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 18781161d1208e7e8d01f99eb9d655803d249e6e
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="too-many-dll-application-clients"></a><span data-ttu-id="f7773-102">DLL 응용 프로그램 클라이언트가 너무 많습니다.</span><span class="sxs-lookup"><span data-stu-id="f7773-102">Too many DLL application clients</span></span>
<span data-ttu-id="f7773-103">동적 연결 라이브러리 (DLL)에 대 한 [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 제한 된 수의 응용 프로그램을 호스트 하 여만 액세스를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7773-103">The dynamic-link library (DLL) for [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] can only accommodate access by a limited number of host applications.</span></span> <span data-ttu-id="f7773-104">응용 프로그램 및 다른 응용 프로그램을 [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 호스트 (의 일부는 액세스할 수 있는 응용 프로그램)에 액세스 하는 모든는 [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 동시에 DLL입니다.</span><span class="sxs-lookup"><span data-stu-id="f7773-104">Your application and other applications that are [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] hosts (some of which may be accessed by your application) are all attempting to access the [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] DLL at the same time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f7773-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="f7773-105">To correct this error</span></span>  
  
-   <span data-ttu-id="f7773-106">열려 있는 응용 프로그램에 액세스할 수를 줄일 [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="f7773-106">Reduce the number of open applications accessing [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7773-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f7773-107">See Also</span></span>  
 [<span data-ttu-id="f7773-108">오류 형식</span><span class="sxs-lookup"><span data-stu-id="f7773-108">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)
