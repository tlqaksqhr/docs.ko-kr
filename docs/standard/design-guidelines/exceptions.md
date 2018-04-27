---
title: 예외 디자인 지침
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exceptions [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], exceptions
- errors [.NET Framework], exceptions
- reporting errors
ms.assetid: bc177b2f-7528-4ae4-83db-aacfb04b86d0
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6dcd29f96ce32f1b2602af5d844339fe33c0ed7b
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="design-guidelines-for-exceptions"></a><span data-ttu-id="457b4-102">예외 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="457b4-102">Design Guidelines for Exceptions</span></span>
<span data-ttu-id="457b4-103">예외 처리에는 오류 반환 값 기반 보고를 통해 많은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="457b4-103">Exception handling has many advantages over return-value-based error reporting.</span></span> <span data-ttu-id="457b4-104">프레임 워크 좋은 디자인 예외의 장점을 실제 이용 하는 응용 프로그램 개발자를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="457b4-104">Good framework design helps the application developer realize the benefits of exceptions.</span></span> <span data-ttu-id="457b4-105">이 섹션의 예외 장점을 설명 하 고을 효과적으로 사용 하는 것에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="457b4-105">This section discusses the benefits of exceptions and presents guidelines for using them effectively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="457b4-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="457b4-106">In This Section</span></span>  
 [<span data-ttu-id="457b4-107">예외 throw</span><span class="sxs-lookup"><span data-stu-id="457b4-107">Exception Throwing</span></span>](../../../docs/standard/design-guidelines/exception-throwing.md)  
 [<span data-ttu-id="457b4-108">표준 예외 형식 사용</span><span class="sxs-lookup"><span data-stu-id="457b4-108">Using Standard Exception Types</span></span>](../../../docs/standard/design-guidelines/using-standard-exception-types.md)  
 [<span data-ttu-id="457b4-109">예외 및 성능</span><span class="sxs-lookup"><span data-stu-id="457b4-109">Exceptions and Performance</span></span>](../../../docs/standard/design-guidelines/exceptions-and-performance.md)  
 <span data-ttu-id="457b4-110">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="457b4-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="457b4-111">*피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*</span><span class="sxs-lookup"><span data-stu-id="457b4-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="457b4-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="457b4-112">See Also</span></span>  
 [<span data-ttu-id="457b4-113">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="457b4-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
